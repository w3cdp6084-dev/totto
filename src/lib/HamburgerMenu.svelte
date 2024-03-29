<script lang="ts">
  import { gsap } from 'gsap';
  let button;

  let isOpen = false;

  function toggleNav() {
    if (!isOpen) {
      // ボタンを水平に400px、その後に垂直に300px伸ばす
      gsap.to(button, { width: 400, duration: 0.5, ease: "power1.inOut" })
        .then(() => {
          gsap.to(button, { height: 300, duration: 0.5, ease: "power1.inOut" });
        });
    } else {
      // ボタンを垂直に元のサイズに戻し、その後に水平に戻す
      gsap.to(button, { height: 50, duration: 0.5, ease: "power1.inOut" })
        .then(() => {
          gsap.to(button, { width: 100, duration: 0.5, ease: "power1.inOut" });
        });
    }
    isOpen = !isOpen;
  }
</script>

<button bind:this={button} on:click={toggleNav} class="nav-button">
  Menu
</button>

<style>
  .nav-button {
    width: 100px; /* 初期幅 */
    height: 50px; /* 初期高さ */
    transition: all 0.5s ease-in-out; /* CSSのトランジションを削除 */
    margin: 0 auto;
    display: block;
  }
</style>