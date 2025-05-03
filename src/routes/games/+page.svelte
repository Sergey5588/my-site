<script>
    import { createDraggable, createSpring, animate } from 'animejs';
    import { onMount } from 'svelte';

    let i = 0

    onMount(() => {

        createDraggable('.grag', {
            container: [-16, 80, 16, 0],
            releaseEase: createSpring({
                stiffness: 120,
                damping: 6,
            }),

            onRelease: () => {
                i+=1;
                animate('.grag', {
                    rotate: i*360,
                    loop: false,
                    duration: 2000,
                    autoplay: true,
                    ease: 'outExpo',
                });
            }
            
        })

    
    })
</script>

<div class='grag' style="height: fit-content; width:fit-content;">
    <button style="cursor:grab"> drag me</button>
</div>