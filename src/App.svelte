<script>
	import ContactCard from './ContactCard.svelte';
	import MsgCard from './MsgCard.svelte';

	let name = '';
	let job = '';
	let desc = '';
	let imgUrl = '';
	let formState = 'empty';

	let createdContacts = [];

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
		createdContacts = [
			...createdContacts, 
			{ id: Math.random(), name, job, desc, imgUrl }
		];
		formState = 'done';
	}

	function deleteFirst() {
		createdContacts = createdContacts.slice(1);
	}

	function deleteLast() {
		createdContacts = createdContacts.slice(0, -1);
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
	<button on:click={deleteFirst}>Delete First Item</button>
	<button on:click={deleteLast}>Delete Last Item</button>
</div>

{#if formState === 'invalid'}
	<MsgCard msg="Input is invalid" />
{:else}
	<MsgCard msg="Please fill out the whole form" />
{/if}

{#each createdContacts as createdContact, index (createdContact.id)}
	<h2>{index}</h2>
	<ContactCard 
		name={createdContact.name}
		job={createdContact.job}
		imgUrl={createdContact.imgUrl}
		desc={createdContact.desc}
	/>
{:else}
	<MsgCard msg="Please start adding contacts. We found none!" />
{/each}