<script>
    let unlimitedMode = true
    const unlimitedButton = () => {
        unlimitedMode = true
    }
    const limitedButton = () => {
        unlimitedMode = false
    }

    let gameOn = false
    const start = () => {
        gameOn = true
    }

    let nameOfSign = ""

    let num = 0
    let numLatest = 0
    let randomNumGenerator = () => {
        num = Math.floor(Math.random() * trafficSigns.length)
        if(num === numLatest){
            randomNumGenerator()
        }
    }

    const trafficSigns = [
        {
            img: '/trafiklevhaları/levha1d.png',
            name: 'anayoldaki trafiğe yol veriniz'
        },
        {
            img: '/trafiklevhaları/levha2d.png',
            name: 'dur ve yol ver'
        },
        {
            img: '/trafiklevhaları/levha3d.png',
            name: 'karşıdan gelen araçlara yol veriniz'
        },
        {
            img: '/trafiklevhaları/levha4d.png',
            name: 'taşıt giremez'
        },
        {
            img: '/trafiklevhaları/levha5d.png',
            name: 'araçlara kapalı yol'
        },
        {
            img: '/trafiklevhaları/levha6d.png',
            name: 'motosiklet dışındaki motorlu araçlar giremez'
        },
        {
            img: '/trafiklevhaları/levha7d.png',
            name: 'motosiklet giremez'
        },
        {
            img: '/trafiklevhaları/levha8d.png',
            name: 'motobisiklet giremez'
        },
        {
            img: '/trafiklevhaları/levha9d.png',
            name: 'kamyon giremez'
        },
        {
            img: '/trafiklevhaları/levha10d.png',
            name: 'otobüs giremez'
        },
        {
            img: '/trafiklevhaları/levha11d.png',
            name: 'treyler giremez'
        },
        {
            img: '/trafiklevhaları/levha12d.png',
            name: 'traktör giremez'
        },
        {
            img: '/trafiklevhaları/levha13d.png',
            name: 'at arabası giremez'
        },
        {
            img: '/trafiklevhaları/levha14d.png',
            name: 'el arabası giremez'
        },
        {
            img: '/trafiklevhaları/levha15d.png',
            name: 'tehlikeli yük taşıyan araç giremez'
        },
        {
            img: '/trafiklevhaları/levha16d.png',
            name: 'motorlu taşıt giremez'
        },
        {
            img: '/trafiklevhaları/levha17d.png',
            name: 'taşıt giremez'
        },
        {
            img: '/trafiklevhaları/levha18d.png',
            name: 'yaya giremez'
        },
        {
            img: '/trafiklevhaları/levha19d.png',
            name: 'su kirletici madde taşıyan araçlar giremez'
        },
        {
            img: '/trafiklevhaları/levha20d.png',
            name: 'limitten geniş araçlar giremez'
        },
        {
            img: '/trafiklevhaları/levha21d.png',
            name: '10 metreden uzun araç veya katar giremez'
        },
        {
            img: '/trafiklevhaları/levha22d.png',
            name: 'limitten yüksek araçlar giremez'
        },
        {
            img: '/trafiklevhaları/levha23d.png',
            name: 'dingil başına 6 tondan fazla yük düşen taşıt giremez'
        },
        {
            img: '/trafiklevhaları/levha24d.png',
            name: 'yük ağırlığı 7 tondan fazla olan araç giremez'
        },
        {
            img: '/trafiklevhaları/levha25d.png',
            name: 'bisiklet giremez'
        },
        {
            img: '/trafiklevhaları/levha26d.png',
            name: 'öndeki taşıt 70 metreden daha yakın takip edilemez'
        },
        {
            img: '/trafiklevhaları/levha27d.png',
            name: 'sola dönülmez'
        },
        {
            img: '/trafiklevhaları/levha28d.png',
            name: 'sağa dönülmez'
        },
        {
            img: '/trafiklevhaları/levha29d.png',
            name: 'u dönüşü yapılmaz'
        },
        {
            img: '/trafiklevhaları/levha30d.png',
            name: 'taşıt geçilmez'
        },
        {
            img: '/trafiklevhaları/levha31d.png',
            name: 'azami sürat'
        },
        {
            img: '/trafiklevhaları/levha32d.png',
            name: 'sesli ikaz cihazları kullanılmaz'
        },
        {
            img: '/trafiklevhaları/levha33d.png',
            name: 'tüm yasaklama ve kısıtlamaların sonu'
        },
        {
            img: '/trafiklevhaları/levha34d.png',
            name: 'geçme yasağı sonu'
        },
        {
            img: '/trafiklevhaları/levha35d.png',
            name: 'hız sınırlamasının sonu'
        },
        {
            img: '/trafiklevhaları/levha36d.png',
            name: 'sola dönünüz'
        },
        {
            img: '/trafiklevhaları/levha37d.png',
            name: 'sağa dönünüz'
        },
        {
            img: '/trafiklevhaları/levha38d.png',
            name: 'yalnız ileriye gidilir'
        },
        {
            img: '/trafiklevhaları/levha39d.png',
            name: 'aynı yere iki yönden ulaşabilirsiniz'
        },
        {
            img: '/trafiklevhaları/levha40d.png',
            name: 'ilerden sola dönünüz'
        },
        {
            img: '/trafiklevhaları/levha41d.png',
            name: 'ilerden sağa dönünüz'
        },
        {
            img: '/trafiklevhaları/levha42d.png',
            name: 'ileri ve sola zorunlu yol'
        },
        {
            img: '/trafiklevhaları/levha43d.png',
            name: 'ileri ve sağa zorunlu yol'
        },
        {
            img: '/trafiklevhaları/levha44d.png',
            name: 'sağa - sola zorunlu yol'
        },
        {
            img: '/trafiklevhaları/levha45d.png',
            name: 'soldan gidiniz'
        },
        {
            img: '/trafiklevhaları/levha46d.png',
            name: 'sağdan gidiniz'
        },
        {
            img: '/trafiklevhaları/levha47d.png',
            name: 'çember sağdan gelene yol ver'
        },
        {
            img: '/trafiklevhaları/levha48d.png',
            name: 'asgari hız'
        },
        {
            img: '/trafiklevhaları/levha49d.png',
            name: 'asgari hız sınırının sonu'
        },
        {
            img: '/trafiklevhaları/levha50d.png',
            name: 'zorunlu atlı yolu'
        },
        {
            img: '/trafiklevhaları/levha51d.png',
            name: 'zorunlu bisiklet yolu'
        },
        {
            img: '/trafiklevhaları/levha52d.png',
            name: 'zincir takmak zorunludur'
        },
        {
            img: '/trafiklevhaları/levha53d.png',
            name: 'zincir takma mecburiyeti sonu'
        },
        {
            img: '/trafiklevhaları/levha54d.png',
            name: 'zorunlu yaya yolu'
        },
        {
            img: '/trafiklevhaları/levha55d.png',
            name: 'sola viraj'
        },
        {
            img: '/trafiklevhaları/levha56d.png',
            name: 'sağa viraj'
        },
        {
            img: '/trafiklevhaları/levha57d.png',
            name: 'tehlikeli virajlar önce sola'
        },
        {
            img: '/trafiklevhaları/levha58d.png',
            name: 'tehlikeli virajlar önce sağa'
        },
        {
            img: '/trafiklevhaları/levha59d.png',
            name: 'tehlikeli eğim iniş'
        },
        {
            img: '/trafiklevhaları/levha60d.png',
            name: 'tehlikeli eğim çıkış'
        },
        {
            img: '/trafiklevhaları/levha61d.png',
            name: 'iki taraftan daralan yol'
        },
        {
            img: '/trafiklevhaları/levha62d.png',
            name: 'soldan daralan yol'
        },
        {
            img: '/trafiklevhaları/levha63d.png',
            name: 'sağdan daralan yol'
        },
        {
            img: '/trafiklevhaları/levha64d.png',
            name: 'deniz veya nehir kıyısında biten yol'
        },
        {
            img: '/trafiklevhaları/levha65d.png',
            name: 'kasisli yol'
        },
        {
            img: '/trafiklevhaları/levha66d.png',
            name: 'tümsekli yol'
        },
        {
            img: '/trafiklevhaları/levha67d.png',
            name: 'kaygan yol'
        },
        {
            img: '/trafiklevhaları/levha68d.png',
            name: 'gevşek malzemeli zemin'
        },
        {
            img: '/trafiklevhaları/levha69d.png',
            name: 'heyelan tehlikesi'
        },
        {
            img: '/trafiklevhaları/levha70d.png',
            name: 'yaya geçidi'
        },
        {
            img: '/trafiklevhaları/levha71d.png',
            name: 'okul geçidi'
        },
        {
            img: '/trafiklevhaları/levha72d.png',
            name: 'bisiklet geçebilir'
        },
        {
            img: '/trafiklevhaları/levha73d.png',
            name: 'açılan köprü'
        },
        {
            img: '/trafiklevhaları/levha74d.png',
            name: 'ehli hayvanlar geçebilir'
        },
        {
            img: '/trafiklevhaları/levha75d.png',
            name: 'vahşi hayvanlar çıkabilir'
        },
        {
            img: '/trafiklevhaları/levha76d.png',
            name: 'yol tamiratı'
        },
        {
            img: '/trafiklevhaları/levha77d.png',
            name: 'trafik ışıkları'
        },
        {
            img: '/trafiklevhaları/levha78d.png',
            name: 'dikkat tehlike'
        },
        {
            img: '/trafiklevhaları/levha79d.png',
            name: 'ileride iki yönlü trafik'
        },
        {
            img: '/trafiklevhaları/levha80d.png',
            name: 'dörtyol kavşağı'
        },
        {
            img: '/trafiklevhaları/levha81d.png',
            name: 'anayol ve taliyol kavşağı'
        },
        {
            img: '/trafiklevhaları/levha82d.png',
            name: 'anayol taliyol kavşağı - sağ'
        },
        {
            img: '/trafiklevhaları/levha83d.png',
            name: 'anayol taliyol kavşağı - sol'
        },
        {
            img: '/trafiklevhaları/levha84d.png',
            name: 'yandan rüzgar'
        },
        {
            img: '/trafiklevhaları/levha85d.png',
            name: 'soldan anayola giriş'
        },
        {
            img: '/trafiklevhaları/levha86d.png',
            name: 'sağdan anayola giriş'
        },
        {
            img: '/trafiklevhaları/levha87d.png',
            name: 'dönel kavşak raundabout'
        },
        {
            img: '/trafiklevhaları/levha88d.png',
            name: 'alçaktan uçan uçak'
        },
        {
            img: '/trafiklevhaları/levha89d.png',
            name: 'kavşak veya geçide 100 metre sol'
        },
        {
            img: '/trafiklevhaları/levha90d.png',
            name: 'kavşak veya geçide 200 metre sol'
        },
        {
            img: '/trafiklevhaları/levha91d.png',
            name: 'kavşak veya geçide 300 metre sol'
        },
        {
            img: '/trafiklevhaları/levha92d.png',
            name: 'kavşak veya geçide 300 metre sağ'
        },
        {
            img: '/trafiklevhaları/levha93d.png',
            name: 'kavşak veya geçide 200 metre sağ'
        },
        {
            img: '/trafiklevhaları/levha94d.png',
            name: 'kavşak veya geçide 100 metre sağ'
        },
        {
            img: '/trafiklevhaları/levha95d.png',
            name: 'engel'
        },
        {
            img: '/trafiklevhaları/levha96d.png',
            name: 'refüj başı ek levhası'
        },
        {
            img: '/trafiklevhaları/levha97d.png',
            name: 'dönüş adası ek levhası'
        },
        {
            img: '/trafiklevhaları/levha98d.png',
            name: 'tünel'
        },
        {
            img: '/trafiklevhaları/levha99d.png',
            name: 'kontrollü demir yolu geçidi'
        },
        {
            img: '/trafiklevhaları/levha100d.png',
            name: 'kontrolsüz demir yolu geçidi'
        },
        {
            img: '/trafiklevhaları/levha101d.png',
            name: 'sağ köprü yaklaşım levhası'
        },
        {
            img: '/trafiklevhaları/levha102d.png',
            name: 'sol köprü yaklaşım levhası'
        },
        {
            img: '/trafiklevhaları/levha103d.png',
            name: 'kontrolsüz demir yolu geçidi (tek hat)'
        },
        {
            img: '/trafiklevhaları/levha104d.png',
            name: 'kontrolsüz demir yolu geçidi (en az 2 hat)'
        },
        {
            img: '/trafiklevhaları/levha105d.png',
            name: 'sola tehlikeli viraj'
        },
        {
            img: '/trafiklevhaları/levha106d.png',
            name: 'sağa tehlikeli viraj'
        },
        {
            img: '/trafiklevhaları/levha107d.png',
            name: 'çıkışı olmayan yol'
        },
        {
            img: '/trafiklevhaları/levha108d.png',
            name: 'çıkışı olmayan yol'
        },
        {
            img: '/trafiklevhaları/levha109d.png',
            name: 'çıkışı olmayan yol'
        },
        {
            img: '/trafiklevhaları/levha110d.png',
            name: 'çıkışı olmayan yol'
        },
        {
            img: '/trafiklevhaları/levha111d.png',
            name: 'kavşak öncesi şerit seçim levhası'
        },
        {
            img: '/trafiklevhaları/levha112d.png',
            name: 'kavşak içi yön levhası (havaalanı)'
        },
        {
            img: '/trafiklevhaları/levha113d.png',
            name: 'kavşak içi yön levhası (kamp yeri)'
        },
        {
            img: '/trafiklevhaları/levha114d.png',
            name: 'okul geçidi'
        },
        {
            img: '/trafiklevhaları/levha115d.jpg',
            name: 'yaya geçidi'
        },
        {
            img: '/trafiklevhaları/levha116d.png',
            name: 'hastane'
        },
        {
            img: '/trafiklevhaları/levha117d.png',
            name: 'motorlu taşıt yolu başlangıcı'
        },
        {
            img: '/trafiklevhaları/levha118d.png',
            name: 'motorlu taşıt yolu sonu'
        },
        {
            img: '/trafiklevhaları/levha119d.png',
            name: 'tamirhane'
        },
        {
            img: '/trafiklevhaları/levha120d.png',
            name: 'telefon'
        },
        {
            img: '/trafiklevhaları/levha121d.png',
            name: 'akaryakıt istasyonu'
        },
        {
            img: '/trafiklevhaları/levha122d.png',
            name: 'lokanta'
        },
        {
            img: '/trafiklevhaları/levha123d.png',
            name: 'otel'
        },
        {
            img: '/trafiklevhaları/levha124d.png',
            name: 'piknik yeri'
        },
        {
            img: '/trafiklevhaları/levha125d.png',
            name: 'kamp yeri'
        },
        {
            img: '/trafiklevhaları/levha126d.png',
            name: 'çadırlı ve karavanlı park yeri'
        },
        {
            img: '/trafiklevhaları/levha127d.png',
            name: 'karavanlı kamp yeri'
        },
        {
            img: '/trafiklevhaları/levha128d.png',
            name: 'çeşme'
        },
        {
            img: '/trafiklevhaları/levha129d.png',
            name: 'ilk yardım'
        },
        {
            img: '/trafiklevhaları/levha130d.png',
            name: 'öncelik olan yol'
        },
        {
            img: '/trafiklevhaları/levha131d.png',
            name: 'yangın tehlikesi'
        },
        {
            img: '/trafiklevhaları/levha132d.png',
            name: 'çayhane veya kafeterya'
        },
        {
            img: '/trafiklevhaları/levha133d.png',
            name: 'anayol başlangıcı (öncelikli yol hakkına sahip yol)'
        },
        {
            img: '/trafiklevhaları/levha134d.png',
            name: 'anayol bitimi'
        },
        {
            img: '/trafiklevhaları/levha135d.png',
            name: 'kavşak kutusu (üzerinde park yapılmaz ve durulmaz)'
        },
        {
            img: '/trafiklevhaları/levha136d.png',
            name: 'ileride kavşak kutusu var'
        },
        {
            img: '/trafiklevhaları/levha137d.png',
            name: 'tek yönlü yol levhası'
        },
        {
            img: '/trafiklevhaları/levha138d.png',
            name: 'park etmek yasaktır'
        },
        {
            img: '/trafiklevhaları/levha139d.png',
            name: 'duraklama ve park etmek yasaktır'
        },
        {
            img: '/trafiklevhaları/levha140d.png',
            name: 'haftanın tek günlerinde park etmek yasaktır'
        },
        {
            img: '/trafiklevhaları/levha141d.png',
            name: 'haftanın çift günlerinde park etmek yasaktır'
        },
        {
            img: '/trafiklevhaları/levha142d.png',
            name: 'park yeri'
        },
        {
            img: '/trafiklevhaları/levha143d.png',
            name: 'sınırlı süreli park yeri'
        },
        {
            img: '/trafiklevhaları/levha144d.png',
            name: 'sınırlı süreli park bölgesi sonu'
        },
        {
            img: '/trafiklevhaları/levha145d.png',
            name: 'otoyol başlangıcı'
        },
        {
            img: '/trafiklevhaları/levha146d.png',
            name: 'otoyol sonu'
        },
        {
            img: '/trafiklevhaları/levha147d.jpeg',
            name: 'otoyol çıkış yaklaşım levhaları'
        },
        {
            img: '/trafiklevhaları/levha148d.png',
            name: 'otoyol bilgi işaretleri (kaplama üstü yön levhası)'
        },
        {
            img: '/trafiklevhaları/levha149d.png',
            name: 'otoyol şerit kapatma levhası'
        },
        {
            img: '/trafiklevhaları/levha150d.png',
            name: 'durak'
        },
        {
            img: '/trafiklevhaları/levha151d.png',
            name: 'gençlik kampı'
        },
        {
            img: '/trafiklevhaları/levha152d.png',
            name: 'meskün mahal (köy başlangıcı)'
        },
        {
            img: '/trafiklevhaları/levha153d.png',
            name: 'meskün mahal (köy sonu)'
        },
        {
            img: '/trafiklevhaları/levha154d.png',
            name: 'kamyonlar vasıta geçemez'
        },
        {
            img: '/trafiklevhaları/levha155d.png',
            name: 'gümrük durmadan geçilmez'
        },
        {
            img: '/trafiklevhaları/levha156d.png',
            name: 'park yapılmaz'
        },
        {
            img: '/trafiklevhaları/levha157d.png',
            name: 'şehir ve varoşlarına ait otobüs durağı'
        },
        {
            img: '/trafiklevhaları/levha158d.png',
            name: 'tümsekli köprü'
        },
        {
            img: '/trafiklevhaları/levha159d.png',
            name: 'kavşak öncesi yön levhası'
        },
        {
            img: '/trafiklevhaları/levha160d.png',
            name: 'kavşak içi yön levhası (turistik)'
        },
        {
            img: '/trafiklevhaları/levha161d.png',
            name: 'mesafe levhası'
        },
        {
            img: '/trafiklevhaları/levha162d.png',
            name: 'meskun mahal (yerleşim bölgesi levhası)'
        },
        {
            img: '/trafiklevhaları/levha163d.png',
            name: 'kktc devlet sınırı levhası'
        },
        {
            img: '/trafiklevhaları/levha164d.png',
            name: 'yüzme yeri'
        },
        {
            img: '/trafiklevhaları/levha165d.png',
            name: 'yüzülmez'
        },
        {
            img: '/trafiklevhaları/levha166d.png',
            name: 'polis'
        },
        {
            img: '/trafiklevhaları/levha167d.png',
            name: 'şerit kullanım levhası (tırmanma şeridi)'
        },
        {
            img: '/trafiklevhaları/levha168d.png',
            name: 'şerit kullanım levhası (yol kenarı)'
        },
        {
            img: '/trafiklevhaları/levha169d.png',
            name: 'bölünmüş yol öncesi yol levhası'
        },
        {
            img: '/trafiklevhaları/levha170d.png',
            name: 'soldan sürünüz'
        },
        {
            img: '/trafiklevhaları/levha171d.jpg',
            name: 'yaya geçidi'
        }
    ]

    randomNumGenerator()
    let questionNumber = 1
    let correctCounter = 0
    let wrongCounter = 0

    let userWantsToSeeWrongies = false

    const userWantsToSeeWrongiesFunc = () => {
        userWantsToSeeWrongies = true
    }

    const wrongQuestionsTexts = []
    const wrongQuestionsImg = []
    let matchedArray

    const checkFunction = () => {
        if(nameOfSign.toLowerCase() === trafficSigns[num].name){
            correctCounter++
        } else {
            wrongCounter++
            wrongQuestionsTexts.push(trafficSigns[num].name)
            wrongQuestionsImg.push(trafficSigns[num].img)
            matchedArray = wrongQuestionsImg.map((item, index) => ({textPart: wrongQuestionsTexts[index], imgPart: item}))
        }
        nameOfSign = ""
        questionNumber++
        numLatest = num
        randomNumGenerator()
    }

    const scoreColor = () => {
        if((correctCounter / 15).toFixed(1) <= 0.4){
            return "text-[red]"
        } else if((correctCounter / 15).toFixed(1) > 0.4 && (correctCounter / 15).toFixed(1) <= 0.7){
            return "text-[yellow]"
        } else {
            return "text-[green]"
        }
    }

