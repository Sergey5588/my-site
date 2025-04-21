
<script>
    import { onMount } from 'svelte';
    
    //export let color = '#000000';

    let canvas;
    let ctx;
    let text = 'Hello';


    const chars = "01日ﾊﾐﾋｰｳｼﾅﾓﾆｻﾜﾂｵﾘｱﾎﾃﾏｹﾒｴｶｷﾑﾕﾗｾﾈｽﾀﾇﾍｦｲｸｺｿﾁﾄﾉﾌﾔﾖﾙﾚﾛﾝ0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    const fontSize = 64;
   
            
    const drops = [];
    
    onMount(() => {
        ctx = canvas.getContext('2d');
        resize()
        window.addEventListener('resize', resize);
        
    });

    function resize() {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    }
    
    
    
    
</script>

<canvas
    tabindex="-1"
    bind:this={canvas}
    class="canvas"
></canvas>
<style>
    .canvas {
        
        border: 1px solid white;
        pointer-events: none;
        -webkit-user-drag: none;
        position: absolute;
        top:0px;
        left: 0px;
        z-index: -1;
    }
    
    
</style>