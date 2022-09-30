<script>
  import { navigating } from "$app/stores";
  import Loader from "$lib/Loader.svelte";
  import { loading } from "$lib/loading";
  $: $loading = !!$navigating;
</script>

{#if $loading}
  <Loader />
{/if}
<div class="outer-container">
  <div class="top-bar">
    <h3
      on:click={() => {
        if (window.location.pathname !== "/") {
          window.location.pathname = "/";
        }
      }}
    >
      <span class="header-bold">C.R.O.P</span>-<span class="header-bold">D</span
      >
    </h3>
    <ul class="top-menu">
      <li>&nbsp;</li>
      <li class="header-bold">
        <a class="github" href="/" target="_blank">Github</a>
      </li>
    </ul>
  </div>
  <slot />
</div>

<style>
  .top-bar {
    font-family: "Major Mono Display", monospace;
  }
</style>
