<script>
	import Card from '../components/Card.svelte'
	import TitleDescription from '../components/TitleDescription.svelte'
	import Divider from '../components/Divider.svelte'

	import pianist from '$lib/images/pianist.png'
	import singer from '$lib/images/singer.png'
	import singer2 from '$lib/images/singer2.jpg'
	import pianist2 from '$lib/images/pianist2.jpg'
	import drummer from '$lib/images/drummer.jpg'
</script>

<div class="pageContainer">
	<div class="pageInner">
		<Card
			id="cozy-tunes"
			class="relative h-[320px] sm:h-[436px] w-[300px] sm:w-[320px] block border-b border-l border-gray-200"
		>
			<div class="flex flex-col justify-end h-full cardInner">
				<div class="cozyTunesImageWrapper">
					<img src={pianist} class="cozyTunesImage h-[280px] sm:h-[350px]" alt="background" />
					<img src={singer} class="cozyTunesImage h-[280px] sm:h-[350px]" alt="background" />
				</div>
				<Divider />
				<TitleDescription
					title="Cozy Tunes"
					description="Blues, jazz, pop covers"
					descriptionStyles="text-center"
				/>
				<Divider />
			</div>
		</Card>
		<Card
			id="swingby"
			class="relative h-[320px] sm:h-[436px] w-[300px] sm:w-[320px] block border-b border-l border-gray-200"
		>
			<div class="flex flex-col justify-end h-full cardInner">
				<div class="swingByImageWrapper">
					<img src={singer2} class="object-cover /*w-[160px] swingByImage1" alt="background" />
					<img src={drummer} class="object-cover /*w-[160px] mt-8 swingByImage2" alt="background" />
					<img
						src={pianist2}
						class="object-cover /*w-[160px] mt-16 swingByImage3"
						alt="background"
					/>
				</div>

				<Divider />
				<TitleDescription title="SwingBy" description="Swing covers of all times" />
				<Divider />
			</div>
		</Card>
	</div>
	<!-- <a href="/cozy-tunes" target="_blank">Cozy Tunes</a> -->
</div>

<style>
	.pageContainer {
		/* min-width: 600px; */
		text-align: center;
	}
	.pageInner {
		height: 100%;
		width: 100%;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		flex-wrap: wrap;
		gap: 160px;
		padding: 96px;
		padding-top: 160px;
	}

	.mainTitle {
		margin-top: 20px;
	}
	.cozyTunesImageWrapper {
		position: absolute;
		display: flex;
		justify-content: center;
		top: -64px;
		left: 0;
		right: 0;
		margin-left: -32px;
		margin-top: -32px;
		margin-right: -32px;
	}
	.swingByImageWrapper {
		/* position: absolute; */
		position: absolute;
		/* scale: 1.1; */
		transition: 0.5 ease-in-out;
		scale: 1;
		top: -64px;
		left: 0;
		right: 0;
		display: flex;
		flex-direction: row;
		flex-wrap: nowrap;
		gap: 8px;
		margin-left: -16px;
		margin-top: -16px;
		margin-right: -16px;
		height: 330px;
		width: 330px;
	}
	.cozyTunesImage {
		/* margin: -40px; */
		scale: 1;
		transition: 0.5s ease-in-out;
		margin-left: -40px;
		margin-top: -32px;
		margin-right: -40px;
	}

	.cardInner:hover .cozyTunesImage {
		scale: 1.1;
		transition: 0.5s ease-in-out;
	}

	.swingByImage1 {
		height: 280px;
		width: 110px;
		transition: 0.5s ease-in-out;
	}

	.swingByImage2 {
		height: 248px;
		width: 110px;
		transition: 0.5s ease-in-out;
	}

	.swingByImage3 {
		height: 216px;
		width: 110px;
		transition: 0.5s ease-in-out;
	}

	.cardInner:hover .swingByImage1 {
		transition: 0.3s ease-in-out;
		height: 320px;
		width: 110px;
	}

	.cardInner:hover .swingByImage2 {
		transition: 0.3s ease-in-out;
		height: 288px;
		width: 110px;
	}

	.cardInner:hover .swingByImage3 {
		transition: 0.3s ease-in-out;
		height: 256px;
		width: 110px;
	}

	.cardInner:hover .swingByImageWrapper {
		/* height: 380px;
		width: 500px; */
		/* scale: 1.1;
		transition: 0.5s ease-in-out; */
		/* top: -16px; */
	}

	@media (max-width: 600px) {
		.pageInner {
			gap: 128px;
			padding: 8px;
			padding-top: 128px;
		}
		.cozyTunesImageWrapper {
			left: 0;
			right: 0;
			margin-left: -16px;
			margin-top: -16px;
			margin-right: 0px;
		}

		.swingByImage1 {
			height: 240px;
			width: 105px;
			transition: 0.5s ease-in-out;
		}

		.swingByImage2 {
			height: 208px;
			width: 105px;
			transition: 0.5s ease-in-out;
		}

		.swingByImage3 {
			height: 176px;
			width: 105px;
			transition: 0.5s ease-in-out;
		}
		.cardInner:hover .swingByImage1 {
			transition: 0.3s ease-in-out;
			height: 260px;
			width: 110px;
		}

		.cardInner:hover .swingByImage2 {
			transition: 0.3s ease-in-out;
			height: 228px;
			width: 110px;
		}

		.cardInner:hover .swingByImage3 {
			transition: 0.3s ease-in-out;
			height: 196px;
			width: 110px;
		}
	}
</style>
