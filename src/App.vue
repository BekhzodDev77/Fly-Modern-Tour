<template>
  <div :class="['page', isDark ? 'dark' : 'light']">

    <!-- =================== HEADER =================== -->
    <header class="header">
      <div class="header__logo">
        <img class="header__logo-img" src="./assets/images/Logo.png" alt="Sayohat agentligi logotipi" />
      </div>

      <!-- Desktop Nav -->
      <nav class="header__nav" aria-label="Asosiy navigatsiya">
        <a href="#sec1" class="header__nav-link">Asosiy sahifa</a>
        <a href="#sec4" class="header__nav-link">Biz haqimizda</a>
        <a href="#sec5" class="header__nav-link">Turlar</a>
        <a href="#sec10" class="header__nav-link">Kontaktlar</a>
      </nav>

      <div class="header__controls">
        <!-- Dark/Light toggle -->
        <button
          @click="toggleTheme"
          class="theme-toggle"
          :aria-label="isDark ? 'Yorug\' rejimga o\'tish' : 'Qorong\'u rejimga o\'tish'"
        >
          <span v-if="isDark" class="theme-toggle__icon">☀️</span>
          <span v-else class="theme-toggle__icon">🌙</span>
        </button>

        <!-- Mobile Hamburger -->
        <button
          @click="menuOpen = !menuOpen"
          class="header__burger"
          :aria-expanded="menuOpen"
          aria-controls="mobile-menu"
          aria-label="Menyuni ochish/yopish"
        >
          <span :class="['burger-line', menuOpen && 'burger-line--top']"></span>
          <span :class="['burger-line', menuOpen && 'burger-line--mid']"></span>
          <span :class="['burger-line', menuOpen && 'burger-line--bot']"></span>
        </button>
      </div>
    </header>

    <!-- Mobile Menu -->
    <nav
      id="mobile-menu"
      v-show="menuOpen"
      class="mobile-menu"
      aria-label="Mobil navigatsiya"
    >
      <a href="#sec1"  class="mobile-menu__link" @click="menuOpen = false">Asosiy sahifa</a>
      <a href="#sec4"  class="mobile-menu__link" @click="menuOpen = false">Biz haqimizda</a>
      <a href="#sec5"  class="mobile-menu__link" @click="menuOpen = false">Turlar</a>
      <a href="#sec10" class="mobile-menu__link" @click="menuOpen = false">Kontaktlar</a>
    </nav>

    <main>

      <!-- =================== HERO =================== -->
      <section id="sec1" class="hero" aria-label="Bosh sahifa banner">
        <div class="hero__overlay" aria-hidden="true"></div>
        <div class="hero__content">
          <span class="hero__accent-line" aria-hidden="true"></span>
          <h1 class="hero__title">Sayohat qilishni xohlaysizmi?</h1>
          <p class="hero__subtitle">
            Sayohat orzularingizni haqiqatga aylantiring: rejalashtiring, kashf qiling va unutilmas xotiralar yarating.
          </p>
          <button class="hero__btn" @click="scrollTo('sec5')">Ko'proq bilish</button>

          <!-- Booking Form -->
          <div class="booking">
            <div class="booking__form">
              <input type="text"  placeholder="Ismingiz..."    class="booking__input" aria-label="Ism" />
              <input type="text"  placeholder="Manzilingiz..." class="booking__input" aria-label="Manzil" />
              <input type="date"  class="booking__input"                               aria-label="Sana" />
              <button class="booking__btn">Joy Band Qilish</button>
            </div>
          </div>
        </div>
      </section>

      <!-- =================== DESTINATIONS =================== -->
      <section class="destinations" aria-labelledby="dest-title">
        <p class="section-label">Bizning mashhur manzilimiz</p>
        <h2 id="dest-title" class="section-title">
          Ushbu yo'nalishlar bilan haqiqatan ham o'ziga xos qiladigan go'zallik, madaniyat va tajribalarni kashf eting.
        </h2>
        <div class="destinations__grid">
          <article class="dest-card dest-card--istanbul">
            <h3 class="dest-card__name">Istanbul</h3>
            <p class="dest-card__count">76 band qilingan</p>
          </article>
          <article class="dest-card dest-card--sharm">
            <h3 class="dest-card__name">Sharm</h3>
            <p class="dest-card__count">76 band qilingan</p>
          </article>
          <article class="dest-card dest-card--tailand">
            <h3 class="dest-card__name">Tailand</h3>
            <p class="dest-card__count">76 band qilingan</p>
          </article>
          <article class="dest-card dest-card--argentina">
            <h3 class="dest-card__name">Argentina</h3>
            <p class="dest-card__count">76 band qilingan</p>
          </article>
          <article class="dest-card dest-card--dubai dest-card--wide">
            <h3 class="dest-card__name">Dubai</h3>
            <p class="dest-card__count">76 band qilingan</p>
          </article>
        </div>
      </section>

      <!-- =================== EXPLORE =================== -->
      <section class="explore" aria-labelledby="explore-title">
  <h2 id="explore-title" class="explore__title">Maqsadlarni osongina o'rganing</h2>

  <article class="explore__item">
    <img src="./assets/images/train.png" alt="Biz bilan arzon temir yo'l chiptalari" class="explore__img" loading="lazy">
    <div class="explore__body">
      <h3 class="explore__item-title">Biz bilan arzon temir yo'l chiptalari</h3>
      <p class="explore__region">Butun dunyo</p>
      <p class="explore__desc">Temir yo'l sarguzashtiga kiring va kashf qiling dunyo bo'ylab yo'nalishlar. Bu go'zal bo'ladimi landshaftlar, gavjum shaharlar yoki madaniy toshlar, bizning temir yo'l xizmatlari noyob va qulay yo'lni taklif qiladi yer sharini aylanib o'tish. Go'zallikka sho'ng'ing turli madaniyatlar, barcha bizning orqali kirish mumkin keng temir yo'l tarmog'i...</p>
    </div>
  </article>

  <article class="explore__item">
    <img src="./assets/images/plane.png" alt="Havo sayohatlari uchun qiziqarli takliflarni kashf eting" class="explore__img" loading="lazy">
    <div class="explore__body">
      <h3 class="explore__item-title">Havo sayohatlari uchun qiziqarli takliflarni kashf eting</h3>
      <p class="explore__region">Global manzillar</p>
      <p class="explore__desc">Havodagi sarguzashtga boring va kashf qiling dunyo bo'ylab yo'nalishlar. Bu bo'ladimi hayajonli landshaftlar, jonli shaharlar yoki madaniy xazinalar, bizning aviakompaniya xizmatlari qulaylikni ta'minlaydi va dunyo bo'ylab sayohat qilishning ajoyib usuli. Suvga cho'ming o'zingizni turli madaniyatlar boyligida, barcha bizning keng qamrovli havo sayohatimiz orqali osongina kirish mumkin tarmoq...</p>
    </div>
  </article>

  <article class="explore__item">
    <img src="./assets/images/dubai.png" alt="Dubay" class="explore__img" loading="lazy">
    <div class="explore__body">
      <h3 class="explore__item-title">Dubay</h3>
      <p class="explore__region">Birlashgan Arab Amirliklari</p>
      <p class="explore__desc">Dubay — Birlashgan Arabistondagi shahar va amirlik. Hashamatli xaridlari bilan mashhur Emirates zamonaviy arxitektura va jonli tungi hayot. 830 metr balandlikdagi Burj Xalifa minorasi hukmronlik qiladi shaharning osmono'par binolari. Uning bazasida Dubay joylashgan favvoralar va chiroqlar moslashtirilgan favvoralarga musiqa. Dengizdagi sun'iy orollarda Atlantis, Palm, mehmonxona, suv parki va dengiz hayvonlari parki.</p>
    </div>
  </article>

  <article class="explore__item">
    <img src="./assets/images/antalya.png" alt="Antalya" class="explore__img" loading="lazy">
    <div class="explore__body">
      <h3 class="explore__item-title">Antalya</h3>
      <p class="explore__region">Turkiya</p>
      <p class="explore__desc">Antalya Turkiyaning eng tez rivojlanayotgan shahri va butun dunyodan sayyohlar uni kashf qilmoqdalar ajoyib plyajlarining ajoyib kombinatsiyasi va an'anaviy turk madaniyati. Bolalar yaxshi ko'radilar Beach Park, Aqualand (suv attraksionlar sevadiganlarning orzusi) va Dolphinarium (quy delfinlar, dengiz sherlari va oq kitlar). Ishonch hosil qiling eski shahar markazini o'rganing va Hadrian darvozasini ko'ring.</p>
    </div>
  </article>

  <article class="explore__item">
    <img src="./assets/images/sharm.png" alt="Sharm al-Shayx" class="explore__img" loading="lazy">
    <div class="explore__body">
      <h3 class="explore__item-title">Sharm al-Shayx</h3>
      <p class="explore__region">Misr</p>
      <p class="explore__desc">Sharm al-Shayx - Sinaydagi turizm markazi. Yarim orol va eng yaxshi sho'ng'in uchun uy dunyo. Ayniqsa, Rasning suv osti mo'jizalari Sharmni olib kelgan Muhammad milliy bog'i butunlay yangi daraja. Shaharda sho'ng'in joylari va havaskor g'avvoslarni jalb qiladigan kema halokatlari noyob kashf qilish uchun dunyodan Qizil dengiz tubidagi dengiz hayoti.</p>
    </div>
  </article>

  <article class="explore__item">
    <img src="./assets/images/istanbul.png" alt="Istanbul" class="explore__img" loading="lazy">
    <div class="explore__body">
      <h3 class="explore__item-title">Istanbul</h3>
      <p class="explore__region">Turkiya</p>
      <p class="explore__desc">Istanbul Turkiya va uning eng gavjum shahar madaniy, iqtisodiy va tarixiy markaz. Joylashgan tomonidan bo'lingan Turkiyaning shimoli-g'arbiy qismida Bosfor bo'g'ozi Yevropa va Osiyo tomonlariga, qayri Marmara va Qora dengizni bog'laydi. Bu shahar dunyodagi yagona shahar ikki qit'ada joylashgan.</p>
    </div>
  </article>

  </section>

      <!-- =================== CARDS / BIZ HAQIMIZDA =================== -->
      <section id="sec4" class="cards-section" aria-labelledby="cards-title">
        <div class="cards-section__inner">
          <header class="cards-section__header">
            <p class="section-label">Bizning manzillarimizni kashf eting</p>
            <h2 id="cards-title" class="section-title">
              Dubay, Turkiya, Sharm El Sheyhni biz bilan kashf eting
            </h2>
          </header>

          <div class="cards-grid">
            <article v-for="(card, i) in tourCards" :key="i" :class="['tour-card', card.wide && 'tour-card--wide']">
              <div :class="['tour-card__img', `tour-card__img--${card.theme}`]">
                <div class="tour-card__stars" aria-label="5 yulduz">
                  <svg v-for="s in 5" :key="s" width="16" height="16" viewBox="0 0 24 24" aria-hidden="true">
                    <path fill="#fff" d="M12,17.27L18.18,21L16.54,13.97L22,9.24L14.81,8.62L12,2L9.19,8.62L2,9.24L7.45,13.97L5.82,21Z"/>
                  </svg>
                </div>
              </div>
              <div class="tour-card__body">
                <h3 class="tour-card__name">{{ card.name }}</h3>
                <p class="tour-card__tag">{{ card.tag }}</p>
                <p class="tour-card__desc">{{ card.desc }}</p>
              </div>
              <footer class="tour-card__actions">
                <a href="tel:+998777777777" class="tour-card__action">KO'PROQ BILISH</a>
                <a href="#"                  class="tour-card__action">BAND QILISH</a>
              </footer>
            </article>
          </div>
        </div>
      </section>

      <!-- =================== SERVICES =================== -->
      <section id="sec5" class="services" aria-labelledby="services-title">
        <header class="services__header">
          <p class="section-label">Bizning xizmatlar</p>
          <h2 id="services-title" class="section-title">Ishonch bilan kashf eting</h2>
        </header>
        <div class="services__grid">
          <article v-for="(svc, i) in services" :key="i" class="service-card">
            <div class="service-card__icon" aria-hidden="true">
              <img src="./assets/images/service_icon.png" alt="" class="service-card__icon-img" />
            </div>
            <div class="service-card__body">
              <h3 class="service-card__title">{{ svc.title }}</h3>
              <p class="service-card__desc">{{ svc.desc }}</p>
            </div>
          </article>
        </div>
        <hr class="divider" />
      </section>

      <!-- =================== DREAM TRIP =================== -->
      <section class="dream-trip" aria-labelledby="dream-title">
        <h2 id="dream-title" class="dream-trip__title">Orzuyingdagi sayohatni rejalashtiring</h2>
        <p class="dream-trip__desc">
          O'zingizning orzuingizdagi sayohatga chiqayotganingizda, har bir tafsilotga e'tibor qaratamiz.
          Bu madaniy qochish, sarguzashtli ekspeditsiya yoki sohilda dam olish bo'ladimi, biz muammosiz va
          unutilmas sayohat tajribasini ta'minlaymiz.
        </p>
        <a href="#sec10" class="cta-btn">Bog'lanish</a>
      </section>

      <!-- =================== PLANS =================== -->
      <section class="plans" aria-labelledby="plans-title">
        <header class="plans__header">
          <p class="section-label">Maxsus Takliflar</p>
          <h2 id="plans-title" class="section-title">O'zingiz orzu qilgan ta'tilni tanlang</h2>
        </header>
        <div class="plans__grid">
          <article v-for="n in 3" :key="n" class="plan-card">
            <div class="plan-card__top">
              <h3 class="plan-card__label">Asosiy Sayohatchi</h3>
              <p class="plan-card__price">Biz bilan bog'laning</p>
              <p class="plan-card__period">/individual</p>
            </div>
            <div class="plan-card__body">
              <ul class="plan-card__features" aria-label="Xizmatlar ro'yxati">
                <li v-for="f in planFeatures" :key="f" class="plan-card__feature">{{ f }}</li>
              </ul>
              <a href="#sec10" class="cta-btn plan-card__btn">Bog'lanish</a>
            </div>
          </article>
        </div>
      </section>

      <!-- =================== MAP =================== -->
      <section class="map-section" aria-label="Bizning manzil xaritada">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d314.85795074969553!2d69.26236261883909!3d41.34256037392012!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x38ae8d0a3eff6793%3A0x374f8cd599c1c8fa!2sYagona%20Darcha%20Shaykhontokhur%20tumani!5e0!3m2!1suz!2s!4v1779775879180!5m2!1suz!2s"
          width="100%" height="100%" style="border:0;" allowfullscreen loading="lazy"
          referrerpolicy="no-referrer-when-downgrade" title="Ofis manzili xaritada"
        ></iframe>
      </section>

      <!-- =================== CTA =================== -->
      <section class="cta-section" aria-labelledby="cta-title">
        <p class="cta-section__label">Biz bilan o'z joyingizni band qiling!</p>
        <h2 id="cta-title" class="cta-section__title">Ta'tilingizni biz bilan o'tkazing</h2>
        <p class="cta-section__director">Direktor: Bekzod Ochilov</p>
        <a href="tel:+998913229025" class="cta-section__phone">+998 91 322 90 25</a>
        <button class="cta-btn">Joy Band Qilish</button>
      </section>

      <hr class="divider" />

    </main>

    <!-- =================== FOOTER =================== -->
    <footer id="sec10" class="footer" aria-label="Footer">
      <div class="footer__grid">

        <!-- Brand -->
        <div class="footer__brand">
          <img src="./assets/images/Screenshot 2026-05-26 114122.png" alt="Logotip" class="footer__logo" />
          <p class="footer__brand-desc">
            Biz bilan dunyoni zabt eting. Sayohat tashkil qilishda eng yaxshi hamkoringiz
          </p>
          <a href="https://www.instagram.com/bekzodochilov57/" class="footer__social" aria-label="Instagram">
            <svg width="44" height="44" viewBox="-2.5 -2.5 30 30" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <path fill-rule="evenodd" clip-rule="evenodd"
                d="M15.5 5H9.5C7.291 5 5.5 6.791 5.5 9V15C5.5 17.209 7.291 19 9.5 19H15.5C17.709 19 19.5 17.209 19.5 15V9C19.5 6.791 17.709 5 15.5 5Z"
                stroke="currentColor" stroke-width="1.55" stroke-linecap="round" stroke-linejoin="round"/>
              <path fill-rule="evenodd" clip-rule="evenodd"
                d="M12.5 15C10.843 15 9.5 13.657 9.5 12C9.5 10.343 10.843 9 12.5 9C14.157 9 15.5 10.343 15.5 12C15.5 12.796 15.184 13.559 14.621 14.121C14.059 14.684 13.296 15 12.5 15Z"
                stroke="currentColor" stroke-width="1.55" stroke-linecap="round" stroke-linejoin="round"/>
              <rect x="15.5" y="9" width="2" height="2" rx="1" transform="rotate(-90 15.5 9)" fill="currentColor"/>
            </svg>
          </a>
        </div>

        <!-- Links -->
        <nav class="footer__links" aria-label="Foydali havolalar">
          <h3 class="footer__links-title">Foydali Havolalar</h3>
          <ul class="footer__links-list">
            <li v-for="link in footerLinks" :key="link.label">
              <a :href="link.href" class="footer__link">
                <span class="footer__link-dot" aria-hidden="true"></span>
                {{ link.label }}
              </a>
            </li>
          </ul>
        </nav>

        <!-- Contact -->
        <address class="footer__contact">
          <h3 class="footer__contact-title">Aloqa Ma'lumoti</h3>
          <p class="footer__contact-desc">
            Keyingi sayohatingizga tayyor bo'lib, shaxsiy sayohat yordam uchun biz bilan bog'laning.
          </p>
          <dl class="footer__contact-list">
            <div class="footer__contact-item">
              <dt class="footer__contact-label">Telefon:</dt>
              <dd><a href="tel:+998913229025" class="footer__contact-value">+998 91 322 90 25</a></dd>
            </div>
            <div class="footer__contact-item">
              <dt class="footer__contact-label">Email:</dt>
              <dd><a href="mailto:bekzodochilov57@gmail.com" class="footer__contact-value">bekzodochilov57@gmail.com</a></dd>
            </div>
            <div class="footer__contact-item">
              <dt class="footer__contact-label">Manzil:</dt>
              <dd class="footer__contact-value">Shayxontohur tumani, Jangoh mavzesi, 1-etaj 37-xonadon, Toshkent shahri</dd>
            </div>
          </dl>
        </address>

      </div>
    </footer>

  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

