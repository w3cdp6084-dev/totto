<script lang="ts">
 import { onMount } from 'svelte';
 import { gsap } from 'gsap';


</script>

<div class="menu-icon">
  <div class="dot"></div>
  <div class="dot"></div>
  <div class="dot"></div>
</div>


<style>
  .menu-icon {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 40px;
    cursor: pointer;
  }

  .dot {
    width: 6px;
    height: 6px;
    background-color: #000;
    border-radius: 50%;
  }


</style>
