<script>
  export let name;
  let age = 39;

  function increment() {
    age += 1;
  }
  function changeName() {
    name = "Max";
  }

  // Reactive variable
  $: nameToUpperCase = name.toUpperCase();
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hello {name}! {age} old</h1>
  <!-- simple javascript -->
  <h2>To uppercase {name.toUpperCase()}</h2>
  or
  <!-- reactive variable -->
  <h2>To uppercase {nameToUpperCase}</h2>

  <button on:click={increment}>Increment</button>
  <button on:click={changeName}>Change name</button>
</main>
