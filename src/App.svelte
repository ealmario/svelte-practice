<script>
	import ContactCard from './ContactCard.svelte';

	let name = '';
	let job = '';
	let desc = '';
	let imgUrl = '';
	let formState = 'empty';

	function addCard() {
		if (
			name.trim().length === 0 ||
			job.trim().length === 0 || 
			desc.trim().length === 0 || 
			imgUrl.trim().length === 0
		) {
			formState = 'invalid';
			return;
		}
		formState = 'done';
	}
</script>

<style>

	.msg-card {
		border-radius: 4px;
		box-shadow: 0px 8px 24px rgba(0,0,0,0.15);
		margin: 0 auto;
		padding: 1rem;
		width: 150px;
	}

	.msg-card p {
		text-align: center;
	}

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

{#if formState === 'invalid'}
	<div class="msg-card">
		<p>Input is invalid.</p>
	</div>
{:else if formState === 'done'}
<ContactCard
	{imgUrl}
	{name}
	{job}
	{desc}
/>
{:else}
	<div class="msg-card">
		<p>Please fill out the whole form.</p>
	</div>
{/if}