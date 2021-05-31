<script>
import { component_subscribe } from "svelte/internal";

	export let name;

	let today = new Date().toISOString().slice(0, 10)
console.log(today)

</script>

<main>
	<h1>Jämför {name}!</h1>
	<p>Dagens datum {today}!</p>

	<script>
		function compareDates() {
		
			var from = document.getElementById('from').textContent;
			var to = document.getElementById('to').textContent;
	
			var splitFrom = from.split('-');
			var splitTo = to.split('-');
		
			var fromDate = Date.parse(splitFrom[0], splitFrom[1] - 1, splitFrom[2]);
			var toDate = Date.parse(splitTo[0], splitTo[1] - 1, splitTo[2]);
	
			return fromDate < toDate;
		}
		
	</script>

	<p>Antal dagar: </p>
	
	<input id="from" type="date" placeholder="dd/mm/yy"><br>
	<input id="to" type="date" placeholder="dd/mm/yy">
	<button onclick="compareDates()">Compare</button>
	

</main>



<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #39a109 ;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>