/* ---------- Theme ---------- */
const isDark = ref(false)

onMounted(() => {
  const saved = localStorage.getItem('theme')
  isDark.value = saved === 'dark'
})

function toggleTheme() {
  isDark.value = !isDark.value
  localStorage.setItem('theme', isDark.value ? 'dark' : 'light')
}

/* ---------- Menu ---------- */
const menuOpen = ref(false)

/* ---------- Scroll ---------- */
function scrollTo(id) {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

/* ---------- Data ---------- */
const explorePlaces = [
  { img: './assets/images/train.png',    title: 'Biz bilan arzon temir yo\'l chiptalari',                   region: 'Butun dunyo',             desc: 'Temir yo\'l sarguzashtiga kiring va kashf qiling dunyo bo\'ylab yo\'nalishlar. Bu go\'zal bo\'ladimi landshaftlar, gavjum shaharlar yoki madaniy toshlar, bizning temir yo\'l xizmatlari noyob va qulay yo\'lni taklif qiladi.' },
  { img: './assets/images/plane.png',    title: 'Havo sayohatlari uchun qiziqarli takliflarni kashf eting', region: 'Global manzillar',          desc: 'Havodagi sarguzashtga boring va kashf qiling dunyo bo\'ylab yo\'nalishlar. Bizning aviakompaniya xizmatlari qulaylikni ta\'minlaydi va dunyo bo\'ylab sayohat qilishning ajoyib usulini taqdim etadi.' },
  { img: './assets/images/dubai2.png',   title: 'Dubay',                                                    region: 'Birlashgan Arab Amirliklari', desc: 'Dubay zamonaviy arxitektura va jonli tungi hayot bilan mashhur. 830 metr balandlikdagi Burj Xalifa minorasi shaharning osmono\'par binolari ustida hukmronlik qiladi.' },
  { img: './assets/images/antalya.png',  title: 'Antalya',                                                  region: 'Turkiya',                   desc: 'Antalya ajoyib plyajlarning ajoyib kombinatsiyasi va an\'anaviy turk madaniyati bilan butun dunyodan sayyohlarni jalb qiladi. Eski shahar markazini o\'rganing va Hadrian darvozasini ko\'ring.' },
  { img: './assets/images/sharm.png',    title: 'Sharm al-Shayx',                                           region: 'Misr',                      desc: 'Sharm al-Shayx Sinay yarim orolidagi turizm markazi bo\'lib, dunyo bo\'ylab eng yaxshi sho\'ng\'in joylari uchun mashhur. Noyob Qizil dengiz tubidagi dengiz hayotini kashf eting.' },
  { img: './assets/images/istanbul2.png',title: 'Istanbul',                                                 region: 'Turkiya',                   desc: 'Istanbul Turkiyaning madaniy, iqtisodiy va tarixiy markazidir. Bosfor bo\'g\'ozi tomonidan bo\'lingan bu shahar dunyodagi yagona ikki qit\'ada joylashgan shahardir.' },
]

const tourCards = [
  { name: 'Dubayda hashamatni his eting',    tag: 'Shahar va sahro uyg\'unligi',         desc: 'Dubayning osmono\'par binolari, hashamatli xaridlari va cho\'l sarguzashtlaridan zavqlaning.',                            theme: 'dubai',  wide: false },
  { name: 'Turkiya madaniyatini kashf eting',tag: 'Tarixiy mo\'jizalar va manzaralar',   desc: 'Turkiyaning qadimiy xarobalardan tortib jonli bozorlarigacha bo\'lgan jozibali tarixiga sho\'ng\'ing.',                  theme: 'turkey', wide: false },
  { name: 'Sharmda dam oling',               tag: 'Shahar va sahro uyg\'unligi',         desc: 'Sharm al-Shayx — Qizil dengizning eng yaxshi sho\'ng\'in joylari va noyob dengiz hayotidan rohatlaning.',                  theme: 'sharm',  wide: true  },
]

const services = [
  { title: 'Sayohat tajribalari',       desc: 'Sizning xohishingizga moslashtirilgan yuqori sifatli tajribalarni ta\'minlab, puxta ishlab chiqilgan sayohat marshrutlarini kashf eting.' },
  { title: 'Eng yaxshi marshrutlar',    desc: 'Sizning noyob qiziqishlaringiz va istaklaringizga mos keladigan to\'liq moslashtirilgan sayohat rejalaridan rohatlaning.' },
  { title: 'Tayyor sayohat yo\'nalishlari', desc: 'Bizning paketlarimiz qulaylik, sarguzasht va madaniy suvga cho\'milishning uzluksiz uyg\'unligini ta\'minlaydi.' },
]

const planFeatures = [
  'Moslashtirilgan Sayohat Rejasi',
  'Shakllantirilgan Manzil Qo\'llanmalar',
  'Mutaxassis Bilan Sayohat Muhokamasi',
  '24/7 Xizmat Ko\'rsatish',
  'Moslashuvchan Narxlar',
]

const footerLinks = [
  { label: 'Blog',              href: '#' },
  { label: 'Biz bilan Aloqa',  href: '#sec10' },
  { label: 'Biz Haqimizda',    href: '#sec4' },
  { label: 'Maxfiylik Siyosati', href: '#' },
]
</script>

<style lang="scss" scoped>
/* ============================================================
   CSS CUSTOM PROPERTIES (Design Tokens)
   ============================================================ */
.page {
  /* --- Brand palette --- */
  --clr-accent:        #f59e0b;
  --clr-accent-hover:  #d97706;
  --clr-accent-light:  #fde68a;

  /* --- Light mode --- */
  --clr-bg:            #ffffff;
  --clr-bg-muted:      #f4f4f4;
  --clr-surface:       #ffffff;
  --clr-border:        #e5e7eb;
  --clr-text:          #0f172a;
  --clr-text-muted:    #6b7280;
  --clr-text-faint:    #9ca3af;
  --clr-header-bg:     #ffffff;
  --clr-shadow:        rgba(0, 0, 0, 0.10);
  --clr-plan-bg:       #e5e7eb;

  /* --- Typography --- */
  --font-family:       'Segoe UI', 'Helvetica Neue', Arial, sans-serif;
  --font-size-xs:      11px;
  --font-size-sm:      13px;
  --font-size-base:    15px;
  --font-size-md:      17px;
  --font-size-lg:      20px;
  --font-size-xl:      24px;
  --font-size-2xl:     30px;
  --font-size-3xl:     36px;
  --font-weight-normal:400;
  --font-weight-medium:500;
  --font-weight-semi:  600;
  --font-weight-bold:  700;
  --line-height-body:  1.625;

  /* --- Spacing --- */
  --space-1:   4px;
  --space-2:   8px;
  --space-3:   12px;
  --space-4:   16px;
  --space-5:   20px;
  --space-6:   24px;
  --space-8:   32px;
  --space-10:  40px;
  --space-12:  48px;
  --space-16:  64px;
  --space-20:  80px;
  --space-24:  96px;

  /* --- Layout --- */
  --px-mobile:  var(--space-4);
  --px-sm:      var(--space-8);
  --px-md:      var(--space-16);
  --px-lg:      10%;

  /* --- Radius --- */
  --radius-sm:  4px;
  --radius-md:  8px;
  --radius-lg:  16px;
  --radius-xl:  20px;

  /* --- Transitions --- */
  --transition-fast:  0.2s ease;
  --transition-base:  0.3s ease;
  --transition-slow:  0.5s ease;
  --transition-card:  0.6s ease-in-out;

  /* --- Z-index --- */
  --z-header: 50;
  --z-menu:   40;

  /* ---- Apply base ---- */
  font-family:      var(--font-family);
  background-color: var(--clr-bg);
  color:            var(--clr-text);
  min-width:        314px;
  transition:       background-color var(--transition-base), color var(--transition-base);
}

/* ============================================================
   DARK MODE OVERRIDES
   ============================================================ */
.page.dark {
  --clr-bg:          #0f172a;
  --clr-bg-muted:    #1e293b;
  --clr-surface:     #1e293b;
  --clr-border:      #334155;
  --clr-text:        #f1f5f9;
  --clr-text-muted:  #94a3b8;
  --clr-text-faint:  #64748b;
  --clr-header-bg:   #1e293b;
  --clr-shadow:      rgba(0, 0, 0, 0.40);
  --clr-plan-bg:     #334155;
}

/* ============================================================
   HEADER
   ============================================================ */
.header {
  position: sticky;
  top: 0;
  z-index: var(--z-header);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--space-3) var(--px-mobile);
  background-color: var(--clr-header-bg);
  box-shadow: 0 1px 3px var(--clr-shadow);
  transition: background-color var(--transition-base);
  gap: var(--space-3);

  @media (min-width: 640px)  { padding: var(--space-3) var(--px-sm); }
  @media (min-width: 1024px) { padding: var(--space-3) var(--px-md); }

  &__logo-img {
    width: 110px;
    height: auto;
    object-fit: contain;
    flex-shrink: 0;
    display: block;

    @media (min-width: 640px)  { width: 140px; }
    @media (min-width: 1024px) { width: 170px; }
  }

  &__nav {
    display: none;
    align-items: center;
    gap: var(--space-6);
    font-weight: var(--font-weight-semi);

    @media (min-width: 797px) {
      display: flex;
    }
  }

  &__nav-link {
    font-size: var(--font-size-base);
    text-decoration: none;
    color: var(--clr-text);
    transition: color var(--transition-slow);
    white-space: nowrap;

    &:hover { color: var(--clr-accent); }
  }

  &__controls {
    display: flex;
    align-items: center;
    gap: var(--space-2);
    flex-shrink: 0;
  }

  &__burger {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 5px;
    padding: var(--space-2);
    background: none;
    border: none;
    cursor: pointer;

    @media (min-width: 797px) { display: none; }
  }
}