</script>
{#if !gameOn}
<section class="mt-10">
    <h1 class="text-center text-2xl font-bold md:text-3xl">Trafik Levhası Pratiği <i class="fa-solid fa-traffic-light text-[#d4ce24]"></i></h1>
    <p class="text-center mt-2 text-[#999] md:text-lg">Ekranda çıkan trafik levhasının ne anlama geldiğini bilmeye çalış <br> Lütfen soruları cevaplarken harf hatası yapmamaya dikkat ediniz</p>
    <h2 class="text-center mt-5 text-xl">Soru Sayısı:</h2>
    <div class="flex justify-center items-center mt-4">
        <button class="p-3 bg-[#333] rounded mr-2 ring-[#d4ce24] {!unlimitedMode ? 'ring-1' : ''}" on:click={limitedButton}>15 soru</button>
        <button class="p-3 bg-[#333] rounded ml-2 ring-[#d4ce24] {unlimitedMode ? 'ring-1' : ''}" on:click={unlimitedButton}>sınırsız</button>
    </div>
    <div class="text-center mt-5">
        <button class="bg-[#333] w-[170px] py-3 rounded bg-[#d4ce24] font-black" on:click={start}>Başlat</button>
    </div>
</section>
{:else}
    {#if unlimitedMode}
        <section class="mx-auto mt-10 w-72">
            <h2 class="text-[#999] font-black text-2xl ml-4 mb-2">Soru {questionNumber}</h2>
            <div class="bg-[#333] p-4 rounded w-64 flex items-center justify-center mx-auto">
                <img src={trafficSigns[num].img} alt="trafik levhası" width="200">
            </div>
            <div class="text-center">
                <form on:submit={checkFunction}>
                    <input type="search" list="possibleOptions" placeholder="trafik levhasını giriniz" class="bg-[#333] mt-5 py-2 pl-2 w-64 text-[#999] rounded" bind:value={nameOfSign} autofocus>
                    <datalist id="possibleOptions">
                        {#each trafficSigns as { name }}
                          <option value={name}>
                        {/each}
                    </datalist>
                </form>
                <button class="mt-5 bg-[#d4ce24] font-bold w-64 rounded py-2" on:click={checkFunction}>Onayla</button>
            </div>
            <div class="text-center flex justify-center mt-5">
                <div class="bg-[#333] py-2 w-[127px] rounded mr-0.5 flex items-center justify-center"><i class="fa-solid fa-square-check text-xl mr-2 text-[#47ed4f]"></i><span class="text-xl text-[#999]">{correctCounter}</span></div>
                <div class="bg-[#333] py-2 w-[127px] rounded ml-0.5 flex items-center justify-center"><i class="fa-solid fa-square-xmark text-xl mr-2 text-[#fc4949]"></i><span class="text-xl text-[#999]">{wrongCounter}</span></div>
            </div>
        </section>
    {:else}
        {#if questionNumber <= 15}
        <section class="mx-auto mt-10 w-72">
            <h2 class="text-[#999] font-black text-2xl ml-4 mb-2">Soru {questionNumber}</h2>
            <div class="bg-[#333] p-4 rounded w-64 flex items-center justify-center mx-auto">
                <img src={trafficSigns[num].img} alt="trafik levhası" width="200">
            </div>
            <div class="text-center">
                <form on:submit={checkFunction}>
                    <input type="search" list="possibleOptions" placeholder="trafik levhasını giriniz" class="bg-[#333] mt-5 py-2 pl-2 w-64 text-[#999] rounded" bind:value={nameOfSign} autofocus>
                    <datalist id="possibleOptions">
                        {#each trafficSigns as { name }}
                          <option value={name}>
                        {/each}
                    </datalist>
                </form>
                <button class="mt-5 bg-[#d4ce24] font-bold w-64 rounded py-2" on:click={checkFunction}>Onayla</button>
            </div>
            <div class="text-center flex justify-center mt-5">
                <div class="bg-[#333] py-2 w-[127px] rounded mr-0.5 flex items-center justify-center"><i class="fa-solid fa-square-check text-xl mr-2 text-[#47ed4f]"></i><span class="text-xl text-[#999]">{correctCounter}</span></div>
                <div class="bg-[#333] py-2 w-[127px] rounded ml-0.5 flex items-center justify-center"><i class="fa-solid fa-square-xmark text-xl mr-2 text-[#fc4949]"></i><span class="text-xl text-[#999]">{wrongCounter}</span></div>
            </div>
        </section>
        {:else}
            {#if !userWantsToSeeWrongies}
                <section class="bg-[#333] text-center mt-10 w-72 md:w-96 mx-auto py-6 md:py-8 rounded">
                    <h2 class="text-2xl py-2 px-1 bg-[#444] w-52 mx-auto rounded font-black">Bölüm Analizi</h2>
                    <p class="mt-5 mb-0.5 text-xl">Doğru sayısı: {correctCounter}</p>
                    <p class="text-xl">Yanlış sayısı: {wrongCounter}</p>
                    <p class="text-xl font-black mt-5" title="0 ile 1 arasında başarı değerlendirmesi">Skor: <span class="{scoreColor()}">{(correctCounter / 15).toFixed(1)}</span></p>
                    <button class="text-lg w-52 mt-5 mx-auto py-2 rounded bg-[tomato]" on:click={userWantsToSeeWrongiesFunc}>yanlışları görüntüle</button>
                    <a href="/"><button class="text-lg w-52 mt-2 mx-auto py-2 rounded bg-[green]">çıkış yap ...<i class="fa-solid fa-person-running"></i></button></a>
                </section>
            {:else}
            <section class="bg-[#333] text-center mt-10 w-72 md:w-96 mx-auto py-6 md:py-8 rounded mb-10">
                <h2 class="text-xl font-black text-[#999] mb-6 bg-[#444] py-4">Yanlış yapılan levhalar ve doğruları</h2>
                    {#each matchedArray as {imgPart, textPart}, index}
                        <div class="flex flex-col items-center mb-8">
                            <h3 class="font-black">{index + 1}</h3>
                            <img src="{imgPart}" alt="{textPart}" width="200">
                            <p class="text-[#999]">{textPart}</p>
                        </div>
                    {/each}
                    <a href="/"><button class="text-lg w-52 mt-2 mx-auto py-2 rounded bg-[green]">çıkış yap ...<i class="fa-solid fa-person-running"></i></button></a>
            </section>
            {/if}
        {/if}
    {/if}
{/if}