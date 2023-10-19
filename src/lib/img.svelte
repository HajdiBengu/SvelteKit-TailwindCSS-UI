<script>
	import Switches from "./switches.svelte";
    import { onMount } from 'svelte';

    let current_theme;
    onMount(() => {
        const theme = document.documentElement.getAttribute('data-theme');
        current_theme = theme;
    });

    function handleTheme(event) {
        current_theme = event.detail.theme
    }
</script>


<Switches on:theme={handleTheme}/>

{#if current_theme == null}
    <div class="mr-4 my-4 static">
        <img src="/Germany.jpg" alt="country" class="shadow rounded-2xl max-w-full align-middle border-none">
    </div>
{:else}
<div class="mr-4 my-4 static">
    <img src="/{current_theme}.jpg" alt="country" class="shadow rounded-2xl max-w-full align-middle border-none">
</div>
{/if}


