<script>
    import Particles from '../lib/Particles.svelte';
    import { onMount } from 'svelte';
    import heroImage from '../assets/hero-section.png';
</script>

<!-- made background image full screen for simplicity -->
<section class="bg-cover bg-center bg-no-repeat w-screen h-screen" style="background-image: url('{heroImage}');">
  <Particles />
</section>