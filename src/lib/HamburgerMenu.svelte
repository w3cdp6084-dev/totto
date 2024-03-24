<script lang="ts">
 import { onMount } from 'svelte';
 import { gsap } from 'gsap';

 let menu;
 let items = [];
 let isOpen = false;

 function toggleMenu() {
   isOpen = !isOpen;
   if (isOpen) {
     gsap.to(menu, { xPercent: 0, duration: 0.5 });
     gsap.fromTo(items, { opacity: 0, y: 20 }, { opacity: 1, y: 0, stagger: 0.1, duration: 0.5 });
   } else {
     gsap.to(menu, { xPercent: -100, duration: 0.5 });
   }
 }

 onMount(() => {
   gsap.set(menu, { xPercent: -100 });
   gsap.set(items, { opacity: 0 });
 });
</script>

<div class="menu-trigger" on:mouseenter={() => isOpen = true} on:mouseleave={() => isOpen = false}>
  <div class="menu-trigger__container">
  <div class="menu-trigger__button">
    <div class="menu-trigger__button--container">
      <div class="menu-trigger__dot"></div>
      <div class="menu-trigger__dot"></div>
      <div class="menu-trigger__dot"></div>
    </div>
    <span class="menu-trigger__button--bg">
    </span>
  </div>
</div>
</div>


<style>
  .menu-trigger {
    position: relative;
  }
  .menu-trigger__button {
    position: relative;
    margin: 0 auto;
    display: inline-block;
    z-index: 1;
    width: 100%;
    height: 100%;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
    pointer-events: auto;
    cursor: pointer;
    -webkit-transition: -webkit-transform .3s;
    transition: -webkit-transform .3s;
    -o-transition: transform .3s;
    transition: transform .3s;
    transition: transform .3s, -webkit-transform .3s;
  }
  .menu-trigger__container {
    position: fixed;
    left: 0;
    right: 0;
    bottom: 40px;
    margin: 0 auto;
    width: 60px;
    height: 60px;
    z-index: 1;
    overflow: visible;
    z-index: 100;
    pointer-events: auto !important;
  }
  .menu-trigger__button--container {
    position: absolute;
    left: 0;
    right: 0;
    margin: 0 auto;
    top: calc(50% - 2.5px);
    z-index: 1;
}
.menu-trigger__button--container .menu-trigger__dot {
    position: absolute;
    display: block;
    top: 0;
    left: 0;
    right: 0;
    width: 5px;
    height: 5px;
    background-color: #fff;
    border-radius: 20px;
    -webkit-transform-origin: center;
    -ms-transform-origin: center;
    transform-origin: center;
    -webkit-transition: opacity .3s, width .3s, -webkit-transform .3s;
    transition: opacity .3s, width .3s, -webkit-transform .3s;
    -o-transition: opacity .3s, transform .3s, width .3s;
    transition: opacity .3s, transform .3s, width .3s;
    transition: opacity .3s, transform .3s, width .3s, -webkit-transform .3s;
    margin: 0 auto;
}
.menu-trigger__button--container .menu-trigger__dot:first-of-type {
    left: -40%;
}
.menu-trigger__button--container .menu-trigger__dot:last-of-type {
    right: -40%;
}
.menu-trigger__button--bg{
  border-radius: 50%;
    opacity: .8;
    -webkit-transition: opacity .3s cubic-bezier(.165,.84,.44,1), -webkit-transform .3s;
    transition: opacity .3s cubic-bezier(.165,.84,.44,1), -webkit-transform .3s;
    -o-transition: transform .3s, opacity .3s cubic-bezier(.165, .84, .44, 1);
    transition: transform .3s, opacity .3s cubic-bezier(.165,.84,.44,1);
    transition: transform .3s, opacity .3s cubic-bezier(.165,.84,.44,1), -webkit-transform .3s;
    -webkit-transform-origin: center;
    -ms-transform-origin: center;
    transform-origin: center;
    overflow: visible;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    background-color: #000;
    width: 100%;
    height: 100%;
    display: inline-block;
}
.menu-trigger__container {
    width: 50px;
    height: 50px;
}
</style>
