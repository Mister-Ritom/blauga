<script lang="ts">
  import SvelteMarkdown from "svelte-markdown";
  import CodeRenderer from "../code/CodeRenderer.svelte";
  import ImageRenderer from "$lib/components/markdown/ImageRenderer.svelte";
  export let className = ""
  export let markdownStyle = ""
  export let bind:HTMLElement
  export let source:string
</script>

<span bind:this={bind} class={className} style={markdownStyle} id="markdown-container">
  <SvelteMarkdown source="{source}" renderers={{
    code:CodeRenderer,
    image:ImageRenderer
  }}></SvelteMarkdown>
</span>

<style>
    :global(#markdown-container) {
        color: var(--text);
        font-family: 'Poppins', sans-serif;
    }
    :global(#markdown-container h1) {
        font-size: 1.7rem;
        font-weight: 700;
        font-family: 'Roboto Condensed', sans-serif;
    }
    :global(#markdown-container h2) {
        font-size: 1.5rem;
        font-weight: 500;
        font-family: 'Roboto Condensed', sans-serif;
    }
    :global(#markdown-container h3) {
        font-size: 1.3rem;
        font-weight: 500;
        font-family: 'Roboto Condensed', sans-serif;
    }
</style>

