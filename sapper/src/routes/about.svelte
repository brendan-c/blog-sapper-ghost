<script context="module">
  export async function preload(page) {
    return this.fetch(
      "http://localhost:2368/ghost/api/v2/content/pages/?key=3495316e1eadc13d0906664487"
    )
      .then(res => {
        return res.json();
      })
      .then(data => {
        const pageName = page.path;
        data.pages = data.pages.filter(page => pageName.includes(page.slug));
        return { pageData: data.pages[0] };
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
