<script>
 import Heading from "../../lib/Heading.svelte";
</script>

<svelte:head>
 <title>About</title>
 <meta name="description" content="About this app" />
</svelte:head>
<Heading level={2} text="about" />

<div class="wrap">
 <div class="inner">
  <p class="description">
   nelというブランドカンパニーです。<br />
   なにとなにとなにを大事にし、こんな未来のために現在の問題を洗い出して解決します。<br
   />
   そのために個人で大事にしてるマインドは、なんとかかんとかです。<br />
   なぜなら、こういう理由でこうしています。<br /><br />
   期待以上のアシストをさせていただけるように努めます。
  </p>
  <div>
   <ul>
    <li>
     <a href="/">
      <img src="/images/works/mock1.svg" alt="リスト" />
     </a>
    </li>
    <li><a href="/">item2</a></li>
    <li><a href="/">item3</a></li>
   </ul>
  </div>
 </div>
</div>

<style lang="scss">
 .wrap {
  max-width: 800px;
  margin: 40px auto 0;
 }
 .inner {
  padding: 24px 40px;
 }
 .description {
  line-height: 1.8;
  color: #666;
 }
</style>
