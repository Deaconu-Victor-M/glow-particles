<script>
  import { onMount } from "svelte";
  import { tsParticles } from "@tsparticles/engine";
  import { loadFull } from "tsparticles";

  let particlesContainer;

  onMount(async () => {
    await loadFull(tsParticles);
    /** @type {import("@tsparticles/engine").ISourceOptions} */
    const options = {
      particles: {
        life: {
          duration: {
            value: 5,
          },
          count: 1,
        },
        number: { value: 40 },
        shape: {
          type: "circle",
        },
        size: { value: { min: 1, max: 2.5 } },
        move: {
          enable: true,
          speed: 0.6,
          direction: "bottom",
          random: true,
          straight: false,
          outModes: "out",
        },
        opacity: {
          value: {
            min: 0.1,
            max: 2,
          },
          animation: {
            enable: true,
            speed: 1,
            sync: false,
          },
        },
        color: {
          value: ["#5191FF", "#FFFFFF"], // Added multiple colors
        },
      },
      interactivity: {
        detectsOn: "canvas",
        events: {
          resize: {
            enable: true,
          },
          onHover: {
            enable: true,
            mode: "attract",
            parallax: {
              enable: true,
              force: 100,
              smooth: 10,
            },
          },
        },
      },
      modes: {
        attract: {
          distance: 100,
          factor: 0.2,
          speed: 1000, // Increased speed for faster movement
        },
      },
      detectRetina: true,
      fpsLimit: 60,
      emitters: {
        direction: "bottom",
        rate: {
          quantity: 1,
          delay: 0.05,
        },
        position: {
          x: 50,
          y: 100,
        },
        size: {
          width: 100,
          height: 0,
        },
      },
    };
    await tsParticles.load({
      id: "tsparticles",
      options: options,
    });
  });
</script>

<div
  id="tsparticles"
  class="hover:[mask-image:radial-gradient(circle,#000_10%,transparent_99%)] [mask-image:radial-gradient(circle,#000_10%,transparent_90%)] rounded-full overflow-clip transition-all duration-300"
  bind:this={particlesContainer}
></div>

<style>
  #tsparticles {
    position: fixed;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    pointer-events: none;
    z-index: 1000;
  }
</style>
