<template>
  <div>
    <!-- HEADER -->
    <header class="flex justify-between items-center px-4 sm:px-8 lg:px-16 py-3 bg-white shadow-sm  top-0 z-50">
      <div>
        <img class="w-[130px] h-[65px] sm:w-[160px] sm:h-[80px] lg:w-[200px] lg:h-[100px] object-contain"
          src="./assets/images/Logo.png"
          alt="logo">
      </div>

      <!-- Desktop Nav -->
      <nav class="hidden md:flex items-center gap-6 lg:gap-10 font-bold">
        <a href="#sec1" class="transition-all duration-500 text-[15px] hover:text-yellow-500 cursor-pointer">Asosiy sahifa</a>
        <a href="#sec4" class="transition-all duration-500 text-[15px] hover:text-yellow-500">Biz haqimizda</a>
        <a href="#sec5" class="transition-all duration-500 text-[15px] hover:text-yellow-500">Turlar</a>
        <a href="#sec10" class="transition-all duration-500 text-[15px] hover:text-yellow-500">Kontaktlar</a>
      </nav>

      <!-- Mobile Hamburger -->
      <button @click="menuOpen = !menuOpen" class="md:hidden flex flex-col gap-1.5 p-2">
        <span :class="['block w-6 h-0.5 bg-gray-800 transition-all duration-300', menuOpen ? 'rotate-45 translate-y-2' : '']"></span>
        <span :class="['block w-6 h-0.5 bg-gray-800 transition-all duration-300', menuOpen ? 'opacity-0' : '']"></span>
        <span :class="['block w-6 h-0.5 bg-gray-800 transition-all duration-300', menuOpen ? '-rotate-45 -translate-y-2' : '']"></span>
      </button>
    </header>

    <!-- Mobile Menu -->
    <div v-if="menuOpen" class="md:hidden bg-white shadow-lg px-6 py-4 flex flex-col gap-4 font-bold z-40">
      <a href="#sec1" class="transition-all duration-500 text-[15px] hover:text-yellow-500" @click="menuOpen=false">Asosiy sahifa</a>
      <a href="" id="sec4" class="transition-all duration-500 text-[15px] hover:text-yellow-500" @click="menuOpen=false">Biz haqimizda</a>
      <a href="" id="sec5" class="transition-all duration-500 text-[15px] hover:text-yellow-500" @click="menuOpen=false">Turlar</a>
      <a href="" id="sec4" class="transition-all duration-500 text-[15px] hover:text-yellow-500" @click="menuOpen=false">Kontaktlar</a>
    </div>

    <!-- SECTION 1 - HERO -->
    <section id="sec1">
      <div id="background"
        class=" relative flex flex-col justify-center items-start min-h-[500px] sm:min-h-[580px] lg:h-[630px] w-full text-white px-4 sm:px-10 lg:px-[150px] xl:px-[300px]">
        <div class="absolute inset-0 bg-black/10"></div>
        <div class="relative z-10 w-full mt-8 sm:mt-16 lg:mt-[100px]">
          <div class="w-[80px] sm:w-[100px] h-[5px] bg-amber-500 mt-[55px] mb-[10px]"></div>
          <h1 class="text-2xl sm:text-3xl lg:text-4xl font-semibold mb-4 max-w-xl">Sayohat qilishni xohlaysizmi?</h1>
          <p class="text-sm sm:text-base lg:text-lg max-w-[600px] mb-6">
            Sayohat orzularingizni haqiqatga aylantiring: rejalashtiring, kashf qiling va unutilmas xotiralar yarating.
          </p>
          <button class="bg-amber-400 text-white font-semibold px-5 py-2.5 sm:px-6 sm:py-3 rounded-[5px] hover:bg-amber-600 text-sm sm:text-base" @click="scrollToSection('sec5')">
            Ko'proq bilish
          </button>

          <!-- Booking Form -->
          <div class=" mb-[0px] mt-[200px]">
            <div class="mt-8 sm:mt-12  lg:mt-16 w-full max-w-[1000px] bg-white text-gray-500 border-b-[5px] border-b-amber-500 p-3 sm:p-4">
            <div class="flex flex-col sm:flex-row gap-2 sm:gap-3 items-stretch sm:items-center flex-wrap">
              <input type="text" placeholder="Ismingiz..."
                class="flex-1 min-w-0 p-2.5 border rounded outline-none placeholder-gray-500 text-gray-800 text-sm" />
              <input type="text" placeholder="Manzilingiz..."
                class="flex-1 min-w-0 p-2.5 border rounded outline-none placeholder-gray-500 text-gray-800 text-sm" />
              <input type="date"
                class="flex-1 min-w-0 p-2.5 border rounded outline-none text-gray-500 text-sm" />
              <button
                class="bg-[#e1ac0c] text-white px-4 py-2.5 rounded hover:bg-[#c8960a] transition-all cursor-pointer text-sm whitespace-nowrap">
                Joy Band Qilish
              </button>
            </div>
          </div>
          </div>
        </div>
      </div>
    </section>

    <!-- SECTION 2 - DESTINATIONS GRID -->
    <section class="px-4 sm:px-8 lg:px-16 my-12 sm:my-16 lg:my-[100px]">
      <h6 class="text-center text-yellow-400 mb-4 text-sm sm:text-base">bizning mashhur manzilimiz</h6>
      <h4 class="text-center text-[17px] sm:text-[20px] lg:text-[25px] font-semibold mb-8 max-w-3xl mx-auto leading-snug">
        Ushbu yo'nalishlar bilan haqiqatan ham o'ziga xos qiladigan go'zallik, madaniyat va tajribalarni kashf eting.
      </h4>
      <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-3 sm:gap-4 lg:gap-[30px]">
        <div id="istanbul" class="h-[160px] sm:h-[190px] lg:h-[210px] rounded-[5px] flex flex-col justify-end p-3 sm:p-5 bg-cover bg-center">
          <h1 class="text-[16px] sm:text-[18px] lg:text-[20px] text-white font-semibold">Istanbul</h1>
          <p class="text-white text-xs sm:text-sm">76 band qilingan</p>
        </div>
        <div id="sharm" class="h-[160px] sm:h-[190px] lg:h-[210px] rounded-[5px] flex flex-col justify-end p-3 sm:p-5 bg-cover bg-center">
          <h1 class="text-[16px] sm:text-[18px] lg:text-[20px] text-white font-semibold">Sharm</h1>
          <p class="text-white text-xs sm:text-sm">76 band qilingan</p>
        </div>
        <div id="tailand" class="h-[160px] sm:h-[190px] lg:h-[210px] rounded-[5px] flex flex-col justify-end p-3 sm:p-5 bg-cover bg-center">
          <h1 class="text-[16px] sm:text-[18px] lg:text-[20px] text-white font-semibold">Tailand</h1>
          <p class="text-white text-xs sm:text-sm">76 band qilingan</p>
        </div>
        <div id="argentina" class="h-[160px] sm:h-[190px] lg:h-[210px] rounded-[5px] flex flex-col justify-end p-3 sm:p-5 bg-cover bg-center">
          <h1 class="text-[16px] sm:text-[18px] lg:text-[20px] text-white font-semibold">Argentina</h1>
          <p class="text-white text-xs sm:text-sm">76 band qilingan</p>
        </div>
        <div id="dubai" class="h-[160px] sm:h-[190px] lg:h-[210px] rounded-[5px] col-span-2 sm:col-span-1 flex flex-col justify-end p-3 sm:p-5 bg-cover bg-center">
          <h1 class="text-[16px] sm:text-[18px] lg:text-[20px] text-white font-semibold">Dubai</h1>
          <p class="text-white text-xs sm:text-sm">76 band qilingan</p>
        </div>
      </div>
    </section>

    <!-- SECTION 3 - EXPLORE DESTINATIONS -->
    <section class="px-4 sm:px-8 lg:px-[10%]">
    <div class="w-full pt-[20px]">
      <h1 class="text-[22px] sm:text-[28px] lg:text-[30px] font-semibold mb-6">Maqsadlarni osongina o'rganing</h1>
    </div>

    <div class="mt-6 flex flex-col sm:flex-row gap-4 sm:gap-6 lg:gap-[35px] items-start pb-6 border-b border-gray-100">
      <img src="./assets/images/train.png" alt="Biz bilan arzon temir yo'l chiptalari"
        class="w-full sm:w-[220px] lg:w-[294px] h-[200px] sm:h-[170px] lg:h-[200px] object-cover rounded-[20px] flex-shrink-0">
      <div class="flex-1">
        <h1 class="text-[20px] sm:text-[24px] lg:text-[30px] font-semibold leading-tight">Biz bilan arzon temir yo'l chiptalari</h1>
        <p class="text-[13px] sm:text-[14px] text-gray-500 mt-1">Butun dunyo</p>
        <p class="text-[12px] sm:text-[13px] leading-[22px] sm:leading-[24px] text-gray-400 mt-2 text-justify">
          Temir yo'l sarguzashtiga kiring va kashf qiling dunyo bo'ylab yo'nalishlar. Bu go'zal bo'ladimi landshaftlar, gavjum shaharlar yoki madaniy toshlar, bizning temir yo'l xizmatlari noyob va qulay yo'lni taklif qiladi yer sharini aylanib o'tish. Go'zallikka sho'ng'ing turli madaniyatlar, barcha bizning orqali kirish mumkin keng temir yo'l tarmog'i...
        </p>
      </div>
    </div>

    <div class="mt-6 flex flex-col sm:flex-row gap-4 sm:gap-6 lg:gap-[35px] items-start pb-6 border-b border-gray-100">
      <img src="./assets/images/plane.png" alt="Havo sayohatlari uchun qiziqarli takliflarni kashf eting"
        class="w-full sm:w-[220px] lg:w-[294px] h-[200px] sm:h-[170px] lg:h-[200px] object-cover rounded-[20px] flex-shrink-0">
      <div class="flex-1">
        <h1 class="text-[20px] sm:text-[24px] lg:text-[30px] font-semibold leading-tight">Havo sayohatlari uchun qiziqarli takliflarni kashf eting</h1>
        <p class="text-[13px] sm:text-[14px] text-gray-500 mt-1">Global manzillar</p>
        <p class="text-[12px] sm:text-[13px] leading-[22px] sm:leading-[24px] text-gray-400 mt-2 text-justify">
          Havodagi sarguzashtga boring va kashf qiling dunyo bo'ylab yo'nalishlar. Bu bo'ladimi hayajonli landshaftlar, jonli shaharlar yoki madaniy xazinolar, bizning aviakompaniya xizmatlari qulaylikni ta'minlaydi va dunyo bo'ylab sayohat qilishning ajoyib usuli. Suvga cho'ming o'zingizni turli madaniyatlar boyligida, barcha bizning keng qamrovli havo sayohatimiz orqali osongina kirish mumkin tarmoq...
        </p>
      </div>
    </div>

    <div class="mt-6 flex flex-col sm:flex-row gap-4 sm:gap-6 lg:gap-[35px] items-start pb-6 border-b border-gray-100">
      <img src="./assets/images/dubai2.png" alt="Dubay"
        class="w-full sm:w-[220px] lg:w-[294px] h-[200px] sm:h-[170px] lg:h-[200px] object-cover rounded-[20px] flex-shrink-0">
      <div class="flex-1">
        <h1 class="text-[20px] sm:text-[24px] lg:text-[30px] font-semibold leading-tight">Dubay</h1>
        <p class="text-[13px] sm:text-[14px] text-gray-500 mt-1">Birlashgan Arab Amirliklari</p>
        <p class="text-[12px] sm:text-[13px] leading-[22px] sm:leading-[24px] text-gray-400 mt-2 text-justify">
          Dubay — Birlashgan Arabistondagi shahar va amirlik. Hashamatli xaridlari bilan mashhur Emirates zamonaviy arxitektura va jonli tungi hayot. 830 metr balandlikdagi Burj Xalifa minorasi hukmronlik qiladi shaharning osmono'par binolari. Uning bazasida Dubay joylashgan favvoralar va chiroqlar moslashtirilgan favvoralarga musiqa. Dengizdagi sun'iy orollarda Atlantis, Palm, mehmonxona, suv parki va dengiz hayvonlari parki.
        </p>
      </div>
    </div>

    <div class="mt-6 flex flex-col sm:flex-row gap-4 sm:gap-6 lg:gap-[35px] items-start pb-6 border-b border-gray-100">
      <img src="./assets/images/antalya.png" alt="Antalya"
        class="w-full sm:w-[220px] lg:w-[294px] h-[200px] sm:h-[170px] lg:h-[200px] object-cover rounded-[20px] flex-shrink-0">
      <div class="flex-1">
        <h1 class="text-[20px] sm:text-[24px] lg:text-[30px] font-semibold leading-tight">Antalya</h1>
        <p class="text-[13px] sm:text-[14px] text-gray-500 mt-1">Turkiya</p>
        <p class="text-[12px] sm:text-[13px] leading-[22px] sm:leading-[24px] text-gray-400 mt-2 text-justify">
          Antalya Turkiyaning eng tez rivojlanayotgan shahri va butun dunyodan sayyohlar uni kashf qilmoqdalar ajoyib plyajlarning ajoyib kombinatsiyasi va an'anaviy turk madaniyati. Bolalar yaxshi ko'radilar Beach Park, Aqualand uyi (rollercoaster sevgilining orzusi) va Dolphinarium (uy delfinlar, dengiz sherlari va oq kitlar). Ishonch hosil qiling eski shahar markazini o'rganing va Hadrian darvozasini ko'ring.
        </p>
      </div>
    </div>

    <div class="mt-6 flex flex-col sm:flex-row gap-4 sm:gap-6 lg:gap-[35px] items-start pb-6 border-b border-gray-100">
      <img src="./assets/images/sharm.png" alt="Sharm al-Shayx"
        class="w-full sm:w-[220px] lg:w-[294px] h-[200px] sm:h-[170px] lg:h-[200px] object-cover rounded-[20px] flex-shrink-0">
      <div class="flex-1">
        <h1 class="text-[20px] sm:text-[24px] lg:text-[30px] font-semibold leading-tight">Sharm al-Shayx</h1>
        <p class="text-[13px] sm:text-[14px] text-gray-500 mt-1">Misr</p>
        <p class="text-[12px] sm:text-[13px] leading-[22px] sm:leading-[24px] text-gray-400 mt-2 text-justify">
          Sharm al-Shayx - Sinaydagi turizm markazi Yarim orol va eng yaxshi sho'ng'in uchun uy dunyo. Ayniqsa, Rasning suv osti mo'jizalari Sharmni olib ketgan Muhammad milliy bog'i butunlay yangi daraja. Shaharda sho'ng'in joylari va havaskor g'avvoslarni jalb qiladigan kema halokatlari noyob kashf qilish uchun butun dunyodan Qizil dengiz tubidagi dengiz hayoti.
        </p>
      </div>
    </div>

    <div class="mt-6 flex flex-col sm:flex-row gap-4 sm:gap-6 lg:gap-[35px] items-start pb-6 last:border-0">
      <img src="./assets/images/istanbul2.png" alt="Istanbul"
        class="w-full sm:w-[220px] lg:w-[294px] h-[200px] sm:h-[170px] lg:h-[200px] object-cover rounded-[20px] flex-shrink-0">
      <div class="flex-1">
        <h1 class="text-[20px] sm:text-[24px] lg:text-[30px] font-semibold leading-tight">Istanbul</h1>
        <p class="text-[13px] sm:text-[14px] text-gray-500 mt-1">Turkiya</p>
        <p class="text-[12px] sm:text-[13px] leading-[22px] sm:leading-[24px] text-gray-400 mt-2 text-justify">
          Istanbul Turkiya va uning aholi eng gavjum shahar madaniy, iqtisodiy va tarixiy markaz. Joylashgan tomonidan bo'lingan Turkiyaning shimoli-g'arbiy qismida Bosfor bo'g'ozi Yevropa va Osiyo tomonlariga, qaysi Marmara va Qora dengizni bog'laydi. Bu shahar dunyodagi yagona shahar ikki qit'ada joylashgan.
        </p>
      </div>
    </div>
  </section>

    <!-- SECTION 4 - CARDS -->
    <section id="sec4" class=" pt-[60px] sm:pt-[80px]">
      <div class="w-full bg-[#f4f4f4] pt-[60px] sm:pt-[80px] pb-[60px] sm:pb-[80px] px-4 sm:px-8 lg:px-[10%]">
        <div class="text-center mb-8 sm:mb-10">
          <h6 class="text-yellow-400 mb-3 text-sm sm:text-base">Bizning manzillarimizni kashf eting</h6>
          <h4 class="text-[18px] sm:text-[22px] lg:text-[25px] font-semibold max-w-2xl mx-auto">
            Dubay, Turkiya, Sharm El Sheyhni biz bilan kashf eting
          </h4>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 justify-items-center">
          <!-- Card 1 -->
          <div class="w-full max-w-[360px] bg-white shadow-lg overflow-hidden rounded-lg">
            <div id="dubay_hashamati" class="w-full h-[200px] flex items-start p-2 bg-cover bg-center">
              <div class="flex gap-0.5">
                <svg v-for="n in 5" :key="n" width="18" height="18" viewBox="0 0 24 24" class="text-white">
                  <path fill="currentColor" d="M12,17.27L18.18,21L16.54,13.97L22,9.24L14.81,8.62L12,2L9.19,8.62L2,9.24L7.45,13.97L5.82,21L12,17.27Z"/>
                </svg>
              </div>
            </div>
            <div class="p-3 border-b">
              <h1 class="text-[13px] font-medium">Dubayda hashamatni his eting</h1>
              <h2 class="text-yellow-500 text-[12px] mb-3 mt-1">Shahar va sahro uyg'unligi</h2>
              <p class="text-[12px] text-[#7a7a7a] leading-[22px]">Dubayning osmono'par binolari, hashamatli xaridlari va cho'l sarguzashtlarining boyligidan zavqlaning.</p>
            </div>
            <div class="flex">
              <a href="tel:+998777777777" class="text-gray-400 hover:text-yellow-500 w-1/2 p-3 text-[11px] text-center border-r border-gray-300">KO'PROQ BILISH</a>
              <a href="" class="text-gray-400 hover:text-yellow-500 w-1/2 p-3 text-[11px] text-center">BAND QILISH</a>
            </div>
          </div>

          <!-- Card 2 -->
          <div class="w-full max-w-[360px] bg-white shadow-lg overflow-hidden rounded-lg">
            <div id="turkiya_madanyati" class="w-full h-[200px] flex items-start p-2 bg-cover bg-center">
              <div class="flex gap-0.5">
                <svg v-for="n in 5" :key="n" width="18" height="18" viewBox="0 0 24 24" class="text-white">
                  <path fill="currentColor" d="M12,17.27L18.18,21L16.54,13.97L22,9.24L14.81,8.62L12,2L9.19,8.62L2,9.24L7.45,13.97L5.82,21L12,17.27Z"/>
                </svg>
              </div>
            </div>
            <div class="p-3 border-b">
              <h1 class="text-[13px] font-medium">Turkiya madaniyatini kashf eting</h1>
              <h2 class="text-yellow-500 text-[12px] mb-3 mt-1">Tarixiy mo'jizalar va hayratlanarli manzaralar</h2>
              <p class="text-[12px] text-[#7a7a7a] leading-[22px]">Turkiyaning qadimiy xarobalardan tortib jonli bozorlarigacha bo'lgan jozibali tarixiga sho'ng'ing.</p>
            </div>
            <div class="flex">
              <a href="tel:+998777777777" class="text-gray-400 hover:text-yellow-500 w-1/2 p-3 text-[11px] text-center border-r border-gray-300">KO'PROQ BILISH</a>
              <a href="" class="text-gray-400 hover:text-yellow-500 w-1/2 p-3 text-[11px] text-center">BAND QILISH</a>
            </div>
          </div>

          <!-- Card 3 -->
          <div class="w-full max-w-[360px] bg-white shadow-lg overflow-hidden rounded-lg sm:col-span-2 lg:col-span-1 sm:max-w-[360px]">
            <div id="sharm_dam_oling" class="w-full h-[200px] flex items-start p-2 bg-cover bg-center">
              <div class="flex gap-0.5">
                <svg v-for="n in 5" :key="n" width="18" height="18" viewBox="0 0 24 24" class="text-white">
                  <path fill="currentColor" d="M12,17.27L18.18,21L16.54,13.97L22,9.24L14.81,8.62L12,2L9.19,8.62L2,9.24L7.45,13.97L5.82,21L12,17.27Z"/>
                </svg>
              </div>
            </div>
            <div class="p-3 border-b">
              <h1 class="text-[13px] font-medium">Sharmda dam oling</h1>
              <h2 class="text-yellow-500 text-[12px] mb-3 mt-1">Shahar va sahro uyg'unligi</h2>
              <p class="text-[12px] text-[#7a7a7a] leading-[22px]">Sharm al-Shayx — Qizil dengizning eng yaxshi sho'ng'in joylari va noyob dengiz hayotidan rohatlaning.</p>
            </div>
            <div class="flex">
              <a href="tel:+998777777777" class="text-gray-400 hover:text-yellow-500 w-1/2 p-3 text-[11px] text-center border-r border-gray-300">KO'PROQ BILISH</a>
              <a href="" class="text-gray-400 hover:text-yellow-500 w-1/2 p-3 text-[11px] text-center">BAND QILISH</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- SECTION 5 - SERVICES -->
    <section id="sec5" class="px-4 sm:px-8 lg:px-16 pt-[60px] sm:pt-[80px]">
      <div class="text-center mb-8 sm:mb-10">
        <h6 class="text-yellow-400 mb-3 text-sm sm:text-base">Bizning xizmatlar</h6>
        <h4 class="text-[20px] sm:text-[24px] lg:text-[25px] font-semibold">Ishonch bilan kashf eting</h4>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 max-w-[1300px] mx-auto">
        <div v-for="(svc, i) in services" :key="i"
          class="bg-white border border-gray-200 shadow-lg overflow-hidden rounded-2xl p-6 sm:p-8 flex flex-col items-center text-center">
          <div class="w-20 h-20 flex items-center justify-center">
            <img src="./assets/images/service_icon.png" alt="" class="w-full h-full object-contain">
          </div>
          <div class="mt-5">
            <h1 class="text-[18px] sm:text-[20px] lg:text-[24px] font-medium text-black mb-3">{{ svc.title }}</h1>
            <p class="text-[13px] sm:text-[14px] text-[#7a7a7a] leading-[24px]">{{ svc.desc }}</p>
          </div>
        </div>
      </div>
      <hr class="my-10 sm:my-[50px] text-gray-300 max-w-[1300px] mx-auto">
    </section>

    <!-- SECTION 6 - PLAN YOUR DREAM TRIP -->
    <section class="px-4 sm:px-8 lg:px-16 pb-[60px] sm:pb-[80px]">
      <div class="bg-white max-w-2xl">
        <h1 class="mb-4 font-semibold text-[18px] sm:text-[20px]">Orzuyingdagi sayohatni rejalashtiring</h1>
        <p class="text-[13px] sm:text-[14px] text-gray-500 leading-relaxed">
          O'zingizning orzuingizdagi sayohatga chiqayotganingizda, har bir tafsilotga e'tibor qaratamiz. Bu madaniy qochish,
          sarguzashtli ekspeditsiya yoki sohilda dam olish bo'ladimi, biz muammosiz va unutilmas sayohat tajribasini ta'minlaymiz.
        </p>
        <div class="mt-5">
          <button class="w-[120px] h-[46px] bg-amber-400 border-2 border-amber-400 transition-colors duration-300 hover:bg-white group">
            <a href="#" class="text-white font-medium transition-colors duration-300 group-hover:text-amber-400 w-full h-full flex items-center justify-center text-sm">
              Bog'lanish
            </a>
          </button>
        </div>
      </div>
    </section>

    <!-- SECTION 7 - PRICING PLANS -->
    <section class="px-4 sm:px-8 lg:px-16 pb-[60px] sm:pb-[80px]">
      <div class="text-center mb-8 sm:mb-10 mt-[40px] sm:mt-[80px]">
        <h6 class="text-yellow-400 mb-3 text-sm sm:text-base">Maxsus Takliflar</h6>
        <h4 class="text-[20px] sm:text-[24px] lg:text-[25px] font-semibold">O'zingiz orzu qilgan ta'tilni tanlang</h4>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 max-w-[1300px] mx-auto">
        <div v-for="(plan, i) in plans" :key="i"
          class="bg-gray-200 shadow-lg overflow-hidden rounded-lg flex flex-col items-center">
          <div class="w-full bg-amber-400 p-5 text-center">
            <h2 class="text-white text-[17px] sm:text-[20px]">Asosiy Sayohatchi</h2>
            <h1 class="text-white text-[24px] sm:text-[28px] lg:text-[30px] font-bold">Biz bilan bog'laning</h1>
            <p class="text-white text-[16px] sm:text-[20px]">/individual</p>
          </div>
          <div class="py-6 sm:py-[30px] text-center w-full px-4">
            <div class="flex flex-col items-center space-y-3 gap-2">
              <a href="" class="transition-all duration-500 hover:text-yellow-500 cursor-pointer text-sm sm:text-base">Moslashtirilgan Sayohat Rejasi</a>
              <a href="" class="transition-all duration-500 hover:text-yellow-500 text-sm sm:text-base">Shakllantirilgan Manzil Qo'llanmalar</a>
              <a href="" class="transition-all duration-500 hover:text-yellow-500 text-sm sm:text-base">Mutaxassis Bilan Sayohat Muhokamasi</a>
              <a href="" class="transition-all duration-500 hover:text-yellow-500 text-sm sm:text-base">24/7 Xizmat Ko'rsatish</a>
              <a href="" class="transition-all duration-500 hover:text-yellow-500 text-sm sm:text-base">Moslashuvchan Narxlar</a>
            </div>
            <div class="mt-6">
              <button class="w-[120px] h-[46px] bg-amber-400 border-2 border-amber-400 transition-colors duration-300 hover:bg-white group">
                <a href="#" class="text-white font-medium transition-colors duration-300 group-hover:text-amber-400 w-full h-full flex items-center justify-center text-sm">
                  Bog'lanish
                </a>
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- SECTION 8 - MAP -->
    <section class="px-0 pt-[40px] sm:pt-[60px]">
      <div class="w-full h-[280px] sm:h-[380px] lg:h-[450px] overflow-hidden shadow-lg">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d314.85795074969553!2d69.26236261883909!3d41.34256037392012!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x38ae8d0a3eff6793%3A0x374f8cd599c1c8fa!2sYagona%20Darcha%20Shaykhontokhur%20tumani!5e0!3m2!1suz!2s!4v1779775879180!5m2!1suz!2s"
          width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"
          referrerpolicy="no-referrer-when-downgrade">
        </iframe>
      </div>
    </section>

    <!-- SECTION 9 - CTA -->
    <section class="w-full min-h-[280px] sm:min-h-[350px] flex flex-col items-center justify-center bg-white px-4 py-10 sm:py-14 text-center">
      <p class="text-amber-400 text-sm font-medium tracking-wide mb-2">Biz bilan o'z joyingizni band qiling!</p>
      <h2 class="text-slate-900 text-xl sm:text-2xl md:text-3xl mb-3">Ta'tilingizni biz bilan o'tkazing</h2>
      <p class="text-sm sm:text-base mb-2">Direktor: Bekzod Ochilov</p>
      <a href="tel:+998938936707"
        class="text-amber-400 text-lg sm:text-xl md:text-2xl font-bold tracking-wider hover:text-amber-500 transition-colors duration-300 mb-6 block">
        +998 91 322 90 25
      </a>
      <button class="hover:bg-white hover:text-amber-400 hover:border-amber-300 hover:border-2 bg-amber-400 text-white font-medium px-6 py-3 min-w-[150px] transition-all duration-300 hover:bg-amber-500 shadow-sm active:scale-95 text-sm sm:text-base">
        Joy Band Qilish
      </button>
    </section>

    <hr class="text-gray-300">

    <!-- SECTION 10 - FOOTER -->
    <section id="sec10" class="px-4 sm:px-8 lg:px-16 my-10 sm:my-[60px] lg:my-[100px]">
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 lg:gap-10">
        <!-- Logo + Social -->
        <div class="flex flex-col gap-4">
          <img src="./assets/images/Screenshot 2026-05-26 114122.png" alt="logo" class="max-w-[160px] sm:max-w-[180px]">
          <p class="text-[13px] sm:text-[14px] text-gray-400">
            Biz bilan dunyoni zabt eting. Sayohat tashkil qilishda eng yaxshi hamkoringiz
          </p>
          <a href="https://www.instagram.com/bekzodochilov57/" class="block">
            <svg width="44px" height="44px" viewBox="-2.5 -2.5 30.00 30.00" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd"
                d="M15.5 5H9.5C7.29086 5 5.5 6.79086 5.5 9V15C5.5 17.2091 7.29086 19 9.5 19H15.5C17.7091 19 19.5 17.2091 19.5 15V9C19.5 6.79086 17.7091 5 15.5 5Z"
                stroke="#000000" stroke-width="1.55" stroke-linecap="round" stroke-linejoin="round"/>
              <path fill-rule="evenodd" clip-rule="evenodd"
                d="M12.5 15C10.8431 15 9.5 13.6569 9.5 12C9.5 10.3431 10.8431 9 12.5 9C14.1569 9 15.5 10.3431 15.5 12C15.5 12.7956 15.1839 13.5587 14.6213 14.1213C14.0587 14.6839 13.2956 15 12.5 15Z"
                stroke="#000000" stroke-width="1.55" stroke-linecap="round" stroke-linejoin="round"/>
              <rect x="15.5" y="9" width="2" height="2" rx="1" transform="rotate(-90 15.5 9)" fill="#000000"/>
              <rect x="16" y="8.5" width="1" height="1" rx="0.5" transform="rotate(-90 16 8.5)" stroke="#000000" stroke-linecap="round"/>
            </svg>
          </a>
        </div>

        <!-- Links -->
        <div class="bg-white">
          <h3 class="text-[17px] sm:text-[19px] font-semibold text-slate-900 mb-4">Foydali Havolalar</h3>
          <ul class="space-y-3">
            <li>
              <a href="#" class="flex items-center text-slate-600 font-medium hover:text-amber-500 text-sm sm:text-base">
                <span class="w-2.5 h-2.5 bg-amber-500 mr-3 flex-shrink-0 block"></span>Blog
              </a>
            </li>
            <li>
              <a href="#" class="flex items-center text-slate-600 font-medium hover:text-amber-500 text-sm sm:text-base">
                <span class="w-2.5 h-2.5 bg-amber-500 mr-3 flex-shrink-0 block"></span>Biz bilan Aloqa
              </a>
            </li>
            <li>
              <a href="#" class="flex items-center text-slate-600 font-medium hover:text-amber-500 text-sm sm:text-base">
                <span class="w-2.5 h-2.5 bg-amber-500 mr-3 flex-shrink-0 block"></span>Biz Haqimizda
              </a>
            </li>
            <li>
              <a href="#" class="flex items-center text-slate-600 font-medium hover:text-amber-500 text-sm sm:text-base">
                <span class="w-2.5 h-2.5 bg-amber-500 mr-3 flex-shrink-0 block"></span>Maxfiylik Siyosati
              </a>
            </li>
          </ul>
        </div>

        <!-- Contact -->
        <div class="bg-white">
          <h2 class="text-xl sm:text-2xl font-semibold text-slate-950 mb-4">Aloqa Ma'lumoti</h2>
          <p class="text-slate-500 text-[13px] sm:text-[15px] leading-relaxed mb-6">
            Keyingi sayohatingizga tayyor bo'lib, shaxsiy sayohat yordam va so'rovnoma uchun biz bilan bog'laning.
          </p>
          <div class="space-y-3 text-[13px] sm:text-[15px]">
            <div class="flex items-start gap-2">
              <span class="text-slate-500 w-[70px] sm:w-[80px] flex-shrink-0">Telefon:</span>
              <a href="tel:+998913229025" class="text-amber-400 break-all">+998 91 322 90 25</a>
            </div>
            <div class="flex items-start gap-2">
              <span class="text-slate-500 w-[70px] sm:w-[80px] flex-shrink-0">Email:</span>
              <a href="mailto:bekzodochilov57@gmail.com" class="text-amber-400 break-all">bekzodochilov57@gmail.com</a>
            </div>
            <div class="flex items-start gap-2">
              <span class="text-slate-500 w-[70px] sm:w-[80px] flex-shrink-0">Manzil:</span>
              <a href="#" class="text-amber-400">Shayxontohur tumani, Jangoh mavzesi, 1-etaj 37-xonadon, Toshkent shahri</a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const scrollToSection = (sec5) => {
  const element = document.getElementById(sec5);
  if (element) {
    element.scrollIntoView({ 
      behavior: 'smooth', 
      block: 'start'
    });
  }
};

