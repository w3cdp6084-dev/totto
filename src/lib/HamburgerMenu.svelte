<script lang="ts">
 import { onMount } from 'svelte';
 import { gsap } from 'gsap';

 let menu;
 let isOpen = false;

 function toggleMenu() {
   isOpen = !isOpen;
   if (isOpen) {
     gsap.fromTo(menu, { xPercent: -100 }, { xPercent: 0, duration: 0.5 });
   } else {
     gsap.fromTo(menu, { xPercent: 0 }, { xPercent: -100, duration: 0.5 });
   }
 }
</script>

<button on:click={toggleMenu}>☰</button>

<div bind:this={menu} class="menu">
 <a href="/">Home</a>
 <a href="/about">About</a>
</div>

<style>
 .menu {
   position: fixed;
   top: 0;
   left: 0;
   width: 80%;
   height: 100%;
   background-color: #000;
   color: #fff;
   transform: translateX(-100%);
   transition: transform 0.3s ease;
   display: flex;
   flex-direction: column;
   justify-content: center;
 }
</style>
