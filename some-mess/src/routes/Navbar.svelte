<script lang="ts">
    import "../global.css"
</script>

<nav>
	<div>
		<a href="/">Home</a>
	</div>
	<div>
		<a href="/stoopid">Stoopid</a>
	</div>
</nav>

<style>
	nav {
		display: flex;
		align-items: center;
		justify-content: flex-end;
	}

    nav>div {
        padding: 1em 2em;
    }

    nav>div>a {
        color: var(--primary-color);
        text-decoration: none;
    }

    nav>div>a:visited{
        color: var(--primary-color);
    }

</style>
