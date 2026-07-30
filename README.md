<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Адвокат Напольских Т.С. - Абонентское обслуживание</title>
    
    <!-- Подключение шрифтов -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- Подключение Tailwind CSS через Play CDN -->
    <script>
        window.tailwind = window.tailwind || {};
        window.tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        serif: ['Playfair Display', 'serif'],
                    },
                    colors: {
                        amber: {
                            400: '#fbbf24',
                            500: '#f59e0b',
                            600: '#d97706',
                            700: '#b45309',
                            900: '#78350f',
                        }
                    }
                }
            }
        };
    </script>
    <script src="https://cdn.tailwindcss.com"></script>

    <style>
        /* Кастомные стили для инпута и плавной анимации */
        input[type=range] {
            -webkit-appearance: none;
            width: 100%;
            background: transparent;
        }
        input[type=range]::-webkit-slider-thumb {
            -webkit-appearance: none;
            height: 20px;
            width: 20px;
            border-radius: 50%;
            background: #d97706;
            cursor: pointer;
            margin-top: -8px;
            box-shadow: 0 0 10px rgba(217, 119, 6, 0.5);
        }
        input[type=range]::-webkit-slider-runnable-track {
            width: 100%;
            height: 6px;
            cursor: pointer;
            background: #e2e8f0;
            border-radius: 4px;
        }
        .fade-transition {
            transition: opacity 0.3s ease-in-out;
        }
        .opacity-0 { opacity: 0; }
        .opacity-100 { opacity: 1; }
        
        /* Скрытие скроллбара, если нужно */
        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
    </style>
