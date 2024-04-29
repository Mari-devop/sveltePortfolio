<script>

    import Navbar from '../components/Navbar.svelte'
</script>


<Navbar />

<slot></slot>

<style>
   :global(body) {
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    line-height: 1.5;
    margin: 0;
    padding: 0;
    background-color: #f2f7f5;
    color: #00473e;
	transition: background-color 0.3s;
    transition: color 0.3s;
}

	:global(body.dark-mode) {
		background-color: #004643;
		color: #abd1c6;
	}
    
    
</style>