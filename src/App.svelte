<script>
	import ContactCard from './ContactCard.svelte';

	let name = '';
	let job = '';
	let desc = '';
	let imgUrl = '';
	let done = false;

	function addCard() {
		done = true;
	}
</script>

<style>
	.form {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin-bottom: 2rem;
	}

	input,
	textarea {
		width: 400px;
	}
</style>

<div class="form">
	<label for="imgUrl">Image URL:</label>
	<input type="text" bind:value={imgUrl} id="imgUrl"/>
	<label for="name">Name:</label>
	<input type="text" bind:value={name} id="name"/>
	<label for="name">Job:</label>
	<input type="text" bind:value={job} id="job"/>
	<label for="desc">Short Description:</label>
	<textarea bind:value={desc} id="desc"/>

	<button on:click={addCard}>Add Card</button>
</div>

{#if done}
<ContactCard
	{imgUrl}
	{name}
	{job}
	{desc}
/>
{/if}