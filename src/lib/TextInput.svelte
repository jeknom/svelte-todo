<script lang="ts">
    export let value: string = '';
    export let placeholder: string | undefined = undefined;
</script>

<input
    type='text'
    placeholder={placeholder}
    bind:value={value}
/>
  
<style>
    input {
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-sizing: border-box;
    }
</style>