<script type="ts">
	import Cart from 'svelte-material-icons/Cart.svelte';

	let carouselContents = [
		{
			id: 'img0',
			img: 'https://source.unsplash.com/ljRiZl00n18',
			alt: 'Img1'
		},
		{
			id: 'img1',
			img: 'https://source.unsplash.com/ljRiZl00n18',
			alt: 'Img1'
		},
		{
			id: 'img2',
			img: 'https://source.unsplash.com/ljRiZl00n18',
			alt: 'Img1'
		}
	];

	let cards = [
		{
			title: 'Yellow chair',
			img: 'https://source.unsplash.com/_HqHX3LBN18',
			description: 'If a dog chews shoes whose shoes does he choose?',
			detail: 'https://example.com/detail/shoes1'
		},
		{
			title: 'White chair',
			img: 'https://source.unsplash.com/buhmhprfo3g',
			description: 'If a dog chews shoes whose shoes does he choose?',
			detail: 'https://example.com/detail/shoes1'
		},
		{
			title: 'Fabric Chair',
			img: 'https://source.unsplash.com/kvmdsTrGOBM',
			description: 'If a dog chews shoes whose shoes does he choose?',
			detail: 'https://example.com/detail/shoes1'
		},
		{
			title: 'Lether Chair',
			img: 'https://source.unsplash.com/1P6AnKDw6S8',
			description: 'If a dog chews shoes whose shoes does he choose?',
			detail: 'https://example.com/detail/shoes1'
		}
	];
</script>

<!-- drawer -->
<div class="drawer drawer-end">
	<input id="my-drawer" type="checkbox" class="drawer-toggle" />
	<div class="drawer-content">
		<!-- /drawer -->

		<!-- header -->
		<div class="sticky top-0 z-50 navbar bg-base-100">
			<div class="flex-1">
				<a href="/" class="btn btn-ghost normal-case text-2xl">Awesome Products</a>
			</div>
			<div class="flex-none">
				<label for="my-drawer" class="btn btn-ghost drawer-button"><Cart /></label>
			</div>
		</div>
		<!-- /header -->

		<div class="carousel w-full h-96">
			{#each carouselContents as content, i}
				<div id={content.id} class="carousel-item relative w-full h-96">
					<img src={content.img} alt={content.alt} class="object-cover w-full h-96" />
					<div
						class="absolute flex justify-between transform -translate-y-1/2 left-5 right-5 top-1/2"
					>
						<a href={'#img' + (i - 1).toString()} class="btn btn-circle">❮</a>
						<a href={'#img' + (i + 1).toString()} class="btn btn-circle">❯</a>
					</div>
				</div>
			{/each}
		</div>

		<div class="pt-40 pb-3">
			<h2 class="text-center align-text-bottom text-3xl">New Products</h2>
		</div>

		<ul class="flex flex-wrap place-content-center pt-3">
			{#each cards as card}
				<li>
					<div class="px-3 pb-6">
						<div class="card drop-shadow-md w-96 bg-white bg-opacity-20 backdrop-blur-lg shadow-xl">
							<figure>
								<img src={card.img} alt={card.title} class="object-cover w-96 h-96" />
							</figure>
							<div class="card-body">
								<h2 class="card-title">{card.title}</h2>
								<p>{card.description}</p>
								<div class="card-actions justify-end">
									<button class="btn btn-primary">Buy Now</button>
								</div>
							</div>
						</div>
					</div>
				</li>
			{/each}
		</ul>
	</div>
	<div class="drawer-side">
		<label for="my-drawer" class="drawer-overlay" />
		<ul class="menu p-4 w-80 bg-base-100 text-base-content">
			<!-- Sidebar content here -->
			<li><a>Sidebar Item 1</a></li>
			<li><a>Sidebar Item 2</a></li>
		</ul>
	</div>
</div>
