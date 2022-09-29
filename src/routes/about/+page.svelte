<script>
  import SvelteMarkdown from "svelte-markdown";

  let source = "Loading...";
  fetch(
    "https://raw.githubusercontent.com/Shoray2002/molars/molar-dev/README.md"
  )
    .then((response) => response.text())
    .then((data) => {
      source = data;
    });
</script>

<div class="container">
  <SvelteMarkdown {source} />
</div>

<style>
  .container {
    max-width: 800px;
    margin: 0 auto;
    padding: 0.5rem 2rem;
    border-radius: 20px;
    background-color: whitesmoke;
  }
</style>
