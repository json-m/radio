<script>
  import Hls from "hls.js";
  import {onMount} from "svelte";

  // onMount load hls.js
  onMount(() => {
    if (Hls.isSupported()) {
      const audio = document.getElementById("audio");
      const hls = new Hls();
      hls.loadSource("https://hls-cdn.zj.is/live/stream.m3u8");
      hls.attachMedia(audio);
    }

    // don't blow people's ears out
    const a = document.getElementById("audio");
    a.volume = 0.5;
  });
</script>

<audio id="audio" controls>
  <source src="https://hls-cdn.zj.is/live/stream.m3u8" type="application/x-mpegURL">
</audio>
