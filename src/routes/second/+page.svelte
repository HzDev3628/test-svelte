<svelte:head>
  <title>Second page</title>
</svelte:head>

<script>
function handleClick() {
  console.log('working')
}
</script>

<main>
  <h1 class="text-4xl">Second page</h1>
  <div class="flex flex-col items-center gap-2">
    <button on:click={() => handleClick()} class="px-4 bg-white text-black rounded-lg text-lg">Click console</button>
    <a href={'/'}>back to home</a>
  </div>
</main>

