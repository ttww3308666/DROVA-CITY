<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>DC CITY | دي سي سيتي - مجتمع الحياة الواقعية</title>
  <!-- خط Inter وخطوط عربية واضحة -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800;900&family=Inter:wght@400;600;700;800;900&display=swap" rel="stylesheet" />
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Cairo', 'Inter', 'sans-serif'],
            display: ['Inter', 'Cairo', 'sans-serif'],
          },
          colors: {
            dcYellow: '#FFE600',
            dcGold: '#FACC15',
            dcAmber: '#EAB308',
            dcDark: '#090A0D',
            dcCard: '#111318',
            dcBorder: '#232732',
          },
          boxShadow: {
            yellowGlow: '0 0 25px rgba(255, 230, 0, 0.28)',
            yellowStrong: '0 0 40px rgba(255, 230, 0, 0.42)',
          },
        },
      },
    };
  </script>
  <style>
    /* تنسيقات إضافية للخلفية، التدرجات، والحركة السلسة */
    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: #090a0d;
      color: #f3f4f6;
      font-family: 'Cairo', 'Inter', sans-serif;
      overflow-x: hidden;
    }

    /* خلفية المدينة الخفيفة في الخلف */
    .city-bg-layer {
      background-image:
        radial-gradient(circle at 50% 20%, rgba(255, 230, 0, 0.08), transparent 55%),
        linear-gradient(to bottom, rgba(9, 10, 13, 0.88), rgba(9, 10, 13, 0.96));
    }

    .skyline-svg {
      opacity: 0.14;
      filter: blur(0.4px);
      pointer-events: none;
    }

    /* شارة DC CITY الصفراء اللامعة مع خط فوق كلمة CITY الصغيرة */
    .dc-emblem-box {
      background: radial-gradient(circle at 30% 25%, #fff275 0%, #ffe600 42%, #eab308 82%, #a16207 100%);
      box-shadow:
        0 0 26px rgba(255, 230, 0, 0.45),
        inset 0 2px 6px rgba(255, 255, 255, 0.7),
        inset 0 -4px 10px rgba(120, 53, 15, 0.55);
    }

    .dc-letters {
      font-family: 'Inter', sans-serif;
      font-weight: 900;
      letter-spacing: -0.06em;
      color: #090a0d;
      text-shadow: 0 1px 0 rgba(255, 255, 255, 0.45);
    }

    .dc-city-line {
      width: 56%;
      height: 1.5px;
      background: linear-gradient(90deg, transparent, #090a0d 25%, #090a0d 75%, transparent);
      margin: 1px auto 2px auto;
    }

    .dc-city-small {
      font-family: 'Inter', sans-serif;
      font-size: 0.55rem;
      font-weight: 800;
      letter-spacing: 0.24em;
      color: #090a0d;
      line-height: 1;
      text-transform: uppercase;
    }

    /* حركة الأكورديون للقوانين */
    .accordion-content {
      display: grid;
      grid-template-rows: 0fr;
      transition: grid-template-rows 0.3s ease;
    }

    .accordion-item.open .accordion-content {
      grid-template-rows: 1fr;
    }

    .accordion-inner {
      overflow: hidden;
    }

    .accordion-chevron {
      transition: transform 0.25s ease;
    }

    .accordion-item.open .accordion-chevron {
      transform: rotate(180deg);
    }
  </style>
</head>
<body class="min-h-screen flex flex-col relative selection:bg-dcYellow selection:text-black">

  <!-- طبقة خلفية المدينة الخفيفة -->
  <div class="fixed inset-0 z-0 city-bg-layer pointer-events-none">
    <svg class="w-full h-full skyline-svg" viewBox="0 0 1440 700" preserveAspectRatio="xMidYMax slice" fill="none" xmlns="http://www.w3.org/2000/svg">
      <!-- أفق مدينة خفيف وهادئ -->
      <path d="M0 700V430H65V350H125V470H180V290H255V395H310V230H395V440H455V320H530V480H585V210H675V360H735V265H825V415H890V310H975V450H1035V245H1125V380H1185V330H1275V460H1340V280H1440V700H0Z" fill="#FFE600" fill-opacity="0.22"/>
      <path d="M0 700V510H90V455H160V535H240V410H335V520H420V440H515V545H610V390H705V505H800V435H895V530H995V420H1090V525H1195V450H1290V540H1375V470H1440V700H0Z" fill="#FACC15" fill-opacity="0.16"/>
      <!-- نوافذ مباني خفيفة -->
      <g fill="#FFE600" fill-opacity="0.28">
        <rect x="200" y="315" width="8" height="12" rx="1"/>
        <rect x="218" y="315" width="8" height="12" rx="1"/>
        <rect x="200" y="340" width="8" height="12" rx="1"/>
        <rect x="330" y="255" width="8" height="12" rx="1"/>
        <rect x="350" y="255" width="8" height="12" rx="1"/>
        <rect x="330" y="280" width="8" height="12" rx="1"/>
        <rect x="610" y="235" width="9" height="13" rx="1"/>
        <rect x="632" y="235" width="9" height="13" rx="1"/>
        <rect x="610" y="262" width="9" height="13" rx="1"/>
        <rect x="1060" y="270" width="8" height="12" rx="1"/>
        <rect x="1080" y="270" width="8" height="12" rx="1"/>
        <rect x="1060" y="295" width="8" height="12" rx="1"/>
      </g>
    </svg>
  </div>

  <!-- شريط التنقل العلوي -->
  <header class="sticky top-0 z-40 w-full backdrop-blur-xl bg-dcDark/85 border-b border-dcBorder/90">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-18 py-3 gap-4">
        <!-- هوية الشعار -->
        <a href="#home" class="flex items-center gap-3 group shrink-0">
          <div class="w-12 h-12 rounded-full dc-emblem-box flex flex-col items-center justify-center p-1 transition-transform duration-300 group-hover:scale-105">
            <span class="dc-letters text-base leading-none">DC</span>
            <span class="dc-city-line"></span>
            <span class="dc-city-small">CITY</span>
          </div>
          <div class="flex flex-col">
            <span class="text-lg font-extrabold tracking-wide text-white group-hover:text-dcYellow transition-colors">
              DC CITY
            </span>
            <span class="text-[11px] text-gray-400">دي سي سيتي • حياة واقعية</span>
          </div>
        </a>

        <!-- روابط التنقل للشاشات الكبيرة -->
        <nav class="hidden lg:flex items-center gap-1 xl:gap-2 text-sm font-bold">
          <a href="#home" class="px-3 py-2 rounded-xl text-gray-200 hover:text-dcYellow hover:bg-white/5 transition">الرئيسية</a>
          <a href="#rules" class="px-3 py-2 rounded-xl text-gray-200 hover:text-dcYellow hover:bg-white/5 transition">القوانين</a>
          <a href="#store" class="px-3 py-2 rounded-xl text-gray-200 hover:text-dcYellow hover:bg-white/5 transition">المتجر</a>
          <a href="#jobs" class="px-3 py-2 rounded-xl text-gray-200 hover:text-dcYellow hover:bg-white/5 transition">تقديم وظائف</a>

          <!-- قائمة السيرفرات المنسدلة -->
          <div class="relative" id="serversDropdownWrapper">
            <button
              type="button"
              id="serversDropdownBtn"
              aria-expanded="false"
              class="flex items-center gap-1.5 px-3 py-2 rounded-xl text-gray-200 hover:text-dcYellow hover:bg-white/5 transition"
            >
              <span>السيرفرات</span>
              <svg class="w-4 h-4 transition-transform duration-200" id="serversChevron" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div
              id="serversDropdownMenu"
              class="hidden absolute right-0 mt-2 w-56 rounded-2xl bg-dcCard border border-dcBorder shadow-2xl p-2 space-y-1 z-50"
            >
              <a
                href="https://discord.gg/YOUR_FIGHTS_INVITE"
                target="_blank"
                rel="noopener noreferrer"
                class="flex items-center justify-between px-3.5 py-2.5 rounded-xl text-sm text-gray-200 hover:bg-dcYellow/15 hover:text-dcYellow transition"
              >
                <span>سيرفر الفايتات</span>
                <span class="text-xs px-2 py-0.5 rounded-md bg-dcYellow/20 text-dcYellow">Discord</span>
              </a>
              <a
                href="https://discord.gg/YOUR_GANGS_RP_INVITE"
                target="_blank"
                rel="noopener noreferrer"
                class="flex items-center justify-between px-3.5 py-2.5 rounded-xl text-sm text-gray-200 hover:bg-dcYellow/15 hover:text-dcYellow transition"
              >
                <span>سيرفر العصابات RP</span>
                <span class="text-xs px-2 py-0.5 rounded-md bg-dcYellow/20 text-dcYellow">RP</span>
              </a>
            </div>
          </div>

          <a href="#founders" class="px-3 py-2 rounded-xl text-gray-200 hover:text-dcYellow hover:bg-white/5 transition">المؤسسين</a>
          <a href="#activation" class="mr-1 px-4 py-2 rounded-xl bg-dcYellow text-black font-extrabold hover:bg-dcGold shadow-yellowGlow transition">
            التفعيل
          </a>
        </nav>

        <!-- زر قائمة الجوال -->
        <button
          type="button"
          id="mobileMenuBtn"
          aria-label="فتح القائمة"
          aria-expanded="false"
          class="lg:hidden p-2.5 rounded-xl bg-dcCard border border-dcBorder text-dcYellow hover:bg-white/5 transition"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
        </button>
      </div>

      <!-- قائمة الجوال المنسدلة -->
      <div id="mobileMenu" class="hidden lg:hidden pb-4 pt-2 border-t border-dcBorder/70 space-y-1.5 text-sm font-bold">
        <a href="#home" class="mobile-nav-link block px-4 py-2.5 rounded-xl text-gray-200 hover:bg-white/5 hover:text-dcYellow">الرئيسية</a>
        <a href="#rules" class="mobile-nav-link block px-4 py-2.5 rounded-xl text-gray-200 hover:bg-white/5 hover:text-dcYellow">القوانين</a>
        <a href="#store" class="mobile-nav-link block px-4 py-2.5 rounded-xl text-gray-200 hover:bg-white/5 hover:text-dcYellow">المتجر</a>
        <a href="#jobs" class="mobile-nav-link block px-4 py-2.5 rounded-xl text-gray-200 hover:bg-white/5 hover:text-dcYellow">تقديم وظائف</a>

        <div class="px-4 py-2 rounded-xl bg-dcCard/80 border border-dcBorder/70 space-y-1.5">
          <div class="text-xs text-dcYellow font-extrabold">السيرفرات</div>
          <a href="https://discord.gg/YOUR_FIGHTS_INVITE" target="_blank" rel="noopener noreferrer" class="block py-1.5 text-gray-300 hover:text-dcYellow">• سيرفر الفايتات</a>
          <a href="https://discord.gg/YOUR_GANGS_RP_INVITE" target="_blank" rel="noopener noreferrer" class="block py-1.5 text-gray-300 hover:text-dcYellow">• سيرفر العصابات RP</a>
        </div>

        <a href="#founders" class="mobile-nav-link block px-4 py-2.5 rounded-xl text-gray-200 hover:bg-white/5 hover:text-dcYellow">المؤسسين</a>
        <a href="#activation" class="mobile-nav-link block px-4 py-2.5 rounded-xl bg-dcYellow text-black text-center font-extrabold">التفعيل</a>
      </div>
    </div>
  </header>

  <main class="relative z-10 flex-1">
    <!-- 1. القسم الرئيسي (Hero Section) -->
    <section id="home" class="pt-14 pb-20 sm:pt-20 sm:pb-24 px-4 sm:px-6 lg:px-8">
      <div class="max-w-5xl mx-auto text-center">
        <!-- الشعار الدائري الأصفر المميز -->
        <div class="mx-auto mb-8 w-36 h-36 sm:w-44 sm:h-44 rounded-full p-2 border-2 border-dcYellow/60 bg-dcDark/80 shadow-yellowStrong flex items-center justify-center">
          <div class="w-full h-full rounded-full dc-emblem-box flex flex-col items-center justify-center px-3">
            <span class="dc-letters text-4xl sm:text-5xl leading-none">DC</span>
            <span class="w-16 sm:w-20 h-[2px] bg-black/80 my-1.5 rounded-full"></span>
            <span class="font-display text-[11px] sm:text-xs font-black tracking-[0.28em] text-black leading-none">
              CITY
            </span>
          </div>
        </div>

        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-dcYellow/10 border border-dcYellow/30 text-dcYellow text-xs sm:text-sm font-bold mb-5">
          <span>مجتمع رول بلاي متكامل</span>
          <span>•</span>
          <span>DC CITY</span>
        </div>

        <h1 class="text-4xl sm:text-6xl font-black tracking-tight text-white mb-5">
          مرحبًا بك في <span class="text-dcYellow">DC CITY</span>
        </h1>

        <p class="max-w-2xl mx-auto text-base sm:text-lg text-gray-300 leading-relaxed mb-9">
          سيرفر <strong class="text-white">دي سي سيتي</strong> مجتمع متكامل يهدف لتقديم تجربة حياة واقعية احترافية وممتعة، نركز فيها على جودة التمثيل والعدالة وبناء سيناريوهات مترابطة لجميع اللاعبين.
        </p>

        <!-- أزرار التواصل بروابط قابلة للتعديل -->
        <div class="flex flex-wrap items-center justify-center gap-4">
          <a
            href="https://discord.gg/YOUR_DISCORD_INVITE"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center gap-3 px-6 py-3.5 rounded-2xl bg-dcYellow text-black font-extrabold text-sm sm:text-base hover:bg-dcGold shadow-yellowGlow transition transform hover:-translate-y-0.5"
          >
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994.021-.041.001-.09-.041-.106a13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.028zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/>
            </svg>
            <span>سيرفر الديسكورد</span>
          </a>

          <a
            href="https://x.com/YOUR_DC_CITY_HANDLE"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center gap-3 px-6 py-3.5 rounded-2xl bg-dcCard border border-dcBorder text-white font-bold text-sm sm:text-base hover:border-dcYellow hover:text-dcYellow transition"
          >
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
              <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
            </svg>
            <span>حسابنا في X</span>
          </a>
        </div>
      </div>
    </section>

    <!-- 2. قسم التفعيل (Activation) -->
    <section id="activation" class="py-16 sm:py-20 px-4 sm:px-6 lg:px-8 border-t border-dcBorder/60">
      <div class="max-w-4xl mx-auto">
        <div class="text-center mb-10">
          <span class="text-xs font-extrabold uppercase tracking-widest text-dcYellow">Activation</span>
          <h2 class="text-3xl sm:text-4xl font-black text-white mt-1">التفعيل والشروط العامة</h2>
          <div class="w-20 h-1 bg-dcYellow mx-auto mt-3 rounded-full"></div>
        </div>

        <div class="rounded-3xl bg-dcCard/95 border border-dcBorder p-6 sm:p-8 shadow-xl space-y-6">
          <div>
            <h3 class="text-xl font-extrabold text-dcYellow mb-4 flex items-center gap-2">
              <span class="w-2.5 h-2.5 rounded-full bg-dcYellow"></span>
              <span>الشروط العامة لدخول السيرفر</span>
            </h3>
            <ul class="space-y-3 text-gray-200 text-sm sm:text-base leading-relaxed">
              <li class="flex items-start gap-3 p-3 rounded-2xl bg-dcDark/70 border border-dcBorder/70">
                <span class="text-dcYellow font-black">01</span>
                <span>العمر المسموح لدخول السيرفر: 13 سنة فما فوق.</span>
              </li>
              <li class="flex items-start gap-3 p-3 rounded-2xl bg-dcDark/70 border border-dcBorder/70">
                <span class="text-dcYellow font-black">02</span>
                <span>ممنوع استخدام أي شخصية افتراضية إلا من خلال المتجر فقط.</span>
              </li>
              <li class="flex items-start gap-3 p-3 rounded-2xl bg-dcDark/70 border border-dcBorder/70">
                <span class="text-dcYellow font-black">03</span>
                <span>ممنوع كتابة اسمك باللغة الإنجليزية أو برموز أو تشكيل أو يكون اسم شخصية مشهورة.</span>
              </li>
              <li class="flex items-start gap-3 p-3 rounded-2xl bg-dcDark/70 border border-dcBorder/70">
                <span class="text-dcYellow font-black">04</span>
                <span>يمنع الدخول من أجهزة غير جهازك الشخصي.</span>
              </li>
              <li class="flex items-start gap-3 p-3 rounded-2xl bg-dcDark/70 border border-dcBorder/70">
                <span class="text-dcYellow font-black">05</span>
                <span>يحق لك امتلاك شخصتين فقط.</span>
              </li>
            </ul>
          </div>

          <!-- أزرار الموافقة / عدم الموافقة -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-2">
            <button
              type="button"
              id="agreeRulesBtn"
              class="flex items-center justify-center gap-3 p-4 rounded-2xl bg-dcYellow text-black font-extrabold hover:bg-dcGold shadow-yellowGlow transition cursor-pointer"
            >
              <span class="w-6 h-6 rounded-full bg-black text-dcYellow flex items-center justify-center text-sm font-black">✓</span>
              <span>الموافقة على الشروط</span>
            </button>

            <button
              type="button"
              id="disagreeRulesBtn"
              class="flex items-center justify-center gap-3 p-4 rounded-2xl bg-dcDark border border-dcBorder text-gray-200 font-bold hover:border-red-500/60 hover:text-red-400 transition cursor-pointer"
            >
              <span class="w-6 h-6 rounded-full bg-red-500/20 text-red-400 flex items-center justify-center text-sm font-black">✕</span>
              <span>غير موافق على الشروط</span>
            </button>
          </div>

          <!-- صندوق الحالة والنموذج التفاعلي للتفعيل -->
          <div id="activationFeedback" class="hidden rounded-2xl p-5 border transition-all"></div>
        </div>
      </div>
    </section>

    <!-- 3. قسم قوانين السيرفر (Laws & Rules) -->
    <section id="rules" class="py-16 sm:py-20 px-4 sm:px-6 lg:px-8 border-t border-dcBorder/60">
      <div class="max-w-5xl mx-auto">
        <div class="text-center mb-10">
          <span class="text-xs font-extrabold uppercase tracking-widest text-dcYellow">Server Rules</span>
          <h2 class="text-3xl sm:text-4xl font-black text-white mt-1">قوانين السيرفر</h2>
          <p class="text-gray-400 text-sm sm:text-base mt-2">اضغط على أي قانون لعرض التفاصيل الكاملة والالتزام بها داخل المدينة</p>
          <div class="w-20 h-1 bg-dcYellow mx-auto mt-3 rounded-full"></div>
        </div>

        <div class="space-y-4" id="rulesAccordion">
          <!-- NLR -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow font-display text-xs font-extrabold">NLR</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">قوانين الحياة الجديدة - NLR</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4">
                في حال إغمائك بشكل كامل لا يمكنك الكلام أو الحركة أو فعل أي شيء. في حال تم إسقاطك من قبل شخص وتم إنعاشك من قبل المسعفين تستطيع تذكر جميع الأحداث، أما في حال تم إعطاؤك إبرة "في العيادة الخاصة" من أحد اللاعبين الذين لديهم عداوة معك فلا تستطيع تذكر أي شيء حصل لك (ومنها العداوات أو الأحداث).
              </div>
            </div>
          </div>

          <!-- PowerGaming -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow font-display text-xs font-extrabold">PG</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">الباور جيمنج - PowerGaming</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4">
                استخدام وسائل أو تصرفات غير منطقية أو غير موجودة في اللعبة للحصول على ميزة غير عادلة، أو عدم التوافق مع العالم بطريقة معقولة وواقعية ضمن سيناريوهات الرول بلاي.
              </div>
            </div>
          </div>

          <!-- NVL -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow font-display text-xs font-extrabold">NVL</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">الخوف على الحياة - NVL</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4">
                عدم الخوف بشكل واقعي على حياتك عندما تتعرض للتهديد بالأسلحة أو بأذى شديد من وسائل أخرى يُعد مخالفة؛ إذ يجب تقدير خطورة الموقف والاستجابة بما يتوافق مع طبيعة الخطر الحقيقي.
              </div>
            </div>
          </div>

          <!-- Metagaming -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow font-display text-xs font-extrabold">MG</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">الميتا جيمنج - Metagaming</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4">
                أي معلومة تحصل عليها من خارج المدينة (مثل بث مباشر، ديسكورد، أو مقطع فيديو) وتستخدمها داخل الرول بلاي تُعد مخالفة صريحة.
              </div>
            </div>
          </div>

          <!-- RDM -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow font-display text-xs font-extrabold">RDM</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">القتل العشوائي - RDM</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4">
                قتل الأشخاص دون سبب واضح أو تهديد مسبق أو عداوة مبنية داخل الرول بلاي، أو القتل بصورة عشوائية ممنوع ومخالف للنظام العام للسيرفر.
              </div>
            </div>
          </div>

          <!-- تقدير الحياة -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow text-xs font-extrabold">تقدير الحياة</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">قانون تقدير الحياة - DC CITY</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4">
                الحفاظ على حياتك وحياة الآخرين، وعدم التهور أو الاستهانة بقتل الأشخاص، وعدم مقاومة المجرم أو الشرطة أو أي شخص يحمل سلاحًا خصوصًا إذا كنت أعزل، مع ضرورة التفاوض والحوار الجيد قبل أي تصعيد يعرض حياة الآخرين للخطر.
              </div>
            </div>
          </div>

          <!-- القوانين العامة والشروط -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow text-xs font-extrabold">عام</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">القوانين العامة والشروط</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4 space-y-5">
                <div>
                  <h4 class="font-extrabold text-dcYellow mb-2">📌 شروط عامة</h4>
                  <ul class="list-disc pr-5 space-y-1.5">
                    <li>العمر المسموح لدخول السيرفر: 13 سنة فما فوق.</li>
                    <li>ممنوع استخدام أي شخصية افتراضية إلا من خلال المتجر فقط.</li>
                    <li>ممنوع كتابة اسمك باللغة الإنجليزية أو برموز أو تشكيل أو يكون اسم شخصية مشهورة.</li>
                    <li>يمنع الدخول من أجهزة غير جهازك الشخصي.</li>
                    <li>يحق لك امتلاك شخصتين فقط.</li>
                  </ul>
                </div>
                <div>
                  <h4 class="font-extrabold text-dcYellow mb-2">🎥 اللعب والبث</h4>
                  <ul class="list-disc pr-5 space-y-1.5">
                    <li>ممنوع الستريم سنايب أو متابعة البثوث أثناء اللعب (عقوبتها شديدة).</li>
                    <li>ممنوع التواجد في الديسكورد أو التواصل الخارجي مع لاعبين آخرين أثناء اللعب.</li>
                  </ul>
                </div>
                <div>
                  <h4 class="font-extrabold text-dcYellow mb-2">💼 القوانين العامة داخل السيرفر</h4>
                  <ul class="list-disc pr-5 space-y-1.5">
                    <li>ممنوع الاعتداء على البوتات (يعتبرون مواطنين).</li>
                    <li>ممنوع طلب تعويض عند خسارة أموالك أو أغراضك بسبب التحلل أو المستشفى.</li>
                    <li>ممنوع الكتابة خارج "الرول بلاي" في تطبيق تويتر داخل المدينة، وتقتصر الكتابة على إطار التمثيل والسيناريوهات.</li>
                    <li>لا يحق لك الدخول في أحداث كبيرة (مثل البيع والشراء) إلا إذا كان بينكم معرفة رول بلاي لمدة لا تقل عن أسبوع.</li>
                    <li>يمنع القذف، الشتم، الطائفية، السياسة، الدين، أو القبلية (العقوبة: باند نهائي).</li>
                    <li>يمنع استخدام كلمات غير مفهومة، مشفرة، أو سب مبطن.</li>
                    <li>يمنع استغلال خدمات الجوال (مثل طلب تاكسي أو خدمات) بهدف الخطف أو القتل.</li>
                    <li>يمنع توزيع مبالغ مالية كبيرة (10 آلاف فأكثر) إلا إذا كان بينكم معرفة لا تقل عن أسبوع.</li>
                    <li>يمنع مشاركة أي من حساباتك أو معلوماتك الشخصية مع أي شخص (العقوبة: باند نهائي).</li>
                    <li>يمنع حمل شخصين في نفس الوقت (حمل + سحب) مهما كانت الأسباب.</li>
                  </ul>
                </div>
              </div>
            </div>
          </div>

          <!-- قوانين القيادة -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow text-xs font-extrabold">القيادة</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">قوانين القيادة</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4">
                <p class="font-bold text-white mb-2">القيادة يجب أن تكون واقعية:</p>
                <ul class="list-disc pr-5 space-y-1.5">
                  <li>لا سرعة مفرطة بدون سبب.</li>
                  <li>لا قطع إشارات عشوائي.</li>
                  <li>لا تهور بدون داعٍ.</li>
                  <li>مخالفة هذه القوانين = تحذير PowerGaming أو باند.</li>
                  <li>يمنع استخدام حركة رفع الدباب والنط من أي مكان سواء الأرصفة القصيرة أو الجسور والجدران والمباني والعوائق التي تجعل الدباب يرتفع عاليًا.</li>
                </ul>
              </div>
            </div>
          </div>

          <!-- نظام الوورنات -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow text-xs font-extrabold">1 - 15</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">نظام الوورنات (التحذيرات)</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4 space-y-3">
                <p class="text-dcYellow font-bold text-sm">
                  || للتنبيه: الوورنات ليست العقوبة الوحيدة للمخالفين، وتوجد بعض المخالفات المستثناة من الوورنات ||
                </p>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-2.5 text-sm">
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">1 &gt;&gt; وارن &gt;&gt; بدون أي إجراء</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">2 &gt;&gt; وارن &gt;&gt; باند 12 ساعة</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">3 &gt;&gt; وارن &gt;&gt; بدون أي إجراء</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">4 &gt;&gt; وارن &gt;&gt; باند 24 ساعة</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">5 &gt;&gt; وارن &gt;&gt; بدون أي إجراء</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">6 &gt;&gt; وارن &gt;&gt; باند 3 أيام</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">7 &gt;&gt; وارن &gt;&gt; بدون أي إجراء</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">8 &gt;&gt; وارن &gt;&gt; باند 7 أيام</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">9 &gt;&gt; وارن &gt;&gt; بدون أي إجراء</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">10 &gt;&gt; وارن &gt;&gt; باند 10 أيام</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">11 &gt;&gt; وارن &gt;&gt; بدون أي إجراء</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">12 &gt;&gt; وارن &gt;&gt; باند أسبوعين</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">13 &gt;&gt; وارن &gt;&gt; بدون أي إجراء</div>
                  <div class="p-2.5 rounded-xl bg-dcDark/80 border border-dcBorder/60">14 &gt;&gt; وارن &gt;&gt; باند 3 أسابيع</div>
                  <div class="p-2.5 rounded-xl bg-dcYellow/15 border border-dcYellow/40 text-dcYellow font-extrabold sm:col-span-2 lg:col-span-3">
                    15 &gt;&gt; باند ثلاثة أشهر أو نهائي
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- قوانين الشرطة -->
          <div class="accordion-item rounded-2xl bg-dcCard/95 border border-dcBorder overflow-hidden">
            <button type="button" class="accordion-trigger w-full flex items-center justify-between gap-4 p-5 text-right hover:bg-white/[0.02] transition">
              <div class="flex items-center gap-3">
                <span class="px-2.5 py-1 rounded-lg bg-dcYellow/15 text-dcYellow text-xs font-extrabold">الشرطة</span>
                <h3 class="text-base sm:text-lg font-extrabold text-white">قوانين الشرطة</h3>
              </div>
              <svg class="w-5 h-5 text-dcYellow accordion-chevron shrink-0" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>
            <div class="accordion-content">
              <div class="accordion-inner px-5 pb-5 text-gray-300 text-sm sm:text-base leading-relaxed border-t border-dcBorder/50 pt-4 space-y-5">
                <div>
                  <h4 class="font-extrabold text-dcYellow mb-2">إيقاف الخدمات والمداهمات وتدرج الأسلحة</h4>
                  <ul class="list-disc pr-5 space-y-1.5">
                    <li>1 - يحق للضابط وما فوق برفع طلب إيقاف خدمات إلى المحكمة ولا يمكن تنفيذ إيقاف الخدمات إلا من خلال حكم من المحكمة.</li>
                    <li>2 - يتم طلب المداهمة من خلال الضباط وما فوق ولا يمكن مداهمة أي شخص إلا من خلال أمر تنفيذ من المحكمة.</li>
                    <li>3 - في حال حدوث أي مخالفة سواء بالرول بلاي أو قوانين الشرطة سوف يتم محاسبة مسؤول الحالة فقط ويتحمل مسؤولية الأفراد.</li>
                    <li>4 - يجب على العسكري عدم إخراج السلاح إلا بعد أن يقوم المجرم بإخراج سلاحه.</li>
                    <li>5 - يجب على العسكري استخدام نفس فئة الأسلحة ("خفيف، ثقيل") المستخدمة من المجرم باستثناء أوامر القيادة.</li>
                    <li>6 - على جميع العساكر والأفراد عدم استخدام الأسلحة النارية في حال استخدام المجرم سلاح أبيض إلا في حالة مهاجمة المجرم للعسكري.</li>
                    <li>7 - في حال التفرقة بين المواطنين في التعامل سواء التفاوض مع مجرم أو التعامل مع مسعف أو مع مواطن بسوء سيتم تحويل الموضوع رقابيًا والتعامل ضمن حدود الرول بلاي.</li>
                  </ul>
                </div>

                <div>
                  <h4 class="font-extrabold text-dcYellow mb-2">سلوك رجل الأمن</h4>
                  <p class="mb-2">
                    يجب أن يكون رجل الأمن مهذبًا تجاه المواطنين ومع زملائه، ولبقًا في أداء واجبه، متحكمًا في أعصابه ويتحمل أقصى درجات الصبر والتقدير، ولا يجوز استخدام لغة أو إيماءات بذيئة أو عنيفة.
                  </p>
                  <p class="mb-2">
                    لا يجوز لرجال الأمن ارتكاب أي عمل من أعمال الفساد، وعليهم معارضة ومكافحة هذه الأعمال بصرامة والإبلاغ عنها، مع احترام وحماية كرامة وحقوق الإنسان.
                  </p>
                  <p>
                    تُعد الخيانة أو التمرد انهيارًا خطيرًا في الانضباط والنظام داخل حكومة السيرفر، ويخضع أي رجل أمن متمرد لإجراءات تأديبية صارمة.
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 4. قسم المتجر (Store) -->
    <section id="store" class="py-16 sm:py-20 px-4 sm:px-6 lg:px-8 border-t border-dcBorder/60">
      <div class="max-w-4xl mx-auto">
        <div class="rounded-3xl bg-dcCard/95 border border-dcBorder p-8 sm:p-12 text-center shadow-xl">
          <span class="inline-block px-3.5 py-1 rounded-full bg-dcYellow/15 text-dcYellow text-xs font-extrabold mb-4">
            المتجر الرسمي
          </span>
          <h2 class="text-3xl sm:text-4xl font-black text-white mb-3">المتجر</h2>
          <p class="text-gray-300 text-base sm:text-lg max-w-xl mx-auto mb-7">
            قريبًا جدًا... نجهز لكم تجربة متجر متميزة وحصرية لسيرفر <strong class="text-dcYellow">DC CITY</strong>.
          </p>
          <div class="inline-flex items-center justify-center px-8 py-3.5 rounded-2xl bg-dcYellow/15 border border-dcYellow/50 text-dcYellow font-display font-black tracking-[0.2em] text-base sm:text-lg">
            COMING SOON
          </div>
        </div>
      </div>
    </section>

    <!-- 5. قسم تقديم الوظائف (Job Applications) -->
    <section id="jobs" class="py-16 sm:py-20 px-4 sm:px-6 lg:px-8 border-t border-dcBorder/60">
      <div class="max-w-5xl mx-auto">
        <div class="text-center mb-10">
          <span class="text-xs font-extrabold uppercase tracking-widest text-dcYellow">Careers</span>
          <h2 class="text-3xl sm:text-4xl font-black text-white mt-1">تقديم وظائف</h2>
          <div class="w-20 h-1 bg-dcYellow mx-auto mt-3 rounded-full"></div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-5 mb-6">
          <button
            type="button"
            data-job="تقديم الشرطة"
            class="job-card group rounded-2xl bg-dcCard border border-dcBorder p-6 text-right hover:border-dcYellow transition cursor-pointer"
          >
            <div class="w-11 h-11 rounded-xl bg-dcYellow/15 text-dcYellow flex items-center justify-center font-black mb-4 group-hover:bg-dcYellow group-hover:text-black transition">
              01
            </div>
            <h3 class="text-xl font-extrabold text-white mb-1.5">تقديم الشرطة</h3>
            <p class="text-sm text-gray-400">الانضمام إلى جهاز الأمن وحفظ النظام داخل المدينة.</p>
          </button>

          <button
            type="button"
            data-job="تقديم الصحة"
            class="job-card group rounded-2xl bg-dcCard border border-dcBorder p-6 text-right hover:border-dcYellow transition cursor-pointer"
          >
            <div class="w-11 h-11 rounded-xl bg-dcYellow/15 text-dcYellow flex items-center justify-center font-black mb-4 group-hover:bg-dcYellow group-hover:text-black transition">
              02
            </div>
            <h3 class="text-xl font-extrabold text-white mb-1.5">تقديم الصحة</h3>
            <p class="text-sm text-gray-400">العمل في الطواقم الطبية والإسعاف ورعاية المواطنين.</p>
          </button>

          <button
            type="button"
            data-job="تقديم وزارة العدل"
            class="job-card group rounded-2xl bg-dcCard border border-dcBorder p-6 text-right hover:border-dcYellow transition cursor-pointer"
          >
            <div class="w-11 h-11 rounded-xl bg-dcYellow/15 text-dcYellow flex items-center justify-center font-black mb-4 group-hover:bg-dcYellow group-hover:text-black transition">
              03
            </div>
            <h3 class="text-xl font-extrabold text-white mb-1.5">تقديم وزارة العدل</h3>
            <p class="text-sm text-gray-400">العمل في السلك القضائي والقانوني وتطبيق الأنظمة.</p>
          </button>
        </div>

        <div id="jobStatusBanner" class="rounded-2xl bg-dcCard/90 border border-dcBorder p-4 text-center text-sm sm:text-base font-bold text-gray-300">
          التقديمات مغلقة حاليًا — اختر أي قطاع لمعاينة حالته أو ربط نموذج التقديم الخاص به.
        </div>
      </div>
    </section>

    <!-- 6. قسم المؤسسين (Founders) -->
    <section id="founders" class="py-16 sm:py-20 px-4 sm:px-6 lg:px-8 border-t border-dcBorder/60">
      <div class="max-w-5xl mx-auto">
        <div class="text-center mb-10">
          <span class="text-xs font-extrabold uppercase tracking-widest text-dcYellow">Leadership</span>
          <h2 class="text-3xl sm:text-4xl font-black text-white mt-1">المؤسسين</h2>
          <p class="text-xs sm:text-sm text-gray-400 mt-2">
            ملاحظة: بيانات المؤسسين أدناه نماذج مبدئية قابلة للتخصيص بأسماء ومناصب فريق إدارة DC CITY.
          </p>
          <div class="w-20 h-1 bg-dcYellow mx-auto mt-3 rounded-full"></div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <!-- المؤسس الأول -->
          <div class="rounded-3xl bg-dcCard/95 border border-dcBorder p-6 text-center hover:border-dcYellow/70 transition">
            <div class="w-20 h-20 mx-auto mb-4 rounded-full dc-emblem-box flex flex-col items-center justify-center">
              <span class="dc-letters text-xl leading-none">DC</span>
              <span class="dc-city-line"></span>
              <span class="dc-city-small">CITY</span>
            </div>
            <h3 class="text-xl font-extrabold text-white">المؤسس الأول (نموذج)</h3>
            <p class="text-sm text-dcYellow font-bold mt-1">مؤسس السيرفر ومطور النظام</p>
            <p class="text-xs text-gray-400 mt-2">قابل للتعديل حسب بيانات الإدارة الفعلية.</p>
          </div>

          <!-- المؤسس الثاني -->
          <div class="rounded-3xl bg-dcCard/95 border border-dcBorder p-6 text-center hover:border-dcYellow/70 transition">
            <div class="w-20 h-20 mx-auto mb-4 rounded-full dc-emblem-box flex flex-col items-center justify-center">
              <span class="dc-letters text-xl leading-none">DC</span>
              <span class="dc-city-line"></span>
              <span class="dc-city-small">CITY</span>
            </div>
            <h3 class="text-xl font-extrabold text-white">المؤسس الثاني (نموذج)</h3>
            <p class="text-sm text-dcYellow font-bold mt-1">مسؤول السيرفر والإدارة والرقابة</p>
            <p class="text-xs text-gray-400 mt-2">قابل للتعديل حسب بيانات الإدارة الفعلية.</p>
          </div>

          <!-- المؤسس الثالث -->
          <div class="rounded-3xl bg-dcCard/95 border border-dcBorder p-6 text-center hover:border-dcYellow/70 transition">
            <div class="w-20 h-20 mx-auto mb-4 rounded-full dc-emblem-box flex flex-col items-center justify-center">
              <span class="dc-letters text-xl leading-none">DC</span>
              <span class="dc-city-line"></span>
              <span class="dc-city-small">CITY</span>
            </div>
            <h3 class="text-xl font-extrabold text-white">المؤسس الثالث (نموذج)</h3>
            <p class="text-sm text-dcYellow font-bold mt-1">نائب المسؤول ومشرف العمليات</p>
            <p class="text-xs text-gray-400 mt-2">قابل للتعديل حسب بيانات الإدارة الفعلية.</p>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- التذييل السفلي -->
  <footer class="relative z-10 border-t border-dcBorder bg-dcDark/95 py-8 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-4 text-center sm:text-right">
      <div class="flex items-center gap-3">
        <div class="w-10 h-10 rounded-full dc-emblem-box flex flex-col items-center justify-center">
          <span class="dc-letters text-sm leading-none">DC</span>
          <span class="dc-city-line"></span>
          <span class="dc-city-small text-[0.45rem]">CITY</span>
        </div>
        <span class="font-extrabold text-white">DC CITY</span>
      </div>
      <p class="text-xs sm:text-sm text-gray-400">
        جميع الحقوق محفوظة © <span id="currentYear"></span> <strong class="text-dcYellow">DC CITY</strong> — مجتمع الحياة الواقعية.
      </p>
    </div>
  </footer>

  <!-- السكربت التفاعلي -->
  <script>
    (function () {
      try {
        // السنة الحالية في التذييل
        const yearEl = document.getElementById('currentYear');
        if (yearEl) {
          yearEl.textContent = new Date().getFullYear();
        }

        // قائمة الجوال
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        if (mobileMenuBtn && mobileMenu) {
          mobileMenuBtn.addEventListener('click', function () {
            const isHidden = mobileMenu.classList.contains('hidden');
            mobileMenu.classList.toggle('hidden', !isHidden);
            mobileMenuBtn.setAttribute('aria-expanded', String(isHidden));
          });

          document.querySelectorAll('.mobile-nav-link').forEach(function (link) {
            link.addEventListener('click', function () {
              mobileMenu.classList.add('hidden');
              mobileMenuBtn.setAttribute('aria-expanded', 'false');
            });
          });
        }

        // قائمة السيرفرات المنسدلة (سطح المكتب)
        const serversBtn = document.getElementById('serversDropdownBtn');
        const serversMenu = document.getElementById('serversDropdownMenu');
        const serversChevron = document.getElementById('serversChevron');

        if (serversBtn && serversMenu) {
          serversBtn.addEventListener('click', function (e) {
            e.stopPropagation();
            const isHidden = serversMenu.classList.contains('hidden');
            serversMenu.classList.toggle('hidden', !isHidden);
            serversBtn.setAttribute('aria-expanded', String(isHidden));
            if (serversChevron) {
              serversChevron.style.transform = isHidden ? 'rotate(180deg)' : 'rotate(0deg)';
            }
          });

          document.addEventListener('click', function (e) {
            if (!serversMenu.contains(e.target) && !serversBtn.contains(e.target)) {
              serversMenu.classList.add('hidden');
              serversBtn.setAttribute('aria-expanded', 'false');
              if (serversChevron) {
                serversChevron.style.transform = 'rotate(0deg)';
              }
            }
          });
        }

        // الأكورديون الخاص بالقوانين
        const triggers = document.querySelectorAll('.accordion-trigger');
        triggers.forEach(function (trigger) {
          trigger.addEventListener('click', function () {
            const item = trigger.closest('.accordion-item');
            if (!item) return;
            item.classList.toggle('open');
          });
        });

        // التفعيل: الموافقة / عدم الموافقة ونموذج مبدئي
        const agreeBtn = document.getElementById('agreeRulesBtn');
        const disagreeBtn = document.getElementById('disagreeRulesBtn');
        const feedbackBox = document.getElementById('activationFeedback');

        function renderActivationBox(agreed) {
          if (!feedbackBox) return;
          feedbackBox.classList.remove('hidden');

          if (!agreed) {
            feedbackBox.className = 'rounded-2xl p-5 border bg-red-500/10 border-red-500/40 text-red-200 space-y-2';
            feedbackBox.innerHTML =
              '<p class="font-extrabold text-red-400">لم يتم قبول الشروط العامة</p>' +
              '<p class="text-sm leading-relaxed">يجب الموافقة على جميع شروط DC CITY العامة للمتابعة نحو خطوات التفعيل.</p>';
            return;
          }

          feedbackBox.className = 'rounded-2xl p-5 border bg-dcYellow/10 border-dcYellow/40 text-gray-100 space-y-4';
          feedbackBox.innerHTML =
            '<div class="flex items-center justify-between flex-wrap gap-2">' +
              '<span class="font-extrabold text-dcYellow">✓ تمت الموافقة على الشروط — نموذج التفعيل المبدئي</span>' +
              '<span class="text-xs px-2.5 py-1 rounded-lg bg-dcYellow text-black font-extrabold">جاهز للتخصيص</span>' +
            '</div>' +
            '<form id="demoActivationForm" class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-sm">' +
              '<div>' +
                '<label class="block text-xs font-bold text-gray-300 mb-1">اسم الشخصية (عربي بدون رموز)</label>' +
                '<input type="text" required placeholder="مثال: طارق العتيبي" class="w-full px-3.5 py-2.5 rounded-xl bg-dcDark border border-dcBorder text-white focus:outline-none focus:border-dcYellow" />' +
              '</div>' +
              '<div>' +
                '<label class="block text-xs font-bold text-gray-300 mb-1">معرف الديسكورد (Discord ID / Username)</label>' +
                '<input type="text" required placeholder="مثال: dc_user" class="w-full px-3.5 py-2.5 rounded-xl bg-dcDark border border-dcBorder text-white focus:outline-none focus:border-dcYellow" />' +
              '</div>' +
              '<div class="sm:col-span-2 flex items-center justify-between gap-3 pt-1 flex-wrap">' +
                '<span class="text-xs text-gray-400">نموذج معاينة محلي — اربطه ببوت الديسكورد أو قاعدة البيانات الخاصة بالسيرفر.</span>' +
                '<button type="submit" class="px-5 py-2.5 rounded-xl bg-dcYellow text-black font-extrabold hover:bg-dcGold transition cursor-pointer">حفظ معاينة الطلب</button>' +
              '</div>' +
            '</form>' +
            '<div id="activationSubmitNote" class="hidden text-xs font-bold text-dcYellow bg-dcDark/80 border border-dcYellow/30 rounded-xl p-3"></div>';

          const form = document.getElementById('demoActivationForm');
          const note = document.getElementById('activationSubmitNote');
          if (form && note) {
            form.addEventListener('submit', function (ev) {
              ev.preventDefault();
              note.classList.remove('hidden');
              note.textContent = 'تم تسجيل معاينة طلب التفعيل محليًا بنجاح. يمكنك ربط هذا النموذج بنظام التفعيل الخاص بسيرفر DC CITY.';
            });
          }
        }

        if (agreeBtn) {
          agreeBtn.addEventListener('click', function () {
            renderActivationBox(true);
          });
        }

        if (disagreeBtn) {
          disagreeBtn.addEventListener('click', function () {
            renderActivationBox(false);
          });
        }

        // بطاقات تقديم الوظائف
        const jobCards = document.querySelectorAll('.job-card');
        const jobBanner = document.getElementById('jobStatusBanner');
        jobCards.forEach(function (card) {
          card.addEventListener('click', function () {
            const jobName = card.getAttribute('data-job') || 'الوظيفة';
            jobCards.forEach(function (c) {
              c.classList.remove('border-dcYellow', 'bg-dcYellow/5');
            });
            card.classList.add('border-dcYellow', 'bg-dcYellow/5');

            if (jobBanner) {
              jobBanner.innerHTML =
                '<span class="text-dcYellow font-extrabold">' + jobName + '</span>: التقديمات مغلقة حاليًا — يمكنك ربط رابط نموذج التقديم الخاص بهذا القسم عند فتح باب القبول.';
            }
          });
        });
      } catch (err) {
        console.error('Error initializing DC CITY website:', err);
      }
    })();
  </script>
</body>
</html>
