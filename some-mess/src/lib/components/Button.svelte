<script lang="ts">
    import '../../global.css'
    let {
        variant = 'primary',
        children,
        ...restProps
    } = $props();
</script>

<button class=btn {variant} {...restProps}>
    {#if children}
        {@render children()}
    {/if}
</button>

<style>
    .btn {
        background-color: var(--primary-color);
        color: white;
        border: none; 
        cursor: pointer;
        border-radius: 1em;
        padding: 1em 2em;
    }

    .primary {
        background-color: var(--primary-color);
    }
    .secondary {
        background-color: var(--secondary-color);
    }
</style>