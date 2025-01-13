<script lang="ts">
import Link from '../components/link.svelte'
import { page } from '$app/stores'

$: postId = $page.params.post

async function getData() {
  return await fetch(
    `https://jsonplaceholder.typicode.com/posts/${$page.params.post}`,
  )
    .then((res) => res.json())
    .catch((err) => console.error(err))
}

type Post = {
  id: number
  title: string
  body: string
}

const data = getData() as Promise<Post>
</script>

<h1>There is an ID on this post: {postId}</h1>
<Link href="/" title="Home page" />
<div class="w-full max-w-[340px] bg-[#09090940] p-4 text-start border border-[#F9F9F940] rounded-md font-normal">
  {#await data}
    <p>Loading...</p>
  {:then post} 
    <h3 class="text-lg font-medium">{post.title}</h3>
    <span>{post.body}</span>
  {/await}
</div>
