<!-- Online Course Platform PRD -->
Technical Assignment (PRD) for Online Course Website

1. General Information
Educational platform for courses on: Targeted Advertising, SMM, Mobilography, Wildberries, YouTube.
Style: Simple, light, beautiful, user-friendly.
Goals: Attract clients, provide a free mini-lesson, convert to purchase.

2. Main Tasks
- Present company and instructor.
- Show course list.
- Provide free mini-lesson after registration.
- Organize course purchase.
- Automatic access to personal account after payment.
- Simple navigation.

3. Site Structure
3.1 Home Page: Minimalist, Banner with instructor, "Watch free lesson" CTA, About, Benefits, Course Cards, Reviews, FAQ, Footer.
3.2 Course Page: Video/Banner, Description, Learning outcomes, Program modules, Audience, Pricing, CTA for free lesson and buy.
3.3 Free Mini-Lesson Page: Video (2-10 min), Buy CTA, Info on what happens after payment, Auto-registration.
3.4 User Account: Only after purchase. Course viewing, progress, downloads, reviews, support chat.
3.5 Payment Page: Cards, e-wallets (Elsom, Balance, MBank Pay), Auto-access after payment.

4. Functional Requirements
- Responsive (Mobile, Tablet, Desktop).
- Fast loading, light UI.
- Admin panel for course management.

5. Design & UI/UX
- Minimalist, neat, clean colors.
- Inspired by Skillbox, Coursera, Udemy.
- Large buttons, clear headers, lots of white space.

6. Technical Part
- Frontend: React / Next.js / Vue.
- Backend: Node.js / PHP / Python.
- Video: YouTube (unlisted) or Vimeo.

7. Security
- SSL, data protection, private lesson access.

<!-- Course Details -->
<!DOCTYPE html>

<html class="light" lang="en"><head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;700;800&amp;family=Plus+Jakarta+Sans:wght@400;500;600;700&amp;display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap" rel="stylesheet"/>
<script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
<script id="tailwind-config">
        tailwind.config = {
            darkMode: "class",
            theme: {
                extend: {
                    "colors": {
                        "surface-container-lowest": "#ffffff",
                        "tertiary-fixed": "#ffdbcf",
                        "on-secondary-fixed": "#00210c",
                        "tertiary-fixed-dim": "#ffb59b",
                        "on-primary-fixed": "#001945",
                        "inverse-on-surface": "#f0f0fb",
                        "on-tertiary-container": "#ffcebd",
                        "on-secondary": "#ffffff",
                        "tertiary-container": "#a93802",
                        "surface-tint": "#215abd",
                        "secondary": "#006d37",
                        "on-background": "#191b23",
                        "surface-container-low": "#f2f3fe",
                        "outline": "#737785",
                        "surface-container-highest": "#e1e2ec",
                        "primary-fixed-dim": "#b0c6ff",
                        "error-container": "#ffdad6",
                        "on-secondary-container": "#00743a",
                        "surface-container-high": "#e7e7f2",
                        "secondary-fixed": "#6bfe9c",
                        "outline-variant": "#c3c6d6",
                        "background": "#faf8ff",
                        "on-primary": "#ffffff",
                        "secondary-fixed-dim": "#4ae183",
                        "primary": "#00429c",
                        "tertiary": "#822800",
                        "on-error": "#ffffff",
                        "surface-bright": "#faf8ff",
                        "error": "#ba1a1a",
                        "inverse-primary": "#b0c6ff",
                        "on-tertiary": "#ffffff",
                        "on-tertiary-fixed-variant": "#812800",
                        "on-surface": "#191b23",
                        "primary-fixed": "#d9e2ff",
                        "surface-container": "#ededf8",
                        "surface-dim": "#d9d9e4",
                        "secondary-container": "#6bfe9c",
                        "primary-container": "#225abd",
                        "surface": "#faf8ff",
                        "on-tertiary-fixed": "#380d00",
                        "inverse-surface": "#2e3038",
                        "on-surface-variant": "#424654",
                        "on-error-container": "#93000a",
                        "on-secondary-fixed-variant": "#005228",
                        "on-primary-container": "#cbd8ff",
                        "on-primary-fixed-variant": "#00429b",
                        "surface-variant": "#e1e2ec"
                    },
                    "borderRadius": {
                        "DEFAULT": "1rem",
                        "lg": "2rem",
                        "xl": "3rem",
                        "full": "9999px"
                    },
                    "fontFamily": {
                        "headline": ["Manrope"],
                        "body": ["Plus Jakarta Sans"],
                        "label": ["Plus Jakarta Sans"]
                    }
                },
            },
        }
    </script>
