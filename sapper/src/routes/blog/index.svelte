<script context="module">
  export async function preload(page) {
    return this.fetch(
      "http://localhost:2368/ghost/api/v2/content/posts/?key=3495316e1eadc13d0906664487"
    )
      .then(res => {
        return res.json();
      })
      .then(data => {
        return { posts: data.posts };
      });
  }
</script>

<script>
  export let posts;
  console.log(posts);
</script>

<svelte:head>
  <title>Blog</title>
</svelte:head>

<div class="content">
  <ul>
    {#each posts as post}
      <li>
        <a rel="prefetch" href="blog/{post.slug}">
          <b>{post.title}</b>
        </a>

      </li>
    {/each}
  </ul>
</div>
