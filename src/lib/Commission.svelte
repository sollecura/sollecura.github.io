<script lang="ts">
let { client, details, updates = [] }: {
	client: string,
	details: Array<any>,
	updates: Array<any>
} = $props();

</script>

<style>
@media only screen and (min-width: 1200px) {
	.commission {
		background-color: var(--commission-background);
		padding: 8px;
		display: grid;
		grid-template-rows: auto auto;
		grid-template-columns: auto auto;
		line-height: 1.5;
		column-gap: 4px;
		row-gap: 4px;
	}
	.commission h2, .commission h3 {
		padding: 0;
		margin: 0;
		text-align: center;
		line-height: 2;
	}
	.commission .updatesTitle {
		background-color: var(--updatesTitle-background);
		color: var(--updatesTitle-text);
	}
	.commission .detailsTitle {
		background-color: var(--detailsTitle-background);
		color: var(--detailsTitle-text);
	}
	.commission .clientName {
		background-color: var(--clientName-background);
		color: var(--clientName-text);
		grid-column: 1 / 3;
	}

	.commission h3 {
		grid-row: 2 / 3;
	}
	.details {
		grid-column: 1 / 2;
		color: var(--details-updates-text);
	}
	.updates {
		grid-column: 2 / 3;
		color: var(--details-updates-text);
	}
}
@media only screen and (max-width: 1199px) {
	.commission {
		background-color: var(--commission-background);
		padding: 8px;
		line-height: 1.5;
		row-gap: 4px;
	}
	.commission h3 {
		padding: 0;
		margin: 0;
		text-align: center;
		background-color: var(--details-updates-background);
		line-height: 2;
	}
	.commission .clientName {
		background-color: var(--clientName-background);
		grid-column: 1 / 3;
		padding: 0;
		margin: 0;
		line-height: 2;
	}
}
</style>

<div class="commission">
	<h2 class="clientName">{ client }</h2>
	<h3 class="detailsTitle">Details</h3>
	<ul class="details">
		{#each details as detail}
		{#if typeof detail == "string"}
		<li>{detail}</li>
		{:else}
		<ul>
			{#each detail as subdetail}
			<li>{subdetail}</li>
			{/each}
		</ul>
		{/if}
		{/each}
	</ul>

	<h3 class="updatesTitle">Updates</h3>
	<ul class="updates">
		{#each updates as cur_update}
		{#if typeof cur_update == "string"}
		<li>{cur_update}</li>
		{:else}
		<ul>
			{#each cur_update as subupdate}
			<li>{subupdate}</li>
			{/each}
		</ul>
		{/if}
		{/each}
	</ul>
</div>

