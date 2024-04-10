<script lang="ts">
 import { gsap } from "gsap";
 import { onMount } from "svelte";
 let button;
 let navLinks;

 let isOpen = false;
 onMount(() => {
  gsap.from(button, { y: 100, opacity: 0, duration: 1 });
 });
 function toggleMenu() {
  if (!isOpen) {
   gsap
    .to(button, { width: 400, duration: 0.5, ease: "power1.inOut" })
    .then(() => {
     return gsap.to(button, {
      height: 300,
      duration: 0.5,
      ease: "power1.inOut",
     });
    })
    .then(() => {
     // ナビゲーションリンクのアニメーションを開始
     return gsap.to(navLinks, {
      autoAlpha: 1,
      duration: 0.5,
      ease: "power1.inOut",
     });
    });
  } else {
   // ナビゲーションリンクを非表示にする
   gsap
    .to(navLinks, { autoAlpha: 0, duration: 0.5, ease: "power1.inOut" })
    .then(() => {
     return gsap.to(button, {
      height: 50,
      duration: 0.5,
      ease: "power1.inOut",
     });
    })
    .then(() => {
     return gsap.to(button, {
      width: 100,
      duration: 0.5,
      ease: "power1.inOut",
     });
    });
  }
  isOpen = !isOpen;
 }
</script>

<button
 bind:this={button}
 on:click={toggleMenu}
 class="hover-target index-viewButton">Menu</button
>
<div bind:this={navLinks} class="nav-links" style="opacity: 0;">
 <a href="/" class="hover-target">Home</a>
 <a href="/about">About</a>
 <a href="/contact">Contact</a>
</div>

<style>
 .index-viewButton {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 100;
  width: 100px;
  height: 50px;
 }
 .nav-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding: 20px;
  /* 初期状態では非表示 */
  visibility: hidden;
 }
</style>
