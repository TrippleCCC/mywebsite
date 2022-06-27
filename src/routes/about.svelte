<svelte:head>
    <title>About</title>
</svelte:head>

<script lang="ts">
    import portrait from "../../static/about-me-pic.jpeg?width=800&jpg";
</script>

<div class="mx-4 top-2 flex flex-row">
    <img src={portrait} class="mx-2" alt="Nonso Chukwuarah" />
    <div class="mx-2">
        <h1 class="text-5xl">About Me</h1>
        <p class="text-2xl">
            <br />
            Hello my name is Nonso Chukwurah. I'm am a software engineer working at
            Google Austin. I recived a in Electrical and Computer Engineering at 
            Rice University in Houston, Texas. 
            <br />
            <br />
            In my free time I enjoy doing anything that keeps my hands busy such 
            as basketball, weightlifting, coding, gaming, and a lot more.
            <br/>
            <br/>
            In software engineering im interested in anything that I can get my hands on.
            Theres no particular thing I like getting my hands on. I just enjoy learning
            more about cool technologies and applying them in any way that benifits people
            around the world.
        </p>
    </div>
</div>