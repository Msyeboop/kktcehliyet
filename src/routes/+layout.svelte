<script>
  import "../app.postcss";
</script>

<header class="bg-[#333] py-5">
  <h1 class="pl-3 md:pl-10 font-black text-2xl"><a href="/">kktcehliyet</a></h1>
</header>
<slot />
<footer class="bg-[#333] py-5 flex justify-between mt-auto text-[#888] md:text-lg">
  <div class="pl-3 md:pl-10"><p>kktcehliyet&copy;2023</p></div>
  <div class="pr-3 md:pr-10">
    <a href="/about">hakkında</a>
    <a href="http://tkodkk.org/index.php/kktctrafiklevhalari" target="_blank" class="ml-1 md:ml-3">kaynakça</a>
  </div>
</footer>