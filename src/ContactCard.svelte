<script>
  export let name;
  export let job;
  export let desc;
  export let imgUrl;

  const initialName = name;
</script>

<style>
  .container {
    width: 90%;
    margin: 0 auto;
  }

  .contact-card {
    border-radius:  8px;
    box-shadow: 0 8px 24px  rgba(0,0,0, 0.15);
    margin: 0 auto;
    padding: 1rem 2rem;
    width: 300px;
  }

  .cc-header {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  img {
    width: 100%;
    height: 100%;
  }

  .thumb {
    height: auto;
    width: 100%;
    margin: 0;
  }

  .thumb-placeholder {
    background-color: gray;
    width: 300px;
    height: 150px;
    margin: 0;
  }

  .divider {
    background: gray;
    margin: 1.5rem 0;
    opacity: 0.2;
    height: 1px;
    width: 100%;
  }
</style>

<div class="container">
  <div class="contact-card">
    <div class="cc-header">
      <!-- <figure class="thumb" class:thumb-placeholder={!imgUrl}> to add a class conditionally using svelte syntax-->
      <figure class={imgUrl ? 'thumb' : 'thumb-placeholder'}>
        <img src={imgUrl} alt="avatar">
      </figure>
      <div class="cc-details">
      <h4>{name} / {initialName}</h4>
        <p>{job}</p>
      </div>
    </div>
    <div class="divider"></div>
    <div class="cc-body">
      {desc}
    </div>
  </div>
</div>