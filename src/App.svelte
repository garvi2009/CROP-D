<script>
  import cropLogo from "./assets/crop.png";
  // @ts-ignore
  import * as toxicity from "@tensorflow-models/toxicity";
  const threshold = 0;
  let model = toxicity.load(threshold);
  model.then((/** @type {any} */ m) => (model = m));
  let sentence = "";
  let classification;
  function predict() {
    classification = model.classify([sentence]);
    classification.then((predictions) => {
      return predictions;
    });
  }
  // @ts-ignore
  const round = (n, d) => Number(Math.round(n + "e" + d) + "e-" + d);
</script>

<main>
  <div class="container">
    {#await model}
      <h1>...loading</h1>
    {:then}
      <img src={cropLogo} class="logo svelte" alt="Svelte Logo" />
      <h1>CROP-D</h1>
      <input
        type="text"
        placeholder="Type a toxic sentence"
        bind:value={sentence}
        on:keydown={(e) => {
          if (e.key === "Enter") {
            predict();
          }
        }}
      />
      {#await classification}
        <h1>...classifying</h1>
      {:then predictions}
        <h1>
          The toxicity level is {predictions
            ? round(predictions[6]["results"][0]["probabilities"][1], 3)
            : 0}
        </h1>
      {/await}
    {/await}
  </div>
</main>

<style>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: all 0.5s ease-in-out;
  }
  .logo:hover {
    transform: scale(2.1);
  }
  .logo {
    filter: invert(1);
    transform: rotate(20deg) scale(2);
  }
</style>