</head>
<body class="min-h-screen bg-slate-50 font-sans text-slate-900 selection:bg-amber-200 antialiased">

    <nav class="bg-white/90 backdrop-blur-md sticky top-0 z-50 border-b border-slate-200 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
            <div class="flex items-center">
                <div class="flex flex-col">
                    <span class="text-[9px] md:text-[10px] text-amber-700 tracking-[0.3em] uppercase font-bold mb-0.5 md:mb-1">Адвокат</span>
                    <span class="font-serif text-base sm:text-lg md:text-xl text-slate-900 font-bold tracking-normal md:tracking-wide leading-none">Напольских Татьяна Сергеевна</span>
                </div>
            </div>
            <div class="hidden lg:flex space-x-8 text-xs font-bold text-slate-500 tracking-widest uppercase">
                <a href="#calculator" class="hover:text-amber-700 transition-colors">Анализ расходов</a>
                <a href="#tariffs" class="hover:text-amber-700 transition-colors">Конструктор защиты</a>
                <a href="#cases" class="hover:text-amber-700 transition-colors">Практика</a>
            </div>
            <a href="#contact" class="hidden sm:inline-flex bg-slate-900 text-white px-6 py-2.5 rounded-sm text-xs font-bold uppercase tracking-wider hover:bg-amber-700 transition-colors shadow-lg shadow-slate-900/10">
                Заказать аудит
            </a>
        </div>
    </nav>

    <section class="relative pt-12 pb-16 lg:pt-20 lg:pb-24 overflow-hidden bg-slate-900 text-white">
        <div class="absolute inset-0 overflow-hidden pointer-events-none">
            <div class="absolute -top-40 -right-40 w-96 h-96 bg-amber-900/30 rounded-full mix-blend-screen filter blur-[100px] opacity-60"></div>
            <div class="absolute bottom-0 -left-40 w-96 h-96 bg-slate-800 rounded-full mix-blend-screen filter blur-[100px] opacity-80"></div>
        </div>
        
        <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <span class="inline-block py-1 px-4 rounded-full bg-amber-500/10 text-amber-500 font-semibold text-xs tracking-widest uppercase border border-amber-500/20 mb-6">
                Интерактивное предложение
            </span>
            <h1 class="font-serif text-3xl md:text-5xl lg:text-6xl font-bold tracking-tight mb-4 leading-[1.1]">
                Замените штатного юриста <br class="hidden md:block"/>на <span class="text-transparent bg-clip-text bg-gradient-to-r from-amber-200 to-amber-600">команду адвоката</span>
            </h1>
            <p class="max-w-2xl mx-auto text-base md:text-lg text-slate-400 mb-8 font-light">
                Сфокусируйтесь на росте бизнеса. Мы берем на себя договоры, защиту от штрафов и суды. Выберите свою сферу, чтобы увидеть главные риски:
            </p>

            <div class="max-w-4xl mx-auto">
                <div class="flex flex-wrap justify-center gap-3 mb-10" id="industry-tabs">
                    <button data-id="it" class="industry-tab px-6 py-3 rounded-md font-medium text-sm transition-all duration-300 border bg-amber-600 text-white border-amber-600 shadow-lg shadow-amber-900/50 scale-105">IT и Digital</button>
                    <button data-id="trade" class="industry-tab px-6 py-3 rounded-md font-medium text-sm transition-all duration-300 border bg-white/5 text-slate-300 border-white/10 hover:bg-white/10 hover:border-white/20">Торговля (Опт/Розница)</button>
                    <button data-id="construction" class="industry-tab px-6 py-3 rounded-md font-medium text-sm transition-all duration-300 border bg-white/5 text-slate-300 border-white/10 hover:bg-white/10 hover:border-white/20">Строительство</button>
                    <button data-id="services" class="industry-tab px-6 py-3 rounded-md font-medium text-sm transition-all duration-300 border bg-white/5 text-slate-300 border-white/10 hover:bg-white/10 hover:border-white/20">Сфера услуг</button>
                </div>

                <div id="industry-content-wrapper" class="fade-transition opacity-100 bg-slate-800/50 border border-slate-700 backdrop-blur-md rounded-2xl p-6 md:p-10 text-left">
                    <h3 id="industry-title" class="font-serif text-2xl font-bold text-white mb-6">Типичные риски: IT и Digital</h3>
                    <div id="industry-points" class="grid md:grid-cols-2 gap-5 mb-8">
                        <!-- Points injected via JS -->
                    </div>
                    <div class="bg-amber-900/20 border border-amber-700/30 rounded-xl p-6 flex flex-col sm:flex-row items-start">
                        <div class="flex-shrink-0 mr-4 mt-1">
                            <svg class="w-10 h-10 text-amber-500 mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path></svg>
                        </div>
                        <div>
                            <h4 class="font-bold text-amber-500 mb-2 tracking-wide uppercase text-sm">Наше решение</h4>
                            <p id="industry-solution" class="text-slate-200 leading-relaxed">Оформим права на софт, внедрим жесткий режим коммерческой тайны (NDA/NCA) и разработаем договоры, исключающие ваши неконтролируемые убытки в B2B.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="calculator" class="py-12 lg:py-16 bg-white relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-10">
                <h2 class="font-serif text-3xl md:text-4xl font-bold text-slate-900 mb-4">Математика безопасности</h2>
                <p class="text-base text-slate-500 max-w-2xl mx-auto font-light">Зарплата в вакансии — это только вершина айсберга. Посчитайте реальные расходы на содержание одного юриста в штате.</p>
            </div>

            <div class="grid lg:grid-cols-2 gap-10 items-center">
                <div class="bg-slate-50 p-6 md:p-8 rounded-3xl border border-slate-100 shadow-sm">
                    <div class="mb-8">
                        <label class="flex justify-between text-sm font-semibold text-slate-700 mb-6 uppercase tracking-wider">
                            <span>Зарплата юриста (на руки)</span>
                            <span class="text-amber-700" id="salary-val-display">80 000 ₽/мес</span>
                        </label>
                        <input 
                            type="range" id="salary-input"
                            min="40000" max="250000" step="5000" value="80000"
                            class="w-full h-1.5 bg-slate-200 rounded-lg appearance-none cursor-pointer focus:outline-none"
                        />
                        <div class="flex justify-between text-xs text-slate-400 mt-3 font-medium">
                            <span>40 тыс. ₽</span>
                            <span>250 тыс. ₽</span>
                        </div>
                    </div>

                    <div class="space-y-5 text-sm text-slate-600 font-medium">
                        <div class="flex justify-between items-center pb-5 border-b border-slate-200/60">
                            <span>Скрытые расходы: Налоги и взносы (~43%)</span>
                            <span class="text-slate-900" id="taxes-display">+34 400 ₽</span>
                        </div>
                        <div class="flex justify-between items-center pb-5 border-b border-slate-200/60">
                            <span>Скрытые расходы: Рабочее место, ПО</span>
                            <span class="text-slate-900">+15 000 ₽</span>
                        </div>
                        <div class="flex justify-between items-center text-slate-400">
                            <span>Отпуска, больничные, риски ошибок</span>
                            <span class="italic">Непредсказуемо</span>
                        </div>
                    </div>
                </div>

                <div class="relative">
                    <div class="flex items-end justify-center gap-6 md:gap-12 h-48 mb-6 mt-8">
                        <div class="w-1/3 max-w-[90px] group relative h-full flex items-end">
                            <div class="text-slate-400 text-[10px] font-bold opacity-0 group-hover:opacity-100 transition-opacity uppercase tracking-widest absolute -top-6 left-1/2 -translate-x-1/2 whitespace-nowrap">Штат</div>
                            <div id="bar-inhouse" class="w-full bg-slate-300 rounded-t-md relative transition-all duration-300 border border-slate-400/20" style="height: 100%;">
                                <div id="total-inhouse-txt" class="absolute -top-7 left-1/2 -translate-x-1/2 text-sm md:text-base font-bold text-slate-800 whitespace-nowrap">129 400 ₽</div>
                            </div>
                        </div>
                        <div class="w-1/3 max-w-[90px] group relative h-full flex items-end">
                            <div class="text-amber-600 text-[10px] font-bold opacity-0 group-hover:opacity-100 transition-opacity uppercase tracking-widest absolute -top-6 left-1/2 -translate-x-1/2 whitespace-nowrap">Аутсорс</div>
                            <div id="bar-outsource" class="w-full bg-gradient-to-t from-amber-600 to-amber-400 rounded-t-md relative transition-all duration-300 shadow-[0_0_20px_rgba(245,158,11,0.3)]" style="height: 57.9%;">
                                <div class="absolute -top-7 left-1/2 -translate-x-1/2 text-sm md:text-base font-bold text-amber-600 whitespace-nowrap">75 000 ₽</div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-slate-900 p-6 rounded-2xl text-white text-center shadow-xl mt-4">
                        <p class="text-[10px] md:text-xs text-slate-400 uppercase tracking-widest font-semibold mb-2">Чистая экономия компании</p>
                        <div id="savings-display" class="text-3xl md:text-4xl font-serif font-bold text-amber-400 mb-2">54 400 ₽ / мес</div>
                        <p class="text-xs text-slate-400 font-light mt-3">Вы получаете команду экспертов дешевле, чем одного рядового сотрудника, и 100% гарантию безотрывной работы.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="tariffs" class="py-12 lg:py-16 bg-slate-50 border-t border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-10">
                <h2 class="font-serif text-3xl md:text-4xl font-bold text-slate-900 mb-4">Конструктор услуг</h2>
                <p class="text-base text-slate-500 max-w-2xl mx-auto font-light">Выберите уровень защиты, подходящий вашему бизнесу. Никаких скрытых платежей, только прозрачная ценность.</p>
            </div>

            <div class="flex flex-col lg:flex-row gap-8">
                <div class="lg:w-2/3 grid md:grid-cols-3 gap-4 mb-20 lg:mb-0" id="tariff-cards-container">
                    <!-- Cards will be initialized by JS to handle selected state -->
                </div>

                <div class="hidden lg:block lg:w-1/3">
                    <div class="bg-slate-900 rounded-2xl p-6 sticky top-24 text-white shadow-2xl">
                        <h3 class="font-serif text-lg font-bold mb-4 text-amber-500">Усиление защиты</h3>
                        <div class="space-y-2 mb-6" id="addons-container">
                            <!-- Addons injected via JS -->
                        </div>

                        <div class="pt-6 border-t border-slate-700">
                            <p class="text-slate-400 text-[10px] tracking-widest uppercase font-semibold mb-1">Итоговая стоимость</p>
                            <div class="text-3xl font-serif font-bold text-white mb-6"><span id="desktop-total-price">75 000</span> ₽ <span class="text-base font-sans font-normal text-slate-500">/ мес</span></div>
                            <a href="https://t.me/Tatiana_Napolskikh" target="_blank" class="block w-full text-center bg-amber-600 hover:bg-amber-500 text-white font-bold py-3 rounded-sm transition-colors shadow-lg shadow-amber-600/20 uppercase tracking-wider text-xs">
                                Оформить договор
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Мобильная липкая панель (Sticky Bottom Bar) -->
        <div class="lg:hidden fixed bottom-0 left-0 w-full bg-slate-900 border-t border-slate-800 p-4 z-50 shadow-[0_-10px_30px_rgba(0,0,0,0.5)]">
            <div class="max-w-7xl mx-auto flex justify-between items-center">
                <div>
                    <p class="text-slate-400 text-[10px] font-semibold uppercase tracking-wider mb-0.5">Итого в месяц:</p>
                    <div class="text-xl font-serif font-bold text-white"><span id="mobile-total-price">75 000</span> ₽</div>
                </div>
                <a href="https://t.me/Tatiana_Napolskikh" target="_blank" class="bg-amber-600 hover:bg-amber-500 text-white font-bold py-2.5 px-5 rounded-sm text-xs uppercase tracking-wider shadow-md">
                    Оформить
                </a>
            </div>
        </div>
    </section>

    <section id="cases" class="py-12 lg:py-16 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row justify-between items-end mb-10 border-b border-slate-200 pb-6">
                <div class="max-w-3xl">
                    <h2 class="font-serif text-3xl md:text-4xl font-bold text-slate-900 mb-4">Практика и результаты</h2>
                    <p class="text-base text-slate-500 font-light">Мы не продаем процесс. Наш KPI — сохраненные активы доверителей. Дела говорят громче слов.</p>
                </div>
            </div>

            <div class="grid md:grid-cols-3 gap-6">
                <div class="bg-slate-50 rounded-xl p-6 border border-slate-100 hover:border-amber-200 hover:shadow-xl hover:shadow-amber-900/5 transition-all duration-300 group">
                    <div class="w-10 h-10 bg-white rounded-full flex items-center justify-center text-amber-600 mb-4 shadow-sm group-hover:scale-110 group-hover:bg-amber-600 group-hover:text-white transition-all">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"></path></svg>
                    </div>
                    <h3 class="font-serif text-lg font-bold text-slate-900 mb-3">Отбили штраф ФНС на 5,2 млн ₽</h3>
                    <p class="text-slate-600 leading-relaxed font-light text-xs">Доказали добросовестность контрагентов торговой компании и отменили решение налоговой в досудебном порядке за 2 месяца.</p>
                </div>
                <div class="bg-slate-50 rounded-xl p-6 border border-slate-100 hover:border-amber-200 hover:shadow-xl hover:shadow-amber-900/5 transition-all duration-300 group">
                    <div class="w-10 h-10 bg-white rounded-full flex items-center justify-center text-amber-600 mb-4 shadow-sm group-hover:scale-110 group-hover:bg-amber-600 group-hover:text-white transition-all">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"></path></svg>
                    </div>
                    <h3 class="font-serif text-lg font-bold text-slate-900 mb-3">Взыскали 12 млн ₽ дебиторки</h3>
                    <p class="text-slate-600 leading-relaxed font-light text-xs">Наложили обеспечительные меры на счета должника строительной фирмы, после чего он добровольно выплатил всю сумму и неустойку.</p>
                </div>
                <div class="bg-slate-50 rounded-xl p-6 border border-slate-100 hover:border-amber-200 hover:shadow-xl hover:shadow-amber-900/5 transition-all duration-300 group">
                    <div class="w-10 h-10 bg-white rounded-full flex items-center justify-center text-amber-600 mb-4 shadow-sm group-hover:scale-110 group-hover:bg-amber-600 group-hover:text-white transition-all">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"></path></svg>
                    </div>
                    <h3 class="font-serif text-lg font-bold text-slate-900 mb-3">Защитили код IT-стартапа</h3>
                    <p class="text-slate-600 leading-relaxed font-light text-xs">Взыскали 3 млн ₽ компенсации с бывшего сотрудника за кражу исходного кода благодаря грамотно составленному режиму коммерческой тайны.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="py-12 lg:py-16 bg-slate-900 relative overflow-hidden">
        <div class="absolute top-0 right-0 w-1/2 h-full bg-gradient-to-l from-amber-900/20 to-transparent pointer-events-none"></div>
        <div class="relative max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-white">
            <div class="inline-flex items-center justify-center px-4 py-1.5 rounded-full bg-slate-800 text-amber-500 text-[10px] font-bold uppercase tracking-widest mb-6 border border-slate-700">
                Персональное предложение
            </div>
            <h2 class="font-serif text-3xl md:text-4xl font-bold mb-6">Безопасный тест-драйв</h2>
            <p class="text-lg text-slate-400 mb-8 max-w-2xl mx-auto font-light leading-relaxed">
                Доверие формируется в деле. Оставьте заявку, и мы <strong class="text-white font-medium">бесплатно проведем правовой аудит 1 договора</strong> или разберем текущую претензию от контрагента.
            </p>
            <form onsubmit="event.preventDefault(); alert('Заявка отправлена. С вами свяжется помощник адвоката.');" class="bg-white rounded-lg p-2 flex flex-col md:flex-row shadow-2xl max-w-2xl mx-auto focus-within:ring-2 focus-within:ring-amber-500 transition-all">
                <input type="tel" placeholder="Ваш номер телефона или Telegram" class="flex-grow bg-transparent border-0 px-5 py-3 text-slate-900 focus:ring-0 placeholder-slate-400 outline-none font-medium" required>
                <button type="submit" class="mt-2 md:mt-0 bg-amber-600 hover:bg-amber-500 text-white px-6 py-3 rounded-md font-bold uppercase tracking-wide text-xs transition-colors whitespace-nowrap shadow-md">
                    Начать работу
                </button>
            </form>
            <p class="text-xs text-slate-500 mt-6 font-light">Нажимая кнопку, вы соглашаетесь с политикой конфиденциальности. Ваши данные защищены адвокатской тайной.</p>
        </div>
    </section>

    <footer class="bg-slate-950 text-slate-500 py-12 border-t border-slate-800 text-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row justify-between items-center pb-24 lg:pb-0">
            <div class="mb-6 md:mb-0 text-center md:text-left">
                <span class="text-amber-700/80 text-[10px] tracking-[0.3em] uppercase font-bold block mb-1">Адвокат</span>
                <span class="text-slate-300 font-serif text-lg md:text-xl font-bold tracking-wide block">Напольских Татьяна Сергеевна</span>
                <span class="font-light mt-2 block text-xs">© 2024 Все права защищены.</span>
            </div>
            <div class="flex flex-wrap justify-center gap-6 font-light">
                <a href="#" class="hover:text-amber-500 transition-colors">Реквизиты</a>
                <a href="#" class="hover:text-amber-500 transition-colors">Договор оферты</a>
                <a href="#" class="hover:text-amber-500 transition-colors">Политика конфиденциальности</a>
            </div>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Данные
            const INDUSTRY_DATA = {
                it: { 
                    title: "IT и Digital", 
                    painPoints: ["Потеря прав на исходный код (нет служебных заданий)", "Штрафы РКН за утечку персональных данных", "Риски утраты IT-аккредитации и льгот", "Финансовая ответственность за сбои в SLA"], 
                    solution: "Оформим права на софт, внедрим жесткий режим коммерческой тайны (NDA/NCA) и разработаем договоры, исключающие ваши неконтролируемые убытки в B2B." 
                },
                trade: { 
                    title: "Торговля (Опт/Розница)", 
                    painPoints: ["Разрывы по НДС и претензии ФНС (ст. 54.1 НК РФ)", "Блокировки счетов по 115-ФЗ", "Кассовые разрывы из-за мертвой дебиторки", "Субсидиарная ответственность учредителя"], 
                    solution: "Внедрим правовой скоринг контрагентов, защитим налоговую выгоду, автоматизируем взыскание долгов и пресечем злоупотребления со стороны покупателей." 
                },
                construction: { 
                    title: "Строительство", 
                    painPoints: ["Отказ заказчика от подписания актов КС-2/КС-3", "Взыскание убытков за скрытые дефекты", "Удержание гарантийных фондов", "Риски субсидиарной ответственности генподрядчика"], 
                    solution: "Легализуем односторонние акты приемки, защитим от финансовых удержаний и выстроим железобетонную договорную обвязку с субподрядчиками." 
                },
                services: { 
                    title: "Сфера услуг", 
                    painPoints: ["Штрафы ФАС за отсутствие маркировки рекламы", "Возврат 100% оплат по ст. 32 ЗОЗПП", "Переквалификация договоров с самозанятыми в трудовые", "Кража клиентской базы сотрудниками"], 
                    solution: "Разработаем безотзывные оферты, легализуем работу с фрилансерами без рисков доначисления налогов и защитим активы компании от бывших сотрудников." 
                }
            };

            const TARIFFS = [
                { id: 'start', name: 'Старт', basePrice: 40000, desc: 'Идеально для микробизнеса. Базовая защита и консультации.', features: ['Консультации (до 5 в мес.)', 'Проверка договоров (до 10 в мес.)', 'Подготовка писем (до 3 в мес.)'] },
                { id: 'business', name: 'Бизнес', basePrice: 75000, desc: 'Оптимально для активно растущих компаний. Полный контроль.', features: ['Всё из тарифа "Старт" (безлимитно)', 'Разработка нетиповых договоров', 'Участие в переговорах', 'Досудебное урегулирование'] },
                { id: 'premium', name: 'Премиум', basePrice: 150000, desc: 'Юридический отдел под ключ. Включая судебную защиту.', features: ['Всё из тарифа "Бизнес"', 'Представительство в судах', 'Сопровождение налоговых проверок', 'Связь 24/7 по критическим вопросам'] }
            ];

            const ADDONS = [
                { id: 'hr', name: 'Аудит кадрового делопроизводства', price: 15000 },
                { id: 'ip', name: 'Регистрация товарного знака', price: 25000 },
                { id: 'arbitration', name: 'Ведение арбитражного дела', price: 40000 }
            ];

            // Вспомогательные функции
            const formatNumber = (num) => num.toLocaleString('ru-RU');
            const iconCheck = `<svg class="w-5 h-5 text-amber-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>`;

            // --- ЛОГИКА ТАБОВ ИНДУСТРИИ ---
            const tabButtons = document.querySelectorAll('.industry-tab');
            const contentWrapper = document.getElementById('industry-content-wrapper');
            const indTitle = document.getElementById('industry-title');
            const indPoints = document.getElementById('industry-points');
            const indSolution = document.getElementById('industry-solution');

            function renderIndustry(key) {
                const data = INDUSTRY_DATA[key];
                indTitle.textContent = `Типичные риски: ${data.title}`;
                indSolution.textContent = data.solution;
                indPoints.innerHTML = data.painPoints.map(point => `
                    <div class="flex items-start">
                        <div class="flex-shrink-0 w-6 h-6 rounded-full bg-red-500/10 border border-red-500/20 flex items-center justify-center mr-4 mt-0.5">
                            <span class="text-red-400 text-xs">✕</span>
                        </div>
                        <span class="text-slate-300 text-sm leading-relaxed">${point}</span>
                    </div>
                `).join('');
            }

            tabButtons.forEach(btn => {
                btn.addEventListener('click', () => {
                    const id = btn.getAttribute('data-id');
                    
                    // Смена стилей кнопок
                    tabButtons.forEach(b => {
                        b.className = "industry-tab px-6 py-3 rounded-md font-medium text-sm transition-all duration-300 border bg-white/5 text-slate-300 border-white/10 hover:bg-white/10 hover:border-white/20";
                    });
                    btn.className = "industry-tab px-6 py-3 rounded-md font-medium text-sm transition-all duration-300 border bg-amber-600 text-white border-amber-600 shadow-lg shadow-amber-900/50 scale-105";

                    // Плавная анимация контента
                    contentWrapper.classList.remove('opacity-100');
                    contentWrapper.classList.add('opacity-0');
                    
                    setTimeout(() => {
                        renderIndustry(id);
                        contentWrapper.classList.remove('opacity-0');
                        contentWrapper.classList.add('opacity-100');
                    }, 300);
                });
            });
            renderIndustry('it'); // Init

            // --- ЛОГИКА КАЛЬКУЛЯТОРА ---
            const salaryInput = document.getElementById('salary-input');
            const displaySalary = document.getElementById('salary-val-display');
            const displayTaxes = document.getElementById('taxes-display');
            const barInhouse = document.getElementById('bar-inhouse');
            const barOutsource = document.getElementById('bar-outsource');
            const txtInhouse = document.getElementById('total-inhouse-txt');
            const txtSavings = document.getElementById('savings-display');
            
            const OUTSOURCE_PRICE = 75000;
            const WORKPLACE_COST = 15000;

            function updateCalculator() {
                const salary = parseInt(salaryInput.value);
                const taxes = Math.round(salary * 0.43);
                const totalInhouse = salary + taxes + WORKPLACE_COST;
                const savings = totalInhouse - OUTSOURCE_PRICE;

                displaySalary.textContent = `${formatNumber(salary)} ₽/мес`;
                displayTaxes.textContent = `+${formatNumber(taxes)} ₽`;
                txtInhouse.textContent = `${formatNumber(totalInhouse)} ₽`;

                if (savings > 0) {
                    txtSavings.textContent = `${formatNumber(savings)} ₽ / мес`;
                } else {
                    txtSavings.textContent = 'Очевидна';
                }

                // Визуализация столбиков (относительно максимального значения)
                const maxVal = Math.max(totalInhouse, OUTSOURCE_PRICE);
                const inhouseHeight = (totalInhouse / maxVal) * 100;
                const outsourceHeight = (OUTSOURCE_PRICE / maxVal) * 100;

                barInhouse.style.height = `${inhouseHeight}%`;
                barOutsource.style.height = `${outsourceHeight}%`;
            }
            salaryInput.addEventListener('input', updateCalculator);
            updateCalculator(); // Init

            // --- ЛОГИКА ТАРИФОВ И ДОПОЛНЕНИЙ ---
            let currentTariffId = 'business';
            let selectedAddonIds = new Set();
            const tariffContainer = document.getElementById('tariff-cards-container');
            const addonsContainer = document.getElementById('addons-container');
            const valDesktopTotal = document.getElementById('desktop-total-price');
            const valMobileTotal = document.getElementById('mobile-total-price');

            function updateTotal() {
                const tariff = TARIFFS.find(t => t.id === currentTariffId);
                let total = tariff.basePrice;
                selectedAddonIds.forEach(id => {
                    const addon = ADDONS.find(a => a.id === id);
                    if (addon) total += addon.price;
                });
                const formatted = formatNumber(total);
                valDesktopTotal.textContent = formatted;
                valMobileTotal.textContent = formatted;
            }

            function renderTariffs() {
                tariffContainer.innerHTML = TARIFFS.map(tariff => {
                    const isSelected = tariff.id === currentTariffId;
                    const cardClass = isSelected 
                        ? 'border-amber-600 shadow-2xl shadow-amber-900/10 scale-[1.02] z-10' 
                        : 'border-slate-200 hover:border-amber-300 hover:shadow-lg';
                    const btnClass = isSelected
                        ? 'bg-amber-600 hover:bg-amber-500 text-white shadow-md shadow-amber-900/20'
                        : 'bg-slate-100 hover:bg-slate-200 text-slate-600';
                    const badge = isSelected 
                        ? `<div class="absolute -top-3 left-1/2 transform -translate-x-1/2 bg-amber-600 text-white px-3 py-0.5 rounded-sm text-[10px] font-bold tracking-widest uppercase shadow-sm">Выбран</div>` 
                        : '';

                    return `
                    <div data-tariff="${tariff.id}" class="tariff-card relative bg-white rounded-2xl p-5 md:p-6 cursor-pointer transition-all duration-300 border flex flex-col ${cardClass}">
                        ${badge}
                        <h3 class="font-serif text-xl font-bold text-slate-900 mb-2">${tariff.name}</h3>
                        <p class="text-xs text-slate-500 font-light h-14 mb-4">${tariff.desc}</p>
                        <div class="text-2xl font-bold text-slate-900 mb-6 pb-4 border-b border-slate-100">${formatNumber(tariff.basePrice)} ₽<span class="text-xs font-normal text-slate-400">/мес</span></div>
                        <ul class="space-y-3 flex-grow">
                            ${tariff.features.map(f => `
                                <li class="flex items-start text-xs text-slate-700">
                                    <span class="mr-2 flex-shrink-0 mt-0.5">${iconCheck}</span>
                                    <span class="leading-relaxed">${f}</span>
                                </li>
                            `).join('')}
                        </ul>
                        <div class="mt-6 pt-4 border-t border-slate-100">
                            <a href="https://t.me/Tatiana_Napolskikh" target="_blank" rel="noopener noreferrer" class="tariff-link block w-full py-2.5 rounded-md text-center text-[10px] font-bold uppercase tracking-wider transition-all duration-300 ${btnClass}">
                                Выбираю «${tariff.name}»
                            </a>
                        </div>
                    </div>
                    `;
                }).join('');

                // Привязка событий после рендера
                document.querySelectorAll('.tariff-card').forEach(card => {
                    card.addEventListener('click', (e) => {
                        // Игнорируем клик, если он был по самой ссылке
                        if(e.target.closest('a')) return;
                        currentTariffId = card.getAttribute('data-tariff');
                        renderTariffs();
                        updateTotal();
                    });
                });
            }

            function renderAddons() {
                addonsContainer.innerHTML = ADDONS.map(addon => {
                    const isSelected = selectedAddonIds.has(addon.id);
                    const bgClass = isSelected ? 'bg-amber-900/30 border-amber-600/50' : 'bg-white/5 border-white/5 hover:bg-white/10';
                    const boxClass = isSelected ? 'bg-amber-600 border-amber-600' : 'border-slate-600';
                    const checkMark = isSelected ? `<svg class="w-3 h-3 text-white" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path></svg>` : '';
                    
                    return `
                    <label class="addon-label flex items-center justify-between p-4 rounded-lg cursor-pointer border transition-all duration-200 ${bgClass}" data-id="${addon.id}">
                        <div class="flex items-center pointer-events-none">
                            <div class="w-5 h-5 rounded-sm flex items-center justify-center mr-4 border transition-colors ${boxClass}">
                                ${checkMark}
                            </div>
                            <span class="text-sm font-medium select-none text-slate-200">${addon.name}</span>
                        </div>
                        <span class="text-sm text-slate-400 whitespace-nowrap ml-4 pointer-events-none">+${formatNumber(addon.price)} ₽</span>
                    </label>
                    `;
                }).join('');

                document.querySelectorAll('.addon-label').forEach(label => {
                    label.addEventListener('click', () => {
                        const id = label.getAttribute('data-id');
                        if (selectedAddonIds.has(id)) {
                            selectedAddonIds.delete(id);
                        } else {
                            selectedAddonIds.add(id);
                        }
                        renderAddons();
                        updateTotal();
                    });
                });
            }

            renderTariffs();
            renderAddons();
            updateTotal();
        });
    </script>
</body>
</html>
