<script>
  export let score;
</script>

<div>
  <h1>Votre score est de : {score} points</h1>
  {#if score > 40}
    <p>Très consommateur</p>
  {:else if 15 > score}
    <p>Très propre</p>
  {:else}
    <p>Fais gaffe mec</p>
  {/if}
</div>

<style>
  div {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
