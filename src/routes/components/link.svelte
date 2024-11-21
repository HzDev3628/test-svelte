<script lang="ts">
    let { title, href } = $props()
</script>

<a {href} class="underline hover:text-blue-300 transition-colors duration-200">{title}</a>