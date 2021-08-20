<script>
  import "../app.postcss";
  import Nav from "$lib/Nav.svelte"
</script>
<Nav/>
<main>
    <slot></slot>
</main>

<style>
  :global(html){
    font-family: 'Shadows Into Light', cursive;
  }
</style>