/* ---- Burger lines ---- */
.burger-line {
  display: block;
  width: 22px;
  height: 2px;
  background-color: var(--clr-text);
  border-radius: 2px;
  transition: transform var(--transition-base), opacity var(--transition-base);

  &--top { transform: translateY(7px) rotate(45deg); }
  &--mid { opacity: 0; }
  &--bot { transform: translateY(-7px) rotate(-45deg); }
}

/* ---- Theme toggle ---- */
.theme-toggle {
  background: none;
  border: 1px solid var(--clr-border);
  border-radius: var(--radius-md);
  padding: 5px var(--space-2);
  cursor: pointer;
  font-size: var(--font-size-md);
  line-height: 1;
  transition: border-color var(--transition-base), background-color var(--transition-base);

  &:hover { background-color: var(--clr-bg-muted); }

  &__icon { display: block; }
}

/* ============================================================
   MOBILE MENU
   ============================================================ */
.mobile-menu {
  position: sticky;
  top: 56px;
  z-index: var(--z-menu);
  display: flex;
  flex-direction: column;
  gap: var(--space-4);
  background-color: var(--clr-surface);
  box-shadow: 0 4px 6px var(--clr-shadow);
  padding: var(--space-4) var(--px-mobile);
  font-weight: var(--font-weight-semi);

  @media (min-width: 797px) { display: none !important; }

  &__link {
    font-size: var(--font-size-base);
    text-decoration: none;
    color: var(--clr-text);
    transition: color var(--transition-slow);

    &:hover { color: var(--clr-accent); }
  }
}

