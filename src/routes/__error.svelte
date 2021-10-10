<script context="module">
	export function load({ error, status }) {
		return {
			props: {
				error,
				status
			}
		};
	}
</script>

<script>
	export let status, error;
</script>

<h1>{status}: {error.message}</h1>

<a href="/posts">Back to Posts</a>
