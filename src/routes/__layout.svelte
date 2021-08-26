<script>
  import "../app.postcss";
  import Nav from "$lib/Nav.svelte"
  import Footer from "$lib/Footer.svelte";
</script>
<Nav/>
<main>
    <slot></slot>
</main>
<Footer/>
<style>
  :global(html){
    font-family: 'Advent Pro', sans-serif;
    scroll-behavior: smooth;
  }
</style>