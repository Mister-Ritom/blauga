<script>
import { goto } from "$app/navigation";
</script>
<div class="main">
    <h1>Create a new post</h1>
  <p>Create a new post about...</p>
  <div class="types">
    <button on:click={()=> {goto("post/blog")}}>Blog</button>
    <button on:click={()=> {goto("post/podcast")}}>Podcast</button>
    <button on:click={()=> {goto("post/video")}}>Video</button>
  </div>
</div>

<style>
  .main {
    width: fit-content;
    margin: 0 auto;
    padding: 5rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border-radius: 16px;
      background: transparent;
      border-radius: 16px;
      box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(10.5px);
      /* Primary color in rgb */
      border: 1px solid rgba(106, 49, 160, 0.54);
  }
  .main::before {
    content: "";
    position: absolute;
    top: 1rem;
    left: 2rem;
    width: 15rem;
      height: 15rem;
    /* height: 100%; */
    background: linear-gradient(45deg, #f3ec78, #af4261);
    z-index: -1;
    border-radius: 50%;
      filter: blur(20px);
  }
  button {
      font-size: 1.5rem;
  }
</style>