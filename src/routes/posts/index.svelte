<script context="module">
	export async function load() {
		const posts = import.meta.globEager('../../posts/*.md');
		const postsList = Object.values(posts);
		const postsMeta = postsList.map((post) => {
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

<h2>Posts</h2>

<ul>
	{#each posts as post}
		<li><a href={`/posts/${post.slug}`}>{post.title}</a></li>
	{/each}
</ul>