/* ============================================================
   SHARED HELPERS
   ============================================================ */
.section-label {
  text-align: center;
  color: var(--clr-accent);
  font-size: var(--font-size-sm);
  margin-bottom: var(--space-4);

  @media (min-width: 640px) { font-size: var(--font-size-base); }
}

.section-title {
  text-align: center;
  font-size: var(--font-size-md);
  font-weight: var(--font-weight-semi);
  max-width: 768px;
  margin: 0 auto var(--space-8);
  line-height: 1.4;
  color: var(--clr-text);

  @media (min-width: 640px)  { font-size: var(--font-size-lg); }
  @media (min-width: 1024px) { font-size: var(--font-size-xl); }
}

.divider {
  border: none;
  border-top: 1px solid var(--clr-border);
  margin: var(--space-10) auto;
  max-width: 1300px;
}

.cta-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background-color: var(--clr-accent);
  color: #fff;
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-sm);
  padding: 11px var(--space-6);
  border: 2px solid var(--clr-accent);
  border-radius: var(--radius-sm);
  cursor: pointer;
  text-decoration: none;
  transition: background-color var(--transition-base), color var(--transition-base);

  &:hover {
    background-color: transparent;
    color: var(--clr-accent);
  }
}

/* ============================================================
   HERO
   ============================================================ */
