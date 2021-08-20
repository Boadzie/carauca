<script>
    import { onMount } from "svelte";
  
    let Carousel;
    onMount(async () => {
      const module = await import("svelte-carousel");
      Carousel = module.default;
      
    });
  
    const items = [
      {
        src: "https://cdn.pixabay.com/photo/2017/03/26/21/54/yoga-2176668_1280.jpg",
        age: 26,
        location: "Italy"
      },
      {
        src: "https://cdn.pixabay.com/photo/2016/01/19/17/47/hiker-1149898_1280.jpg",
        age: 27,
        location: "Brazil"
      },
      {
        src: "https://cdn.pixabay.com/photo/2016/10/10/14/44/train-1728537_1280.jpg",
        age: 28,
        location: "United States"
      },
      {
    src: "https://cdn.pixabay.com/photo/2016/10/14/19/21/canyon-1740973_1280.jpg",
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
          class="absolute z-50 px-4 font-bold text-white transform -translate-x-1/2 -translate-y-1/2 top-1/2 left-8 -inset-x-2/4"
              type="button"
              slot="prev"
              on:click={showPrevPage}
          >
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 19l-7-7 7-7m8 14l-7-7 7-7"></path></svg>
          </button>
      {#each items as item, i (item.src)}
      <div class="relative flex items-center justify-center w-full min-h-screen text-center bg-gray-200 ">
          <img class="absolute object-cover object-center w-full h-full bg-gray-500 opacity-70 before:absolute before:inset-0 before:bg-black/50" src={item.src} alt={items.age}/>
          <div class="absolute z-50 p-4 mx-2 text-white rounded-md lg:w-1/2">
           <h2 class="p-2 text-5xl uppercase lg:text-8xl">Discover</h2>
            <p class="text-4xl prose ">The free Wild!!</p> 
        </div>
        </div>
      {/each}
          <button
          class="absolute right-0 z-50 font-bold text-white transform -translate-x-1/2 -translate-y-1/2 top-1/2"
              type="button"
              slot="next"
              on:click={showNextPage}
          >
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 5l7 7-7 7M5 5l7 7-7 7"></path></svg>
          </button>
      </svelte:component>
  
  