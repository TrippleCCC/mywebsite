<script lang="ts" context="module">
    /** @type {import('@sveltejs/kit').Load} */
    export const load = async ({url}) => {
        return {props: {url}};
    };

</script>

<script lang="ts">
    import PageTransition from "$lib/components/PageTransition.svelte";
    import "../app.css";
    import Typewriter from "svelte-typewriter";

    export let url;

    let cursor = "|";

    const updateCursor = () => {
        if (cursor.localeCompare("|") == 0)
            cursor = ""
        else
            cursor = "|"
    };

</script>

<div class="flex justify-between flex-wrap mt-2 mb-5 mx-4">
    <div id="name">
        <Typewriter interval={[30, 50, 80, 100, 500]}>
            <h1 class="text-7xl">Nonso</h1>
            <h1 class="text-7xl">Chukwurah</h1>
        </Typewriter>
        <Typewriter loopRandom={true}>
            <h1 class="text-xl">Thinker</h1>
            <h1 class="text-xl">Engineer</h1>
            <h1 class="text-xl">Gamer</h1>
            <h1 class="text-xl">Coder</h1>
            <h1 class="text-xl">Tinkerer</h1>
        </Typewriter>
    </div>
    <div id="nav" class="grow">
        <ul class="text-4xl text-right">
            <Typewriter>
                <a href="/"><li class="hover:font-bold">Home</li></a>
                <a href="/about"><li class="hover:font-bold">About Me</li></a>
                <a href="/resume"><li class="hover:font-bold">Resume</li></a>
                <a href="/contributions"><li class="hover:font-bold">Contributions</li></a>
            </Typewriter>
        </ul>
    </div>
</div>

<PageTransition {url}>
    <slot></slot>
</PageTransition>
