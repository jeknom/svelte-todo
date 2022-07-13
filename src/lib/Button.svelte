<script lang='ts'>
    export let onClick: () => void | undefined;
</script>

<button on:click={onClick}>
    <slot />
</button>
  
<style>
    button {
        cursor: pointer;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #912400;
        border-radius: 4px;
        box-sizing: border-box;
        background-color: #ff3e00;
        color: white;
    }
    
    button:hover {
        background-color: #ff632f;
    }

    button:active {
        background-color: #ffa789;
    }
</style>