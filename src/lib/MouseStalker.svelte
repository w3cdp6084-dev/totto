<script>
 import { onMount } from "svelte";

 let stalkerX = 0;
 let stalkerY = 0;
 let currentX = 0;
 let currentY = 0;
 let stalkerSize = 20; // 初期サイズ
 const hoverSize = 40; // ホバー時のサイズ
 let rafId;
 let stalker; // mouse-stalker要素への参照

 onMount(() => {
  const updatePosition = (event) => {
   stalkerX = event.clientX;
   stalkerY = event.clientY;
  };

  const loop = () => {
   currentX += (stalkerX - currentX) * 0.1;
   currentY += (stalkerY - currentY) * 0.1;
   if (stalker) {
    stalker.style.transform = `translate(${currentX - stalkerSize / 2}px, ${currentY - stalkerSize / 2}px)`;
   }
   rafId = requestAnimationFrame(loop);
  };

  const hoverElements = document.querySelectorAll(".hover-target");
  hoverElements.forEach((element) => {
   element.addEventListener("mouseover", () => {
    stalkerSize = hoverSize; // ホバー時にサイズを変更
   });
   element.addEventListener("mouseleave", () => {
    stalkerSize = 20; // リセット
   });
  });

  window.addEventListener("mousemove", updatePosition);
  loop();

  return () => {
   window.removeEventListener("mousemove", updatePosition);
   cancelAnimationFrame(rafId);
  };
 });

 // リアクティブステートメントでスタイルを更新
 $: if (stalker) {
  stalker.style.width = `${stalkerSize}px`;
  stalker.style.height = `${stalkerSize}px`;
 }
</script>

<div bind:this={stalker} class="mouse-stalker"></div>

<style>
 @keyframes ripple {
  from {
   opacity: 1;
   transform: scale(1);
  }
  to {
   opacity: 0;
   transform: scale(1.5);
  }
 }

 .mouse-stalker {
  position: fixed;
  border-radius: 50%;
  background-color: red;
  pointer-events: none;
  z-index: 9999;
  transition:
   transform 0.2s ease-out,
   width 0.3s ease-out,
   height 0.3s ease-out;
 }
</style>
