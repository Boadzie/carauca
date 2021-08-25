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
        name: "Joe Dart",
        text: "The experience was amazing.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua"
      },
      {
        src: "https://cdn.pixabay.com/photo/2016/01/19/17/47/hiker-1149898_1280.jpg",
        name: "Kelly Fox",
        text: "My first time in Ghana and I love the experience. Lorem ipsum dolor sempor incididunt ut labore et dolore magna aliqua"
      },
      {
        src: "https://cdn.pixabay.com/photo/2016/10/10/14/44/train-1728537_1280.jpg",
        name: "Mina Outter",
        text: "The experience was soo cool. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua"
      },
      {
    src: "https://cdn.pixabay.com/photo/2016/10/14/19/21/canyon-1740973_1280.jpg",
    name: "Naomi Mint",
    text: "The experience was awesome. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua"
      }
      
    ];
  </script>
  <h1 class="px-1 pb-3 text-4xl font-bold text-center text-gray-600 uppercase lg:text-5xl">What our customers say</h1>
  <svelte:component 
  autoplay
  autoplayDuration={2000}
  pauseOnFocus
  this={Carousel} let:showPrevPage let:showNextPage>
          <button
          class="z-50 font-bold text-gray-600 lg:px-4 "
              type="button"
              slot="prev"
              on:click={showPrevPage}
          >
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 19l-7-7 7-7m8 14l-7-7 7-7"></path></svg>
          </button>
      
      {#each items as item, i (item.src)}
      <div class="relative flex items-center justify-center w-full text-center bg-gray-200 h ">
          
          <div class="absolute z-50 w-full p-4 mx-4 text-gray-600 bg-white rounded-md lg:w-1/2">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-blockquote" width="40" height="40" viewBox="0 0 24 24" stroke-width="1.5" stroke="#ffffff" fill="none" stroke-linecap="round" stroke-linejoin="round">
                <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
                <path d="M6 15h15" />
                <path d="M21 19h-15" />
                <path d="M15 11h6" />
                <path d="M21 7h-6" />
                <path d="M9 9h1a1 1 0 1 1 -1 1v-2.5a2 2 0 0 1 2 -2" />
                <path d="M3 9h1a1 1 0 1 1 -1 1v-2.5a2 2 0 0 1 2 -2" />
              </svg>
            <h2 class="p-2 text-2xl font-bold uppercase lg:text-3xl">{item.name}</h2>
            <p class="py-2 text-2xl italic prose">❝{item.text}❞</p> 
        </div>
        </div>
      {/each}
          <button
          class="z-50 font-bold text-gray-600 lg:px-4 "
              type="button"
              slot="next"
              on:click={showNextPage}
          >
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 5l7 7-7 7M5 5l7 7-7 7"></path></svg>
          </button>
      </svelte:component>
<style>
    .h{
        height: 20rem;
    }

</style>