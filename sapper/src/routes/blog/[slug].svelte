<script context="module">
  export async function preload(page) {
    return this.fetch(
      "http://localhost:2368/ghost/api/v2/content/posts/?key=3495316e1eadc13d0906664487"
    )
      .then(res => {
        return res.json();
      })
      .then(data => {
        const pageName = page.path;
        data.posts = data.posts.filter(post => pageName.includes(post.slug));
        return { pageData: data.posts[0] };
      });
  }
</script>

<script>
  export let pageData;
</script>

<svelte:head>
  <title>{pageData.title}</title>
</svelte:head>

<div class="content">
  <h1>{pageData.title}</h1>
  {@html pageData.html}
</div>
