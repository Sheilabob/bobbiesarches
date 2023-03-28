<script lang="ts">
  import coronaarch from "$lib/images/corona-arch.jpg";
  import angelarch from "$lib/images/angel-arch.jpeg";
</script>

<div class="piccards">
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
  <div class="coronaarch card">
    <picture>
      <source srcset={angelarch} type="image/jpg" />
      <img src={angelarch} alt="Columbine with Angel Arch in the background" />
    </picture>
    <div class="piclabel">Angel Arch</div>
  </div>
  <div class="card angelarch">
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
  </div>
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
