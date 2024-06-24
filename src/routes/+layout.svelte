<script>
    import '../styles/variables.css';
</script>

<slot />

<style>
    :global(body) {
        font-family: 'Montserrat', sans-serif;
        font-size: 16px;
        line-height: 1.5;
        margin: 0;
        padding: 0;
        background-color: var(--main-bg-color);
        color: var(--secondary-text-color);
        transition: background-color 0.3s, color 0.3s;
    }  
</style>
