<script>
  export let name;
  export let job;
  export let desc;
  export let imgUrl;
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
    height: 400px;
  }

  .cc-header img {
    width: 100%;
    height: auto;
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
      <img src={imgUrl} alt="avatar">
      <div class="cc-details">
        <h4>{name}</h4>
        <p>{job}</p>
      </div>
    </div>
    <div class="divider"></div>
    <div class="cc-body">
      {desc}
    </div>
  </div>
</div>