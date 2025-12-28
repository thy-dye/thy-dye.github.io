<script lang="ts">
  import { onMount } from 'svelte';
  
  let cam: HTMLCanvasElement | null = null;
  
  onMount(() => {
    // TypeScript knows canvas could be null, so we need to check
    if (!cam) return;
    
    const ctx = cam.getContext('2d');
    if (!ctx) return;
    
    ctx.fillStyle = 'red';
    ctx.fillRect(0, 0, 350, 200);
  });
</script>

<h1>Home</h1>
<h3>Ty Torres</h3>
<p>about me and blah blah</p>

<canvas bind:this={cam} width="350" height="200"></canvas>
<div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
</div>

<style>
  canvas {
    width: 350px;
    height: 200px;
    border: 2px solid black;
  }
</style>