<script>
    import { onMount } from "svelte";
  
    let Carousel;
    onMount(async () => {
      const module = await import("svelte-carousel");
      Carousel = module.default;
      
    });
  
    const items = [
      {
        src: "https://cdn.pixabay.com/photo/2016/03/30/21/59/coffee-beans-1291656_1280.jpg",
        age: 26,
        location: "Italy"
      },
      {
        src: "https://cdn.pixabay.com/photo/2021/06/06/12/23/landscape-6315249_1280.jpg",
        age: 27,
        location: "Brazil"
      },
      {
        src: "https://cdn.pixabay.com/photo/2017/04/09/09/56/avenue-2215317_1280.jpg",
        age: 28,
        location: "United States"
      },
      {
    src: "https://cdn.pixabay.com/photo/2017/07/28/14/29/macarons-2548827_1280.jpg",
    age: 28,
    location: "United States"
      }
      
    ];
  </script>
  
  <svelte:component 
  autoplay
  autoplayDuration={2000}
  pauseOnFocus
  this={Carousel} let:showPrevPage let:showNextPage>
          <button
          class=" absolute top-1/2 left-8 transform -translate-x-1/2 -translate-y-1/2 px-4 font-bold -inset-x-2/4 z-50 text-white"
              type="button"
              slot="prev"
              on:click={showPrevPage}
          >
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 19l-7-7 7-7m8 14l-7-7 7-7"></path></svg>
          </button>
      {#each items as item, i (item.src)}
      <div class="relative w-full flex items-center justify-center text-center bg-gray-200 min-h-screen ">
          <img class="before:absolute before:inset-0 before:bg-black/50 bg-gray-500 h-full w-full z-40 absolute object-cover object-center" src={item.src} alt={items.age}/>
          <div class="bg-white mx-2 lg:w-1/2 rounded-md p-4 absolute z-50 text-red-400">
           <h2 class="p-2 text-7xl">Discover</h2>
            <p class=" prose text-3xl">The free Wild!!</p> 
        </div>
        </div>
      {/each}
          <button
          class="absolute top-1/2 right-0 transform -translate-x-1/2 -translate-y-1/2 px-4 font-bold  z-50 text-white"
              type="button"
              slot="next"
              on:click={showNextPage}
          >
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 5l7 7-7 7M5 5l7 7-7 7"></path></svg>
          </button>
      </svelte:component>
  
  