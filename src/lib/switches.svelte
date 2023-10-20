<script>
	import { createEventDispatcher } from 'svelte';
    import { themes } from './themes';

    const dispatch = createEventDispatcher();

    function setTheme(event) {
        const theme = event.target.dataset.value
        if (themes.includes(theme)) {
            document.documentElement.setAttribute('data-theme', theme)
        }
        dispatch('theme', {theme})
	}
</script>

<div class="absolute z-1 mr-10 grid grid-cols-1 gap-4 h-screen content-center inset-y-0 right-0 justify-items-end">
    {#each themes as theme}
        <button class="badge badge-accent" data-value={theme} on:click={setTheme}>{theme}</button>
	{/each}
</div>