<script lang="ts">
import Commission from "$lib/Commission.svelte";
</script>

<style>
@media only screen and (min-width: 850px) {
	h1 {
		text-align: center;
	}
	div {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		row-gap: 4px;
		column-gap: 4px;
		align-items: start;
	}
	div div {
		grid-template-columns: 1fr;
		grid-row: 2 / 3;
	}
	.inProgress {
		grid-column: 1 / 2;
	}
	.todo {
		grid-column: 2 / 3;
	}
	.owed {
		grid-column: 3 / 4;
	}
	#inProgressTitle {
		background-color: var(--inProgress-background);
		color: var(--inProgress-text);
	}
	#todoTitle {
		background-color: var(--todo-background);
		color: var(--todo-text);
	}
	#owedTitle {
		background-color: var(--owed-background);
		color: var(--owed-text);
	}
	#tradesTitle {
		background-color: var(--trades-background);
		color: var(--trades-text);
	}
}

@media only screen and (max-width: 849px) {
	div {
		display: grid;
		grid-template-columns: repeat(1, 100%);
		align-items: start;
		row-gap: 4px;
		column-gap: 4px;
	}
	div div {
		grid-template-columns: 1fr;
	}
	#inProgressTitle {
		background-color: var(--inProgress-background);
		color: var(--inProgress-text);
	}
	#todoTitle {
		background-color: var(--todo-background);
		color: var(--todo-text);
	}
	#owedTitle {
		background-color: var(--owed-background);
		color: var(--owed-text);
	}
	#tradesTitle {
		background-color: var(--trades-background);
		color: var(--trades-text);
	}
}
</style>

<div>
	<h1 id="inProgressTitle">in progress</h1>
	<div class="inProgress">
		<Commission 
			client="at_fox"
			details={[
				"possum custom",
				"ref sheet",
			]}
			updates = {["1/2 halfbodies sketched"]}
		/>
		<Commission 
			client="palamutes"
			details={["val beach pin up"]}
			updates = {["rough sketch sent"]}
		/>
	</div>

	<h1 id="todoTitle">to-do / paid</h1>
	<div class="todo">
		<Commission
			client = "at_fox"
			details = {["snoot ref sheet"]}/>
		<Commission
			client = "at_fox"
			details = {["trio cuddle piece"]}/>
	</div>

	<h1 id="owedTitle">owed</h1>
	<div class="owed">
		<Commission
			client = "valkenite"
			details = {["halfbody sketch"]}/>
		<Commission
			client = "figgly_pickle"
			details = {["nsfw fullbody"]}/>
	</div>

	<h1 id="tradesTitle">trades</h1>
	<div class="trades">
		<Commission
			client = "_northerndragon"
			details = {[
				"couple halfbody scene", [
					"to be re-sketched"
				]
			]}/>
	</div>
</div>
