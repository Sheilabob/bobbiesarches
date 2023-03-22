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
  <span class="coronaarch">
    <picture>
      <source srcset={coronaarch} type="image/jpg" />
      <img src={coronaarch} alt="Corona Arch with Claret Cup in front" />
    </picture>
    <div class="piclabel">Corona Arch</div>
  </span>

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
    width: 100%;
    padding: 0;
  }

  .piclabel {
    margin-top: 5px;
  }
</style>
