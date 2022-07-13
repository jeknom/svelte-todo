<script lang='ts'>
    let align: 'flex-start' | 'flex-end' | 'center' = 'center';
    let justify: 'normal' | 'center' = 'center';
    let gap: number = 8;
</script>

<div
    style:align-items={align}
    style:justify-content={justify}
    style:gap={`${gap}px`}
>
    <slot></slot>
</div>
  
<style>
    div {
        display: flex;
        flex-direction: column;
    }
</style>