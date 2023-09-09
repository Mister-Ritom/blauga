<script lang="ts">
  export let href:string
  export let title:string
  export let text:string

  console.log(`href ${href} title ${title} text ${text}`)

  function getImageWidth() {
    if (!title) return "500"
    const words = text.split(' ')
    for (let i = 0; i < words.length; i++) {
      const word = words[i]
      console.log(`word ${word}`)
      if (word.startsWith('width=')) {
        const width = word.split('=')[1]
        console.log(`width ${width}`)
        return width
      }
    }
    return "500"
  }

  function getImageHeight() {
    if (!title) return "500"
    const words = text.split(' ')
    for (let i = 0; i < words.length; i++) {
      const word = words[i]
      if (word.startsWith('height=')) {
        const width = word.split('=')[1]
        return width
      }
    }
    return "500"
  }

</script>

<p>{title}</p>
<img src={href} alt={text} width={getImageWidth()} height={getImageHeight()} >