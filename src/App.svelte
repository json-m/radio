<script>
  import Radio from "./lib/Radio.svelte";
  import Viz from "./lib/Viz.svelte";
</script>

<main>
  <div class="wrapper">
    <video autoplay loop muted playsinline>
      <source src="/bg.mp4" type="video/mp4">
    </video>
    <canvas id="canviz" class="viz"></canvas>

    <div class="header">
      <Viz></Viz>
      <img src="https://c.zj.is/kerdesk.png" class="center" alt="froge"><br />
      <Radio></Radio>
    </div>
  </div>
</main>

<style>
  .viz {
    width: 100%;
    height: auto;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 10;
  }

  video {
    object-fit: fill;
    position: absolute;
    top: auto;
    left: auto;
    height: 100%;
    width: 100%;
  }

  .wrapper {
    border: 2px solid #000;
    /*width: 400px;*/
    width: 100vh;
    height: 100vh;
    /*height: 200px;*/
    position: relative;
    overflow: hidden;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .header {
    position: relative;
  }
</style>