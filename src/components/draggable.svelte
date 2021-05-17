<script>
    export let left = 0;
    export let top = 30;
    let moving = false;

    function start(){
        moving = true;
    }

    function stop() {
        moving = false;
    }

    function move(e){
        if (moving){
            left +=e.movementX;
            top+= e.movementY;
        }
    }


</script>

<style>
    .draggable{
        user-select: none;
        position:absolute;
        border: solid 1px black;
        background-color: white;
        width: fit-content;
    }
</style>

<svelte:window on:onmouseup={stop} on:click={stop} on:mousemove={move}/>

<section on:t on:mousedown={start} style="left: {left}px; top: {top}px;" class="draggable">
    <slot></slot>
</section>