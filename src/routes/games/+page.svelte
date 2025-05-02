<script>
    import { createDraggable, createSpring, animate } from 'animejs';
    import { onMount } from 'svelte';

    

    onMount(() => {

        createDraggable('.grag', {
            container: [-16, 80, 16, 0],
            releaseEase: createSpring({
                stiffness: 120,
                damping: 6,
            }),
            
        })

        animate('.grag', {
            rotate: 360,
            loop: true,
            autoplay: true,
            ease: 'inOutExpo',
        });
    
    })
</script>

<div class='grag' style="height: fit-content; width:fit-content;">
    <button style="cursor:grab"> drag me</button>
</div>