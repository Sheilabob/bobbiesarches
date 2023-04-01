<script lang="ts">
  import coronaarch from "$lib/images/corona-arch.jpg";
  import angelarch from "$lib/images/angel-arch.jpeg";

  function flip(node, { delay = 0, duration = 1500 }) {
    return {
      delay,
      duration,
      css: (t, u) => `
				transform: rotateY(${1 - u * 180}deg);
				opacity: ${1 - u};
			`,
    };
  }

  let arches = [
    {
      title: "Corona Arch",
      flipped: true,
      size: "110ft x 110ft",
      picdate: "4/24/22",
      type: "Buttress",
      traildesc: "Well-marked, busy trail near Moab, UT.",
      gps: "38 34.790' -109 37.197'",
      srcset: coronaarch,
      alt: "Corona Arch with Claret Cup in front",
    },
    {
      title: "Angel Arch",
      flipped: true,
      size: "135ft x 120ft",
      picdate: "6/3/20",
      type: "Fin",
      traildesc:
        "Marked back-country trail (13 miles to nearest trailhead) leads to front, route-finding and scrambling to get up to and behind. Inside Needles District of Canyonlands National Park, Salt Creek. Permit required for overnight stays.",
      gps: "38 3.106' -109 45.406'",
      srcset: angelarch,
      alt: "Columbine with Angel Arch in the background",
    },
  ];
</script>

<div class="piccards">
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  {#each arches as arch}
    <div class="card-container" on:click={() => (arch.flipped = !arch.flipped)}>
      <div class="card">
        {#if arch.flipped}
          <div class="coronaarch side" transition:flip>
            <picture>
              <source srcset={arch.srcset} type="image/jpg" />
              <img src={arch.srcset} alt={arch.alt} />
            </picture>
            <div class="piclabel">{arch.title}</div>
          </div>
        {:else}
          <div class="coronaarch side back" transition:flip>
            <picture>
              <source srcset={arch.srcset} type="image/jpg" />
              <img
                src={arch.srcset}
                alt="Corona Arch with Claret Cup in front"
              />
            </picture>
            <h2>{arch.title}</h2>
            <p>Size: {arch.size}</p>
            <p>Type: {arch.type}</p>
            <p>Date of Picture: {arch.picdate}</p>
            <p>Trail Description: {arch.traildesc}</p>
            <p>GPS: {arch.gps}</p>
          </div>
        {/if}
      </div>
    </div>
  {/each}
  <!-- <div class="coronaarch card">
    <picture>
      <source srcset={angelarch} type="image/jpg" />
      <img src={angelarch} alt="Columbine with Angel Arch in the background" />
    </picture>
    <div class="piclabel">Angel Arch</div>
  </div> -->
  <!-- <div class="card angelarch">
    <h2>Angel Arch Info</h2>
    <p>Size: 135ft x 120ft</p>
    <p>Type: Fin</p>
    <p>Date of Picture: 6/3/20</p>
    <p>
      Trail Description: Marked back-country trail (13 miles to nearest
      trailhead) leads to front, route-finding and scrambling to get up to and
      behind. Inside Needles District of Canyonlands National Park, Salt Creek.
      Permit required for overnight stays.
    </p>
    <p>GPS: 38 3.106' -109 45.406'</p>
  </div> -->
</div>

<style>
  .piccards {
    display: flex;
  }

  .coronaarch {
    display: inline-block;
    position: relative;
  }

  .angelarch {
    font-size: 11px;
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

  .card-container {
    position: relative;
    width: 200px;
    height: 270px;
    margin: 10px;
  }

  .card {
    border-radius: 6px;
    padding: 10px;
    text-align: center;
    margin: 5px;
    /* position: absolute; */
    perspective: 600;
  }

  .side {
    position: absolute;
    height: 100%;
    width: 100%;
    background-color: #4b2421;
    overflow: hidden;
    color: #d5c6b9;
    display: flex;
    flex-direction: column;
    /* justify-content: center; */
    /* align-items: center; */
  }

  .back {
    height: 225%;
    width: 225%;
    z-index: 5;
  }

  h2 {
    font-size: 22px;
  }

  p {
    margin: 5px 0px;
  }
</style>
