<script>
  import Select from "svelte-select";
  import items from "./items.js";
  import Count from "./Components/Count.svelte";

  const groupBy = (item) => item.group;
  let selectedItems = [];
  let sum = 0;

  function handleSelect(event) {
    selectedItems = event.detail;

    if (selectedItems !== null) {
      sum = selectedItems.reduce((acc, o) => acc + parseInt(o.score), 0);
    } else {
      sum = 0;
    }
  }
</script>

<main>
  <Count score={sum} />
  <h3>Sélectionner vos biens</h3>

  <Select
    {items}
    isMulti={true}
    on:select={handleSelect}
    {groupBy}
    placeholder="Sélectionner"
  />

  <div class="text">
    <p>La définition de la sobriété :</p>
    <div class="quote">
      <q
        ><em>
          Le consentement délibéré pour avoir moins de choses physiques et
          penser que cela ne nous empêche pas d'être heureux.
        </em></q
      >
      <p>Jean-Marc Jancovici</p>
    </div>
  </div>
</main>

<style>
  :global(body) {
    font-family: sans-serif;
  }

  main {
    margin: 5rem 20rem;
  }

  .text {
    padding-top: 2rem;
  }

  .quote {
    display: flex;
    flex-direction: column;
    padding: 2rem;
    margin: 4rem;
    background-color: aliceblue;
  }
</style>
