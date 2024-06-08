<script>
	import { onMount } from 'svelte'
	import { fade, slide } from 'svelte/transition'
	import { quintOut } from 'svelte/easing'
	import { Hamburger } from 'svelte-hamburgers'

	import Divider from '../../components/Divider.svelte'
	import TitleDescription from '../../components/TitleDescription.svelte'
	import loaderGif from '$lib/images/loader.gif'
	import coverSmall from '$lib/images/coverSmall11.jpg'
	import coverBig from '$lib/images/coverBig111.jpg'
	import coverSmall2 from '$lib/images/coverSmall22.jpg'
	import coverBig2 from '$lib/images/coverBig22.jpg'
	import coverSmall3 from '$lib/images/coverSmall3.jpg'
	import coverBig3 from '$lib/images/coverBig3.jpg'
	import piano1 from '$lib/images/piano1.jpg'
	import piano2 from '$lib/images/piano2.jpg'
	import drums1 from '$lib/images/drums1.jpg'
	import drums2 from '$lib/images/drums2.jpg'

	import Title from '../../components/Title.svelte'
	import Menu from '../../components/Menu.svelte'
	import Description from '../../components/Description.svelte'

	let loading = true

	onMount(async () => {
		loading = false
	})

	let innerWidth = 0
	let innerHeight = 0

	let open = false

	let sm = 640
	let md = 768
	let lg = 1024
	let xl = 1280
	let xxl = 1536
</script>

<svelte:head>
	<!-- <link href="https://fonts.googleapis.com/css?family=Homenaje" rel="stylesheet" /> -->
	<link href="https://fonts.googleapis.com/css?family=Raleway" rel="stylesheet" />
</svelte:head>

<svelte:window bind:innerWidth bind:innerHeight />

<div class="pageContainer">
	<div
		class="sticky top-0 left-0 z-10 flex flex-row items-center justify-between w-full pt-6 pb-6 pl-2 pr-2 bg-white navbar"
	>
		<Title class="logo">SwingBy</Title>
		<Hamburger bind:open />
	</div>
	<div class="fixed right-0 z-10 w-full">
		<Menu bind:open />
	</div>
	<!-- <Menu bind:open /> -->

	<div class="relative page-container /*2xl:pl-2 /*2xl:pr-2">
		{#if loading}
			<div
				out:slide={{ delay: 600, duration: 600, easing: quintOut, axis: 'y' }}
				class="fixed top-0 bottom-0 left-0 right-0 z-50 flex items-center bg-white"
			>
				<img src={loaderGif} alt="loading" class="m-auto scale-50" />
			</div>
		{/if}

		<!-- Responsive images for different screen sizes -->
		<picture>
			<source srcset={coverSmall} media="(max-width: {sm}px)" />
			<img
				src={coverBig}
				alt="background"
				class="sticky top-16 left-0 /*max-h-[60vh] w-full lg:w-[99%] lg:m-1"
			/>
		</picture>

		<img
			src={drums1}
			alt="drums1"
			class="sticky border-r-8 border-t-8 border-l-[16px] border-white /*md:w-1/2 top-16 left-6"
		/>
		<img
			src={piano1}
			alt="piano1"
			class="sticky ml-auto border-l-8 border-t-8 border-r-[16px] border-white /*md:w-1/2 md:-mt-48 top-[56px]"
		/>
		<Divider size={12} class="bg-white 0" />
		<picture>
			<source srcset={coverSmall2} media="(max-width: {sm}px)" />
			<img
				src={coverBig2}
				alt="background"
				class="sticky top-16 left-0 /*max-h-[60vh] w-full z-20 border-b-8 border-white"
			/>
		</picture>
		<img
			src={drums2}
			alt="drums2"
			class="sticky border-r-8 border-t-8 border-l-[16px] border-white /*md:w-1/2 top-16 left-6"
		/>
		<img
			src={piano2}
			alt="piano2"
			class="sticky ml-auto border-l-8 border-t-8 border-r-[16px] border-white /*md:w-1/2 md:-mt-48 top-16"
		/>
		<div class="flex flex-col items-center bg-white 0 md:mt-12 content">
			<Divider size={32} />
			<!-- <TitleDescription title="About" description=" 'There is one language that speaks to everyone: Music'" descriptionStyles=" text-center" /> -->
			<!-- <TitleDescription description="As an international duo from Horsens with a passion for music, we enjoy performing in the cozy atmosphere of bars and cafes."/>
			<TitleDescription description="Our repertoire mostly consists of jazz/blues/pop cover songs, but we also love to create mashups and more upbeat tunes."/> -->
			<Title>About</Title>
			<Divider />
			<Description class="text-center"
				>There is one language that speaks to everyone: Music</Description
			>
			<Divider />
			<Description class="text-center"
				>As an international duo from Horsens with a passion for music, we enjoy performing in the
				cozy atmosphere of bars and cafes.</Description
			>
			<Divider />
			<Description class="text-center"
				>Our repertoire mostly consists of jazz/blues/pop cover songs, but we also love to create
				mashups and more upbeat tunes.</Description
			>
			<Divider size={24} />
			<a>Listen to our portfolio</a>
			<Divider size={48} />
			<TitleDescription title="Booking" description="hello@gmail.com"></TitleDescription>
		</div>
		<Divider />
	</div>
</div>

<style>
	* {
		/* font-family: 'Homenaje'; */
		font-family: 'Raleway', sans-serif;
		font-weight: 100;
	}
	:global(body) {
		/* background-color: rgb(0, 0, 0);
		color: white; */
		display: flex;
		justify-content: center;

		padding: 0;
	}

	.pageContainer {
		/* background-color: bisque; */
		/* opacity: 0.5; */
		position: relative;
		/* display: flex;
		flex-direction: column;
		align-self: center; */
		/* MAKE CONDITION */
		/* max-width: 800px; */
		/* max-width: 1536px; */
		max-width: 1280px;
		/* margin-top: 25vh; */
	}

	.imageWrapper {
		background-image: url('../../lib/images/coverPic.jpg');
		background-position: 50% 40%;
		/* background-size: cover; */
		background-size: cover;
		background-repeat: no-repeat;
		width: 100%;
		/* height: 0;
		padding-top: 81.56%; */
	}
	.mainTitle {
		/* font-family: Homenaje; */
		position: relative;
		/* left: 10px; */
		/* MAKE CONDITION */
		/* margin-left: 15%; */
		margin-top: -10px;
		font-size: 5em;
		background-color: rgba(0, 0, 0, 0.5);
		width: fit-content;
	}
	img {
		/* position: absolute; */
		/* margin: -10 */
		/* width: 100%; */
		/* aspect-ratio: 16/9; */
		object-fit: cover;
		/* border-radius: 20px; */
		z-index: -1;

		/* width: 100vw;
		position: relative;
		left: calc(-50vw + 50%); */
	}
	.video {
		margin-top: 24px;

		aspect-ratio: 16/9;
		border-radius: 20px;
		z-index: -1;
	}
	/* .coverImage {
        width: min-content;
    } */
	@media (min-width: 600px) {
		.pageContainer {
			min-width: 600px;
		}
		.mainTitle {
			margin-top: 20px;
		}
	}
</style>
