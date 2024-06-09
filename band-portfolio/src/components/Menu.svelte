<script lang="ts">
	import { fly, scale } from 'svelte/transition'
	import { quadOut } from 'svelte/easing'
	import Divider from './Divider.svelte'

	export let open: boolean
	export let portfolioLink: string

	// SCROLL INTO VIEW
	function scrollIntoView({ target }) {
		//set open to false
		open = false

		//scroll into view
		const el = document.querySelector(target.getAttribute('href'))
		if (!el) return
		el.scrollIntoView({
			behavior: 'smooth'
		})
	}
</script>

{#if open}
	<div transition:fly={{ y: -200, duration: 200 }} class="menu">
		<!-- Not working in Svelte -->
		<!-- {#each ['Home', 'Example', 'About', 'Contact'] as link, i}
            <p transition:fly={{ y: -15, delay: 50 * i }}>
                {link}
            </p>
        {/each} -->
		<div class="flex flex-col justify-center">
			<!-- <a href="#homeSection" transition:fly={{ y: -15, delay: 200 }}>Home</a> -->
			<a
				href="#aboutSection"
				on:click|preventDefault={scrollIntoView}
				transition:fly={{ y: -15, delay: 200 }}>About</a
			>
			<a target="_blank" href={portfolioLink} transition:fly={{ y: -15, delay: 250 }}>Portfolio</a>
			<!-- NOT NEEDED BECAUSE CONTACTS ARE IN ABOUT PAGE -->
			<!-- <a
				href="#contactSection"
				on:click|preventDefault={scrollIntoView}
				transition:fly={{ y: -15, delay: 300 }}>Contact</a
			> -->
		</div>
		<Divider size={24} />
		<div class="bar" transition:scale={{ duration: 750, easing: quadOut, opacity: 1 }} />
	</div>
{/if}

<style>
	:global(html) {
		/* background: #1d1d2f; */
	}
	.menu {
		text-align: center;
		font-size: 1.5em;
		letter-spacing: 0.15em;
		padding: 1em;
		padding-top: 0;
		background-color: white;
		padding: 18px;
		/* color: #eef; */
	}
	p {
		cursor: pointer;
		width: max-content;
		margin: 1rem auto;
	}
	p:hover {
		text-decoration: underline;
	}
	.bar {
		border-style: solid;
		border-color: rgb(0, 0, 0);
		border-width: 1px;
		height: 0;
	}
</style>