.hero {
  position: relative;
  display: flex;
  align-items: flex-start;
  min-height: 480px;
  background-image: url(./assets/images/dubai2.png);
  background-size: cover;
  background-position: center;
  color: #fff;

  @media (min-width: 640px)  { min-height: 560px; }
  @media (min-width: 1024px) { min-height: 630px; }

  &__overlay {
    position: absolute;
    inset: 0;
    background-color: rgba(0, 0, 0, 0.12);
  }

  &__content {
    position: relative;
    z-index: 1;
    width: 100%;
    padding: var(--space-8) var(--px-mobile) var(--space-8);

    @media (min-width: 640px)  { padding: var(--space-16) var(--px-sm) var(--space-8); }
    @media (min-width: 1024px) { padding: var(--space-24) var(--px-lg) var(--space-8); }
  }

  &__accent-line {
    display: block;
    width: 80px;
    height: 5px;
    background-color: var(--clr-accent);
    margin-bottom: var(--space-3);

    @media (min-width: 640px) { width: 100px; }
  }

  &__title {
    font-size: var(--font-size-xl);
    font-weight: var(--font-weight-semi);
    margin-bottom: var(--space-4);
    max-width: 576px;
    line-height: 1.2;

    @media (min-width: 640px)  { font-size: var(--font-size-2xl); }
    @media (min-width: 1024px) { font-size: var(--font-size-3xl); }
  }

  &__subtitle {
    font-size: var(--font-size-sm);
    max-width: 560px;
    margin-bottom: var(--space-6);
    line-height: var(--line-height-body);

    @media (min-width: 640px)  { font-size: var(--font-size-base); }
    @media (min-width: 1024px) { font-size: var(--font-size-md); }
  }

  &__btn {
    background-color: var(--clr-accent);
    color: #fff;
    font-weight: var(--font-weight-semi);
    font-size: var(--font-size-sm);
    padding: 10px var(--space-5);
    border-radius: var(--radius-sm);
    border: none;
    cursor: pointer;
    transition: background-color var(--transition-base);
    margin-bottom: var(--space-12);

    @media (min-width: 640px) { font-size: var(--font-size-base); padding: 12px var(--space-6); }

    &:hover { background-color: var(--clr-accent-hover); }
  }
}

