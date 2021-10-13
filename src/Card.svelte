<script>
  export let id;
  export let email;
  export let name;
  let number = 1

  function handleClick() {
    number = (number >= 3) ? 1 : ++number
  }
</script>

<main>
  <div on:click={handleClick} {id}>
    <img
      alt="robot card"
      role="presentation"  
      src={`//robohash.org/${id}?size=200x200&set=set${number}`}
    />
    <h2>{name}</h2>
    <p>{email || 'no email'}</p>
  </div>
</main>

<style>
  div {
    background-color: #9eebcf;
    border-radius: 0.5rem;
    box-sizing: border-box;
    display: inline-block;
    font-family: sans-serif;
    line-height: 18.4px;
    margin: 0.5rem;
    padding: 1rem;
    text-align: center;

    /* transform */
    -moz-osx-font-smoothing: grayscale;
    backface-visibility: hidden;
    transform: translateZ(0);
    transition: transform .25s ease-out;
  }

  div:hover {
    transform: scale(1.05);
  }
</style>
