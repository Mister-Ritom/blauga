<script lang="ts">
  import "./CodeStyle.css"
  import {
    java, javascript,
    typescript, c, cpp, elixir, go, haskell, gradle, groovy, kotlin, lua,
    python, dart, php, cmake, css, markdown, ruby,
    swift, sql, yaml, json, xml, shell, bash, ini, plaintext
  } from "svelte-highlight/languages";

  import type { LanguageType } from "svelte-highlight/languages";
  import { Highlight, HighlightAuto, HighlightSvelte, LineNumbers } from "svelte-highlight";
  export let code:string | undefined = "auto";
  export let lang = ""


  const languageMap = new Map<string, LanguageType<string>>([
    ["ts", typescript],
    ["typescript", typescript],
    ["js", javascript],
    ["javascript", javascript],
    ["java", java],
    ["cpp",cpp],
    ["c",c],
    ["elixir",elixir],
    ["go",go],
    ["haskell",haskell],
    ["gradle",gradle],
    ["groovy",groovy],
    ["kt",kotlin],
    ["kotlin",kotlin],
    ["lua",lua],
    ["python",python],
    ["py",python],
    ["dart",dart],
    ["php",php],
    ["cmake",cmake],
    ["css",css],
    ["markdown",markdown],
    ["md",markdown],
    ["ruby",ruby],
    ["swift",swift],
    ["sql",sql],
    ["yaml",yaml],
    ["json",json],
    ["xml",xml],
    ["shell",shell],
    ["bash",bash],
    ["ini",ini],
    ["plaintext",plaintext],
  ]);

  function getLanguageType() {
    return languageMap.get(lang) || plaintext;
  }

</script>

{#if lang==="svelte"}
  <HighlightSvelte {code} />
{:else if lang==="auto"}
  <HighlightAuto {code} />
{:else}
  <Highlight language={getLanguageType()} {code} langtag={true} let:highlighted>
    <LineNumbers {highlighted} hideBorder wrapLines
    --padding-left="0"
    --padding-right="0.7rem"
    />
  </Highlight>
{/if}

<style>
  :global(body) {
      --langtag-background: black;
      --langtag-color: #fff;
      --langtag-border-radius: 8px;
  }
</style>