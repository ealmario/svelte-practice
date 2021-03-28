<script>
  export let msg;
</script>

<style>
  .msg-card {
		border-radius: 4px;
		box-shadow: 0px 8px 24px rgba(0,0,0,0.15);
		margin: 0 auto 1rem auto;
		padding: 1rem;
		width: 150px;
	}

	.msg-card p {
		text-align: center;
	}
</style>

<div class="msg-card">
  <p>{msg}</p>
</div>