<style>
        .material-symbols-outlined {
            font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
        }
        body { font-family: 'Plus Jakarta Sans', sans-serif; background-color: #faf8ff; color: #191b23; }
        h1, h2, h3 { font-family: 'Manrope', sans-serif; }
    </style>
<style>
    body {
      min-height: max(884px, 100dvh);
    }
  </style>
  </head>
<body class="bg-background text-on-surface">
<!-- TopAppBar Shell -->
<header class="fixed top-0 w-full z-50 bg-slate-50/80 backdrop-blur-xl flex justify-between items-center px-6 py-4 w-full">
<div class="flex items-center gap-3">
<span class="font-['Manrope'] font-extrabold text-blue-800 tracking-tighter text-xl">The Atelier</span>
</div>
<nav class="hidden md:flex items-center gap-8">
<a class="font-['Plus_Jakarta_Sans'] text-slate-500 hover:bg-slate-100 rounded-full transition-colors px-4 py-1" href="#">Home</a>
<a class="font-['Plus_Jakarta_Sans'] text-blue-700 font-bold px-4 py-1" href="#">My Courses</a>
<a class="font-['Plus_Jakarta_Sans'] text-slate-500 hover:bg-slate-100 rounded-full transition-colors px-4 py-1" href="#">Search</a>
</nav>
<div class="flex items-center gap-4">
<button class="p-2 text-slate-500 hover:bg-slate-100 rounded-full transition-colors active:scale-95">
<span class="material-symbols-outlined" data-icon="notifications">notifications</span>
</button>
<div class="w-10 h-10 rounded-full bg-surface-container-highest overflow-hidden">
<img alt="User profile photo" data-alt="close-up portrait of a smiling young professional woman with natural lighting and soft blurred office background" src="https://lh3.googleusercontent.com/aida-public/AB6AXuBj-em58vFJ7VDJxQ2cYGDRIM6aTaIylfVUMiFwBfCrTKKIkFd-eNxa_z-BEVju8tAtzciDeQZvaCDp9ri0V3wtA02w-sVSmm2UPmDO7G9sq0SJ1S3nJ4BgxSAqyVGpdfLjpBAv0LUyTgv_FKR6_R_ijxdKRp9kVh1UlZqHHyWeYmgHPmDoMSEeo2bvMKoiAZ5Z3kuRbGROIFp6s6rEYIM9HOCKlFj78UWyeM5j0_D7ksc9JfbdIeLKymi9OFULeQ8GKm_vyICiig7_"/>
</div>
</div>
</header>
<main class="pt-24 pb-32">
<!-- Hero Section: Video Preview/Banner -->
<section class="px-6 mb-16">
<div class="max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-[1.2fr_0.8fr] gap-12 items-center">
<div class="relative group aspect-video rounded-xl overflow-hidden shadow-2xl bg-surface-container-low">
<img class="w-full h-full object-cover" data-alt="Modern workspace with a glowing screen showing social media marketing analytics and digital charts in a dimly lit room" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDYrmqQBSqvS-Bi64pYDqqqW8o7Qioo9I3XH-Z6tkuqXKCtwQ92eXd9A1M-9n0YgeH1L6puQg-N64qaquq4XFoz5meo14-bSsQOMl9YtMkV6xPp8qG8VKRXK7WjhWWeNmcog5sxNBB8aTwVF8S3ZrFAN3hCqYG3-vJdJVmvUJeHLBolFUKRXE_oP08kVh1GwstDlZ9Q3sTKBC6ExL0HNyygPfKT4aaP50EaAkUzdbFFxT3baTZnN46oB22MYVFzx1dB3SmQ6BAPQnOM"/>
<div class="absolute inset-0 bg-primary/20 flex items-center justify-center cursor-pointer group-hover:bg-primary/30 transition-all">
<div class="w-20 h-20 bg-surface-container-lowest rounded-full flex items-center justify-center shadow-xl group-hover:scale-110 transition-transform">
<span class="material-symbols-outlined text-primary text-4xl" data-weight="fill" style="font-variation-settings: 'FILL' 1;">play_arrow</span>
</div>
</div>
<div class="absolute bottom-6 left-6 bg-inverse-surface/90 backdrop-blur-md px-4 py-2 rounded-full flex items-center gap-2">
<span class="material-symbols-outlined text-white text-sm" data-icon="visibility">visibility</span>
<span class="text-white text-xs font-semibold">PREVIEW LESSON</span>
</div>
</div>
<div class="space-y-6">
<div class="inline-flex items-center gap-2 px-4 py-1 bg-secondary/10 text-secondary rounded-full">
<span class="material-symbols-outlined text-sm" data-weight="fill" style="font-variation-settings: 'FILL' 1;">verified</span>
<span class="text-xs font-bold uppercase tracking-widest">Masterclass Series</span>
</div>
<h1 class="text-5xl font-extrabold tracking-tight text-on-surface leading-[1.1]">The Precision Targeting Blueprint</h1>
<p class="text-on-surface-variant text-lg leading-relaxed">Master the architecture of high-conversion social ads. A deep dive into SMM strategy, algorithmic behavior, and neuro-marketing for the modern digital era.</p>
<div class="flex flex-col sm:flex-row gap-4 pt-4">
<button class="px-10 py-4 bg-gradient-to-br from-primary to-primary-container text-on-primary rounded-full font-bold shadow-lg shadow-primary/20 active:scale-95 transition-all text-center">Buy Course</button>
<button class="px-10 py-4 bg-surface-container-lowest text-primary rounded-full font-bold border-2 border-primary/10 hover:border-primary/30 active:scale-95 transition-all text-center">Get Free Lesson</button>
</div>
</div>
</div>
</section>
<!-- Learning Outcomes & Description -->
<section class="bg-surface-container-low py-24">
<div class="max-w-7xl mx-auto px-6">
<div class="grid grid-cols-1 lg:grid-cols-2 gap-20">
<div>
<span class="label-md uppercase tracking-[0.2em] text-on-surface-variant font-bold text-xs mb-4 block">The Curriculum</span>
<h2 class="text-4xl font-bold mb-8">What you will learn</h2>
<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
<div class="bg-surface-container-lowest p-8 rounded-lg space-y-4">
<div class="w-12 h-12 bg-primary/10 rounded-full flex items-center justify-center text-primary">
<span class="material-symbols-outlined" data-icon="psychology">psychology</span>
</div>
<h3 class="font-bold text-xl">Consumer Psychology</h3>
<p class="text-on-surface-variant text-sm leading-relaxed">Understand the triggers that turn a scroller into a loyal customer through behavioral analysis.</p>
</div>
<div class="bg-surface-container-lowest p-8 rounded-lg space-y-4">
<div class="w-12 h-12 bg-secondary/10 rounded-full flex items-center justify-center text-secondary">
<span class="material-symbols-outlined" data-icon="analytics">analytics</span>
</div>
<h3 class="font-bold text-xl">Data-Driven Logic</h3>
<p class="text-on-surface-variant text-sm leading-relaxed">Interpret complex analytics to refine and scale your campaigns with surgical precision.</p>
</div>
<div class="bg-surface-container-lowest p-8 rounded-lg space-y-4">
<div class="w-12 h-12 bg-tertiary/10 rounded-full flex items-center justify-center text-tertiary">
<span class="material-symbols-outlined" data-icon="brush">brush</span>
</div>
<h3 class="font-bold text-xl">Creative Direction</h3>
<p class="text-on-surface-variant text-sm leading-relaxed">Learn to brief and design visual assets that bypass digital fatigue and demand attention.</p>
</div>
<div class="bg-surface-container-lowest p-8 rounded-lg space-y-4">
<div class="w-12 h-12 bg-on-surface/5 rounded-full flex items-center justify-center text-on-surface">
<span class="material-symbols-outlined" data-icon="architecture">architecture</span>
</div>
<h3 class="font-bold text-xl">Funnel Architecture</h3>
<p class="text-on-surface-variant text-sm leading-relaxed">Build multi-stage remarketing systems that nurture leads from awareness to conversion.</p>
</div>
</div>
</div>
<div class="space-y-10">
<div class="bg-surface-container-highest/30 p-10 rounded-xl">
<h2 class="text-2xl font-bold mb-6">Course Description</h2>
<p class="text-on-surface-variant text-lg leading-relaxed mb-6">
                                Digital advertising is no longer about just "setting up a pixel." It's an art form supported by rigorous data science. This course is designed to move you beyond the basics of Ads Manager and into the strategic mind of a high-ticket media buyer.
                            </p>
<p class="text-on-surface-variant text-lg leading-relaxed">
                                We strip away the fluff and focus on the mechanics of scale. From iOS14 workarounds to advanced CBO strategies, you'll gain the toolkit necessary to manage accounts spending $10k+ daily.
                            </p>
</div>
<div class="flex items-center gap-6 p-6 border-l-4 border-secondary bg-surface-container-lowest rounded-r-lg">
<div class="flex-1">
<p class="text-sm font-bold text-secondary uppercase tracking-widest mb-1">Current Progress</p>
<div class="h-3 w-full bg-surface-container-highest rounded-full">
<div class="h-3 bg-secondary rounded-full" style="width: 65%;"></div>
</div>
</div>
<span class="text-2xl font-bold text-secondary">65%</span>
</div>
</div>
</div>
</div>
</section>
<!-- Detailed Program (Module by Module) -->
<section class="py-24 px-6">
<div class="max-w-4xl mx-auto">
<div class="text-center mb-16">
<span class="label-md uppercase tracking-[0.2em] text-on-surface-variant font-bold text-xs mb-4 block">The Journey</span>
<h2 class="text-4xl font-bold">Module-by-Module Breakdown</h2>
</div>
<div class="space-y-4">
<!-- Module 1 -->
<div class="bg-surface-container-low p-8 rounded-lg">
<div class="flex justify-between items-center mb-4">
<span class="text-primary font-bold">MODULE 01</span>
<span class="text-xs font-semibold text-on-surface-variant bg-surface-container-highest px-3 py-1 rounded-full uppercase tracking-widest">4 Lessons</span>
</div>
<h3 class="text-2xl font-bold mb-4">The Foundation: Algorithms &amp; Audience</h3>
<p class="text-on-surface-variant leading-relaxed">How the modern auction works. Machine learning vs. Manual bidding. Defining 'Cold' audiences through interest stacking and lookalikes.</p>
</div>
<!-- Module 2 -->
<div class="bg-surface-container-low p-8 rounded-lg">
<div class="flex justify-between items-center mb-4">
<span class="text-primary font-bold">MODULE 02</span>
<span class="text-xs font-semibold text-on-surface-variant bg-surface-container-highest px-3 py-1 rounded-full uppercase tracking-widest">6 Lessons</span>
</div>
<h3 class="text-2xl font-bold mb-4">The Creative Engine: Hook, Story, Offer</h3>
<p class="text-on-surface-variant leading-relaxed">Analyzing high-performing ad copy. The 3-second hook rule. Designing for the scroll-stop. A/B testing creative assets at scale.</p>
</div>
<!-- Module 3 -->
<div class="bg-surface-container-low p-8 rounded-lg">
<div class="flex justify-between items-center mb-4">
<span class="text-primary font-bold">MODULE 03</span>
<span class="text-xs font-semibold text-on-surface-variant bg-surface-container-highest px-3 py-1 rounded-full uppercase tracking-widest">5 Lessons</span>
</div>
<h3 class="text-2xl font-bold mb-4">Scaling Operations: CBO, ABO &amp; Bidding</h3>
<p class="text-on-surface-variant leading-relaxed">Vertical vs. Horizontal scaling. When to switch to Campaign Budget Optimization. The art of the 'Surfing' method for daily budget increases.</p>
</div>
<!-- Module 4 -->
<div class="bg-surface-container-low p-8 rounded-lg">
<div class="flex justify-between items-center mb-4">
<span class="text-primary font-bold">MODULE 04</span>
<span class="text-xs font-semibold text-on-surface-variant bg-surface-container-highest px-3 py-1 rounded-full uppercase tracking-widest">3 Lessons</span>
</div>
<h3 class="text-2xl font-bold mb-4">The Reporting Matrix</h3>
<p class="text-on-surface-variant leading-relaxed">Attribution models post-iOS. Custom conversions. Using external tracking (Triple Whale, Hyros) to verify your ROAS.</p>
</div>
</div>
</div>
</section>
<!-- Who is this for? -->
<section class="py-24 bg-surface-container-high">
<div class="max-w-7xl mx-auto px-6 grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
<div class="order-2 lg:order-1">
<img class="rounded-xl shadow-xl rotate-1 grayscale hover:grayscale-0 transition-all duration-500" data-alt="A focused diverse team of marketing professionals brainstorming around a large wooden table with laptops and coffee" src="https://lh3.googleusercontent.com/aida-public/AB6AXuA1IzITiW-DeDsNaw-NwJbtCopP1g2lqSVLumAKinUvQXerFdmw47gPTLh8zMaqGyQRVmXdeK-FyadItcRIPj8jfDBcJB5Ink-Sdg3LNtDhjIOxCU6uyoEktgOK0pn9s4wFRpBnhb67QQXRj3nHfMbunZrbY7nAsjqIk-dsjMsnjGr5gCU1mtJZZbUXiZDg7HrnAR8iSeDhtW4xm0VV_zIPhfOFp27z5MQbhoLvgEBGoxL99ZsIt0Yk6ifKwIJ4qoc8SBFzOQGgCDnW"/>
</div>
<div class="order-1 lg:order-2 space-y-8">
<span class="label-md uppercase tracking-[0.2em] text-on-surface-variant font-bold text-xs block">Is this you?</span>
<h2 class="text-4xl font-bold">Designed for the growth-minded</h2>
<ul class="space-y-6">
<li class="flex gap-4">
<div class="mt-1 w-6 h-6 rounded-full bg-secondary text-white flex items-center justify-center flex-shrink-0">
<span class="material-symbols-outlined text-xs" data-icon="check">check</span>
</div>
<div>
<h4 class="font-bold">Agency Owners</h4>
<p class="text-on-surface-variant text-sm">Scale your clients' accounts with confidence and predictable results.</p>
</div>
</li>
<li class="flex gap-4">
<div class="mt-1 w-6 h-6 rounded-full bg-secondary text-white flex items-center justify-center flex-shrink-0">
<span class="material-symbols-outlined text-xs" data-icon="check">check</span>
</div>
<div>
<h4 class="font-bold">E-commerce Entrepreneurs</h4>
<p class="text-on-surface-variant text-sm">Stop burning budget on ads that don't convert and master your own traffic.</p>
</div>
</li>
<li class="flex gap-4">
<div class="mt-1 w-6 h-6 rounded-full bg-secondary text-white flex items-center justify-center flex-shrink-0">
<span class="material-symbols-outlined text-xs" data-icon="check">check</span>
</div>
<div>
<h4 class="font-bold">Career Freelancers</h4>
<p class="text-on-surface-variant text-sm">Charge premium rates by providing high-level strategy instead of just execution.</p>
</div>
</li>
</ul>
</div>
</div>
</section>
<!-- Pricing Section -->
<section class="py-32 px-6">
<div class="max-w-4xl mx-auto text-center">
<div class="bg-surface-container-lowest p-12 lg:p-20 rounded-xl shadow-2xl border border-primary/5 relative overflow-hidden">
<div class="absolute top-0 right-0 bg-primary text-on-primary px-8 py-2 rounded-bl-xl text-xs font-bold tracking-widest uppercase">Best Value</div>
<h2 class="text-4xl font-bold mb-4">Investment for Growth</h2>
<p class="text-on-surface-variant mb-10">Get lifetime access to all modules, templates, and the private community.</p>
<div class="flex flex-col items-center mb-12">
<span class="text-7xl font-extrabold tracking-tighter text-on-surface">$599</span>
<span class="text-on-surface-variant font-medium mt-2">One-time payment or 3x $220</span>
</div>
<div class="flex flex-col sm:flex-row justify-center gap-4">
<button class="px-12 py-5 bg-gradient-to-br from-primary to-primary-container text-on-primary rounded-full font-extrabold shadow-xl active:scale-95 transition-all text-xl">Enroll in Course</button>
</div>
<div class="mt-12 pt-12 border-t border-surface-container-highest flex flex-wrap justify-center gap-8">
<div class="flex items-center gap-2 opacity-60">
<span class="material-symbols-outlined" data-icon="update">update</span>
<span class="text-xs font-bold uppercase tracking-widest">Lifetime Updates</span>
</div>
<div class="flex items-center gap-2 opacity-60">
<span class="material-symbols-outlined" data-icon="group">group</span>
<span class="text-xs font-bold uppercase tracking-widest">Private Discord</span>
</div>
<div class="flex items-center gap-2 opacity-60">
<span class="material-symbols-outlined" data-icon="card_membership">card_membership</span>
<span class="text-xs font-bold uppercase tracking-widest">Certification</span>
</div>
</div>
</div>
</div>
</section>
</main>
<!-- BottomNavBar Shell (Mobile Only) -->
<nav class="md:hidden fixed bottom-0 left-0 w-full flex justify-around items-center px-4 pb-8 pt-4 bg-slate-50 dark:bg-slate-950 z-50 rounded-t-[3rem] shadow-[0_-4px_24px_rgba(0,66,156,0.04)]">
<a class="flex flex-col items-center justify-center text-slate-400 px-5 py-2 hover:text-blue-600 transition-all" href="#">
<span class="material-symbols-outlined" data-icon="home">home</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Home</span>
</a>
<a class="flex flex-col items-center justify-center text-blue-700 bg-blue-50 rounded-full px-5 py-2" href="#">
<span class="material-symbols-outlined" data-icon="school">school</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">My Courses</span>
</a>
<a class="flex flex-col items-center justify-center text-slate-400 px-5 py-2 hover:text-blue-600 transition-all" href="#">
<span class="material-symbols-outlined" data-icon="search">search</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Search</span>
</a>
</nav>
</body></html>

<!-- Design System -->
<!DOCTYPE html>

<html class="light" lang="en"><head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;600;700;800&amp;family=Plus+Jakarta+Sans:wght@400;500;600;700&amp;display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap" rel="stylesheet"/>
<script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
<script id="tailwind-config">
      tailwind.config = {
        darkMode: "class",
        theme: {
          extend: {
            "colors": {
                    "surface-container-lowest": "#ffffff",
                    "tertiary-fixed": "#ffdbcf",
                    "on-secondary-fixed": "#00210c",
                    "tertiary-fixed-dim": "#ffb59b",
                    "on-primary-fixed": "#001945",
                    "inverse-on-surface": "#f0f0fb",
                    "on-tertiary-container": "#ffcebd",
                    "on-secondary": "#ffffff",
                    "tertiary-container": "#a93802",
                    "surface-tint": "#215abd",
                    "secondary": "#006d37",
                    "on-background": "#191b23",
                    "surface-container-low": "#f2f3fe",
                    "outline": "#737785",
                    "surface-container-highest": "#e1e2ec",
                    "primary-fixed-dim": "#b0c6ff",
                    "error-container": "#ffdad6",
                    "on-secondary-container": "#00743a",
                    "surface-container-high": "#e7e7f2",
                    "secondary-fixed": "#6bfe9c",
                    "outline-variant": "#c3c6d6",
                    "background": "#faf8ff",
                    "on-primary": "#ffffff",
                    "secondary-fixed-dim": "#4ae183",
                    "primary": "#00429c",
                    "tertiary": "#822800",
                    "on-error": "#ffffff",
                    "surface-bright": "#faf8ff",
                    "error": "#ba1a1a",
                    "inverse-primary": "#b0c6ff",
                    "on-tertiary": "#ffffff",
                    "on-tertiary-fixed-variant": "#812800",
                    "on-surface": "#191b23",
                    "primary-fixed": "#d9e2ff",
                    "surface-container": "#ededf8",
                    "surface-dim": "#d9d9e4",
                    "secondary-container": "#6bfe9c",
                    "primary-container": "#225abd",
                    "surface": "#faf8ff",
                    "on-tertiary-fixed": "#380d00",
                    "inverse-surface": "#2e3038",
                    "on-surface-variant": "#424654",
                    "on-error-container": "#93000a",
                    "on-secondary-fixed-variant": "#005228",
                    "on-primary-container": "#cbd8ff",
                    "on-primary-fixed-variant": "#00429b",
                    "surface-variant": "#e1e2ec"
            },
            "borderRadius": {
                    "DEFAULT": "1rem",
                    "lg": "2rem",
                    "xl": "3rem",
                    "full": "9999px"
            },
            "fontFamily": {
                    "headline": ["Manrope"],
                    "body": ["Plus Jakarta Sans"],
                    "label": ["Plus Jakarta Sans"]
            }
          },
        },
      }
    </script>
<style>
        .material-symbols-outlined {
            font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
            display: inline-block;
            line-height: 1;
        }
        .vibration-feedback-on-tap:active {
            transform: scale(0.95);
        }
    </style>
<style>
    body {
      min-height: max(884px, 100dvh);
    }
  </style>
  </head>
<body class="bg-surface text-on-surface font-body selection:bg-primary-container selection:text-on-primary-container">
<!-- TopAppBar -->
<header class="bg-slate-50/80 dark:bg-slate-950/80 backdrop-blur-xl fixed top-0 w-full z-50">
<div class="flex justify-between items-center px-6 py-4 w-full max-w-7xl mx-auto">
<div class="flex items-center gap-4">
<div class="w-10 h-10 rounded-full bg-primary-container flex items-center justify-center">
<img class="w-full h-full rounded-full object-cover" data-alt="professional male instructor in a sharp blue suit with a confident smile against a minimalist office background" src="https://lh3.googleusercontent.com/aida-public/AB6AXuAgKqmczf4zYN54kutZEMfRGV9DZYzipm52Xa5TG-m4uZFRqNKh6yhrKoGjBf6iV_E6uhYqSaJ13laB4lyIHN4bf47cF-dJBx1XlJzEug3LYDSEEn_g-TphJ41f21EFSz3QVOxqyD-1zyLLstQ1dhMclNdZPT9RWi3087rvnLniR18Hym80x0T8_f0s_MKgbrFB8wRM33tBfDWADDMaYvp4ygdB1nQalmdmS0OE7zyYrt5FubTvC8ZrLWBB-L0rnqDcXzV6g97Mg3U2"/>
</div>
<span class="font-['Manrope'] font-extrabold text-blue-800 dark:text-blue-300 tracking-tighter text-xl">The Atelier</span>
</div>
<nav class="hidden md:flex items-center gap-8">
<a class="text-blue-700 dark:text-blue-400 font-bold font-label text-sm transition-colors" href="#">Home</a>
<a class="text-slate-500 dark:text-slate-400 font-label text-sm hover:bg-slate-100 dark:hover:bg-slate-800 rounded-full transition-colors px-3 py-1" href="#">My Courses</a>
<a class="text-slate-500 dark:text-slate-400 font-label text-sm hover:bg-slate-100 dark:hover:bg-slate-800 rounded-full transition-colors px-3 py-1" href="#">Search</a>
</nav>
<div class="flex items-center gap-2">
<button class="p-2 text-blue-700 dark:text-blue-400 hover:bg-slate-100 dark:hover:bg-slate-800 rounded-full transition-colors active:scale-95 duration-150 ease-in-out">
<span class="material-symbols-outlined" data-icon="notifications">notifications</span>
</button>
</div>
</div>
</header>
<main class="pt-24 pb-32">
<!-- Hero Section -->
<section class="px-6 py-12 md:py-20 max-w-7xl mx-auto">
<div class="grid grid-cols-1 md:grid-cols-12 gap-12 items-center">
<div class="md:col-span-7 space-y-8">
<div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-secondary-container text-on-secondary-container font-label text-xs font-bold uppercase tracking-widest">
<span class="material-symbols-outlined text-sm" data-icon="bolt">bolt</span>
                        New Enrollment Open
                    </div>
<h1 class="font-headline font-extrabold text-5xl md:text-7xl text-on-surface tracking-tight leading-[1.1]">
                        Online courses on <span class="text-primary italic">SMM</span>, target, YouTube and more.
                    </h1>
<p class="text-on-surface-variant text-lg md:text-xl max-w-xl font-body leading-relaxed">
                        Curated learning experiences designed by industry masters to help you dominate the digital landscape.
                    </p>
<div class="flex flex-wrap gap-4">
<button class="rounded-full bg-gradient-to-br from-primary to-primary-container text-on-primary px-10 py-4 font-bold text-lg shadow-lg hover:shadow-primary/20 transition-all active:scale-95">
                            Watch free lesson
                        </button>
<button class="rounded-full px-8 py-4 font-bold text-primary hover:underline transition-all">
                            Browse Courses
                        </button>
</div>
</div>
<div class="md:col-span-5 relative">
<div class="aspect-[4/5] rounded-xl overflow-hidden bg-surface-container-low">
<img class="w-full h-full object-cover" data-alt="high-end editorial portrait of a professional female creative director in a bright minimalist studio with soft natural light" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDWvaaBQCFW26zk4A5GM1zwcqzLdtdZ15XLVK3_zKl4eUMnOLy0zNm4fb8t1m0vFTYTwTjJQAGlA-3rTeNJW0CGSIsv32rP0pJBbmYd0jbFt6UCpXRW_juktNKnHn2OQ7JVHKR1NOum3jfcZpAVUsXf-5_9o3hvRSw_p_R00Mdg7GCsaIXVlWBN6DPhdr6Cva_-tuuHuFqIDGCnJu_Q6wD5KSnXJjDuGLQ7ZvNzyN0fyGkBwNip7j6rcq3ZEXeh7DinUeW9udAB44xX"/>
</div>
<!-- Learning Coach Tooltip -->
<div class="absolute -bottom-6 -left-6 md:-left-12 p-6 bg-inverse-surface/90 backdrop-blur-md rounded-lg shadow-2xl max-w-xs text-white">
<div class="flex gap-3 items-start">
<span class="material-symbols-outlined text-secondary" data-icon="lightbulb">lightbulb</span>
<p class="text-sm font-medium leading-snug">Expert Tip: Success in SMM starts with high-quality visual storytelling, not just algorithms.</p>
</div>
</div>
</div>
</div>
</section>
<!-- About Us Section -->
<section class="bg-surface-container-low py-24">
<div class="max-w-7xl mx-auto px-6">
<div class="flex flex-col md:flex-row gap-16 items-start">
<div class="md:w-1/3">
<span class="font-label text-sm font-bold uppercase tracking-[0.2em] text-on-surface-variant">About Us</span>
<h2 class="font-headline font-bold text-4xl mt-4 text-on-surface">The Digital Sanctuary for Focus.</h2>
</div>
<div class="md:w-2/3">
<p class="text-xl text-on-surface-variant leading-relaxed font-body">
                            Lumina Academy was founded with a singular vision: to bridge the gap between academic theory and industry execution. We don't just teach platforms; we cultivate digital strategists who understand the "why" behind the "how." Our curriculum is live, breathing, and constantly evolving alongside the digital world.
                        </p>
</div>
</div>
</div>
</section>
<!-- Why Us Section (Bento Style) -->
<section class="py-24 max-w-7xl mx-auto px-6">
<div class="text-center mb-16">
<h2 class="font-headline font-bold text-4xl text-on-surface">Why Choose Lumina</h2>
</div>
<div class="grid grid-cols-1 md:grid-cols-4 gap-6">
<div class="md:col-span-2 bg-surface-container-lowest p-8 rounded-lg shadow-sm">
<div class="w-12 h-12 rounded-full bg-primary-fixed flex items-center justify-center mb-6">
<span class="material-symbols-outlined text-primary" data-icon="schedule">schedule</span>
</div>
<h3 class="font-headline font-bold text-xl mb-3">Study anytime</h3>
<p class="text-on-surface-variant leading-relaxed">Lifetime access to all modules, permitting you to learn at your own pace from any corner of the globe.</p>
</div>
<div class="bg-surface-container-lowest p-8 rounded-lg shadow-sm">
<div class="w-12 h-12 rounded-full bg-secondary-fixed flex items-center justify-center mb-6">
<span class="material-symbols-outlined text-secondary" data-icon="handyman">handyman</span>
</div>
<h3 class="font-headline font-bold text-xl mb-3">Practical lessons</h3>
<p class="text-on-surface-variant leading-relaxed">Zero filler. Every lesson is a hands-on project that builds your portfolio.</p>
</div>
<div class="bg-surface-container-lowest p-8 rounded-lg shadow-sm">
<div class="w-12 h-12 rounded-full bg-tertiary-fixed flex items-center justify-center mb-6">
<span class="material-symbols-outlined text-tertiary" data-icon="diversity_3">diversity_3</span>
</div>
<h3 class="font-headline font-bold text-xl mb-3">Mentor support</h3>
<p class="text-on-surface-variant leading-relaxed">Direct 1-on-1 feedback from industry experts who have been in your shoes.</p>
</div>
<div class="md:col-span-4 bg-primary text-on-primary p-12 rounded-lg flex flex-col md:flex-row items-center justify-between gap-8">
<div>
<h3 class="font-headline font-bold text-3xl mb-4">Official Accreditation</h3>
<p class="text-on-primary-container max-w-xl text-lg">Every graduate receives a verified blockchain certificate recognized by our network of over 500+ digital agency partners worldwide.</p>
</div>
<div class="w-24 h-24 flex-shrink-0 bg-white/10 backdrop-blur-md rounded-full flex items-center justify-center">
<span class="material-symbols-outlined text-5xl" data-icon="workspace_premium" style="font-variation-settings: 'FILL' 1;">workspace_premium</span>
</div>
</div>
</div>
</section>
<!-- Our Courses Section -->
<section class="py-24 bg-surface-container-low">
<div class="max-w-7xl mx-auto px-6">
<div class="flex justify-between items-end mb-16">
<div>
<span class="font-label text-sm font-bold uppercase tracking-[0.2em] text-on-surface-variant">Academy Tracks</span>
<h2 class="font-headline font-bold text-4xl mt-4 text-on-surface">Curated Mastery</h2>
</div>
<button class="hidden md:block font-bold text-primary group">
                        View All Programs <span class="inline-block transition-transform group-hover:translate-x-1">→</span>
</button>
</div>
<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
<!-- Course Card 1 -->
<div class="bg-surface-container-lowest rounded-xl overflow-hidden shadow-sm hover:shadow-xl hover:shadow-primary/5 transition-all group">
<div class="h-56 relative overflow-hidden">
<img class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" data-alt="close-up of a high-end smartphone displaying a vibrant social media feed on a wooden table with aesthetic coffee cup" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDznl39Nd-qqdKAy7WH3gS15_kosbrQbPTiwI1AQnCVehkJMJZs-0nu8Ocg81v7hTCw-xtO4TFKIolc7gEEqk6oNXHdr9yI--hZzTr6dc73ohKazm_1JhG5U-jhdDgbsgwcZhaNXHdYVoaPwF3Q9cTH9q3PlJ1i1pSnHXRUYyIAirUaGllJJiB80hTox_WbUmgYtUkHIHV-X1tkaQG1sNgxfw5AupCvdjP-a-6xURQF03r_VFGREGlKPkqjaGcMteIN6hjhBmuOz8aN"/>
<div class="absolute top-4 left-4 bg-white/90 backdrop-blur-md px-3 py-1 rounded-full text-xs font-bold text-primary uppercase">Best Seller</div>
</div>
<div class="p-8">
<h3 class="font-headline font-bold text-2xl mb-3 text-on-surface">Mastering SMM</h3>
<p class="text-on-surface-variant mb-6 line-clamp-2">Complete guide to brand growth across Instagram, TikTok, and LinkedIn in 2024.</p>
<div class="flex items-center justify-between mt-auto">
<div>
<span class="block text-xs font-label text-slate-400 uppercase">Investment</span>
<span class="text-2xl font-extrabold text-on-surface">$299</span>
</div>
<button class="bg-surface-container-highest px-6 py-3 rounded-full font-bold text-on-surface hover:bg-primary hover:text-on-primary transition-colors">
                                    Details / 1 lesson free
                                </button>
</div>
</div>
</div>
<!-- Course Card 2 -->
<div class="bg-surface-container-lowest rounded-xl overflow-hidden shadow-sm hover:shadow-xl hover:shadow-primary/5 transition-all group">
<div class="h-56 relative overflow-hidden">
<img class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" data-alt="professional data dashboard on a large monitor in a dark sleek office with neon blue accents" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDzak52GcTlUIOz3VwIHIYGGPyxXoqAVg00QGf0aLXqQnyxw8SXmEBoQWqaDwvT1SiJ65JuQsrucwUthJX5YYnlySglarOjWPlFiaH2zEi8E2Z0RC2KcUB9x59LKthvUK-oONCRVe7D5vw8Ql_ap202wE6NiSt6OfNVTWaFrKvAhb1sPOj_VxFt8VluqznqaowQ29i-ga2X3PYDnWTHAtSiC3YKs19Gk8-AHRHVrXUzcRpA7ZOkTC4ptbjvxpURe-a6lQQlooHkLJhu"/>
<div class="absolute top-4 left-4 bg-white/90 backdrop-blur-md px-3 py-1 rounded-full text-xs font-bold text-secondary uppercase">Highly Rated</div>
</div>
<div class="p-8">
<h3 class="font-headline font-bold text-2xl mb-3 text-on-surface">Target Advertising</h3>
<p class="text-on-surface-variant mb-6 line-clamp-2">Advanced performance marketing strategies for Meta, Google, and Amazon Ads.</p>
<div class="flex items-center justify-between mt-auto">
<div>
<span class="block text-xs font-label text-slate-400 uppercase">Investment</span>
<span class="text-2xl font-extrabold text-on-surface">$450</span>
</div>
<button class="bg-surface-container-highest px-6 py-3 rounded-full font-bold text-on-surface hover:bg-primary hover:text-on-primary transition-colors">
                                    Details / 1 lesson free
                                </button>
</div>
</div>
</div>
<!-- Course Card 3 -->
<div class="bg-surface-container-lowest rounded-xl overflow-hidden shadow-sm hover:shadow-xl hover:shadow-primary/5 transition-all group">
<div class="h-56 relative overflow-hidden">
<img class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" data-alt="cinematic shot of a professional mirrorless camera on a gimbal stabilizer in a sunlit urban setting" src="https://lh3.googleusercontent.com/aida-public/AB6AXuBqm4xNRZmMvel95l27zoFtFxVF64jX_MXFwhfhkbfsAqKeQu8VZkKYjnaXGP6FbmEsHHEwDPa-EPjoA92Xt9OXxRrwaGSsu39INKcOSYadwMLBuZF5kHO-9KDOZ_6UgUglNOELqFBtwt1g30oZhq-ovuRS9b8cKjR36n8bSaSOvvx9t5oxHo3h6FO9wi-kxengeXhK69t1o1HjGjRdMfkV0VW5knUD-gjFRRGtZeQyX_AaJR8TqhEHEYfP51hIxnewgdlI0iZc7Htm"/>
</div>
<div class="p-8">
<h3 class="font-headline font-bold text-2xl mb-3 text-on-surface">YouTube Growth</h3>
<p class="text-on-surface-variant mb-6 line-clamp-2">From zero to monetized: Video production, SEO, and audience building at scale.</p>
<div class="flex items-center justify-between mt-auto">
<div>
<span class="block text-xs font-label text-slate-400 uppercase">Investment</span>
<span class="text-2xl font-extrabold text-on-surface">$380</span>
</div>
<button class="bg-surface-container-highest px-6 py-3 rounded-full font-bold text-on-surface hover:bg-primary hover:text-on-primary transition-colors">
                                    Details / 1 lesson free
                                </button>
</div>
</div>
</div>
</div>
</div>
</section>
<!-- Testimonials -->
<section class="py-24 max-w-7xl mx-auto px-6">
<div class="grid grid-cols-1 md:grid-cols-2 gap-16">
<div>
<span class="font-label text-sm font-bold uppercase tracking-[0.2em] text-on-surface-variant">Success Stories</span>
<h2 class="font-headline font-bold text-4xl mt-4 mb-8 text-on-surface">What our graduates say</h2>
<div class="space-y-8">
<div class="flex gap-6 items-start p-6 bg-surface rounded-lg">
<div class="w-16 h-16 rounded-full overflow-hidden flex-shrink-0">
<img class="w-full h-full object-cover" data-alt="headshot of a smiling young woman with glasses in a professional studio" src="https://lh3.googleusercontent.com/aida-public/AB6AXuBYrkGhCYhJ3x49cTlRLnEbGsofgfgYB4k2c8a5RRuLuyzCHSZ3UTNCD1zx02sE5QLVbpEP1Ki8_cCAGhDps0AylDRSy_he56P_O78wKgAZwD739ZP1fDznnb6Fzg_-TH-ajG-GK9K-AYckbwuxHfMn3CS7citeGxMTfaq5EnQhC80mcLNRQhu-4mpnI-kCTXg__OD1pBE9nPr_LwHLDfYho42w4Yh38QQgE5blSaRIb4NW2eywdEPpiIJk1s5d9AyNzEjdvp095aJE"/>
</div>
<div>
<p class="text-lg italic text-on-surface-variant mb-4">"The practical approach at Lumina changed my career. I landed a senior SMM role just two months after completing the course."</p>
<h4 class="font-bold text-on-surface">Elena Rodriguez</h4>
<span class="text-sm text-slate-400">Social Media Manager, Flow Agency</span>
</div>
</div>
<div class="flex gap-6 items-start p-6 bg-surface rounded-lg">
<div class="w-16 h-16 rounded-full overflow-hidden flex-shrink-0">
<img class="w-full h-full object-cover" data-alt="portrait of a young man with a beard looking thoughtful in an office environment" src="https://lh3.googleusercontent.com/aida-public/AB6AXuA1ZEuLyYyanryqYGk2XtPFucUPnhAQx8nCjGGRe7cb9RZE0wKV_rSDSgGSqrogc79_7FDzSIwBZCwikdGmDREsI27PcGvxGYxrqdIxAlfVeabZ8q9jXS7Mz4lmKh4NCvA6uRdm7hD-51jjPK43Jv3-WilhwEN43vERsVo7cfcdxx9GjAblfQrG0vLjQlQxfJz_nLivIibfba12Wt4KdPqIqAIVL679R-YEfvi8Ot8IVvjKd7pKQ0XJ06QDWZLYLiN9xvNz7upFdShI"/>
</div>
<div>
<p class="text-lg italic text-on-surface-variant mb-4">"The mentor support is unmatched. Having someone look over my ad accounts saved me thousands in trial and error."</p>
<h4 class="font-bold text-on-surface">Mark Thompson</h4>
<span class="text-sm text-slate-400">Founder, Velocity Media</span>
</div>
</div>
</div>
</div>
<div class="relative group">
<div class="aspect-video bg-slate-900 rounded-xl overflow-hidden relative shadow-2xl">
<img class="w-full h-full object-cover opacity-60" data-alt="cinematic overhead shot of creative professionals working together on a collaborative project in a bright modern office" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDBE7gN-gxvZaw-e0mJJitNy27nLuEgUM2KLTyVupM0vNBgZs3kTbE9P70iRI5n4pzUTVa4FLY4Z-4U0ILIPKm44ns5Uqbd8WQajdo3eCT67519VYQkpciT81hY6hsAlDuliAX-1z_nRNp876ewfScL0f94wgWf9nWJeCvKyRj9JwxnBKiHr6cwdOl6NOuWDIOzWKTe20T7Djn4-fPMVY7Vmz9oJKWTSh4cLBfu4XSQvO3sXK5wRShbaABzNwoKMv1Uxlpb4SH4LrWY"/>
<button class="absolute inset-0 flex items-center justify-center group-hover:scale-110 transition-transform">
<div class="w-20 h-20 rounded-full bg-white flex items-center justify-center text-primary shadow-lg">
<span class="material-symbols-outlined text-4xl" data-icon="play_arrow" style="font-variation-settings: 'FILL' 1;">play_arrow</span>
</div>
</button>
</div>
<p class="mt-4 text-center text-sm font-label text-on-surface-variant font-medium">Watch: Inside the Lumina Learning Experience</p>
</div>
</div>
</section>
<!-- FAQ Section -->
<section class="py-24 bg-surface-container-low">
<div class="max-w-3xl mx-auto px-6">
<h2 class="font-headline font-bold text-4xl text-center mb-12">Frequently Asked Questions</h2>
<div class="space-y-4">
<div class="bg-surface-container-lowest p-6 rounded-lg">
<button class="flex justify-between items-center w-full text-left font-bold text-lg">
<span>How long do I have access to the materials?</span>
<span class="material-symbols-outlined text-primary" data-icon="expand_more">expand_more</span>
</button>
<p class="mt-4 text-on-surface-variant leading-relaxed">You get lifetime access to the course content, including all future updates. The digital landscape changes fast, so we keep our modules fresh.</p>
</div>
<div class="bg-surface-container-lowest p-6 rounded-lg">
<button class="flex justify-between items-center w-full text-left font-bold text-lg">
<span>Is there a certificate after completion?</span>
<span class="material-symbols-outlined text-primary" data-icon="expand_more">expand_more</span>
</button>
</div>
<div class="bg-surface-container-lowest p-6 rounded-lg">
<button class="flex justify-between items-center w-full text-left font-bold text-lg">
<span>Can I pay in installments?</span>
<span class="material-symbols-outlined text-primary" data-icon="expand_more">expand_more</span>
</button>
</div>
</div>
</div>
</section>
</main>
<!-- Footer -->
<footer class="bg-inverse-surface text-on-primary-container py-20">
<div class="max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-4 gap-12">
<div class="md:col-span-1">
<span class="font-['Manrope'] font-extrabold text-white tracking-tighter text-2xl">The Atelier</span>
<p class="mt-6 text-slate-400 text-sm leading-relaxed">Refining the next generation of digital creators and strategists through curated academic excellence.</p>
</div>
<div>
<h4 class="font-bold text-white mb-6">Courses</h4>
<ul class="space-y-4 text-slate-400 text-sm">
<li><a class="hover:text-white transition-colors" href="#">Social Media Marketing</a></li>
<li><a class="hover:text-white transition-colors" href="#">Target Advertising</a></li>
<li><a class="hover:text-white transition-colors" href="#">YouTube Mastery</a></li>
<li><a class="hover:text-white transition-colors" href="#">Content Strategy</a></li>
</ul>
</div>
<div>
<h4 class="font-bold text-white mb-6">Company</h4>
<ul class="space-y-4 text-slate-400 text-sm">
<li><a class="hover:text-white transition-colors" href="#">About Us</a></li>
<li><a class="hover:text-white transition-colors" href="#">Success Stories</a></li>
<li><a class="hover:text-white transition-colors" href="#">Partner Program</a></li>
<li><a class="hover:text-white transition-colors" href="#">Contact</a></li>
</ul>
</div>
<div>
<h4 class="font-bold text-white mb-6">Connect</h4>
<div class="flex gap-4 mb-8">
<a class="w-10 h-10 rounded-full bg-white/10 flex items-center justify-center hover:bg-primary transition-colors" href="#">
<span class="material-symbols-outlined text-xl" data-icon="alternate_email">alternate_email</span>
</a>
<a class="w-10 h-10 rounded-full bg-white/10 flex items-center justify-center hover:bg-primary transition-colors" href="#">
<span class="material-symbols-outlined text-xl" data-icon="video_library">video_library</span>
</a>
<a class="w-10 h-10 rounded-full bg-white/10 flex items-center justify-center hover:bg-primary transition-colors" href="#">
<span class="material-symbols-outlined text-xl" data-icon="public">public</span>
</a>
</div>
<p class="text-xs text-slate-500">© 2024 Lumina Academy. All rights reserved.</p>
</div>
</div>
</footer>
<!-- BottomNavBar (Mobile Only) -->
<nav class="md:hidden fixed bottom-0 left-0 w-full flex justify-around items-center px-4 pb-8 pt-4 bg-slate-50 dark:bg-slate-950 z-50 rounded-t-[3rem] shadow-[0_-4px_24px_rgba(0,66,156,0.04)]">
<a class="flex flex-col items-center justify-center text-blue-700 dark:text-blue-300 bg-blue-50 dark:bg-blue-900/30 rounded-full px-5 py-2 vibration-feedback-on-tap transition-transform duration-300" href="#">
<span class="material-symbols-outlined" data-icon="home" style="font-variation-settings: 'FILL' 1;">home</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Home</span>
</a>
<a class="flex flex-col items-center justify-center text-slate-400 dark:text-slate-500 px-5 py-2 hover:text-blue-600 dark:hover:text-blue-300 transition-all vibration-feedback-on-tap" href="#">
<span class="material-symbols-outlined" data-icon="school">school</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Courses</span>
</a>
<a class="flex flex-col items-center justify-center text-slate-400 dark:text-slate-500 px-5 py-2 hover:text-blue-600 dark:hover:text-blue-300 transition-all vibration-feedback-on-tap" href="#">
<span class="material-symbols-outlined" data-icon="search">search</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Search</span>
</a>
</nav>
</body></html>

<!-- Lumina Academy - Home -->
<!DOCTYPE html>

<html class="light" lang="en"><head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<link href="https://fonts.googleapis.com" rel="preconnect"/>
<link crossorigin="" href="https://fonts.gstatic.com" rel="preconnect"/>
<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@700;800&amp;family=Plus+Jakarta+Sans:wght@400;500;600;700&amp;display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap" rel="stylesheet"/>
<script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
<script id="tailwind-config">
      tailwind.config = {
        darkMode: "class",
        theme: {
          extend: {
            "colors": {
                    "surface-container-lowest": "#ffffff",
                    "tertiary-fixed": "#ffdbcf",
                    "on-secondary-fixed": "#00210c",
                    "tertiary-fixed-dim": "#ffb59b",
                    "on-primary-fixed": "#001945",
                    "inverse-on-surface": "#f0f0fb",
                    "on-tertiary-container": "#ffcebd",
                    "on-secondary": "#ffffff",
                    "tertiary-container": "#a93802",
                    "surface-tint": "#215abd",
                    "secondary": "#006d37",
                    "on-background": "#191b23",
                    "surface-container-low": "#f2f3fe",
                    "outline": "#737785",
                    "surface-container-highest": "#e1e2ec",
                    "primary-fixed-dim": "#b0c6ff",
                    "error-container": "#ffdad6",
                    "on-secondary-container": "#00743a",
                    "surface-container-high": "#e7e7f2",
                    "secondary-fixed": "#6bfe9c",
                    "outline-variant": "#c3c6d6",
                    "background": "#faf8ff",
                    "on-primary": "#ffffff",
                    "secondary-fixed-dim": "#4ae183",
                    "primary": "#00429c",
                    "tertiary": "#822800",
                    "on-error": "#ffffff",
                    "surface-bright": "#faf8ff",
                    "error": "#ba1a1a",
                    "inverse-primary": "#b0c6ff",
                    "on-tertiary": "#ffffff",
                    "on-tertiary-fixed-variant": "#812800",
                    "on-surface": "#191b23",
                    "primary-fixed": "#d9e2ff",
                    "surface-container": "#ededf8",
                    "surface-dim": "#d9d9e4",
                    "secondary-container": "#6bfe9c",
                    "primary-container": "#225abd",
                    "surface": "#faf8ff",
                    "on-tertiary-fixed": "#380d00",
                    "inverse-surface": "#2e3038",
                    "on-surface-variant": "#424654",
                    "on-error-container": "#93000a",
                    "on-secondary-fixed-variant": "#005228",
                    "on-primary-container": "#cbd8ff",
                    "on-primary-fixed-variant": "#00429b",
                    "surface-variant": "#e1e2ec"
            },
            "borderRadius": {
                    "DEFAULT": "1rem",
                    "lg": "2rem",
                    "xl": "3rem",
                    "full": "9999px"
            },
            "fontFamily": {
                    "headline": ["Manrope"],
                    "body": ["Plus Jakarta Sans"],
                    "label": ["Plus Jakarta Sans"]
            }
          },
        },
      }
    </script>
<style>
        .material-symbols-outlined {
            font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
        }
        .vibration-feedback-on-tap:active {
            transform: scale(0.95);
        }
    </style>
<style>
    body {
      min-height: max(884px, 100dvh);
    }
  </style>
  </head>
<body class="bg-surface font-body text-on-surface selection:bg-primary-container selection:text-on-primary-container">
<!-- TopAppBar -->
<header class="fixed top-0 w-full z-50 bg-slate-50/80 backdrop-blur-xl flex justify-between items-center px-6 py-4 w-full">
<div class="flex items-center gap-3">
<button class="material-symbols-outlined text-on-surface-variant p-2 hover:bg-slate-100 rounded-full transition-colors active:scale-95 duration-150 ease-in-out">arrow_back</button>
<h1 class="font-headline font-extrabold text-blue-800 tracking-tighter text-xl">The Atelier</h1>
</div>
<div class="flex items-center gap-4">
<button class="material-symbols-outlined text-slate-500 hover:bg-slate-100 rounded-full p-2 transition-colors active:scale-95 duration-150 ease-in-out">notifications</button>
<div class="w-10 h-10 rounded-full bg-surface-container-highest overflow-hidden border-2 border-primary-container">
<img alt="User profile photo" data-alt="close-up portrait of a professional woman with a warm smile in a brightly lit modern office environment" src="https://lh3.googleusercontent.com/aida-public/AB6AXuAzpeCYPsSfAuGFrgwQfqnNEhJXICqRZ3lSm1OY3GRFVC9Rk1TUhHjUpqUDwlrxvPRoyGJOaZk1ADN0eXYYMdD0BU-EY7LIU931M2_W9ObTZMmFmaHGRSjzo-LF1nNm2G0sYnohpu6h9EQnnc8kTk3MkDj6aSo85ZQrcr5bzmF9P26ryN-QqWgKTCvedqjCD50fyP93QDQ0HuQ0V-hYqRNIAxMIIQIUaCQayP3D7ybpoyI4FJgDyOwt9ZmKd7y4CCaWEl1vxeUvDi-I"/>
</div>
</div>
</header>
<main class="pt-24 pb-32 px-6 max-w-6xl mx-auto">
<!-- Editorial Header -->
<section class="mb-12">
<span class="font-label text-blue-700 font-bold uppercase tracking-widest text-[11px] mb-2 block">Mini-Lesson • Module 01</span>
<h2 class="font-headline font-bold text-4xl md:text-5xl text-on-surface tracking-tight max-w-3xl leading-tight">
                Mastering the Art of <span class="text-primary italic">Visual Storytelling</span>
</h2>
</section>
<!-- Video Player Section -->
<section class="relative group mb-16">
<div class="aspect-video w-full rounded-xl overflow-hidden bg-surface-container-highest shadow-2xl relative">
<img alt="Video Placeholder" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-700" data-alt="cinematic shot of a vintage camera and high-tech monitor on a designer desk with soft blue and purple ambient lighting" src="https://lh3.googleusercontent.com/aida-public/AB6AXuAsNMf_wQbGsQSZD1NXpUzPymmi2WGeSvJ-nIHW4lwEKuHuROYmYaznYBX3A4ExWxBDRXevW1_MT0KNWzmlW9gCGxjJV2DYP9Tta0sxtJqj121802AHtFG02Ync9uGywy8ChphnThstbFr7riYvT8outhpWXO1rN5td7l2Ec0M3KT6Am5DmfGXcyXZHUCoG-Ud-qdln4UWWjmvZvuK7-EYH4C0vCv1uvsW7aoIbQnOsltE7v7bxi3x0pTK5xIVbupqukqY9UGvxRvZZ"/>
<!-- Play Overlay -->
<div class="absolute inset-0 flex items-center justify-center bg-on-surface/20 group-hover:bg-on-surface/10 transition-all duration-300">
<button class="w-20 h-20 md:w-28 md:h-28 bg-surface/90 backdrop-blur-md rounded-full flex items-center justify-center shadow-2xl transition-transform hover:scale-110 active:scale-95 group">
<span class="material-symbols-outlined text-primary text-5xl md:text-6xl" style="font-variation-settings: 'FILL' 1;">play_arrow</span>
</button>
</div>
<!-- Video Metadata Overlay -->
<div class="absolute bottom-0 left-0 right-0 p-6 bg-gradient-to-t from-on-surface/80 to-transparent">
<div class="flex items-center justify-between text-white">
<div class="flex items-center gap-4">
<span class="font-label text-sm font-semibold bg-primary-container px-3 py-1 rounded-full">FREE PREVIEW</span>
<span class="text-sm opacity-90 font-medium">08:42 Duration</span>
</div>
<div class="flex items-center gap-6">
<span class="material-symbols-outlined">closed_caption</span>
<span class="material-symbols-outlined">settings</span>
<span class="material-symbols-outlined">fullscreen</span>
</div>
</div>
</div>
</div>
</section>
<!-- Content & CTA Grid (Editorial 60/40 Split) -->
<div class="grid grid-cols-1 lg:grid-cols-10 gap-16 items-start">
<!-- Information Side -->
<div class="lg:col-span-6 space-y-8">
<div class="space-y-4">
<h3 class="font-headline text-2xl font-bold text-on-surface">About this lesson</h3>
<p class="text-lg leading-relaxed text-on-surface-variant font-body">
                        In this introductory session, we explore the fundamental principles of composition that separate amateur snapshots from professional narratives. You'll learn how to leverage negative space and tonal balance to guide the viewer's eye.
                    </p>
</div>
<div class="grid grid-cols-1 md:grid-cols-2 gap-6 pt-4">
<div class="p-6 bg-surface-container-low rounded-lg space-y-3">
<span class="material-symbols-outlined text-secondary text-3xl">verified</span>
<h4 class="font-bold text-on-surface">Curated Insights</h4>
<p class="text-sm text-on-surface-variant">Access specific techniques used by industry-leading visual directors.</p>
</div>
<div class="p-6 bg-surface-container-low rounded-lg space-y-3">
<span class="material-symbols-outlined text-primary text-3xl">download</span>
<h4 class="font-bold text-on-surface">Resource Pack</h4>
<p class="text-sm text-on-surface-variant">Includes a downloadable PDF guide of the rule of thirds and golden ratio.</p>
</div>
</div>
</div>
<!-- CTA Side (Floating Effect) -->
<div class="lg:col-span-4 sticky top-32">
<div class="bg-surface-container-lowest p-8 rounded-xl shadow-[0_24px_48px_rgba(0,66,156,0.06)] border border-outline-variant/10">
<div class="mb-6">
<span class="font-label text-blue-700 font-bold uppercase tracking-widest text-[10px]">Lifetime Access</span>
<h3 class="font-headline text-3xl font-bold text-on-surface mt-1">Unlock Full Mastery</h3>
<div class="flex items-baseline gap-2 mt-2">
<span class="text-4xl font-extrabold text-on-surface">$149</span>
<span class="text-slate-400 line-through font-medium text-lg">$299</span>
</div>
</div>
<ul class="space-y-4 mb-8">
<li class="flex items-start gap-3">
<span class="material-symbols-outlined text-secondary mt-1">check_circle</span>
<span class="text-sm font-medium text-on-surface-variant">42 HD Video Lessons (24+ hours)</span>
</li>
<li class="flex items-start gap-3">
<span class="material-symbols-outlined text-secondary mt-1">check_circle</span>
<span class="text-sm font-medium text-on-surface-variant">Private Student Discord Community</span>
</li>
<li class="flex items-start gap-3">
<span class="material-symbols-outlined text-secondary mt-1">check_circle</span>
<span class="text-sm font-medium text-on-surface-variant">Direct Feedback from Instructors</span>
</li>
<li class="flex items-start gap-3">
<span class="material-symbols-outlined text-secondary mt-1">check_circle</span>
<span class="text-sm font-medium text-on-surface-variant">Certification of Completion</span>
</li>
</ul>
<button class="w-full bg-gradient-to-br from-primary to-primary-container text-white py-5 rounded-full font-bold text-lg shadow-lg hover:shadow-primary/20 hover:scale-[1.02] active:scale-95 transition-all mb-4">
                        Enroll in Full Course
                    </button>
<p class="text-[11px] text-center text-slate-400 uppercase tracking-tighter font-semibold">
                        30-Day Money Back Guarantee • Secure Payment
                    </p>
</div>
</div>
</div>
</main>
<!-- BottomNavBar (Mobile Only) -->
<nav class="md:hidden fixed bottom-0 left-0 w-full flex justify-around items-center px-4 pb-8 pt-4 bg-slate-50 dark:bg-slate-950 z-50 rounded-t-[3rem] shadow-[0_-4px_24px_rgba(0,66,156,0.04)]">
<div class="flex flex-col items-center justify-center text-slate-400 dark:text-slate-500 px-5 py-2 hover:text-blue-600 transition-all vibration-feedback-on-tap">
<span class="material-symbols-outlined">home</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Home</span>
</div>
<div class="flex flex-col items-center justify-center text-blue-700 dark:text-blue-300 bg-blue-50 dark:bg-blue-900/30 rounded-full px-5 py-2 vibration-feedback-on-tap">
<span class="material-symbols-outlined" style="font-variation-settings: 'FILL' 1;">school</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">My Courses</span>
</div>
<div class="flex flex-col items-center justify-center text-slate-400 dark:text-slate-500 px-5 py-2 hover:text-blue-600 transition-all vibration-feedback-on-tap">
<span class="material-symbols-outlined">search</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Search</span>
</div>
</nav>
<!-- Tonal Shift Spacer -->
<div class="h-1 bg-surface-container-low w-full mt-20"></div>
</body></html>

<!-- Free Mini-Lesson -->
<!DOCTYPE html>

<html class="light" lang="en"><head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>The Atelier - Student Dashboard</title>
<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;600;700;800&amp;family=Plus+Jakarta+Sans:wght@400;500;600;700&amp;display=swap" rel="stylesheet"/>
<!-- Material Symbols -->
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap" rel="stylesheet"/>
<script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
<script id="tailwind-config">
        tailwind.config = {
            darkMode: "class",
            theme: {
                extend: {
                    "colors": {
                        "surface-container-lowest": "#ffffff",
                        "tertiary-fixed": "#ffdbcf",
                        "on-secondary-fixed": "#00210c",
                        "tertiary-fixed-dim": "#ffb59b",
                        "on-primary-fixed": "#001945",
                        "inverse-on-surface": "#f0f0fb",
                        "on-tertiary-container": "#ffcebd",
                        "on-secondary": "#ffffff",
                        "tertiary-container": "#a93802",
                        "surface-tint": "#215abd",
                        "secondary": "#006d37",
                        "on-background": "#191b23",
                        "surface-container-low": "#f2f3fe",
                        "outline": "#737785",
                        "surface-container-highest": "#e1e2ec",
                        "primary-fixed-dim": "#b0c6ff",
                        "error-container": "#ffdad6",
                        "on-secondary-container": "#00743a",
                        "surface-container-high": "#e7e7f2",
                        "secondary-fixed": "#6bfe9c",
                        "outline-variant": "#c3c6d6",
                        "background": "#faf8ff",
                        "on-primary": "#ffffff",
                        "secondary-fixed-dim": "#4ae183",
                        "primary": "#00429c",
                        "tertiary": "#822800",
                        "on-error": "#ffffff",
                        "surface-bright": "#faf8ff",
                        "error": "#ba1a1a",
                        "inverse-primary": "#b0c6ff",
                        "on-tertiary": "#ffffff",
                        "on-tertiary-fixed-variant": "#812800",
                        "on-surface": "#191b23",
                        "primary-fixed": "#d9e2ff",
                        "surface-container": "#ededf8",
                        "surface-dim": "#d9d9e4",
                        "secondary-container": "#6bfe9c",
                        "primary-container": "#225abd",
                        "surface": "#faf8ff",
                        "on-tertiary-fixed": "#380d00",
                        "inverse-surface": "#2e3038",
                        "on-surface-variant": "#424654",
                        "on-error-container": "#93000a",
                        "on-secondary-fixed-variant": "#005228",
                        "on-primary-container": "#cbd8ff",
                        "on-primary-fixed-variant": "#00429b",
                        "surface-variant": "#e1e2ec"
                    },
                    "borderRadius": {
                        "DEFAULT": "1rem",
                        "lg": "2rem",
                        "xl": "3rem",
                        "full": "9999px"
                    },
                    "fontFamily": {
                        "headline": ["Manrope"],
                        "body": ["Plus Jakarta Sans"],
                        "label": ["Plus Jakarta Sans"]
                    }
                }
            }
        }
    </script>
<style>
        .material-symbols-outlined {
            font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
        }
        body { font-family: 'Plus Jakarta Sans', sans-serif; }
        h1, h2, h3 { font-family: 'Manrope', sans-serif; }
    </style>
<style>
    body {
      min-height: max(884px, 100dvh);
    }
  </style>
  </head>
<body class="bg-surface text-on-surface min-h-screen pb-32 md:pb-0">
<!-- TopAppBar from JSON -->
<header class="bg-slate-50/80 dark:bg-slate-950/80 backdrop-blur-xl fixed top-0 w-full z-50">
<div class="flex justify-between items-center px-6 py-4 w-full">
<div class="flex items-center gap-4">
<img alt="User profile photo" class="w-10 h-10 rounded-full object-cover" data-alt="High-end professional portrait of a woman in a creative studio with soft lighting and neutral tones" src="https://lh3.googleusercontent.com/aida-public/AB6AXuBfpRZ-R6KcBM6DZhfdCHY-IYIPvk2ekbs17ycEf8sBUbqzvgmodXattilg1H_jyqBXNci0s1nhpL8OkF2hRtV1d-dVF4rMBkE2UG0Fz67GdZ1IYt9PfE6TKnRp5lAUKPuQGII3LN8G57IcQSxZw9cPeyrdyN0S9Bb9Zv2sFH7WfPajz4OzuFA4QAwAD08cg61RuhMkAVRebtMLtHqaUaThJnfXwHOC9bck_mvnFZceUXlQXZ2qVBs6YVxw5BIONUNtGpNHe5BsHukS"/>
<span class="font-['Manrope'] font-extrabold text-blue-800 dark:text-blue-300 tracking-tighter text-xl">The Atelier</span>
</div>
<!-- Desktop Nav Hidden on Mobile -->
<nav class="hidden md:flex gap-8">
<a class="text-slate-500 dark:text-slate-400 font-semibold hover:text-blue-700 transition-colors" href="#">Home</a>
<a class="text-blue-700 dark:text-blue-400 font-bold" href="#">My Courses</a>
<a class="text-slate-500 dark:text-slate-400 font-semibold hover:text-blue-700 transition-colors" href="#">Search</a>
</nav>
<div class="flex items-center gap-2">
<button class="p-2 hover:bg-slate-100 dark:hover:bg-slate-800 rounded-full transition-colors active:scale-95 duration-150 ease-in-out">
<span class="material-symbols-outlined text-slate-500">notifications</span>
</button>
</div>
</div>
</header>
<main class="pt-24 px-6 max-w-7xl mx-auto">
<!-- Welcome Hero Section (Editorial Asymmetric) -->
<section class="mb-16 grid grid-cols-1 md:grid-cols-12 gap-8 items-center">
<div class="md:col-span-7">
<span class="font-label text-on-surface-variant font-semibold uppercase tracking-widest text-xs mb-3 block">Welcome back, Sarah</span>
<h1 class="text-5xl font-extrabold tracking-tight mb-4 leading-tight">Master your craft through <span class="text-primary">curated focus.</span></h1>
<p class="text-on-surface-variant text-lg max-w-xl leading-relaxed mb-8">You've completed 64% of your current curriculum. Continue where you left off or explore your latest resources.</p>
<div class="flex flex-wrap gap-4">
<button class="bg-gradient-to-br from-primary to-primary-container text-on-primary px-10 py-4 rounded-full font-bold shadow-lg shadow-primary/10 active:scale-95 transition-transform">
                        Resume Learning
                    </button>
</div>
</div>
<div class="md:col-span-5 relative">
<div class="aspect-[4/5] rounded-xl overflow-hidden shadow-2xl">
<img alt="Artistic workspace" class="w-full h-full object-cover" data-alt="Minimalist artist studio with canvas and paints in a sunlit room with clean white walls and wooden floors" src="https://lh3.googleusercontent.com/aida-public/AB6AXuCClA3kFkB_9GMS_FsQBIkFq1CXXhtEPRxmUoUyVyniM3f1qpWxagMwarr0uCDQsHysTy4fvGiBNucX1Mr0B9l8jiAq9AvXv_0BjILVmrTL4XD6xnE-tVFjALYLeXm6061c5gf_SrKBcGQoEW-5c4Zwh__06qlOBCeMjmpqi1YLsdwL_C4n7l39gdlhZ8yyObSmCRXwkSf1piozYTGGOcy8DBe5oDiNSJqZVdFHEmIl-9K9iaCbf7JnDrim_TENKI2kFWPBXPDijDcN"/>
</div>
<!-- Glassmorphic floating card -->
<div class="absolute -bottom-6 -left-6 bg-surface-container-lowest/90 backdrop-blur-xl p-6 rounded-lg shadow-xl max-w-[240px]">
<div class="flex items-center gap-3 mb-2">
<span class="material-symbols-outlined text-secondary" style="font-variation-settings: 'FILL' 1;">verified</span>
<span class="text-sm font-bold">Daily Streak</span>
</div>
<p class="text-2xl font-black text-on-surface">12 Days</p>
<div class="mt-3 w-full bg-surface-container-highest h-1 rounded-full overflow-hidden">
<div class="bg-secondary h-full w-[80%]"></div>
</div>
</div>
</div>
</section>
<!-- Course Grid (Bento Style) -->
<section class="mb-20">
<div class="flex justify-between items-end mb-10">
<div>
<h2 class="text-3xl font-bold tracking-tight">Your Curriculum</h2>
<div class="h-1 w-12 bg-primary mt-2 rounded-full"></div>
</div>
<button class="text-primary font-bold hover:underline">View All Courses</button>
</div>
<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
<!-- Course Card 1 - Main -->
<div class="md:col-span-2 bg-surface-container-lowest rounded-xl p-8 flex flex-col md:flex-row gap-8 shadow-sm hover:shadow-md transition-shadow group">
<div class="md:w-2/5 aspect-video md:aspect-square rounded-lg overflow-hidden shrink-0">
<img alt="Oil painting course" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" data-alt="Close up of vibrant oil paint textures on a palette with professional brushes in soft focus background" src="https://lh3.googleusercontent.com/aida-public/AB6AXuBo_-cju55FApVkkZMWXLTduXUVVzirH2hHExHTf0p_VqvCQ08e8QdkKigBd1Nl_6Ih1zQ4RxTBEWKgXpaV6HZfZWzY-78wN2quWVAFZOZr2j_YXGnaYTg3Iz8wNQsJPRs-xndsBsqHTdaDp3xKEs_TotjFJAITgxJcUSnpQOh-XXUorngyxdUHRBWKsJ_tlhsV_1vaU43ucCEeaO32WLvsU1tt1sfjVxMk7Dqgk8rrYWxjgmcjWCMbYm9oxkgdk2grBBfwtLx7GvVo"/>
</div>
<div class="flex flex-col justify-between py-2">
<div>
<span class="text-[10px] font-bold uppercase tracking-[0.2em] text-secondary mb-2 block">In Progress</span>
<h3 class="text-2xl font-bold mb-3">Oil Painting: Advanced Textures &amp; Light</h3>
<p class="text-on-surface-variant text-sm mb-6 line-clamp-2">Master the complexity of light diffusion and heavy impasto techniques in contemporary portraiture.</p>
</div>
<div>
<div class="flex justify-between text-xs font-bold mb-2">
<span>Module 4 of 12</span>
<span>72%</span>
</div>
<div class="w-full bg-surface-container-highest h-3 rounded-full overflow-hidden">
<div class="bg-secondary h-full w-[72%]"></div>
</div>
</div>
</div>
</div>
<!-- Course Card 2 -->
<div class="bg-surface-container-low rounded-xl p-8 shadow-sm group">
<div class="aspect-video rounded-lg overflow-hidden mb-6">
<img alt="Sketching course" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" data-alt="Detailed graphite sketch of a human eye on textured paper with art pencils scattered around" src="https://lh3.googleusercontent.com/aida-public/AB6AXuC3bQ_yNFi2KReAKDvvWdNypvLRpDqrtkJwFP6_UJ2UX676HLfDnyuwb_byt7SVxGMVxfYua2OKur7lSzt61gCT7561Bb4gcP_u4Agp6f3J3vvGLKfScJjo--Xhek0OTEZeXQCoGvNJYElwxBZej-Fs_b4eVTQNIWisyuqIvj9TSsMUrGfKXOxJSPMkLEJLkipMsLFN8N9H5xvVxr9MMSMpRnFbgmo1w0ZbHdLA-mGTt_6i1wL3G11eSkW5OXR0-fmjNDaHGLagNlpP"/>
</div>
<h3 class="text-xl font-bold mb-2">Anatomical Sketching</h3>
<div class="flex items-center gap-2 mb-6">
<span class="material-symbols-outlined text-sm text-on-surface-variant">schedule</span>
<span class="text-xs text-on-surface-variant font-medium">8 Hours Total</span>
</div>
<div class="w-full bg-surface-container-highest h-3 rounded-full overflow-hidden mb-4">
<div class="bg-secondary h-full w-[15%]"></div>
</div>
<button class="w-full py-3 rounded-full border border-outline-variant/30 font-bold hover:bg-surface-container-lowest transition-colors">Continue</button>
</div>
</div>
</section>
<!-- Resources & Feedback (Asymmetric split) -->
<section class="grid grid-cols-1 md:grid-cols-12 gap-8 mb-20">
<!-- Downloadable Materials -->
<div class="md:col-span-8 bg-surface-container-low rounded-xl p-10">
<div class="flex items-center gap-3 mb-8">
<span class="material-symbols-outlined text-primary p-3 bg-primary/10 rounded-full">folder_open</span>
<h2 class="text-2xl font-bold">Downloadable Materials</h2>
</div>
<div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
<!-- Resource Item -->
<div class="bg-surface-container-lowest p-6 rounded-lg flex items-center justify-between group cursor-pointer hover:bg-primary hover:text-white transition-all duration-300">
<div class="flex items-center gap-4">
<span class="material-symbols-outlined">description</span>
<div>
<p class="font-bold text-sm">Color Theory PDF</p>
<p class="text-[10px] uppercase tracking-wider opacity-60">Manual • 12MB</p>
</div>
</div>
<span class="material-symbols-outlined opacity-0 group-hover:opacity-100 transition-opacity">download</span>
</div>
<!-- Resource Item -->
<div class="bg-surface-container-lowest p-6 rounded-lg flex items-center justify-between group cursor-pointer hover:bg-primary hover:text-white transition-all duration-300">
<div class="flex items-center gap-4">
<span class="material-symbols-outlined">brush</span>
<div>
<p class="font-bold text-sm">Procreate Brush Pack</p>
<p class="text-[10px] uppercase tracking-wider opacity-60">Asset • 45MB</p>
</div>
</div>
<span class="material-symbols-outlined opacity-0 group-hover:opacity-100 transition-opacity">download</span>
</div>
<!-- Resource Item -->
<div class="bg-surface-container-lowest p-6 rounded-lg flex items-center justify-between group cursor-pointer hover:bg-primary hover:text-white transition-all duration-300">
<div class="flex items-center gap-4">
<span class="material-symbols-outlined">movie</span>
<div>
<p class="font-bold text-sm">Masterclass Replay</p>
<p class="text-[10px] uppercase tracking-wider opacity-60">Video • 1.2GB</p>
</div>
</div>
<span class="material-symbols-outlined opacity-0 group-hover:opacity-100 transition-opacity">download</span>
</div>
<!-- Resource Item -->
<div class="bg-surface-container-lowest p-6 rounded-lg flex items-center justify-between group cursor-pointer hover:bg-primary hover:text-white transition-all duration-300">
<div class="flex items-center gap-4">
<span class="material-symbols-outlined">palette</span>
<div>
<p class="font-bold text-sm">Swatch Samples</p>
<p class="text-[10px] uppercase tracking-wider opacity-60">Image • 5MB</p>
</div>
</div>
<span class="material-symbols-outlined opacity-0 group-hover:opacity-100 transition-opacity">download</span>
</div>
</div>
</div>
<!-- Review Section -->
<div class="md:col-span-4 bg-primary text-on-primary rounded-xl p-10 flex flex-col justify-between">
<div>
<h2 class="text-2xl font-bold mb-4">Share Your Progress</h2>
<p class="text-primary-container text-sm leading-relaxed mb-8">How is your learning journey going? Your feedback helps us curate better experiences for everyone.</p>
<div class="flex gap-2 mb-8">
<span class="material-symbols-outlined text-tertiary-fixed" style="font-variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-tertiary-fixed" style="font-variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-tertiary-fixed" style="font-variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-tertiary-fixed" style="font-variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-tertiary-fixed">star</span>
</div>
</div>
<button class="bg-surface-container-lowest text-primary py-4 rounded-full font-bold active:scale-95 transition-transform">Leave a Review</button>
</div>
</section>
</main>
<!-- Support Floating FAB -->
<div class="fixed bottom-24 right-8 z-40 md:bottom-8">
<button class="w-16 h-16 bg-gradient-to-br from-primary to-primary-container text-on-primary rounded-full shadow-2xl flex items-center justify-center group active:scale-90 transition-transform">
<span class="material-symbols-outlined text-3xl group-hover:scale-110 transition-transform">chat</span>
</button>
<!-- Tooltip -->
<div class="absolute bottom-20 right-0 bg-inverse-surface text-white px-4 py-2 rounded-lg text-xs whitespace-nowrap opacity-0 group-hover:opacity-90 transition-opacity pointer-events-none">
            Chat with Support
        </div>
</div>
<!-- BottomNavBar from JSON (Mobile Only) -->
<footer class="md:hidden bg-slate-50 dark:bg-slate-950 fixed bottom-0 left-0 w-full flex justify-around items-center px-4 pb-8 pt-4 z-50 rounded-t-[3rem] shadow-[0_-4px_24px_rgba(0,66,156,0.04)]">
<a class="flex flex-col items-center justify-center text-slate-400 dark:text-slate-500 px-5 py-2 hover:text-blue-600 transition-all" href="#">
<span class="material-symbols-outlined">home</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Home</span>
</a>
<a class="flex flex-col items-center justify-center text-blue-700 dark:text-blue-300 bg-blue-50 dark:bg-blue-900/30 rounded-full px-5 py-2" href="#">
<span class="material-symbols-outlined">school</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">My Courses</span>
</a>
<a class="flex flex-col items-center justify-center text-slate-400 dark:text-slate-500 px-5 py-2 hover:text-blue-600 transition-all" href="#">
<span class="material-symbols-outlined">search</span>
<span class="font-['Plus_Jakarta_Sans'] text-[11px] font-semibold uppercase tracking-widest mt-1">Search</span>
</a>
</footer>
</body></html>
