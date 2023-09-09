<script lang="ts">
  import CodeHightlight from "$lib/components/code/CodeHightlight.svelte";

  export let lang:string;
  export let text:string;

</script>

<span>
  <code><CodeHightlight lang={lang} code={text}/></code>
</span>