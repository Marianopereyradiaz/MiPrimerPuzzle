<script>
    export let left = 0;
    export let top = 30;
    let moving = false;

    function start(){
        moving = true;
    }

    function startTouch(){
        preventDefault() 
        moving = true;
    }

    function stop() {
        moving = false;
    }

    function stopTouch() {
        preventDefault() 
        moving = false;
    }

    function moveTouch(e){
        preventDefault() 
        if (moving){
            left +=e.touches[0].clientX;
            top+=e.touches[0].clientY;
        }
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

<svelte:window on:touchend={stopTouch} on:click={stop} on:mousemove={move} on:touchmove={moveTouch}/>

<section on:touchstart={startTouch} on:mousedown={start} style="left: {left}px; top: {top}px;" class="draggable">
    <slot></slot>
</section>