/* ============================================================
   BOOKING
   ============================================================ */
.booking {
  background-color: #fff;
  color: var(--clr-text-muted);
  border-bottom: 5px solid var(--clr-accent);
  padding: var(--space-3);
  margin-top: 200px;
  margin-bottom: 0px;
  margin-left: 100px;
  max-width: 960px;

  @media (min-width: 640px) { padding: var(--space-4); }

  &__form {
    display: flex;
    flex-direction: column;
    gap: var(--space-2);

    @media (min-width: 540px) {
      flex-direction: row;
      flex-wrap: wrap;
      align-items: center;
      gap: var(--space-3);
    }
  }

  &__input {
    flex: 1 1 120px;
    min-width: 0;
    padding: 9px var(--space-3);
    border: 1px solid var(--clr-border);
    border-radius: var(--radius-sm);
    outline: none;
    font-size: var(--font-size-sm);
    color: #1f2937;
    background-color: #fff;

    &::placeholder { color: var(--clr-text-muted); }
  }

  &__btn {
    flex-shrink: 0;
    background-color: #e1ac0c;
    color: #fff;
    padding: 9px var(--space-4);
    border-radius: var(--radius-sm);
    border: none;
    cursor: pointer;
    font-size: var(--font-size-sm);
    white-space: nowrap;
    transition: background-color var(--transition-base);

    &:hover { background-color: #c8960a; }
  }
}

/* ============================================================
   DESTINATIONS
   ============================================================ */
.destinations {
  padding: var(--space-12) var(--px-mobile);

  @media (min-width: 640px)  { padding: var(--space-16) var(--px-sm); }
  @media (min-width: 1024px) { padding: var(--space-24) var(--px-md); }

  &__grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: var(--space-3);

    @media (min-width: 480px)  { grid-template-columns: repeat(3, 1fr); gap: var(--space-4); }
    @media (min-width: 1024px) { grid-template-columns: repeat(5, 1fr); gap: var(--space-5); }
  }
}

.dest-card {
  height: 150px;
  border-radius: var(--radius-sm);
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: var(--space-3);
  background-size: cover;
  background-position: center;
  transition: transform var(--transition-card);
  cursor: pointer;

  @media (min-width: 480px)  { height: 180px; }
  @media (min-width: 1024px) { height: 210px; padding: var(--space-5); }

  &:hover { transform: scale(1.08); }

  &--istanbul  { background-image: url(./assets/images/istanbul.png); }
  &--sharm     { background-image: url(./assets/images/sharm.png); }
  &--tailand   { background-image: url(./assets/images/Tailand.png); }
  &--argentina { background-image: url(./assets/images/Argentina.png); }
  &--dubai     { background-image: url(./assets/images/dubai2.png); }

  &--wide {
    grid-column: span 2;

    @media (min-width: 480px)  { grid-column: span 1; }
  }

  &__name {
    font-size: var(--font-size-base);
    color: #fff;
    font-weight: var(--font-weight-semi);
    margin: 0 0 var(--space-1);

    @media (min-width: 640px)  { font-size: var(--font-size-md); }
    @media (min-width: 1024px) { font-size: var(--font-size-lg); }
  }

  &__count {
    color: #fff;
    font-size: var(--font-size-xs);
    margin: 0;

    @media (min-width: 640px) { font-size: var(--font-size-sm); }
  }
}

/* ============================================================
   EXPLORE
   ============================================================ */
.explore {
  padding: var(--space-6) var(--px-mobile) var(--space-8);

  @media (min-width: 640px)  { padding: var(--space-8) var(--px-sm); }
  @media (min-width: 1024px) { padding: var(--space-8) var(--px-lg); }

  &__title {
    font-size: var(--font-size-lg);
    font-weight: var(--font-weight-semi);
    margin-bottom: var(--space-6);
    color: var(--clr-text);

    @media (min-width: 640px)  { font-size: var(--font-size-2xl); }
    @media (min-width: 1024px) { font-size: var(--font-size-2xl); }
  }

  &__item {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
    padding-bottom: var(--space-6);
    border-bottom: 1px solid var(--clr-border);
    margin-bottom: var(--space-6);
    transition: transform var(--transition-card);

    @media (min-width: 540px)  { flex-direction: row; gap: var(--space-6); }
    @media (min-width: 1024px) { gap: var(--space-8); }

    &:hover { transform: scale(1.02); }

    &:last-of-type { border-bottom: none; margin-bottom: 0; }
  }

  &__img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    border-radius: var(--radius-xl);
    flex-shrink: 0;

    @media (min-width: 540px)  { width: 200px; height: 160px; }
    @media (min-width: 1024px) { width: 280px; height: 200px; }
  }

  &__body { flex: 1; min-width: 0; }

  &__item-title {
    font-size: var(--font-size-lg);
    font-weight: var(--font-weight-semi);
    line-height: 1.3;
    margin: 0 0 var(--space-1);
    color: var(--clr-text);

    @media (min-width: 640px)  { font-size: var(--font-size-xl); }
    @media (min-width: 1024px) { font-size: var(--font-size-2xl); }
  }

  &__region {
    font-size: var(--font-size-sm);
    color: var(--clr-text-muted);
    margin: 0 0 var(--space-2);
  }

  &__desc {
    font-size: var(--font-size-xs);
    line-height: 22px;
    color: var(--clr-text-faint);
    margin: 0;
    text-align: justify;

    @media (min-width: 640px) { font-size: var(--font-size-sm); line-height: 24px; }
  }
}

