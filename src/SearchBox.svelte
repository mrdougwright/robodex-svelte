<script>
  export let onSearch
  let search = ''
</script>

<main>
  <div>
    <input
      bind:value={search}
      on:keyup={onSearch(search)}
      placeholder='Search Robots...'
      type="text"
    />
  </div>
</main>

<style>
  div {
    text-align: center;
  }
</style>
