<script lang="ts">
    import Link from '../components/link.svelte'
    import { page } from '$app/stores';

    $: postId = $page.params.post;
</script>

<h1>There is an ID on this post: {postId}</h1>
<Link href="/" title="Home page" />