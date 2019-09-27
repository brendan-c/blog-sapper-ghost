<script>
  export let segment;
</script>

<style>

</style>

<nav class="nav">
  <span class="font-bold text-xl tracking-tight text-gray-900">shty</span>
  <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
    <div class="text-sm lg:flex-grow text-right">
      <a class={segment === undefined ? 'selected' : ''} href="#">home</a>

      <a
        rel="prefetch"
        class={segment === 'blog' ? 'selected' : ''}
        href="blog">
        blog
      </a>
      <a class={segment === 'about' ? 'selected' : ''} href="about">about</a>
    </div>
  </div>
</nav>
