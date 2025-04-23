<script>
    import { createDraggable } from 'animejs';
    import { onMount } from 'svelte';
    onMount(() => {

        createDraggable('.grag');
    })
</script>

<div class='grag' style="height: fit-content; width:fit-content;">
    <button> drag me</button>
</div>