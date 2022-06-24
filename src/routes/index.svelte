<svelte:head>
    <title>Home</title>
</svelte:head>

<script lang="ts">
    import * as THREE from 'three';
    import * as SC from 'svelte-cubed';
    import { blur } from 'svelte/transition';

    // Canvas Properties
    const canvasProps = {
        width: 960,
        height: 500,
        aspectRatio: 960/500,
        D: 1,
        background: new THREE.Color("white"),
    };

    // Cube Properties
    const cubeProps = {
        geometry: new THREE.BoxGeometry(1, 1, 1),
        rotation: [0, 0, 0],
    };

    let lastValues = [0, 0, 0];
    let direction = Math.floor(Math.random() * 2) == 0 ? -1 : 1;
    let currentIndex = Math.floor(Math.random() * 3);
    let delta = .015

    // Animation for rotation of the cube
    SC.onFrame(() => {
        if (Math.abs(cubeProps.rotation[currentIndex] - lastValues[currentIndex]) <= Math.PI / 2)
            cubeProps.rotation[currentIndex] += delta * direction;
        else {
            lastValues[currentIndex] = cubeProps.rotation[currentIndex];
            direction = Math.floor(Math.random() * 2) == 0 ? -1 : 1;
            currentIndex = Math.floor(Math.random() * 3);
        }
    });

    // Camera Properties
    const camProps = {
        left: -canvasProps.D*canvasProps.aspectRatio,
        right: canvasProps.D*canvasProps.aspectRatio,
        top: canvasProps.D,
        bottom: -canvasProps.D,
        near: 1,
        far: 1000,
        position: [20, 20, 20]
    };

</script>

<div id="animation" class="flex justify-center" transition:blur>
    <SC.Canvas {...canvasProps} >
        <SC.Mesh {...cubeProps} />
        <SC.OrthographicCamera {...camProps} />
    </SC.Canvas>
</div>