/* ============================================================
   CARDS SECTION
   ============================================================ */
.cards-section {
  padding-top: var(--space-16);

  &__inner {
    background-color: var(--clr-bg-muted);
    padding: var(--space-16) var(--px-mobile);
    transition: background-color var(--transition-base);

    @media (min-width: 640px)  { padding: var(--space-20) var(--px-sm); }
    @media (min-width: 1024px) { padding: var(--space-20) var(--px-lg); }
  }

  &__header {
    text-align: center;
    margin-bottom: var(--space-8);

    @media (min-width: 640px) { margin-bottom: var(--space-10); }
  }
}

.cards-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-6);
  justify-items: center;

  @media (min-width: 540px)  { grid-template-columns: repeat(2, 1fr); }
  @media (min-width: 1024px) { grid-template-columns: repeat(3, 1fr); }
}

.tour-card {
  width: 100%;
  max-width: 360px;
  background-color: var(--clr-surface);
  box-shadow: 0 4px 6px var(--clr-shadow);
  border-radius: var(--radius-md);
  overflow: hidden;
  transition: transform var(--transition-card), background-color var(--transition-base);

  &:hover { transform: scale(1.05); }

  &--wide {
    @media (min-width: 540px)  { grid-column: span 2; max-width: 360px; }
    @media (min-width: 1024px) { grid-column: span 1; }
  }

  &__img {
    width: 100%;
    height: 200px;
    background-size: cover;
    background-position: center;
    display: flex;
    align-items: flex-start;
    padding: var(--space-2);

    &--dubai  { background-image: url(./assets/images/dubai.png); }
    &--turkey { background-image: url(./assets/images/istanbul.png); }
    &--sharm  { background-image: url(./assets/images/sharm2.png); }
  }

  &__stars { display: flex; gap: 2px; }

  &__body {
    padding: var(--space-3);
    border-bottom: 1px solid var(--clr-border);
  }

  &__name {
    font-size: var(--font-size-sm);
    font-weight: var(--font-weight-medium);
    margin: 0 0 var(--space-1);
    color: var(--clr-text);
  }

  &__tag {
    color: var(--clr-accent);
    font-size: var(--font-size-xs);
    margin: 0 0 var(--space-3);
  }

  &__desc {
    font-size: var(--font-size-xs);
    color: var(--clr-text-muted);
    line-height: 22px;
    margin: 0;
  }

  &__actions { display: flex; }

  &__action {
    color: var(--clr-text-faint);
    width: 50%;
    padding: var(--space-3);
    font-size: var(--font-size-xs);
    text-align: center;
    text-decoration: none;
    transition: color var(--transition-slow);

    &:first-child { border-right: 1px solid var(--clr-border); }
    &:hover { color: var(--clr-accent); }
  }
}

/* ============================================================
   SERVICES
   ============================================================ */
.services {
  padding: var(--space-16) var(--px-mobile) 0;

  @media (min-width: 640px)  { padding: var(--space-20) var(--px-sm) 0; }
  @media (min-width: 1024px) { padding: var(--space-20) var(--px-md) 0; }

  &__header {
    text-align: center;
    margin-bottom: var(--space-8);
  }

  &__grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--space-6);
    max-width: 1300px;
    margin: 0 auto;

    @media (min-width: 540px)  { grid-template-columns: repeat(2, 1fr); }
    @media (min-width: 1024px) { grid-template-columns: repeat(3, 1fr); }
  }
}

.service-card {
  background-color: var(--clr-surface);
  border: 1px solid var(--clr-border);
  box-shadow: 0 4px 6px var(--clr-shadow);
  border-radius: var(--radius-lg);
  padding: var(--space-6);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  transition: transform var(--transition-card), background-color var(--transition-base);

  @media (min-width: 640px) { padding: var(--space-8); }

  &:hover { transform: scale(1.06); }

  &__icon {
    width: 72px;
    height: 72px;

    &-img { width: 100%; height: 100%; object-fit: contain; }
  }

  &__body { margin-top: var(--space-5); }

  &__title {
    font-size: var(--font-size-md);
    font-weight: var(--font-weight-medium);
    margin: 0 0 var(--space-3);
    color: var(--clr-text);

    @media (min-width: 640px)  { font-size: var(--font-size-lg); }
    @media (min-width: 1024px) { font-size: var(--font-size-xl); }
  }

  &__desc {
    font-size: var(--font-size-sm);
    color: var(--clr-text-muted);
    line-height: 24px;
    margin: 0;
  }
}

/* ============================================================
   DREAM TRIP
   ============================================================ */
.dream-trip {
  text-align: center;
  padding: var(--space-16) var(--px-mobile);
  max-width: 672px;
  margin: 0 auto;

  @media (min-width: 640px)  { padding: var(--space-20) var(--px-sm); }
  @media (min-width: 1024px) { padding: var(--space-20) var(--px-md); }

  &__title {
    font-size: var(--font-size-xl);
    font-weight: var(--font-weight-semi);
    margin-bottom: var(--space-4);
    color: var(--clr-text);

    @media (min-width: 640px) { font-size: var(--font-size-2xl); }
  }

  &__desc {
    font-size: var(--font-size-sm);
    color: var(--clr-text-muted);
    line-height: var(--line-height-body);
    margin-bottom: var(--space-6);

    @media (min-width: 640px) { font-size: var(--font-size-base); }
  }
}

/* ============================================================
   PLANS
   ============================================================ */
.plans {
  padding: 0 var(--px-mobile) var(--space-16);

  @media (min-width: 640px)  { padding: 0 var(--px-sm) var(--space-20); }
  @media (min-width: 1024px) { padding: 0 var(--px-md) var(--space-20); }

  &__header {
    text-align: center;
    margin: var(--space-10) 0 var(--space-8);

    @media (min-width: 640px) { margin: var(--space-20) 0 var(--space-10); }
  }

  &__grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--space-6);
    max-width: 1300px;
    margin: 0 auto;

    @media (min-width: 540px)  { grid-template-columns: repeat(2, 1fr); }
    @media (min-width: 1024px) { grid-template-columns: repeat(3, 1fr); }
  }
}

