<script lang="ts">
    import {page} from "$app/stores";

    $: activeUrl = $page.url.pathname;
</script>
<p>{activeUrl} in +layout</p>

<slot/>
