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
  <div class="card">
    <h2>Corona Arch Info</h2>
    <p>Size: 110ft x 110ft</p>
    <p>Type: Buttress</p>
    <p>Date of Picture: 4/24/22</p>
    <p>Trail Description: Well-marked, busy trail near Moab, UT.</p>
    <p>GPS: 38 34.790' -109 37.197'</p>
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
  }

  .coronaarch img {
    display: inline-block;
    width: 160px;
    padding: 20px;
    padding-bottom: 0px;
  }

  .piclabel {
    margin: 5px auto;
  }

  .card {
    background-color: #4b2421;
    border-radius: 6px;
    width: 200px;
    height: 270px;
    color: #d5c6b9;
    padding: 10px;
    text-align: center;
    margin: 5px;
  }

  h2 {
    font-size: 22px;
  }

  p {
    margin: 5px 0px;
  }
</style>
