<script>
  import { page } from '$app/stores'
  $: pathname = $page.url.pathname
  $: console.log(pathname)
</script>

<nav>
  <a href="/" class:active={pathname === '/'}>Home</a>
  <a href="about" class:active={pathname === '/about'}>About</a>
  <a href="/user" class:active={pathname === '/user'}>user</a>
</nav>

<slot />

<style>
  .active {
    color: red;
    font-weight: 900;
  }
</style>
