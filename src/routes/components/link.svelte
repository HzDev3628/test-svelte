<script lang="ts">
    let { title, href } = $props()
</script>

<a {href} class="underline hover:text-blue-300">{title}</a>