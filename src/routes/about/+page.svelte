<svelte:head>
    <script id="ratufa_loader" src="https://www.ratufa.io/c/ld.js?f=g3va6l3m&n=n1.ratufa.io" defer></script>
</svelte:head>
<h1 class="text-center mt-10 text-xl px-4 text-[#999] font-bold">KKTC'de kullanılan trafik levhalarını hızlı bir şekilde </h1>
<div class="flex flex-col md:flex-row items-center justify-center mt-5 text-center">
    <span class="bg-[#B81B0E] w-24 py-2 bg-[#333] rounded font-bold">öğren </span>
    <span class="bg-[#F7B500] w-24 py-2 bg-[#333] rounded my-2 md:mx-2 font-bold">pratik yap </span>
    <span class="bg-[#549C30] w-24 py-2 bg-[#333] rounded font-bold">sınavı kazan</span>
</div>

<section class="flex flex-col items-center justify-center bg-[#333] py-6 w-80 mx-auto my-10 md:w-[420px]">
    <p class="text-xl text-[#999] mb-5 font-bold">Sorunuz ya da tavsiyeniz mi var?</p>
    <form>
        <div class="flex flex-col">
            <label for="name" class="font-bold">isim</label>
            <input type="text" name="name" placeholder="isminiz..." class="py-2 px-1.5 bg-[#222] rounded">
        </div>
        <div class="flex flex-col my-4">
            <label for="name" class="font-bold">e-mail</label>
            <input type="text" name="email" placeholder="e-mailiniz..." class="py-2 px-1.5 bg-[#222] rounded">
        </div>
        <div class="flex flex-col">
            <label for="message" class="font-bold">mesaj</label>
            <textarea type="text" name="message" placeholder="mesajınız..." class="h-32 w-64 py-2 px-1.5 bg-[#222] rounded"></textarea>
        </div>
        <button type="submit" class="bg-[#549c30] py-2 w-64 rounded mt-10">Gönder</button>
    </form>
</section>