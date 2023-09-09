<script lang="ts">
  import MarkdownRenderer from "$lib/components/markdown/MarkdownRenderer.svelte";
  import Dialog from "$lib/components/utils/Dialog.svelte";
  import Fa from "svelte-fa";
  import { faPlus,faSquareCaretUp, faFileImport } from "@fortawesome/free-solid-svg-icons";
  import { storage, auth, db } from "$lib/firebase";
  import { getDownloadURL, ref, uploadBytes } from "firebase/storage";
  import { setDoc, collection,doc } from "firebase/firestore";
  import { userStore } from "sveltefire";
	import BlogModel, { blogConverter } from "$lib/models/Blog";
	import { goto } from "$app/navigation";
  
  let source = ""
  let title = ""
  let keywords = ""
  let error = ""
  let rows = 30;
  let uploadButton:HTMLButtonElement
  const user = userStore(auth)
  let renderer:HTMLElement
  let dialog:HTMLDialogElement
  const fileMap = new Map<string, File>()

  function addTextBlock() {
    rows+=10;
  }

  function addFile(type:string) {
    const input = document.getElementById("image-input") as HTMLInputElement
    input.click()
    input.onchange = () => {
      if (input.files) {
        const file = input.files[0]
        const src = URL.createObjectURL(file)
        fileMap.set(src, file)
        const text = type=="image"? `\n <img src=${src} width=500 height=500]/>`:
          type=="video"?`<video src=${src}  controls>
  Your browser does not support the video tag.
</video> `:`[Title](${src})`
        source += text
      }
    }
  }

  function addImageFile() {
    addFile("image")
  }
  function addDownloadFIle() {
    addFile("download")
  }
  function addVideoFIle() {
    addFile("video")
  }


 async function uploadFiles(id:string) {
    if(fileMap.size==0 || !$user) return
    for (const [src, file] of fileMap) {
      const storageRef = ref(storage, `blogs/${$user.uid}/${id}/${file.name}`)
      await uploadBytes(storageRef, file)
      const url = await getDownloadURL(storageRef)
      source = source.replace(src, url)
    }
 }

  async function upload() {
    if(!$user || !source) return
    try {
    if (uploadButton)uploadButton.disabled = true  
    const id = Date.now().toString()
    await uploadFiles(id)
    const keywordsArray = keywords.split(",").map((keyword) => keyword.trim())
    const blog = new BlogModel(id, title, source, $user!.uid,Date.now(), [], keywordsArray)
    const blogCollection = collection(db, "posts", $user.uid, "blogs")
    const blogDoc = doc(blogCollection, id)
    await setDoc(blogDoc,  blogConverter.toFirestore(blog))
    goto(`/blog/${$user.uid}/${id}`)
    }
    catch(e:any) {
      if (e.code) {
        error = e.code
      }
      if (uploadButton)uploadButton.disabled = false  
      console.log(e)
    }
  }

</script>

<header>
  <h1>Create a new blog post</h1>
  <h2>I can sense that your readers are going to love this</h2>
</header>

{#if $user}
<div class="blog-text">
  <div class="textarea">
    <h2>Write a blog for your readers</h2>
    <label for="title">Title</label>
    <input bind:value={title} type="text" name="title" id="title">
    <textarea name="post" id="post-text" rows={rows} bind:value={source}></textarea>
  </div>
  <div class="toolbar">
    <h2>Toolbar</h2>
    <span class="line"></span>
    <button id="preview" on:click={() => dialog.showModal()}>Preview</button>
    <Dialog bind:dialog>
      <div class="preview-dialog">
        <h1>Preview markdown</h1>
        <button on:click={() => dialog.close()}>Close</button>
        <MarkdownRenderer bind={renderer} source={`# ${title}\n${source}`} />
      </div>
    </Dialog>
    <div class="add-wrapper">
      <Fa  style="color: var(--text)" size="lg" icon={faPlus} />
      <button id="add" on:click={addTextBlock}>Add text block</button>
    </div>
    <div class="add-wrapper">
      <Fa style="color: var(--text)" size="lg" icon={faSquareCaretUp} />
      <button id="add" on:click={addImageFile}>Add image block</button>
    </div>
    <div class="add-wrapper">
      <Fa style="color: var(--text)" size="lg" icon={faSquareCaretUp} />
      <button id="add" on:click={addVideoFIle}>Add video block</button>
    </div>
    <div class="add-wrapper">
      <Fa style="color: var(--text)" size="lg" icon={faFileImport} />
      <button id="add" on:click={addDownloadFIle}>Add file block</button>
    </div>
    <div class="add-wrapper">
      <input type="text" placeholder="Keywords(Comma separated)"  id="keywords" bind:value={keywords} />
    </div>
    <button bind:this={uploadButton} id="upload" on:click={upload}>Upload blog</button>
    {#if error&&error.length>1}
      <h2>{error}</h2>
    {/if}
  </div>
</div>
{:else}
  <h1>You need to login to create a blog</h1>
  <a href="/signup">Signup</a>
{/if}



<input  style="visibility: collapse; display:none; widht:0;height:0;" type="file" name="image" id="image-input">

<style>
  header {
    text-align: center;
    margin-bottom: 50px;
  }

  header h1 {
    font-size: 40px;
    font-weight: 700;
    margin-bottom: 10px;
  }

  header h2 {
    font-size: 20px;
    font-weight: 400;
    color: #666;
  }

  #keywords {
    width: 100%;
    height: 2rem;
    box-shadow: none;
  }

  #upload {
    width: 75%;
  }

  .blog-text {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  .textarea {
    display: flex;
    flex: 3;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  #title {
    width: 95%;
    height: 2rem;
    font-size: 1.5rem;
    font-family:'Phudu' , sans-serif;
    padding: 10px;
    border: 1px solid var(--primary);
    border-radius: 5px;
    background: var(--bg);
    color: var(--text);
    margin: 1rem;
  }

  textarea {
      width: 95%;
      font-size: 16px;
      font-family: monospace;
      padding: 10px;
      border: 1px solid var(--primary);
      border-radius: 5px;
      resize: none;
      background: var(--bg);
      color: var(--text);
      margin: 1rem;
  }

  textarea:focus {
    outline: none;
    border: 1px solid var(--accent);
  }

  .toolbar {
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: start;
      align-items: center;
      padding: 1rem;
  }

  .line {
    width: 100%;
    height: 1px;
    background: var(--primary);
    margin: 1rem;
  }

  .add-wrapper {
    width: 95%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
      margin: 1rem;
      background: var(--bg);
      border-radius: 16px;
      border: 2px dashed var(--primary);
  }

  #add {
    font-family: 'Courier New', Courier, monospace;
    color: var(--text);
    text-align: center;
    border:none;
    background: none;
    box-shadow: none;
    padding: 10px;
    font-size: 1rem;
  }

  #add:hover::before {
    background: none;
  }

  #preview {
    width: 70%;
    text-align: center;
  }

  .preview-dialog {
      padding: 1rem 3rem;
      background: transparent;
      border-radius: 16px;
      box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
      backdrop-filter: blur(11px);
      -webkit-backdrop-filter: blur(11px);
      /* Primary color in rgb */
      border: 1px solid rgba(106, 49, 160, 0.54);
      width: fit-content;
      height: fit-content;
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
      align-items: center;
      overflow: scroll;
      text-wrap: normal;
  }

</style>

