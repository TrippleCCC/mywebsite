<script lang="ts">
    import { blur } from "svelte/transition";

    export let url = "";

    const TransitionDuration = 1000;
    const PixelSize = 20;
</script>

{#key url}
    <div in:blur={{duration: TransitionDuration, amount: PixelSize}}
        out:blur={{duration: TransitionDuration, amount: PixelSize}}>
        <slot />
    </div>
{/key}