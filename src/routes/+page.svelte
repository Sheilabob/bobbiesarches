<script>
  import Counter from "./Counter.svelte";
  import welcome from "$lib/images/svelte-welcome.webp";
  import welcome_fallback from "$lib/images/svelte-welcome.png";
  import coronaarch from "$lib/images/corona-arch.jpg";
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
  <div class="coronaarch card">
    <picture>
      <source srcset={coronaarch} type="image/jpg" />
      <img src={coronaarch} alt="Corona Arch with Claret Cup in front" />
    </picture>
    <div class="piclabel">Corona Arch</div>
  </div>

  <h2>
    try editing <strong>src/routes/+page.svelte</strong>
  </h2>

  <Counter />
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 0.6;
  }

  .coronaarch {
    display: inline-block;
    position: relative;
    width: 25%;
  }

  .coronaarch img {
    width: 85%;
    padding: 20px;
  }

  .piclabel {
    color: #d5c6b9;
    padding: 5px;
  }

  .card {
    background-color: #4b2421;
    border-radius: 6px;
  }
</style>
