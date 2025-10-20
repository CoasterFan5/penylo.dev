<h2>Pricing</h2>
<p>Please refer to our pricing table</p>

<div class="tableWrap">
	<table>
		<thead>
			<tr>
				<td class="label"> Plan Name </td>
				<td> Free </td>
				<td> Pro </td>
				<td> Scale </td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td class="label"> Price </td>
				<td> $0.00/mo </td>
				<td> Also $0.00/mo </td>
				<td> Still $0.00/mo </td>
			</tr>
			<tr>
				<td class="label"> Requests </td>
				<td> Infinity </td>
				<td> Infinity + 1 </td>
				<td> Infinity^2 </td>
			</tr>
			<tr>
				<td class="label"> Seats </td>
				<td> 12E9 </td>
				<td> 12E12 </td>
				<td> 12E15 </td>
			</tr>
			<tr>
				<td class="label">
					Rate Limit
					<span><div class="sub">1</div></span>
				</td>
				<td> 10,000 req/s </td>
				<td> 10,000 req/s </td>
				<td> 10,000 req/s </td>
			</tr>
			<tr>
				<td class="label"> Redistribution</td>
				<td> Yes </td>
				<td> Of course </td>
				<td> 100% </td>
			</tr>
			<tr>
				<td class="label"> Attribution <span><div class="sub">2</div></span></td>
				<td> Not Required </td>
				<td> Appreciated </td>
				<td> Not necessary </td>
			</tr>
			<tr>
				<td class="label"> Support </td>
				<td> Discord </td>
				<td> Discord </td>
				<td> Discord</td>
			</tr>
		</tbody>
	</table>
</div>

<div class="small">
	1: This isn't strictly enforced, but going over this number may trigger DDOS protection. If you
	begin to approach this number, please reach out or consider implementing caching.
</div>
<div class="small">
	2: Attribution may be required for some Penylo services due to third party constraints.
</div>

<style lang="scss">
	.label {
		font-weight: 700;
		position: sticky;
		left: 0px;
		border-left: 1px solid var(--text-25);
		display: flex;
		flex-direction: row;
	}

	.tableWrap {
		overflow-x: auto;
		z-index: 50;
	}

	table {
		width: 100%;
		z-index: 50;
		border: 0px;
		outline: 0px;
		border-collapse: collapse;
		border-bottom: 1px solid var(--text-25);
	}

	tbody {
		display: table;
		width: 100%;
		margin: 0px;
	}

	thead {
		border-top: 1px solid var(--text-25);
		border-bottom: 1px solid var(--text-25);
	}

	tr {
		width: 100%;
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	td {
		width: 25%;
		border-right: 1px solid var(--text-25);
		text-align: center;
		background: var(--background);
		padding: 0.25rem 1rem;
		flex-wrap: nowrap;
		white-space: nowrap;
	}

	.small {
		opacity: 0.8;
		font-size: 0.8rem;
		margin-top: 0.5rem;
	}

	.sub {
		height: 100;
		font-size: 0.6rem;
		margin-left: 0.25rem;
		text-align: start;
		margin-bottom: auto;
	}
</style>
