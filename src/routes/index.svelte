<script>
	import Banner from '$lib/Banner.svelte';
	import Feature from '$lib/Feature.svelte';
	import Best from '$lib/Best.svelte';
	import Testimonials from '$lib/Testimonials.svelte';
  import Contact from '$lib/Contact.svelte';
</script>

<section>
	<Banner />
</section>
<section>
	<Feature />
</section>
<section id="offers">
	<Best />
</section>
<section id="testimonials" class="py-24 bg-gray-200 to-blue-500 ">
	<Testimonials />
</section>
<section id="contact">
	<Contact />
</section>
