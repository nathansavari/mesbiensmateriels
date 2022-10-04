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
</main>

<style>
  :global(body) {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }

  main {
    margin: 5rem;
  }
</style>
