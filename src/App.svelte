<script>
  import { onMount } from 'svelte'
  import CardList from './CardList.svelte'
  import SearchBox from './SearchBox.svelte'
  export let robots;
  let filteredRobots;
  let isPending = true

  onMount(async () => {
    const res = await fetch('https://jsonplaceholder.typicode.com/users')
    robots = await res.json()
    onSearch()
    isPending = false
  })

  function onSearch(term = '') {
    filteredRobots = robots.filter(robot => {
      return robot.name.toLowerCase().includes(term)
    })
  }
</script>

<main>
  <h1>RoboDex</h1>
  <SearchBox {onSearch} />
  {#if isPending}
    <h2>Loading...</h2>
  {:else}
    <CardList robots={filteredRobots} />
  {/if}
</main>

<style>
  main {
    text-align: center;
  }
</style>
