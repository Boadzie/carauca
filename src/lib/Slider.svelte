<script>
    import { onMount } from "svelte";
  
    let Carousel;
    onMount(async () => {
      const module = await import("svelte-carousel");
      Carousel = module.default;
      
    });
  
    const items = [
      {
        name: "Leonardo",
        age: 26,
        location: "Italy"
      },
      {
        name: "Maria",
        age: 27,
        location: "Brazil"
      },
      {
        name: "Oliver",
        age: 28,
        location: "United States"
      },
      {
        name: "Margarida",
        age: 29,
        location: "Portugal"
      }
    ];
  </script>
  
  <svelte:component this={Carousel} let:showPrevPage let:showNextPage>
          <button
              type="button"
              slot="prev"
              on:click={showPrevPage}
          >
              &LongLeftArrow;
          </button>
      {#each items as item, i (item.name)}
      <div style="padding: 30px 8px; text-align: center; background: #EEE; border-radius: 5px;">
          <strong>{item.name}</strong> ({item.age})
          from {item.location}
        </div>
      {/each}
          <button
              type="button"
              slot="next"
              on:click={showNextPage}
          >
      &LongRightArrow;
          </button>
      </svelte:component>
  
  