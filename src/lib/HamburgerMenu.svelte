<script lang="ts">
 import { onMount } from 'svelte';
 import { gsap } from 'gsap';


</script>

<div class="menu">
  <a class="menu-text">Menu</a>
</div>


<style lang="scss">
.menu{
  background-color: #fff;
  width: 120px;
  height: 52px;
  border-radius: 16px;
  position: fixed;
  bottom: 10%;
  left: 50%;
  .menu-text{
    font-size: 14px;
    font-weight: bold;
    color: #3a3a3a;
    text-align: center;
    display: block;
    padding: 16px 28px;
    text-decoration: none;
  }
}


</style>
