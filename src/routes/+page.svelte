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
  <h1>
    <span class="welcome">
      <picture>
        <source srcset={welcome} type="image/webp" />
        <img src={welcome_fallback} alt="Welcome" />
      </picture>
    </span>
    <span class="coronaarch">
      <picture>
        <source srcset={coronaarch} type="image/jpg" />
        <img src={coronaarch} alt="Corona Arch with Claret Cup in front" />
      </picture>
    </span>
    <div class="piclabel">Corona Arch</div>

    to my new<br />SvelteKit app
  </h1>

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

  h1 {
    width: 100%;
  }

  .welcome {
    display: block;
    position: relative;
    width: 100%;
    height: 0;
    padding: 0 0 calc(100% * 495 / 2048) 0;
  }

  .welcome img {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    display: block;
  }

  .coronaarch {
    display: inline-block;
    position: relative;
    width: 25%;
    height: 0;
    padding: 0 0 calc(100% * 495 / 2048) 0;
  }

  .coronaarch img {
    position: absolute;
    width: 100%;
    top: 0;
    display: inline-block;
  }

  .piclabel {
    margin-top: 50px;
  }
</style>