const menuOpen = ref(false)

const destinations = [
  {
    img: './assets/images/train.png',
    title: 'Biz bilan arzon temir yo\'l chiptalari',
    region: 'Butun dunyo',
    desc: 'Temir yo\'l sarguzashtiga kiring va kashf qiling dunyo bo\'ylab yo\'nalishlar. Bu go\'zal bo\'ladimi landshaftlar, gavjum shaharlar yoki madaniy toshlar, bizning temir yo\'l xizmatlari noyob va qulay yo\'lni taklif qiladi yer sharini aylanib o\'tish.'
  },
  {
    img: './assets/images/plane.png',
    title: 'Havo sayohatlari uchun qiziqarli takliflarni kashf eting',
    region: 'Global manzillar',
    desc: 'Havodagi sarguzashtga boring va kashf qiling dunyo bo\'ylab yo\'nalishlar. Bizning aviakompaniya xizmatlari qulaylikni ta\'minlaydi va dunyo bo\'ylab sayohat qilishning ajoyib usuli.'
  },
  {
    img: './assets/images/dubai2.png',
    title: 'Dubay',
    region: 'Birlashgan Arab Amirliklari',
    desc: 'Dubay — Birlashgan Arabistondagi shahar va amirlik. Hashamatli xaridlari bilan mashhur Emirates zamonaviy arxitektura va jonli tungi hayot. 830 metr balandlikdagi Burj Xalifa minorasi hukmronlik qiladi shaharning osmono\'par binolari.'
  },
  {
    img: './assets/images/antalya.png',
    title: 'Antalya',
    region: 'Turkiya',
    desc: 'Antaliya Turkiyaning eng tez rivojlanayotgan shahri va Butun dunyodan sayyohlar uni kashf qilmoqdalar ajoyib plyajlarning ajoyib kombinatsiyasi va an\'anaviy turk madaniyati.'
  },
  {
    img: './assets/images/sharm.png',
    title: 'Sharm al-Shayx',
    region: 'Misr',
    desc: 'Sharm al-Shayx - Sinaydagi turizm markazi Yarim orol va eng yaxshi sho\'ng\'in uchun uy dunyo. Ayniqsa, Rasning suv osti mo\'jizalari Sharmni olib ketgan Muhammad milliy bog\'i butunlay yangi daraja.'
  },
  {
    img: './assets/images/istanbul2.png',
    title: 'Istanbul',
    region: 'Turkiya',
    desc: 'Istanbul Turkiya va uning aholisi eng gavjum shahar madaniy, iqtisodiy va tarixiy markaz. Joylashgan tomonidan bo\'lingan Turkiyaning shimoli-g\'arbiy qismida Bosfor bo\'g\'ozi Yevropa va Osiyo tomonlariga.'
  }
]

