<script>
  import Card from './Card.svelte'
  export let robots = [];
</script>

<main>
  <div>
    {#each robots as {email, id, name}}
      <Card {email} {id} {name}/>
    {/each}
  </div>
</main>

<style>
  div {
    border-top: 1px solid black;
    display: flex;
    flex-wrap: wrap;
    height: 80vh;
    justify-content: center;
    overflow-y: scroll;
  }
</style>
