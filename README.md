<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Юридический аутсорс</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
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
    /* Жесткая фиксация цветов для защиты от перекрытия стилями тильды на мобильных устройствах */
    .btn-telegram {
      color: #ffffff !important;
      transition: all 0.2s ease-in-out;
    }
    .btn-telegram:hover {
      background-color: #b45309 !important;
    }
    .btn-telegram-outline {
      color: #d97706 !important;
      transition: all 0.2s ease-in-out;
    }
    .btn-telegram-outline:hover {
      background-color: #fef3c7 !important;
    }
    /* Плавное появление контента */
    .fade-in {
      animation: fadeIn 0.5s ease-in;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans leading-relaxed">

  <!-- Навигация -->
  <nav class="bg-brand-dark text-white py-3 px-4 shadow-md">
    <div class="max-w-5xl mx-auto flex justify-between items-center">
      <div class="flex items-center gap-3">
        <span class="text-xs tracking-widest uppercase text-slate-300">Адвокат</span>
        <div class="w-px h-5 bg-slate-500"></div>
        <span class="font-bold text-lg font-serif tracking-wide">Напольских Татьяна Сергеевна</span>
      </div>
    </div>
  </nav>

  <!-- Главный экран -->
  <header class="py-12 px-4 text-center max-w-4xl mx-auto fade-in">
    <h1 class="text-3xl md:text-4xl font-bold font-serif mb-4 text-brand-dark">Юридическая безопасность бизнеса без раздутого штата</h1>
    <p class="text-lg text-slate-600 mb-8">Команда адвоката берет на себя все правовые риски, пока вы масштабируете прибыль.</p>
  </header>

  <!-- Калькулятор расходов -->
  <section class="max-w-5xl mx-auto px-4 mb-16 fade-in">
    <div class="bg-white rounded-xl shadow-sm border border-slate-200 p-6 md:p-8">
      <h2 class="text-2xl font-bold mb-8 font-serif text-center">Математика безопасности</h2>
      
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
        <!-- Левая часть: ползунок -->
        <div>
          <div class="flex justify-between mb-2">
            <span class="text-sm font-semibold text-slate-500 uppercase">Зарплата штатного юриста на руки</span>
            <span class="font-bold text-brand-gold" id="salary-val">80 000 ₽</span>
          </div>
          <input type="range" id="salary" min="40000" max="250000" step="5000" value="80000" class="w-full h-2 bg-slate-200 rounded-lg appearance-none cursor-pointer mb-6 accent-brand-gold">
          
          <div class="space-y-3 text-sm text-slate-600">
            <div class="flex justify-between items-center pb-2 border-b border-slate-100">
              <span>Скрытые расходы: Налоги и взносы (~43%)</span>
              <span class="font-medium" id="tax-val">+34 400 ₽</span>
            </div>
            <div class="flex justify-between items-center pb-2 border-b border-slate-100">
              <span>Скрытые расходы: Рабочее место, ПО</span>
              <span class="font-medium">+15 000 ₽</span>
            </div>
            <div class="flex justify-between items-center text-slate-400 italic">
              <span>Отпуска, больничные, риски ошибок</span>
              <span>Непредсказуемо</span>
            </div>
          </div>
        </div>

        <!-- Правая часть: график (столбцы растут вверх) -->
        <div class="flex items-end justify-center h-56 gap-6 pt-8">
           <div class="relative w-24 bg-slate-300 rounded-t-md transition-all duration-300 ease-in-out flex flex-col justify-end" id="bar-staff" style="height: 100%;">
              <span class="absolute -top-7 left-1/2 -translate-x-1/2 whitespace-nowrap text-sm font-bold text-slate-700" id="total-staff">129 400 ₽</span>
              <div class="text-center text-xs font-semibold text-slate-600 pb-2">Штат</div>
           </div>
           <div class="relative w-24 bg-gradient-to-t from-brand-gold to-yellow-500 rounded-t-md shadow-lg transition-all duration-300 ease-in-out flex flex-col justify-end" id="bar-outsource" style="height: 60%;">
              <span class="absolute -top-7 left-1/2 -translate-x-1/2 whitespace-nowrap text-sm font-bold text-brand-gold">75 000 ₽</span>
              <div class="text-center text-xs font-bold text-white pb-2 shadow-sm">Аутсорс</div>
           </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Тарифы -->
  <section class="max-w-5xl mx-auto px-4 mb-16 fade-in">
    <h2 class="text-2xl font-bold mb-8 font-serif text-center">Конструктор решений</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      
      <!-- Базовый -->
      <div class="border border-slate-200 p-6 rounded-xl bg-white shadow-sm hover:shadow-md transition flex flex-col">
        <h3 class="font-bold text-xl mb-1 text-slate-800">Базовый</h3>
        <p class="text-sm text-slate-500 mb-4">Для микробизнеса</p>
        <p class="text-2xl font-bold mb-6 text-brand-dark">40 000 ₽ <span class="text-sm font-normal text-slate-400">/ мес</span></p>
        <div class="flex-grow"></div>
        <hr class="border-slate-100 mb-4">
        <a href="https://t.me/Tatiana_Napolskikh" target="_blank" rel="noopener noreferrer" class="btn-telegram-outline block w-full text-center border-2 border-brand-gold py-3 rounded-lg font-bold">Выбираю Базовый</a>
      </div>

      <!-- Бизнес (Акцентный) -->
      <div class="border border-brand-dark p-6 rounded-xl bg-brand-dark text-white shadow-xl relative transform md:-translate-y-2 flex flex-col">
        <div class="absolute top-0 right-0 bg-brand-gold text-white text-xs font-bold px-3 py-1 rounded-bl-lg rounded-tr-xl">ХИТ</div>
        <h3 class="font-bold text-xl mb-1 text-brand-gold">Бизнес</h3>
        <p class="text-sm text-slate-300 mb-4">Для развивающихся компаний</p>
        <p class="text-2xl font-bold mb-6">75 000 ₽ <span class="text-sm font-normal text-slate-400">/ мес</span></p>
        <div class="flex-grow"></div>
        <hr class="border-slate-700 mb-4">
        <a href="https://t.me/Tatiana_Napolskikh" target="_blank" rel="noopener noreferrer" class="btn-telegram block w-full text-center bg-brand-gold py-3 rounded-lg font-bold shadow-md">Выбираю Бизнес</a>
      </div>

      <!-- Премиум -->
      <div class="border border-slate-200 p-6 rounded-xl bg-white shadow-sm hover:shadow-md transition flex flex-col">
        <h3 class="font-bold text-xl mb-1 text-slate-800">Премиум</h3>
        <p class="text-sm text-slate-500 mb-4">Комплексная защита</p>
        <p class="text-2xl font-bold mb-6 text-brand-dark">150 000 ₽ <span class="text-sm font-normal text-slate-400">/ мес</span></p>
        <div class="flex-grow"></div>
        <hr class="border-slate-100 mb-4">
        <a href="https://t.me/Tatiana_Napolskikh" target="_blank" rel="noopener noreferrer" class="btn-telegram-outline block w-full text-center border-2 border-brand-gold py-3 rounded-lg font-bold">Выбираю Премиум</a>
      </div>

    </div>
  </section>

  <!-- Скрипт логики калькулятора -->
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const salaryInput = document.getElementById('salary');
      const salaryVal = document.getElementById('salary-val');
      const taxVal = document.getElementById('tax-val');
      const totalStaff = document.getElementById('total-staff');
      const barStaff = document.getElementById('bar-staff');
      const barOutsource = document.getElementById('bar-outsource');
      
      const outsourceCost = 75000;
      const workspaceCost = 15000;

      function formatMoney(amount) {
        return amount.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " ") + " ₽";
      }

      function updateCalculator() {
        const salary = parseInt(salaryInput.value, 10);
        const tax = Math.round(salary * 0.43);
        const total = salary + tax + workspaceCost;
        
        salaryVal.textContent = formatMoney(salary);
        taxVal.textContent = "+" + formatMoney(tax);
        totalStaff.textContent = formatMoney(total);
        
        // Расчет высоты столбцов (выравнивание от низа)
        const maxVal = Math.max(total, outsourceCost) * 1.2; // Добавляем 20% запаса сверху для красивого отображения цифр
        
        barStaff.style.height = `${(total / maxVal) * 100}%`;
        barOutsource.style.height = `${(outsourceCost / maxVal) * 100}%`;
      }

      salaryInput.addEventListener('input', updateCalculator);
      
      // Инициализация при первой загрузке
      updateCalculator();
    });
  </script>
</body>
</html>
