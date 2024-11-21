<svelte:head>
  <title>Home page</title>
</svelte:head>

<script lang="ts">
import Link from './components/link.svelte'
async function getData() {
  return await fetch('https://jsonplaceholder.typicode.com/posts')
    .then((res) => res.json())
    .catch((err) => console.log(err))
}

type Posts = {
  id: number
  title: string
  body: string
}[]

const data = getData() as Promise<Posts>
</script>


<h1 class="text-5xl">Welcome to SvelteKit</h1>
<Link href="/click-handler" title="Click Handler Page" />

<div>
    {#await data}
      <p>Loading...</p>
    {:then posts}
      <div class="grid grid-cols-3 gap-4">
        {#each posts as post}
            <a href={`/${post.id}`} class="hover:scale-105 transition-transform duration-200">
              <div class="flex flex-col gap-2 items-start bg-[#09090940] border border-[#F9F9F940] w-full max-w-[340px] h-[300px] rounded-md p-4 text-start">
                <h4 class="text-xl font-medium">{post.title}</h4>
                <span class="text-[#F9F9F990]">{post.body}</span>
              </div>
            </a>
        {/each}
      </div>
    {:catch error}
      <p>{error}, please try again 🥲</p>
    {/await}
</div>