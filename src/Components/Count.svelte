<script>
  export let score;
</script>

<div>
  <h1>
    Votre score est de :
    {score}
    {score === 1 ? "point" : "points"}
  </h1>
  {#if score > 50}
    <p>
      Attention, vous possedez beaucoup de biens ! Avez-vous réellement besoin
      de tout ça ?
    </p>
  {:else if 15 > score}
    <p>Woaw, un vrai minimaliste !</p>
  {:else}
    <p>Vous êtes dans la moyenne : ni matérialiste, ni minimaliste !</p>
  {/if}
</div>

<style>
  div {
    margin-bottom: 3rem;
  }
  h1 {
    font-weight: 400;
  }
</style>
