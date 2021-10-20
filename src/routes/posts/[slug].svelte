<script context="module">
	export async function load({ page }) {
		try {
			const Post = await import(`../../posts/${page.params.slug}.md`);
			return {
				props: {
					Post: Post.default,
					metadata: Post.metadata
				}
			};
		} catch (error) {
			return {
				status: 404,
				error: 'Post not found'
			};
		}
	}
</script>

<script>
	export let Post, metadata;
	let contentEl;
	$: contentHeight = contentEl?.offsetHeight;
	$: showThird = contentHeight > 1000;
	// $: {
	// 	console.log(contentHeight, showThird);
	// }
</script>

<div class="relative py-16 bg-white overflow-hidden" bind:this={contentEl}>
	<div class="hidden lg:block lg:absolute lg:inset-y-0 lg:h-full lg:w-full">
		<div class="relative h-full text-lg max-w-prose mx-auto" aria-hidden="true">
			{#if showThird}
				<svg
					class="absolute top-12 left-full transform translate-x-32"
					width="404"
					height="384"
					fill="none"
					viewBox="0 0 404 384"
				>
					<defs>
						<pattern
							id="74b3fd99-0a6f-4271-bef2-e80eeafdf357"
							x="0"
							y="0"
							width="20"
							height="20"
							patternUnits="userSpaceOnUse"
						>
							<rect x="0" y="0" width="4" height="4" class="text-gray-200" fill="currentColor" />
						</pattern>
					</defs>
					<rect width="404" height="384" fill="url(#74b3fd99-0a6f-4271-bef2-e80eeafdf357)" />
				</svg>
			{/if}
			<svg
				class="absolute top-1/2 right-full transform -translate-y-1/2 -translate-x-32"
				width="404"
				height="384"
				fill="none"
				viewBox="0 0 404 384"
			>
				<defs>
					<pattern
						id="f210dbf6-a58d-4871-961e-36d5016a0f49"
						x="0"
						y="0"
						width="20"
						height="20"
						patternUnits="userSpaceOnUse"
					>
						<rect x="0" y="0" width="4" height="4" class="text-gray-200" fill="currentColor" />
					</pattern>
				</defs>
				<rect width="404" height="384" fill="url(#f210dbf6-a58d-4871-961e-36d5016a0f49)" />
			</svg>
			<svg
				class="absolute bottom-12 left-full transform translate-x-32"
				width="404"
				height="384"
				fill="none"
				viewBox="0 0 404 384"
			>
				<defs>
					<pattern
						id="d3eb07ae-5182-43e6-857d-35c643af9034"
						x="0"
						y="0"
						width="20"
						height="20"
						patternUnits="userSpaceOnUse"
					>
						<rect x="0" y="0" width="4" height="4" class="text-gray-200" fill="currentColor" />
					</pattern>
				</defs>
				<rect width="404" height="384" fill="url(#d3eb07ae-5182-43e6-857d-35c643af9034)" />
			</svg>
		</div>
	</div>
	<header class="post">
		<h1>
			{metadata.title}
		</h1>
	</header>
	<section class="post">
		<svelte:component this={Post} />
	</section>
</div>
