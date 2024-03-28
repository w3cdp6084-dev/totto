<script lang="ts">
  import { gsap } from 'gsap';
  let button;

  function animateButton() {
    const tl = gsap.timeline();
    tl.to(button, { width: 500, duration: 1, ease: "power1.inOut" })
      .to(button, { height: 500, duration: 1, ease: "power1.inOut" });
  }
</script>

<button bind:this={button} on:click={animateButton} class="animate-button">
  Click Me
</button>

<style>
  .animate-button {
    width: 100px; /* 初期幅 */
    height: 50px; /* 初期高さ */
    transition: all 0.5s ease-in-out; /* CSSのトランジションを削除 */
    overflow: hidden; /* テキストがはみ出さないように */
  }
</style>