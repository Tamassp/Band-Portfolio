<script>
	import { twMerge } from 'tailwind-merge'

	const classes = twMerge(
		'/*h-full w-[320px] block border-l border-b border-gray-200 cursor-pointer shadow-md hover:shadow-lg transition duration-300 ease-in-out /*hover:bg-cozyTunes',
		$$props.class
	)

	export const onCardClick = () => {
		console.log('onCardClick')
	}

	export let id = ''
</script>

<!-- <div class={classes} on:click={onCardClick} {id}>
	<slot />
</div> -->

<a class={classes} {id} href="/{id}">
	<slot />
</a>
