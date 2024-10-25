<script lang="ts">
	import LottieAnimation from '$lib/components/LottieAnimation.svelte';
</script>

<svelte:head>
	<title>Example animation</title>
</svelte:head>

<section class="page" id="home">
	<section class="lottie-demo">
		<LottieAnimation />
	</section>

	<section class="intro">
		<h2 class="header h2">Chipmunk Animation</h2>

		<ol class="sub-header chipmunk-description">
			This chipmunk animation was created by:
			<li>designing a multi-layer vector in Adobe Illustrator and saving it as a .ai file,</li>
			<li>Importing the .ai file to Adobe After Effects, animating the individual body parts with keyframes and custom expressions,</li>
			<li>Rendering the animation to .json using the Bodymovin plugin,</li>
			<li>Copying the exported JSON and image files into this SvelteKit project,</li>
			<li>Finally, using lottie-web to display the animation from the JSON file.</li>
		</ol>
	</section>


</section>

<style lang="scss">
	.chipmunk-description {
		margin: 2rem auto 2rem;
		list-style-type: decimal;
		padding-left: 20px; // Add left indent for the ordered list

		li {
			margin: 0.2rem 0 0 3rem;

			&:first-of-type {
				margin-top: 1rem;
			}
		}
	}
</style>
