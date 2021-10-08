<script context="module">
	export async function load() {
		const posts = import.meta.globEager('../../posts/*.md');
		const postsList = Object.values(posts);
		const postsMeta = postsList.map((post) => {
			let format = { year: 'numeric', month: 'long', day: 'numeric' };
			console.log(Date.parse(post.metadata.date));
			post.metadata.date = new Intl.DateTimeFormat('en-US', format).format(
				Date.parse(post.metadata.date)
			);
			return post.metadata;
		});

		return {
			props: {
				posts: postsMeta
			}
		};
	}
</script>

<script>
	export let posts;
</script>

<h2 class="text-3xl font-bold">Posts</h2>

<div class="bg-white pt-16 pb-20 px-4 sm:px-6 lg:pt-24 lg:pb-28 lg:px-8">
	<div class="relative max-w-lg mx-auto divide-y-2 divide-gray-200 lg:max-w-7xl">
		<div>
			<h2 class="text-3xl tracking-tight font-extrabold text-gray-900 sm:text-4xl">Patterns</h2>
			<p class="mt-3 text-xl text-gray-500 sm:mt-4" />
		</div>
		<div class="mt-12 grid gap-16 pt-12 lg:grid-cols-3 lg:gap-x-5 lg:gap-y-12">
			{#each posts as post}
				<div>
					<div>
						<!-- <a href="#" class="inline-block">
						<span
							class="inline-flex items-center px-3 py-0.5 rounded-full text-sm font-medium bg-indigo-100 text-indigo-800"
						>
							Article
						</span>
					</a> -->
					</div>
					<a href="/posts/{post.slug}" class="block mt-4">
						<p class="text-xl font-semibold text-gray-900">{post.title}</p>
						<p class="mt-3 text-base text-gray-500" />
					</a>
					<div class="mt-6 flex items-center">
						<div class="flex-shrink-0">
							<button>
								<span class="sr-only">{post?.author || 'Author'}</span>
								<img
									class="h-10 w-10 rounded-full"
									src={post?.authorImage || 'https://source.unsplash.com/random'}
									alt=""
								/>
							</button>
						</div>
						<div class="ml-3">
							<p class="text-sm font-medium text-gray-900">
								{post?.author || 'Author'}
							</p>
							<div class="flex space-x-1 text-sm text-gray-500">
								<time datetime="2020-03-16">{post?.date} </time>
								<!-- <span aria-hidden="true"> &middot; </span>
								<span> 6 min read </span> -->
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</div>

<ul>
	{#each posts as post}
		<li><a href={`/posts/${post.slug}`}>{post.title}</a></li>
	{/each}
</ul>
