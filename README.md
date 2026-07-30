<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Юридический аутсорс - Адвокат Напольских Т.С.</title>
  
  <!-- Подключение шрифтов -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            serif: ['Playfair Display', 'serif'],
          },
          colors: {
            brand: {
              dark: '#1e293b', /* Глубокий графитовый */
              gold: '#d97706', /* Бронзовый акцент */
              light: '#f8fafc'
            }
          }
        }
      }
    }
  </script>
  <style>
    /* Кастомные стили для защиты от Тильды */
    .btn-telegram { color: #ffffff !important; transition: all 0.2s ease-in-out; }
    .btn-telegram:hover { background-color: #b45309 !important; }
    .btn-telegram-outline { color: #d97706 !important; transition: all 0.2s ease-in-out; }
    .btn-telegram-outline:hover { background-color: #fef3c7 !important; }
    
    /* Анимация табов */
    .fade-transition { transition: opacity 0.3s ease-in-out; }
    .opacity-0 { opacity: 0; }
    .opacity-100 { opacity: 1; }
    
    /* Стили ползунка */
    input[type=range]::-webkit-slider-thumb {
      -webkit-appearance: none;
      height: 18px; width: 18px;
      border-radius: 50%;
      background: #d97706;
      cursor: pointer;
      margin-top: -6px;
    }
    input[type=range]::-webkit-slider-runnable-track {
      width: 100%; height: 6px;
      cursor: pointer;
      background: #e2e8f0;
      border-radius: 4px;
    }
  </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans leading-relaxed antialiased">

  <nav class="bg-brand-dark text-white py-4 px-4 shadow-md sticky top-0 z-50">
    <div class="max-w-6xl mx-auto flex justify-between items-center">
      <div class="flex items-center gap-4">
        <span class="text-xs tracking-widest uppercase text-slate-400 font-semibold">Адвокат</span>
        <div class="w-px h-6 bg-slate-600"></div>
        <span class="font-bold text-xl md:text-2xl font-serif tracking-wide">Напольских Татьяна Сергеевна</span>
      </div>
      <div class="hidden md:flex gap-6 text-sm font-medium text-slate-300">
        <a href="#risks" class="hover:text-brand-gold transition">Риски</a>
        <a href="#calculator" class="hover:text-brand-gold transition">Калькулятор</a>
        <a href="#tariffs" class="hover:text-brand-gold transition">Тарифы</a>
      </div>
    </div>
  </nav>

  <section id="risks" class="py-12 md:py-16 px-4 max-w-6xl mx-auto">
    <div class="text-center mb-10">
      <div class="inline-block py-1 px-4 rounded-full bg-brand-gold/10 text-brand-gold font-semibold text-xs tracking-widest uppercase mb-4 border border-brand-gold/20">Интерактивное предложение</div>
      <h1 class="text-3xl md:text-5xl font-bold font-serif mb-4 text-brand-dark leading-tight">Замените штатного юриста <br class="hidden md:block"/>на команду адвоката</h1>
      <p class="text-lg text-slate-600 max-w-2xl mx-auto">Выберите вашу сферу бизнеса, чтобы увидеть главные финансовые и правовые риски, которые мы берем на себя:</p>
    </div>

    <!-- Табы индустрий -->
    <div class="flex flex-wrap justify-center gap-2 mb-8">
      <button class="ind-btn px-5 py-2.5 rounded-md font-medium text-sm transition-all duration-300 border bg-brand-gold text-white border-brand-gold shadow-md" data-tab="it">IT и Digital</button>
      <button class="ind-btn px-5 py-2.5 rounded-md font-medium text-sm transition-all duration-300 border bg-white text-slate-600 border-slate-200 hover:bg-slate-100" data-tab="trade">Торговля (Опт/Розница)</button>
      <button class="ind-btn px-5 py-2.5 rounded-md font-medium text-sm transition-all duration-300 border bg-white text-slate-600 border-slate-200 hover:bg-slate-100" data-tab="construction">Строительство</button>
      <button class="ind-btn px-5 py-2.5 rounded-md font-medium text-sm transition-all duration-300 border bg-white text-slate-600 border-slate-200 hover:bg-slate-100" data-tab="services">Сфера услуг</button>
    </div>

    <!-- Контент индустрий -->
    <div id="ind-content" class="fade-transition opacity-100 bg-white border border-slate-200 rounded-xl p-6 md:p-8 shadow-sm max-w-4xl mx-auto">
      <h3 id="ind-title" class="font-serif text-2xl font-bold text-brand-dark mb-6">Типичные риски: IT и Digital</h3>
      <div id="ind-points" class="grid md:grid-cols-2 gap-4 mb-8">
        <!-- JS injects points here -->
      </div>
      <div class="bg-orange-50 border border-orange-100 rounded-lg p-5 flex items-start gap-4">
        <svg class="w-8 h-8 text-brand-gold flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path></svg>
        <div>
          <h4 class="font-bold text-brand-gold mb-1 text-sm uppercase tracking-wider">Наше решение</h4>
          <p id="ind-solution" class="text-slate-700 text-sm leading-relaxed">Оформим права на софт, внедрим жесткий режим коммерческой тайны (NDA/NCA) и разработаем договоры, исключающие ваши неконтролируемые убытки в B2B.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="calculator" class="bg-white py-12 md:py-16 border-t border-slate-200">
    <div class="max-w-5xl mx-auto px-4">
      <h2 class="text-3xl font-bold mb-3 font-serif text-center text-brand-dark">Математика безопасности</h2>
      <p class="text-center text-slate-500 mb-10 max-w-2xl mx-auto">Зарплата в вакансии — это только вершина айсберга. Посчитайте реальные расходы на содержание одного юриста в штате.</p>
      
      <div class="grid grid-cols-1 md:grid-cols-2 gap-10 items-center bg-slate-50 border border-slate-100 p-6 md:p-10 rounded-2xl">
        <!-- Левая часть: ползунок -->
        <div>
          <div class="flex justify-between mb-4 text-sm font-bold uppercase tracking-wider">
            <span class="text-slate-500">Зарплата юриста (на руки)</span>
            <span class="text-brand-gold" id="salary-val">80 000 ₽/мес</span>
          </div>
          <input type="range" id="salary" min="40000" max="250000" step="5000" value="80000" class="w-full appearance-none bg-transparent mb-6">
          
          <div class="space-y-4 text-sm text-slate-600 font-medium">
            <div class="flex justify-between items-center pb-3 border-b border-slate-200">
              <span>Налоги и взносы (~43%)</span>
              <span class="text-slate-900" id="tax-val">+34 400 ₽</span>
            </div>
            <div class="flex justify-between items-center pb-3 border-b border-slate-200">
              <span>Рабочее место, ПО</span>
              <span class="text-slate-900">+15 000 ₽</span>
            </div>
            <div class="flex justify-between items-center text-slate-400">
              <span>Отпуска, больничные, ошибки</span>
              <span class="italic font-normal">Непредсказуемо</span>
            </div>
          </div>
        </div>

        <!-- Правая часть: график -->
        <div class="relative pt-6">
          <div class="flex items-end justify-center h-48 gap-8 border-b border-slate-300 pb-1">
             <!-- Бар: Штат -->
             <div class="relative w-20 bg-slate-300 rounded-t-sm transition-all duration-300 flex flex-col justify-end group" id="bar-staff" style="height: 100%;">
                <span class="absolute -top-7 left-1/2 -translate-x-1/2 whitespace-nowrap text-sm font-bold text-slate-800" id="total-staff">129 400 ₽</span>
                <span class="text-center text-[10px] font-bold text-slate-500 uppercase tracking-widest pb-2 opacity-50 group-hover:opacity-100 transition">Штат</span>
             </div>
             <!-- Бар: Аутсорс -->
             <div class="relative w-20 bg-gradient-to-t from-brand-gold to-yellow-500 rounded-t-sm shadow-md transition-all duration-300 flex flex-col justify-end" id="bar-outsource" style="height: 58%;">
                <span class="absolute -top-7 left-1/2 -translate-x-1/2 whitespace-nowrap text-sm font-bold text-brand-gold">75 000 ₽</span>
                <span class="text-center text-[10px] font-bold text-white uppercase tracking-widest pb-2">Аутсорс</span>
             </div>
          </div>
          <!-- Экономия -->
          <div class="mt-6 text-center bg-brand-dark text-white p-4 rounded-xl shadow-lg">
            <div class="text-[10px] uppercase tracking-widest text-slate-400 mb-1 font-bold">Чистая экономия компании</div>
            <div class="text-2xl md:text-3xl font-serif font-bold text-brand-gold" id="savings-val">54 400 ₽ / мес</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="tariffs" class="py-12 md:py-16 max-w-6xl mx-auto px-4">
    <h2 class="text-3xl font-bold mb-3 font-serif text-center text-brand-dark">Конструктор услуг</h2>
    <p class="text-center text-slate-500 mb-10 max-w-2xl mx-auto">Никаких скрытых платежей. Только прозрачная ценность и гарантия результата.</p>
    
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      
      <!-- Базовый -->
      <div class="tariff-card cursor-pointer border-2 border-slate-100 p-8 rounded-xl bg-white flex flex-col hover:border-brand-gold/30 transition-all duration-300 relative">
        <div class="selection-badge opacity-0 absolute -top-3 left-1/2 -translate-x-1/2 bg-brand-gold text-white text-[10px] font-bold px-3 py-1 rounded-sm uppercase tracking-widest transition-opacity duration-300">Выбран</div>
        <h3 class="font-bold text-xl mb-2 text-slate-800 font-serif">Старт</h3>
        <p class="text-xs text-slate-500 mb-4 h-8">Идеально для микробизнеса. Базовая защита и консультации.</p>
        <p class="text-3xl font-bold mb-6 text-brand-dark">40 000 ₽ <span class="text-sm font-normal text-slate-400">/мес</span></p>
        <ul class="text-sm text-slate-600 space-y-3 mb-8 flex-grow">
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Консультации (до 5 в мес.)</li>
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Проверка договоров (до 10 шт)</li>
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Подготовка писем (до 3 шт)</li>
        </ul>
        <hr class="border-slate-100 mb-5">
        <a href="https://t.me/Tatiana_Napolskikh" target="_blank" rel="noopener noreferrer" class="tariff-btn btn-telegram-outline block w-full text-center border-2 border-brand-gold py-3 rounded-md font-bold text-xs uppercase tracking-wider">Выбираю Старт</a>
      </div>

      <!-- Бизнес (Акцентный) -->
      <div class="tariff-card cursor-pointer border-2 border-brand-dark p-8 rounded-xl bg-brand-dark text-white flex flex-col relative transform md:-translate-y-4 shadow-xl transition-all duration-300">
        <div class="selection-badge opacity-0 absolute -top-3 left-1/2 -translate-x-1/2 bg-brand-gold text-white text-[10px] font-bold px-3 py-1 rounded-sm uppercase tracking-widest transition-opacity duration-300">Выбран</div>
        <h3 class="font-bold text-xl mb-2 text-brand-gold font-serif">Бизнес</h3>
        <p class="text-xs text-slate-400 mb-4 h-8">Для активно растущих компаний. Полный правовой контроль.</p>
        <p class="text-3xl font-bold mb-6">75 000 ₽ <span class="text-sm font-normal text-slate-400">/мес</span></p>
        <ul class="text-sm text-slate-200 space-y-3 mb-8 flex-grow">
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Всё из тарифа "Старт" (безлимит)</li>
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Разработка нетиповых договоров</li>
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Участие в переговорах</li>
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Досудебное урегулирование</li>
        </ul>
        <hr class="border-slate-700 mb-5">
        <a href="https://t.me/Tatiana_Napolskikh" target="_blank" rel="noopener noreferrer" class="tariff-btn btn-telegram-outline block w-full text-center border-2 border-brand-gold py-3 rounded-md font-bold text-xs uppercase tracking-wider">Выбираю Бизнес</a>
      </div>

      <!-- Премиум -->
      <div class="tariff-card cursor-pointer border-2 border-slate-100 p-8 rounded-xl bg-white flex flex-col hover:border-brand-gold/30 transition-all duration-300 relative">
        <div class="selection-badge opacity-0 absolute -top-3 left-1/2 -translate-x-1/2 bg-brand-gold text-white text-[10px] font-bold px-3 py-1 rounded-sm uppercase tracking-widest transition-opacity duration-300">Выбран</div>
        <h3 class="font-bold text-xl mb-2 text-slate-800 font-serif">Премиум</h3>
        <p class="text-xs text-slate-500 mb-4 h-8">Юридический отдел под ключ. Включая судебную защиту.</p>
        <p class="text-3xl font-bold mb-6 text-brand-dark">150 000 ₽ <span class="text-sm font-normal text-slate-400">/мес</span></p>
        <ul class="text-sm text-slate-600 space-y-3 mb-8 flex-grow">
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Всё из тарифа "Бизнес"</li>
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Представительство в судах</li>
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Сопровождение налоговых проверок</li>
          <li class="flex items-start gap-2"><svg class="w-4 h-4 text-brand-gold mt-0.5 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>Связь 24/7 по критическим вопросам</li>
        </ul>
        <hr class="border-slate-100 mb-5">
        <a href="https://t.me/Tatiana_Napolskikh" target="_blank" rel="noopener noreferrer" class="tariff-btn btn-telegram-outline block w-full text-center border-2 border-brand-gold py-3 rounded-md font-bold text-xs uppercase tracking-wider">Выбираю Премиум</a>
      </div>

    </div>
  </section>

  <section class="bg-slate-50 py-12 md:py-16 border-t border-slate-200">
    <div class="max-w-6xl mx-auto px-4">
      <h2 class="text-3xl font-bold mb-8 font-serif text-brand-dark">Практика и результаты</h2>
      <div class="grid md:grid-cols-3 gap-6">
        <div class="bg-white rounded-xl p-6 border border-slate-100 shadow-sm">
          <div class="text-brand-gold text-2xl font-bold mb-2">5.2 млн ₽</div>
          <h3 class="font-bold text-brand-dark mb-2">Отбит штраф ФНС</h3>
          <p class="text-sm text-slate-600">Доказана добросовестность контрагентов торговой компании по ст. 54.1 НК РФ. Решение налоговой отменено в досудебном порядке.</p>
        </div>
        <div class="bg-white rounded-xl p-6 border border-slate-100 shadow-sm">
          <div class="text-brand-gold text-2xl font-bold mb-2">12 млн ₽</div>
          <h3 class="font-bold text-brand-dark mb-2">Взыскана дебиторка</h3>
          <p class="text-sm text-slate-600">Наложены обеспечительные меры на счета должника стройфирмы. Добровольная выплата всей суммы и неустойки без долгих судов.</p>
        </div>
        <div class="bg-white rounded-xl p-6 border border-slate-100 shadow-sm">
          <div class="text-brand-gold text-2xl font-bold mb-2">3 млн ₽</div>
          <h3 class="font-bold text-brand-dark mb-2">Защита IT-кода</h3>
          <p class="text-sm text-slate-600">Взыскана компенсация с бывшего сотрудника за кражу исходного кода благодаря грамотно внедренному режиму NDA/NCA.</p>
        </div>
      </div>
    </div>
  </section>

  <footer class="bg-brand-dark text-slate-400 py-8 border-t border-slate-800 text-sm">
    <div class="max-w-6xl mx-auto px-4 flex flex-col md:flex-row justify-between items-center gap-4">
      <div>
        <span class="text-[10px] tracking-widest uppercase block mb-1">Адвокат</span>
        <span class="font-serif text-lg font-bold text-slate-200">Напольских Татьяна Сергеевна</span>
      </div>
      <div class="text-center md:text-right">
        <p>© 2024 Все права защищены.</p>
        <p class="text-xs mt-1">Оставляя заявку в Telegram, вы соглашаетесь с политикой конфиденциальности.</p>
      </div>
    </div>
  </footer>

  <script>
    document.addEventListener('DOMContentLoaded', () => {
      // --- Логика Калькулятора ---
      const salaryInput = document.getElementById('salary');
      const salaryVal = document.getElementById('salary-val');
      const taxVal = document.getElementById('tax-val');
      const totalStaff = document.getElementById('total-staff');
      const savingsVal = document.getElementById('savings-val');
      const barStaff = document.getElementById('bar-staff');
      const barOutsource = document.getElementById('bar-outsource');
      
      const outsourceCost = 75000;
      const workspaceCost = 15000;

      function formatMoney(amount) {
        return amount.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " ") + " ₽";
      }

      // Объект для отмены предыдущих анимаций при быстром перетягивании ползунка
      const animationIds = {};

      // Функция плавной анимации чисел
      function animateValue(elementId, obj, start, end, duration, formatFn) {
        if (animationIds[elementId]) window.cancelAnimationFrame(animationIds[elementId]);
        
        let startTimestamp = null;
        const step = (timestamp) => {
          if (!startTimestamp) startTimestamp = timestamp;
          const progress = Math.min((timestamp - startTimestamp) / duration, 1);
          const easeProgress = 1 - Math.pow(1 - progress, 3); // Плавное замедление (ease-out)
          const currentVal = Math.floor(easeProgress * (end - start) + start);
          
          obj.textContent = formatFn(currentVal);
          
          if (progress < 1) {
            animationIds[elementId] = window.requestAnimationFrame(step);
          } else {
            obj.textContent = formatFn(end);
          }
        };
        animationIds[elementId] = window.requestAnimationFrame(step);
      }

      // Стартовые значения для анимации
      let prevSalary = parseInt(salaryInput.value, 10);
      let prevTax = Math.round(prevSalary * 0.43);
      let prevTotal = prevSalary + prevTax + workspaceCost;
      let prevSavings = prevTotal - outsourceCost;

      function updateCalculator() {
        const salary = parseInt(salaryInput.value, 10);
        const tax = Math.round(salary * 0.43);
        const total = salary + tax + workspaceCost;
        const savings = total - outsourceCost;
        
        // Плавная накрутка цифр (скорость 350мс)
        animateValue('sal', salaryVal, prevSalary, salary, 350, val => formatMoney(val) + "/мес");
        animateValue('tax', taxVal, prevTax, tax, 350, val => "+" + formatMoney(val));
        animateValue('tot', totalStaff, prevTotal, total, 350, val => formatMoney(val));
        
        if (savings > 0) {
          animateValue('sav', savingsVal, Math.max(0, prevSavings), savings, 350, val => formatMoney(val) + " / мес");
          savingsVal.classList.remove('text-slate-400');
          savingsVal.classList.add('text-brand-gold');
        } else {
          savingsVal.textContent = "Очевидна";
          savingsVal.classList.remove('text-brand-gold');
          savingsVal.classList.add('text-slate-400');
        }

        // Обновляем "предыдущие" значения для следующего шага
        prevSalary = salary;
        prevTax = tax;
        prevTotal = total;
        prevSavings = savings;
        
        // Высота баров (основана на процентах относительно максимума)
        const maxVal = Math.max(total, outsourceCost) * 1.2; 
        barStaff.style.height = `${(total / maxVal) * 100}%`;
        barOutsource.style.height = `${(outsourceCost / maxVal) * 100}%`;
      }

      salaryInput.addEventListener('input', updateCalculator);
      
      // Инициализация при первой загрузке (без анимации)
      salaryVal.textContent = formatMoney(prevSalary) + "/мес";
      taxVal.textContent = "+" + formatMoney(prevTax);
      totalStaff.textContent = formatMoney(prevTotal);
      if (prevSavings > 0) {
        savingsVal.textContent = formatMoney(prevSavings) + " / мес";
      } else {
        savingsVal.textContent = "Очевидна";
      }
      const initMax = Math.max(prevTotal, outsourceCost) * 1.2; 
      barStaff.style.height = `${(prevTotal / initMax) * 100}%`;
      barOutsource.style.height = `${(outsourceCost / initMax) * 100}%`;

      // --- Логика Вкладок Индустрий ---
      const indData = {
        it: { 
          title: "IT и Digital", 
          points: ["Потеря прав на исходный код (нет служебных заданий)", "Штрафы РКН за утечку персональных данных", "Риски утраты IT-аккредитации и льгот"], 
          solution: "Оформим права на софт, внедрим жесткий режим коммерческой тайны (NDA/NCA) и исключим ваши убытки в B2B." 
        },
        trade: { 
          title: "Торговля (Опт/Розница)", 
          points: ["Разрывы по НДС и претензии ФНС (ст. 54.1 НК РФ)", "Блокировки счетов по 115-ФЗ", "Кассовые разрывы из-за мертвой дебиторки"], 
          solution: "Внедрим правовой скоринг контрагентов, защитим налоговую выгоду и автоматизируем взыскание долгов." 
        },
        construction: { 
          title: "Строительство", 
          points: ["Отказ заказчика от подписания актов КС-2/КС-3", "Взыскание убытков за скрытые дефекты", "Риски субсидиарной ответственности"], 
          solution: "Легализуем односторонние акты приемки, защитим от финансовых удержаний и выстроим обвязку с субподрядчиками." 
        },
        services: { 
          title: "Сфера услуг", 
          points: ["Штрафы ФАС за отсутствие маркировки рекламы", "Переквалификация договоров с самозанятыми в трудовые", "Возврат 100% оплат по ст. 32 ЗОЗПП"], 
          solution: "Разработаем безотзывные оферты, легализуем работу с фрилансерами и защитим активы компании от бывших сотрудников." 
        }
      };

      const indBtns = document.querySelectorAll('.ind-btn');
      const indContent = document.getElementById('ind-content');
      const indTitle = document.getElementById('ind-title');
      const indPoints = document.getElementById('ind-points');
      const indSolution = document.getElementById('ind-solution');

      indBtns.forEach(btn => {
        btn.addEventListener('click', () => {
          const tab = btn.getAttribute('data-tab');
          
          // Смена стилей кнопок
          indBtns.forEach(b => {
            b.className = "ind-btn px-5 py-2.5 rounded-md font-medium text-sm transition-all duration-300 border bg-white text-slate-600 border-slate-200 hover:bg-slate-100";
          });
          btn.className = "ind-btn px-5 py-2.5 rounded-md font-medium text-sm transition-all duration-300 border bg-brand-gold text-white border-brand-gold shadow-md scale-105";

          // Анимация смены контента
          indContent.classList.add('opacity-0');
          setTimeout(() => {
            const data = indData[tab];
            indTitle.textContent = `Типичные риски: ${data.title}`;
            indSolution.textContent = data.solution;
            indPoints.innerHTML = data.points.map(p => `
              <div class="flex items-start gap-3">
                <div class="w-5 h-5 rounded-full bg-red-100 flex items-center justify-center shrink-0 mt-0.5"><span class="text-red-500 text-[10px] font-bold">✕</span></div>
                <span class="text-slate-600 text-sm">${p}</span>
              </div>
            `).join('');
            indContent.classList.remove('opacity-0');
          }, 300);
        });
      });
      
      // Рендер первой вкладки при загрузке
      const firstData = indData['it'];
      indPoints.innerHTML = firstData.points.map(p => `
        <div class="flex items-start gap-3">
          <div class="w-5 h-5 rounded-full bg-red-100 flex items-center justify-center shrink-0 mt-0.5"><span class="text-red-500 text-[10px] font-bold">✕</span></div>
          <span class="text-slate-600 text-sm">${p}</span>
        </div>
      `).join('');

      // --- Логика Выбора Тарифов ---
      const tariffCards = document.querySelectorAll('.tariff-card');
      
      function selectTariff(clickedCard) {
        // 1. Сброс всех карточек
        tariffCards.forEach(card => {
          card.classList.remove('border-brand-gold', 'shadow-2xl', 'scale-105', 'z-10');
          
          const isDark = card.classList.contains('bg-brand-dark');
          if (isDark) {
            card.classList.add('border-brand-dark'); // Возвращаем родную рамку
          } else {
            card.classList.add('border-slate-100');
          }

          // Прячем бейджи
          const badge = card.querySelector('.selection-badge');
          if (badge) badge.classList.add('opacity-0');
          
          // Сбрасываем кнопки в outline-режим (кроме темной темы, там свои стили)
          const btn = card.querySelector('.tariff-btn');
          if (btn) {
            btn.classList.remove('btn-telegram', 'bg-brand-gold', 'text-white');
            btn.classList.add('btn-telegram-outline', 'border-2', 'border-brand-gold', 'text-brand-gold');
          }
        });
        
        // 2. Активация выбранной карточки
        clickedCard.classList.remove('border-slate-100', 'border-brand-dark');
        clickedCard.classList.add('border-brand-gold', 'shadow-2xl', 'scale-105', 'z-10');
        
        const activeBadge = clickedCard.querySelector('.selection-badge');
        if (activeBadge) activeBadge.classList.remove('opacity-0');
        
        // Кнопка становится яркой и залитой цветом
        const activeBtn = clickedCard.querySelector('.tariff-btn');
        if (activeBtn) {
          activeBtn.classList.remove('btn-telegram-outline', 'border-2', 'text-brand-gold');
          activeBtn.classList.add('btn-telegram', 'bg-brand-gold', 'text-white');
        }
      }

      // Привязываем события клика
      tariffCards.forEach(card => {
        card.addEventListener('click', (e) => {
          // Игнорируем клик, если он был по самой ссылке (кнопке Telegram)
          if(e.target.closest('a')) return; 
          selectTariff(card);
        });
      });
      
      // По умолчанию "выбираем" центральный тариф Бизнес
      const defaultCard = document.querySelector('.tariff-card.bg-brand-dark');
      if (defaultCard) {
        selectTariff(defaultCard);
      }

    });
  </script>
</body>
</html>
