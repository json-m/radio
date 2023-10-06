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

  // register some hotkeys //

  // click anywhere on page to start playing
  document.addEventListener("click", () => {
      const a = document.getElementById("audio");
      a.play();
  });
  // spacebar to start or pause playing
  document.addEventListener("keydown", (e) => {
      if (e.code === "Space") {
          const a = document.getElementById("audio");
          if (a.paused) {
              a.play();
          } else {
              a.pause();
          }
      }
  });

  // volume up: A, Equal, or ArrowUp
  document.addEventListener("keydown", (e) => {
      if (e.code === "ArrowUp" || e.code === "Equal" || e.code === "KeyW") {
          const a = document.getElementById("audio");
          a.volume += 0.1;
      }
  });

  // volume down: S, Minus, or ArrowDown
  document.addEventListener("keydown", (e) => {
      if (e.code === "ArrowDown" || e.code === "Minus" || e.code === "KeyS") {
          const a = document.getElementById("audio");
          a.volume -= 0.1;
      }
  });

  // toggle mute: M
    document.addEventListener("keydown", (e) => {
        if (e.code === "KeyM") {
            const a = document.getElementById("audio");
            a.muted = !a.muted;
        }
    });

  // A or Left Arrow to rewind 10 seconds
  document.addEventListener("keydown", (e) => {
      if (e.code === "KeyA" || e.code === "ArrowLeft") {
          const a = document.getElementById("audio");
          a.currentTime -= 10;
      }
  });

  // D or Right Arrow to fast forward to live playback
  document.addEventListener("keydown", (e) => {
      if (e.code === "KeyD" || e.code === "ArrowRight") {
          const a = document.getElementById("audio");
          a.currentTime = a.duration;
      }
  });

  // get "hotkeys" element and toggle hiding it with K
  document.addEventListener("keydown", (e) => {
      if (e.code === "KeyK") {
          const hotkeys = document.getElementById("hotkeys");
          hotkeys.classList.toggle("hidden");
      }
  });
</script>

<audio id="audio" class="audio-controls" controls>
  <source src="https://hls-cdn.zj.is/live/stream.m3u8" type="application/x-mpegURL">
</audio>
