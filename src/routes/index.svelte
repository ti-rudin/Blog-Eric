<script context="module">
  export function preload() {
    return this.fetch(`blog.json`)
      .then((r) => r.json())
      .then((posts) => {
        return { posts };
      });
  }
</script>

<script>
	import Post from '../components/Post.svelte'
  export let posts;
</script>

<svelte:head>
  <title>Eric Gomez</title>
  <meta name="description" content="Blog de ericgomez live">
  
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:site" content="@ericgomezmx">
  <meta name="twitter:creator" content="@ericgomezmx">
  <meta name="twitter:title" content="Eric Gomez">
  <meta name="twitter:description" content="Blog de ericgomez live">
  <meta name="twitter:image" content="https://arepa.s3.amazonaws.com/blogpost-cover.png">

  <meta name="og:title" content="Eric Gomez">
  <meta name="og:description" content="Blog de ericgomez live">
  <meta name="og:image" content="https://arepa.s3.amazonaws.com/blogpost-cover.png">
  <meta name="og:url" content="https://blog.ericgomez.live">
  <meta name="og:site_name" content="es_ES">
  <meta name="og:locale" content="Eric Gomez">
  <meta name="og:type" content="article">
  <meta name="fb:app_id" content="Eric Gomez">


</svelte:head>

<div class="Home">
  <div class="Posts">
    {#each posts as post}
      <Post {post} />
    {/each}
  </div>
</div>

<style>
	.Posts {
		display: grid;
		justify-content: space-between;
		gap: 15px;
		grid-template-columns: 1fr;
	}

</style>
