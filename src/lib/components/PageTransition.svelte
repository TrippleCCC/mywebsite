<script lang="ts">
    import { blur } from "svelte/transition";

    export let url = "";

    const TransitionProperties = {
        duration: 1000,
        amount: 20,
    };
</script>

{#key url}
    <div in:blur={TransitionProperties}
        out:blur={TransitionProperties}>
        <slot />
    </div>
{/key}