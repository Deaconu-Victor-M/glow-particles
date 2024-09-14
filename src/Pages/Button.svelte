<script>
  import ButtonParticles from "../lib/ButtonParticles.svelte";
</script>

<section class="bg-[#070A15] w-screen h-screen">
  <div class="flex justify-center items-center h-full">
    <button
      class=" relative bg-gradient-to-b from-[#F8FAFD] to-[#BBC5EA] font-normal rounded-full text-4xl p-[1px] scale-100 font-instrument-serif transition-transform duration-300 group"
    >
      <div
        class="button-glow relative bg-[#070A15] rounded-full py-4 px-16 overflow-hidden"
      >
        <div
          class="absolute inset-0 opacity-100 group-hover:opacity-100 transition-opacity duration-300 blur-[0.2px]"
        >
          <ButtonParticles />
        </div>
        <span
          class="relative bg-gradient-to-b from-[#F8FAFD] to-[#BBC5EA] bg-clip-text text-transparent z-10 group-hover:shadow-xl shadow-white"
          >Click me</span
        >
      </div>
    </button>
  </div>
</section>

<style>
  .button-glow {
    box-shadow:
      0px 45px 31.7px -41px rgba(111, 133, 255, 0.66),
      0px 51px 5.4px -50px rgba(154, 111, 255, 0.41),
      0px 22px 11.5px -25px #e0d3ff,
      0px 0px 32.4px 7px rgba(81, 145, 255, 0.13) inset,
      0px 0px 1.2px 3px rgba(0, 0, 0, 0.13) inset,
      0px 0px 8px 3px rgba(81, 84, 255, 0.12) inset,
      0px 0px 5px 1px rgba(81, 84, 255, 0.38) inset,
      0px 0px 18.7px 2px rgba(81, 84, 255, 0.01) inset;
      transition: all 0.3s ease-in-out;
  }

  .button-glow:hover {
    box-shadow:
      0px 45px 31.7px -41px rgba(111, 133, 255, 0.66),
      0px 51px 5.4px -50px rgba(154, 111, 255, 0.41),
      0px 22px 11.5px -25px #e0d3ff,
      0px 0px 32.4px 7px rgba(81, 145, 255, 0.13) inset,
      0px 0px 1.2px 3px rgba(0, 0, 0, 0.23) inset,
      0px 0px 8px 3px rgba(81, 84, 255, 0.42) inset,
      0px 0px 5px 1px rgba(81, 84, 255, 0.68) inset,
      0px 0px 18.7px 2px rgba(81, 84, 255, 0.31) inset;
  }
</style>
