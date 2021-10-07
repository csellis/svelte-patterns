<script context="module">
	export async function load({ page }) {
		const Post = await import(`../../posts/${page.params.slug}.md`);
		return {
			props: {
				Post: Post.default,
				metadata: Post.metadata
			}
		};
	}
</script>

<script>
	export let Post;
	export let metadata;
</script>

<Post />
