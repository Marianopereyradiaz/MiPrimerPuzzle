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
        cursor: move;
        background-color: white;
        width: fit-content;
    }
</style>

<svelte:window on:mouseup={stop} on:mousemove={move}/>

<section on:mousedown={start} style="left: {left}px; top: {top}px;" class="draggable">
    <slot></slot>
</section>