<script>
    import { onMount, onDestroy } from 'svelte';
    import lottie from 'lottie-web';

    let animationInstance;

    // Load and play the animation
    function loadAnimation() {
        animationInstance = lottie.loadAnimation({
            container: document.getElementById('animation-container'),
            renderer: 'svg',
            loop: true, // Set to true for your idle animation loop
            autoplay: true, // Automatically play the animation when loaded
            path: '/animations/chipmunk-repeat-big.json' // Path to your exported Lottie JSON file
        });
    }

    // Stop animation when the component is destroyed
    onDestroy(() => {
        if (animationInstance) {
            animationInstance.destroy();
        }
    });

    onMount(() => {
        loadAnimation();
    });
</script>

<div class="lottie-animation">
    <div class="shadow"></div>
    <div id="animation-container" style="width: 300px; height: 300px;"></div>
</div>

<style lang="text/css">
    @keyframes move-left-right {
        0% {
            transform: translateX(0px) rotate(0deg);
        }
        50% {
            transform: translateX(100px) rotate(2deg);
        }
        100% {
            transform: translateX(0px) rotate(0deg);
        }
    }

    @keyframes rotate {
        0% {
            transform: translateX(-20px) rotate(4deg);
        }
        25% {
            transform: rotate(0deg);
        }
        50% {
            transform: translateX(5px) rotate(-4deg);
        }
        75% {
            transform: rotate(0deg);
        }
        100% {
            transform: translateX(-20px) rotate(4deg);
        }
    }

    div.lottie-animation {
        animation: rotate 10s ease-in-out infinite;
        position: relative;
        height: 18rem;
        width: 100%;
        display: flex;
        justify-content: left;
    }

    div#animation-container {
        z-index: 9999;
        position: fixed;
        bottom: 0;
    }

    div.shadow {
        z-index: 0;
        position: fixed;
        bottom: 26px;
        border-radius: 100%;
        left: 53px;
        width: 170px;
        height: 30px;
        background-color: rgba(255, 255, 255, 0.15);
        box-shadow: 0 15px 10px rgba(0, 0, 0, 0.8);
    }
</style>