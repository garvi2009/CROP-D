<script>
  import "../app.postcss";
  import {
    Navbar,
    NavBrand,
    NavLi,
    NavUl,
    NavHamburger,
  } from "flowbite-svelte";
</script>

<Navbar let:hidden let:toggle>
  <NavBrand href="/">
    <img src="src/assets/crop.png" class="h-14 " alt="CROP-D Logo" />
    <span
      class="self-center whitespace-nowrap text-xl font-semibold nav-color"
    >
      CROP-D
    </span>
  </NavBrand>
  <NavHamburger on:click={toggle} />
  <NavUl {hidden}>
    <NavLi href="/" active={true}>Home</NavLi>
    <NavLi href="/about">About</NavLi>
    <NavLi href="/">Services</NavLi>
    <NavLi href="/">Pricing</NavLi>
    <NavLi href="/">Contact</NavLi>
  </NavUl>
</Navbar>

<slot />

<style>
  .nav-color {
    background-color: var(--nav-color-1);
  }
</style>
