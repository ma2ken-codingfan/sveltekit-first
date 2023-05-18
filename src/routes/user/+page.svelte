<script lang="ts">
  import { onMount } from 'svelte'

  type User = {
    name: string
  }

  let users: User[] = []

  onMount( async () => {
    const response = await fetch('https://jsonplaceholder.typicode.com/users')
    const data = await response.json()
    users = data
  } )
</script>
<h1>ユーザー一覧</h1>

<ul>
  {#each users as user }
    <li>{user.name}</li>
  {/each}
</ul>

<!-- TODO: https://reffect.co.jp/svelte/sveltekit#Active page.tsとpage.server.tsの設定  -->