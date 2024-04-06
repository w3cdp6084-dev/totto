<script>
 export let level = 1;
 export let text = '';
</script>

{#if level === 1}
 <h1 class="heading-1">{text}</h1>
{:else if level === 2}
 <h2 class="heading-2">{text}</h2>
{:else if level === 3}
 <h3 class="heading-3">{text}</h3>
{:else if level === 4}
 <h4>{text}</h4>
{:else if level === 5}
 <h5>{text}</h5>
{:else}
 <h6>{text}</h6>
{/if}

<style>
 .heading-2 {
  font-size: 1.5rem;
  font-weight: bold;
  text-align: center;
  width: 100%;
  background-color: #fff;
  line-height: 88px;
  margin: 0;
  height: 88px;
 }
 .heading-3 {
  font-size: 1.1rem;
  font-weight: bold;
  text-align: center;
 }
</style>