.plan-card {
  background-color: var(--clr-plan-bg);
  box-shadow: 0 4px 6px var(--clr-shadow);
  border-radius: var(--radius-md);
  overflow: hidden;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: transform var(--transition-card), background-color var(--transition-base);

  &:hover { transform: scale(1.04); }

  &__top {
    width: 100%;
    background-color: var(--clr-accent);
    padding: var(--space-5);
    text-align: center;
  }

  &__label {
    color: #fff;
    font-size: var(--font-size-md);
    margin: 0 0 var(--space-2);

    @media (min-width: 640px) { font-size: var(--font-size-lg); }
  }

  &__price {
    color: #fff;
    font-size: var(--font-size-xl);
    font-weight: var(--font-weight-bold);
    margin: 0;

    @media (min-width: 640px) { font-size: var(--font-size-2xl); }
  }

  &__period {
    color: #fff;
    font-size: var(--font-size-base);
    margin: var(--space-1) 0 0;
  }

  &__body {
    padding: var(--space-6) var(--space-4);
    text-align: center;
    width: 100%;

    @media (min-width: 640px) { padding: var(--space-8) var(--space-4); }
  }

  &__features {
    list-style: none;
    padding: 0;
    margin: 0 0 var(--space-6);
    display: flex;
    flex-direction: column;
    gap: var(--space-2);
  }

  &__feature {
    font-size: var(--font-size-sm);
    color: var(--clr-text);

    @media (min-width: 640px) { font-size: var(--font-size-base); }
  }

  &__btn {
    min-width: 120px;
  }
}

/* ============================================================
   MAP
   ============================================================ */
.map-section {
  width: 100%;
  height: 260px;
  overflow: hidden;
  box-shadow: 0 4px 6px var(--clr-shadow);
  margin-top: var(--space-10);

  @media (min-width: 640px)  { height: 360px; }
  @media (min-width: 1024px) { height: 440px; }

  iframe { display: block; }
}

/* ============================================================
   CTA SECTION
   ============================================================ */
.cta-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: var(--space-10) var(--px-mobile);
  background-color: var(--clr-surface);
  transition: background-color var(--transition-base);

  @media (min-width: 640px) { padding: var(--space-16) var(--px-sm); }

  &__label {
    color: var(--clr-accent);
    font-size: var(--font-size-sm);
    font-weight: var(--font-weight-medium);
    letter-spacing: 0.05em;
    margin-bottom: var(--space-2);
  }

  &__title {
    color: var(--clr-text);
    font-size: var(--font-size-lg);
    margin-bottom: var(--space-3);

    @media (min-width: 640px) { font-size: var(--font-size-xl); }
    @media (min-width: 768px) { font-size: var(--font-size-2xl); }
  }

  &__director {
    font-size: var(--font-size-sm);
    color: var(--clr-text-muted);
    margin-bottom: var(--space-2);

    @media (min-width: 640px) { font-size: var(--font-size-base); }
  }

  &__phone {
    display: block;
    color: var(--clr-accent);
    font-size: var(--font-size-lg);
    font-weight: var(--font-weight-bold);
    letter-spacing: 0.05em;
    text-decoration: none;
    margin-bottom: var(--space-6);
    transition: color var(--transition-base);

    @media (min-width: 640px) { font-size: var(--font-size-xl); }
    @media (min-width: 768px) { font-size: var(--font-size-2xl); }

    &:hover { color: var(--clr-accent-hover); }
  }
}

/* ============================================================
   FOOTER
   ============================================================ */
.footer {
  background-color: var(--clr-surface);
  padding: var(--space-10) var(--px-mobile);
  transition: background-color var(--transition-base);

  @media (min-width: 640px)  { padding: var(--space-16) var(--px-sm); }
  @media (min-width: 1024px) { padding: var(--space-24) var(--px-md); }

  &__grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--space-8);

    @media (min-width: 540px)  { grid-template-columns: repeat(2, 1fr); }
    @media (min-width: 1024px) { grid-template-columns: repeat(3, 1fr); gap: var(--space-10); }
  }

  &__brand {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
  }

  &__logo {
    max-width: 150px;

    @media (min-width: 640px) { max-width: 170px; }
  }

  &__brand-desc {
    font-size: var(--font-size-sm);
    color: var(--clr-text-faint);
    margin: 0;
  }

  &__social {
    display: block;
    width: fit-content;
    color: var(--clr-text);
    transition: transform var(--transition-base), color var(--transition-base);

    &:hover { transform: scale(1.15); color: var(--clr-accent); }
  }

  /* nav links */
  &__links-title {
    font-size: var(--font-size-md);
    font-weight: var(--font-weight-semi);
    color: var(--clr-text);
    margin: 0 0 var(--space-4);
  }

  &__links-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: var(--space-3);
  }

  &__link {
    display: flex;
    align-items: center;
    color: var(--clr-text-muted);
    font-weight: var(--font-weight-medium);
    font-size: var(--font-size-sm);
    text-decoration: none;
    transition: color var(--transition-base);

    @media (min-width: 640px) { font-size: var(--font-size-base); }

    &:hover { color: var(--clr-accent); }
  }

  &__link-dot {
    width: 9px;
    height: 9px;
    background-color: var(--clr-accent);
    margin-right: var(--space-3);
    flex-shrink: 0;
    display: block;
    border-radius: 1px;
  }

  /* contact */
  &__contact-title {
    font-size: var(--font-size-lg);
    font-weight: var(--font-weight-semi);
    color: var(--clr-text);
    margin: 0 0 var(--space-4);

    @media (min-width: 640px) { font-size: var(--font-size-xl); }
  }

  &__contact-desc {
    color: var(--clr-text-muted);
    font-size: var(--font-size-sm);
    line-height: var(--line-height-body);
    margin: 0 0 var(--space-6);
    font-style: normal;

    @media (min-width: 640px) { font-size: var(--font-size-base); }
  }

  &__contact-list {
    display: flex;
    flex-direction: column;
    gap: var(--space-3);
    font-size: var(--font-size-sm);
    font-style: normal;

    @media (min-width: 640px) { font-size: var(--font-size-base); }
  }

  &__contact-item {
    display: flex;
    align-items: flex-start;
    gap: var(--space-2);
    margin: 0;
  }

  &__contact-label {
    color: var(--clr-text-muted);
    min-width: 64px;
    flex-shrink: 0;
  }

  &__contact-value {
    color: var(--clr-accent);
    text-decoration: none;
    word-break: break-word;
  }
}
</style>