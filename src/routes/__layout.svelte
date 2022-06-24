<script lang="ts">
    import "../app.css";
</script>

<div class="flex justify-between flex-wrap mt-2 mb-5 mx-4">
    <div id="name">
        <h1 class="text-7xl">Nonso</h1>
        <h1 class="text-7xl">Chukwurah</h1>
    </div>
    <div id="nav" class="grow">
        <ul class="text-4xl text-right">
            <a href="/"><li class="hover:font-bold">Home</li></a>
            <a href="/about"><li class="hover:font-bold">About Me</li></a>
            <a href="/resume"><li class="hover:font-bold">Resume</li></a>
            <a href="/contributions"><li class="hover:font-bold">Contributions</li></a>
        </ul>
    </div>
</div>

<div>
    <slot></slot>
</div>
