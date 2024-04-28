<script>
  import ModeButton from "./ModeButton.svelte";


</script>

<nav>
    <ModeButton />
</nav>

<style>
    nav {
        position: fixed;
        top: 1rem;
        right: 1rem;
        width: 100%;
        display: flex;
        justify-content: flex-end;
        padding: 0.5rem;
        box-sizing: border-box;
        transition: background-color 0.3s; 
    }

</style>