const services = [
  {
    title: 'Sayohat tajribalari',
    desc: 'Sizning xohishingizga moslashtirilgan yuqori sifatli tajribalarni ta\'minlab, puxta ishlab chiqilgan sayohat marshrutlarini kashf eting. Mutaxassislar tomonidan tayyorlangan paketlarimiz unutilmas sarguzashtlarni kafolatlaydi.'
  },
  {
    title: 'Eng yaxshi marshrutlar',
    desc: 'Sizning noyob qiziqishlaringiz va istaklaringizga mos keladigan to\'liq moslashtirilgan sayohat rejalaridan rohatlaning. Biz sizning shaxsiy imtiyozlaringiz va sayohat intilishlaringizni aks ettiruvchi sayohatlarni yaratishga ixtisoslashganmiz.'
  },
  {
    title: 'Tayyor sayohat yo\'nalishlari',
    desc: 'Bizning paketlarimiz qulaylik, sarguzasht va madaniy suvga cho\'milishning uzluksiz uyg\'unligini ta\'minlaydi va ajoyib sayohat tajribasini ta\'minlaydi.'
  }
]

const plans = [1, 2, 3]
</script>

<style lang="scss" scoped>
#background {
  background-image: url(./assets/images/dubai2.png);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

#istanbul {
  background-image: url(./assets/images/istanbul.png);
  background-size: cover;
  background-position: center;
}

#sharm {
  background-image: url(./assets/images/sharm.png);
  background-size: cover;
  background-position: center;
}

#tailand {
  background-image: url(./assets/images/Tailand.png);
  background-size: cover;
  background-position: center;
}

#argentina {
  background-image: url(./assets/images/Argentina.png);
  background-size: cover;
  background-position: center;
}

#dubai {
  background-image: url(./assets/images/dubai2.png);
  background-size: cover;
  background-position: center;
}

#dubay_hashamati {
  background-image: url(./assets/images/dubai.png);
  background-size: cover;
  background-position: center;
}

#turkiya_madanyati {
  background-image: url(./assets/images/istanbul.png);
  background-size: cover;
  background-position: center;
}

#sharm_dam_oling {
  background-image: url(./assets/images/sharm2.png);
  background-size: cover;
  background-position: center;
}
</style>