<script>
  import Radio from "./lib/Radio.svelte";
  import Viz from "./lib/Viz.svelte";
  import Hotkeys from "./lib/Hotkeys.svelte";

  // register hotkey V to toggle hiding the following elements: visualization, background-video
  document.addEventListener("keydown", (e) => {
    if (e.key === "v") {
      const viz = document.getElementById("visualization");
      const bg = document.getElementById("background-video");
      if (viz.style.display === "none") {
        viz.style.display = "block";
        bg.style.display = "block";
      } else {
        viz.style.display = "none";
        bg.style.display = "none";
      }
    }
  });

</script>

<main>
  <div class="background-video" id="background-video">
    <video autoplay loop muted>
      <source src="https://c.zj.is/t/radio/bg.mp4" type="video/mp4">
    </video>
  </div>

  <div class="canvas-overlay" id="visualization">
    <Viz></Viz>
  </div>

  <div class="audio-controls">
    <Radio></Radio>
  </div>

  <div id="hotkeys" class="hotkeys">
    <Hotkeys></Hotkeys>
  </div>
</main>

<style>
  html, body {
    height: 100%;
    margin: 0;
    overflow: hidden;
  }

  .background-video {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
  }

  .background-video video {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .canvas-overlay {
    display: flex;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
  }

  /* show canvas on bottom of page */
  #visualization {
    position: absolute;
    bottom: 0;
    left: 0;
    z-index: 4;
  }

  .audio-controls {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 2;
  }

  /*show hotkeys on top left*/
  .hotkeys {
    position: absolute;
    top: 0;
    left: 0;
    z-index: 5;
  }

</style>