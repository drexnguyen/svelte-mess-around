<script lang="ts">
    let facts = $state([]);
    import Button from "#lib/components/Button.svelte"
	import { applyReroute } from "@sveltejs/kit/adapter";

    async function fetch_new_fact() {
        console.log("hit");
        try {
            const result = await fetch("https://catfact.ninja/fact");
            if (result.ok) {
                const data = result.json();
                console.log(data);
                facts.push(data.fact);
            }
            else {
                alert("It broke :(");
            }
        } catch {
            alert("Damn bruh what are you doing");
        }

    }
</script>

<ul>
    {#each facts as fact}
        <li>{fact}</li>
    {/each}
</ul>
<button onclick={fetch_new_fact}>More facts!</button>