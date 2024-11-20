<svelte:head>
  <title>Second page</title>
</svelte:head>

<script>
  import Link from '../components/link.svelte'
  function handleClick() {
    alert('Click working')
  }
</script>

<h1 class="text-4xl">Click Handler page</h1>
<div class="flex flex-col items-center gap-2">
  <button on:click={() => handleClick()} class="px-4 bg-white text-black rounded-lg text-lg">Show alert</button>
  <Link href="/" title="Home page" />
</div>

