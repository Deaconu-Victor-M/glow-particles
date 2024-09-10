<script>
    import { onMount } from 'svelte';
    import { tsParticles } from '@tsparticles/engine';
    import { loadFull } from 'tsparticles';

    let particlesContainer;

    onMount(async () => {
        await loadFull(tsParticles);
        /** @type {import("@tsparticles/engine").ISourceOptions} */
        const options = {
            particles: {
                life: {
                    duration: {
                        value: 30,
                    },
                    count: 1,
                },
                number: { value: 1000 },
                shape: {
                    type: 'circle',
                },
                size: { value: 1 },
                move: {
                    enable: true,
                    speed: 2,
                    direction: 'none',
                    random: true,
                    straight: false,
                    outModes: 'out',
                },
                opacity: {
                    value: {
                        min: 0.1,
                        max: 1,
                    },
                    animation: {
                        enable: true,
                        speed: 1,
                        sync: false
                    }
                },
            },
            interactivity: {
                detectsOn: 'canvas',
                events: {
                    resize: {
                        enable: true
                    }
                }
            },
            detectRetina: true,
            fpsLimit: 60,
            emitters: {
                direction: "bottom",
                rate: {
                    quantity: 5,
                    delay: 0.1
                },
                position: {
                    x: 50,
                    y: 100
                },
                size: {
                    width: 100,
                    height: 0
                }
            },
            life: {
                duration: {
                    sync: false,
                    value: 3
                },
                count: 1
            }
        };
        await tsParticles.load({
            id: 'tsparticles',
            options: options
        });
    });
</script>

<div id="tsparticles" class="[mask-image:radial-gradient(circle,#000_10%,transparent_80%)]" bind:this={particlesContainer}></div>

<style>
    #tsparticles {
        position: fixed;
        width: 100%;
        height: 40%;
        top: 0;
        left: 0;
        pointer-events: none;
        z-index: 1000;
    }
</style>