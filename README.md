import React, { useState, useEffect, useMemo } from 'react';

const IconCheck = () => <svg className="w-5 h-5 text-amber-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" d="M5 13l4 4L19 7"></path></svg>;
const IconShield = () => <svg className="w-10 h-10 text-amber-500 mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth="1.5" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path></svg>;
const IconScale = () => <svg className="w-10 h-10 text-amber-600 mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth="1.5" d="M3 6l3 1m0 0l-3 9a5.002 5.002 0 006.001 0M6 7l3 9M6 7l6-2m6 2l3-1m-3 1l-3 9a5.002 5.002 0 006.001 0M18 7l3 9m-3-9l-6-2m0-2v2m0 16V5m0 16H9m3 0h3"></path></svg>;
const IconBriefcase = () => <svg className="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth="1.5" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>;
const IconTrendUp = () => <svg className="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"></path></svg>;

const INDUSTRY_DATA = {
  it: { 
    title: "IT и Digital", 
    painPoints: ["Потеря прав на исходный код (нет служебных заданий)", "Штрафы РКН за утечку персональных данных", "Риски утраты IT-аккредитации и льгот", "Финансовая ответственность за сбои в SLA"], 
    solution: "Оформим права на софт, внедрим жесткий режим коммерческой тайны (NDA/NCA) и разработаем договоры, исключающие ваши неконтролируемые убытки в B2B." 
  },
  trade: { 
    title: "Торговля (Опт/Розница)", 
    painPoints: ["Разрывы по НДС и претензии ФНС (ст. 54.1 НК РФ)", "Блокировки счетов по 115-ФЗ", "Кассовые разрывы из-за мертвой дебиторки", "Потребительский экстремизм"], 
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

// Хук для логики калькулятора (Инкапсуляция + useMemo)
const useCalculator = (initialSalary = 80000) => {
  const [inhouseSalary, setInhouseSalary] = useState(initialSalary);
  
  const stats = useMemo(() => {
    const taxesMultiplier = 0.43; // НДФЛ 13% + Взносы ~30%
    const workplaceCost = 15000; // ПО, место
    const calculatedInhouse = Math.round(inhouseSalary + (inhouseSalary * taxesMultiplier) + workplaceCost);
    const calculatedOutsource = 75000; // Средний чек тарифа Бизнес
    const calculatedSavings = calculatedInhouse - calculatedOutsource;
    
    return { calculatedInhouse, calculatedOutsource, calculatedSavings };
  }, [inhouseSalary]);

  return { inhouseSalary, setInhouseSalary, ...stats };
};

// Хук для конструктора тарифов
const useTariffBuilder = (initialTariff = TARIFFS[1]) => {
  const [selectedTariff, setSelectedTariff] = useState(initialTariff);
  const [selectedAddons, setSelectedAddons] = useState([]);

  const toggleAddon = (addon) => {
    setSelectedAddons(prev => 
      prev.find(a => a.id === addon.id) 
        ? prev.filter(a => a.id !== addon.id) 
        : [...prev, addon]
    );
  };

  const finalPrice = useMemo(() => {
    return selectedTariff.basePrice + selectedAddons.reduce((sum, a) => sum + a.price, 0);
  }, [selectedTariff, selectedAddons]);

  return { selectedTariff, setSelectedTariff, selectedAddons, toggleAddon, finalPrice };
};

export default function PremiumInteractiveProposal() {
  const [activeIndustry, setActiveIndustry] = useState('it');
  const [isAnimating, setIsAnimating] = useState(false);
  
  // Инициализация кастомных хуков
  const { inhouseSalary, setInhouseSalary, calculatedInhouse, calculatedOutsource, calculatedSavings } = useCalculator();
  const { selectedTariff, setSelectedTariff, selectedAddons, toggleAddon, finalPrice } = useTariffBuilder();

  // Плавная смена контента в Hero-секции
  const handleIndustryChange = (key) => {
    if (key === activeIndustry) return;
    setIsAnimating(true);
    setTimeout(() => {
      setActiveIndustry(key);
      setIsAnimating(false);
    }, 300); // Соответствует transition-duration
  };

  return (
    <div className="min-h-screen bg-slate-50 font-sans text-slate-900 selection:bg-amber-200">
      
      <nav className="bg-white/90 backdrop-blur-md sticky top-0 z-50 border-b border-slate-200 shadow-sm">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
          <div className="flex items-center">
            <div className="flex flex-col">
              <span className="text-[9px] md:text-[10px] text-amber-700 tracking-[0.3em] uppercase font-bold mb-0.5 md:mb-1">Адвокат</span>
              <span className="font-serif text-base sm:text-lg md:text-xl text-slate-900 font-bold tracking-normal md:tracking-wide leading-none">Напольских Татьяна Сергеевна</span>
            </div>
          </div>
          <div className="hidden lg:flex space-x-8 text-xs font-bold text-slate-500 tracking-widest uppercase">
            <a href="#calculator" className="hover:text-amber-700 transition-colors">Анализ расходов</a>
            <a href="#tariffs" className="hover:text-amber-700 transition-colors">Конструктор защиты</a>
            <a href="#cases" className="hover:text-amber-700 transition-colors">Практика</a>
          </div>
          <a href="#contact" className="hidden sm:inline-flex bg-slate-900 text-white px-6 py-2.5 rounded-sm text-xs font-bold uppercase tracking-wider hover:bg-amber-700 transition-colors shadow-lg shadow-slate-900/10">
            Заказать аудит
          </a>
        </div>
      </nav>

      <section className="relative pt-20 pb-28 lg:pt-32 lg:pb-40 overflow-hidden bg-slate-900 text-white">
        {/* Премиальный фон: Глубокий графит + мягкие засветки */}
        <div className="absolute inset-0 overflow-hidden pointer-events-none">
          <div className="absolute -top-40 -right-40 w-96 h-96 bg-amber-900/30 rounded-full mix-blend-screen filter blur-[100px] opacity-60"></div>
          <div className="absolute bottom-0 -left-40 w-96 h-96 bg-slate-800 rounded-full mix-blend-screen filter blur-[100px] opacity-80"></div>
        </div>
        
        <div className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <span className="inline-block py-1 px-4 rounded-full bg-amber-500/10 text-amber-500 font-semibold text-xs tracking-widest uppercase border border-amber-500/20 mb-8">
            Интерактивное предложение
          </span>
          <h1 className="font-serif text-4xl md:text-6xl lg:text-7xl font-bold tracking-tight mb-6 leading-[1.1]">
            Замените штатного юриста <br className="hidden md:block"/>на <span className="text-transparent bg-clip-text bg-gradient-to-r from-amber-200 to-amber-600">команду адвоката</span>
          </h1>
          <p className="max-w-2xl mx-auto text-lg md:text-xl text-slate-400 mb-12 font-light">
            Сфокусируйтесь на росте бизнеса. Мы берем на себя договоры, защиту от штрафов и суды. Выберите свою сферу, чтобы увидеть главные риски:
          </p>

          <div className="max-w-4xl mx-auto">
            <div className="flex flex-wrap justify-center gap-3 mb-10" role="tablist">
              {Object.entries(INDUSTRY_DATA).map(([key, data]) => (
                <button
                  key={key}
                  role="tab"
                  aria-selected={activeIndustry === key}
                  onClick={() => handleIndustryChange(key)}
                  className={`px-6 py-3 rounded-md font-medium text-sm transition-all duration-300 border ${
                    activeIndustry === key 
                    ? 'bg-amber-600 text-white border-amber-600 shadow-lg shadow-amber-900/50 scale-105' 
                    : 'bg-white/5 text-slate-300 border-white/10 hover:bg-white/10 hover:border-white/20'
                  }`}
                >
                  {data.title}
                </button>
              ))}
            </div>

            {/* Блок с плавной сменой контента */}
            <div className={`bg-slate-800/50 border border-slate-700 backdrop-blur-md rounded-2xl p-6 md:p-10 text-left transition-opacity duration-300 ${isAnimating ? 'opacity-0' : 'opacity-100'}`}>
              <h3 className="font-serif text-2xl font-bold text-white mb-6">Типичные риски: {INDUSTRY_DATA[activeIndustry].title}</h3>
              <div className="grid md:grid-cols-2 gap-5 mb-8">
                {INDUSTRY_DATA[activeIndustry].painPoints.map((point, idx) => (
                  <div key={idx} className="flex items-start">
                    <div className="flex-shrink-0 w-6 h-6 rounded-full bg-red-500/10 border border-red-500/20 flex items-center justify-center mr-4 mt-0.5">
                      <span className="text-red-400 text-xs">✕</span>
                    </div>
                    <span className="text-slate-300 text-sm leading-relaxed">{point}</span>
                  </div>
                ))}
              </div>
              <div className="bg-amber-900/20 border border-amber-700/30 rounded-xl p-6 flex flex-col sm:flex-row items-start">
                <div className="flex-shrink-0 mr-4 mt-1"><IconShield /></div>
                <div>
                  <h4 className="font-bold text-amber-500 mb-2 tracking-wide uppercase text-sm">Наше решение</h4>
                  <p className="text-slate-200 leading-relaxed">{INDUSTRY_DATA[activeIndustry].solution}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="calculator" className="py-24 bg-white relative">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="font-serif text-3xl md:text-5xl font-bold text-slate-900 mb-6">Математика безопасности</h2>
            <p className="text-lg text-slate-500 max-w-2xl mx-auto font-light">Зарплата в вакансии — это только вершина айсберга. Посчитайте реальные расходы на содержание одного юриста в штате.</p>
          </div>

          <div className="grid lg:grid-cols-2 gap-16 items-center">
            {/* Левая колонка: Инпуты и детализация */}
            <div className="bg-slate-50 p-8 md:p-10 rounded-3xl border border-slate-100 shadow-sm">
              <div className="mb-10">
                <label className="flex justify-between text-sm font-semibold text-slate-700 mb-6 uppercase tracking-wider">
                  <span>Зарплата юриста (на руки)</span>
                  <span className="text-amber-700">{inhouseSalary.toLocaleString()} ₽/мес</span>
                </label>
                <input 
                  type="range" 
                  min="40000" max="250000" step="5000" 
                  value={inhouseSalary}
                  onChange={(e) => setInhouseSalary(Number(e.target.value))}
                  aria-label="Выбор зарплаты штатного юриста"
                  className="w-full h-1.5 bg-slate-200 rounded-lg appearance-none cursor-pointer accent-amber-600 focus:outline-none focus:ring-2 focus:ring-amber-500/50"
                />
                <div className="flex justify-between text-xs text-slate-400 mt-3 font-medium">
                  <span>40 тыс. ₽</span>
                  <span>250 тыс. ₽</span>
                </div>
              </div>

              <div className="space-y-5 text-sm text-slate-600 font-medium">
                <div className="flex justify-between items-center pb-5 border-b border-slate-200/60">
                  <span>Скрытые расходы: Налоги и взносы (~43%)</span>
                  <span className="text-slate-900">+{Math.round(inhouseSalary * 0.43).toLocaleString()} ₽</span>
                </div>
                <div className="flex justify-between items-center pb-5 border-b border-slate-200/60">
                  <span>Скрытые расходы: Рабочее место, ПО</span>
                  <span className="text-slate-900">+15 000 ₽</span>
                </div>
                <div className="flex justify-between items-center text-slate-400">
                  <span>Отпуска, больничные, риски ошибок</span>
                  <span className="italic">Непредсказуемо</span>
                </div>
              </div>
            </div>

            <div className="relative">
              <div className="flex items-end justify-center gap-6 md:gap-12 h-64 mb-8 pt-10">
                {/* Бар: Штатный юрист */}
                <div className="w-1/3 max-w-[120px] flex flex-col items-center group" style={{ height: '100%' }}>
                  <div className="text-slate-400 text-[10px] font-bold mb-2 opacity-0 group-hover:opacity-100 transition-opacity uppercase tracking-widest">Штат</div>
                  <div className="w-full bg-slate-300 rounded-t-md relative flex-1 transition-all duration-500 border border-slate-400/20">
                    <div className="absolute -top-8 left-1/2 -translate-x-1/2 text-lg font-bold text-slate-800 whitespace-nowrap">{calculatedInhouse.toLocaleString()} ₽</div>
                  </div>
                </div>
                {/* Бар: Аутсорс */}
                <div className="w-1/3 max-w-[120px] flex flex-col items-center group" style={{ height: `${(calculatedOutsource / calculatedInhouse) * 100}%`, minHeight: '30%' }}>
                  <div className="text-amber-600 text-[10px] font-bold mb-2 opacity-0 group-hover:opacity-100 transition-opacity uppercase tracking-widest">Аутсорс</div>
                  <div className="w-full bg-gradient-to-t from-amber-600 to-amber-400 rounded-t-md relative flex-1 transition-all duration-500 shadow-[0_0_20px_rgba(245,158,11,0.3)]">
                    <div className="absolute -top-8 left-1/2 -translate-x-1/2 text-lg font-bold text-amber-600 whitespace-nowrap">{calculatedOutsource.toLocaleString()} ₽</div>
                  </div>
                </div>
              </div>

              <div className="bg-slate-900 p-8 rounded-2xl text-white text-center shadow-xl">
                <p className="text-sm text-slate-400 uppercase tracking-widest font-semibold mb-3">Чистая экономия компании</p>
                <div className="text-4xl md:text-5xl font-serif font-bold text-amber-400 mb-2">
                  {calculatedSavings > 0 ? `${calculatedSavings.toLocaleString()} ₽ / мес` : 'Очевидна'}
                </div>
                <p className="text-sm text-slate-400 font-light mt-4">Вы получаете команду экспертов дешевле, чем одного рядового сотрудника, и 100% гарантию безотрывной работы.</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="tariffs" className="py-24 bg-slate-50 border-t border-slate-200">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="font-serif text-3xl md:text-5xl font-bold text-slate-900 mb-6">Конструктор услуг</h2>
            <p className="text-lg text-slate-500 max-w-2xl mx-auto font-light">Выберите уровень защиты, подходящий вашему бизнесу. Никаких скрытых платежей, только прозрачная ценность.</p>
          </div>

          <div className="flex flex-col lg:flex-row gap-10">
            
            {/* Карточки тарифов (Десктоп и Мобайл) */}
            <div className="lg:w-2/3 grid md:grid-cols-3 gap-6 mb-24 lg:mb-0">
              {TARIFFS.map(tariff => (
                <div 
                  key={tariff.id}
                  onClick={() => setSelectedTariff(tariff)}
                  role="radio"
                  aria-checked={selectedTariff.id === tariff.id}
                  tabIndex="0"
                  className={`relative bg-white rounded-2xl p-8 cursor-pointer transition-all duration-300 border flex flex-col outline-none
                    ${selectedTariff.id === tariff.id 
                      ? 'border-amber-600 shadow-2xl shadow-amber-900/10 scale-[1.02] z-10' 
                      : 'border-slate-200 hover:border-amber-300 hover:shadow-lg'}`}
                >
                  {selectedTariff.id === tariff.id && (
                    <div className="absolute -top-3 left-1/2 transform -translate-x-1/2 bg-amber-600 text-white px-4 py-1 rounded-sm text-xs font-bold tracking-widest uppercase shadow-sm">
                      Выбран
                    </div>
                  )}
                  <h3 className="font-serif text-2xl font-bold text-slate-900 mb-3">{tariff.name}</h3>
                  <p className="text-sm text-slate-500 font-light h-16 mb-6">{tariff.desc}</p>
                  <div className="text-3xl font-bold text-slate-900 mb-8 pb-6 border-b border-slate-100">{tariff.basePrice.toLocaleString()} ₽<span className="text-sm font-normal text-slate-400">/мес</span></div>
                  
                  <ul className="space-y-4 flex-grow">
                    {tariff.features.map((feature, idx) => (
                      <li key={idx} className="flex items-start text-sm text-slate-700">
                        <span className="mr-3 flex-shrink-0 mt-0.5"><IconCheck /></span>
                        <span className="leading-relaxed">{feature}</span>
                      </li>
                    ))}
                  </ul>
                  
                  {/* Кнопка перехода в Telegram */}
                  <div className="mt-8 pt-6 border-t border-slate-100">
                    <a 
                      href="https://t.me/Tatiana_Napolskikh"
                      target="_blank"
                      rel="noopener noreferrer"
                      onClick={(e) => e.stopPropagation()}
                      className={`block w-full py-3 md:py-4 rounded-md text-center text-xs font-bold uppercase tracking-wider transition-all duration-300 ${
                        selectedTariff.id === tariff.id
                          ? 'bg-amber-600 hover:bg-amber-500 text-white shadow-md shadow-amber-900/20'
                          : 'bg-slate-100 hover:bg-slate-200 text-slate-600'
                      }`}
                    >
                      Выбираю «{tariff.name}»
                    </a>
                  </div>
                </div>
              ))}
            </div>

            <div className="hidden lg:block lg:w-1/3">
              <div className="bg-slate-900 rounded-2xl p-8 sticky top-28 text-white shadow-2xl">
                <h3 className="font-serif text-xl font-bold mb-6 text-amber-500">Усиление защиты</h3>
                <div className="space-y-3 mb-8">
                  {ADDONS.map(addon => {
                    const isSelected = selectedAddons.find(a => a.id === addon.id);
                    return (
                      <label key={addon.id} className={`flex items-center justify-between p-4 rounded-lg cursor-pointer border transition-all duration-200 ${isSelected ? 'bg-amber-900/30 border-amber-600/50' : 'bg-white/5 border-white/5 hover:bg-white/10'}`}>
                        <div className="flex items-center">
                          <div className={`w-5 h-5 rounded-sm flex items-center justify-center mr-4 border transition-colors ${isSelected ? 'bg-amber-600 border-amber-600' : 'border-slate-600'}`}>
                            {isSelected && <svg className="w-3 h-3 text-white" fill="currentColor" viewBox="0 0 20 20"><path fillRule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clipRule="evenodd"></path></svg>}
                          </div>
                          <span className="text-sm font-medium select-none text-slate-200">{addon.name}</span>
                        </div>
                        <span className="text-sm text-slate-400 whitespace-nowrap ml-4">+{addon.price.toLocaleString()} ₽</span>
                        <input type="checkbox" className="hidden" aria-label={`Добавить ${addon.name}`} checked={!!isSelected} onChange={() => toggleAddon(addon)} />
                      </label>
                    );
                  })}
                </div>

                <div className="pt-8 border-t border-slate-700">
                  <p className="text-slate-400 text-xs tracking-widest uppercase font-semibold mb-2">Итоговая стоимость</p>
                  <div className="text-4xl font-serif font-bold text-white mb-8">{finalPrice.toLocaleString()} ₽ <span className="text-lg font-sans font-normal text-slate-500">/ мес</span></div>
                  <a href="#contact" className="block w-full text-center bg-amber-600 hover:bg-amber-500 text-white font-bold py-4 rounded-sm transition-colors shadow-lg shadow-amber-600/20 uppercase tracking-wider text-sm">
                    Оформить договор
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div className="lg:hidden fixed bottom-0 left-0 w-full bg-slate-900 border-t border-slate-800 p-4 z-50 shadow-[0_-10px_30px_rgba(0,0,0,0.3)]">
          <div className="max-w-7xl mx-auto flex justify-between items-center">
            <div>
              <p className="text-slate-400 text-xs font-semibold uppercase tracking-wider mb-1">Итого:</p>
              <div className="text-2xl font-serif font-bold text-white">{finalPrice.toLocaleString()} ₽</div>
            </div>
            <a href="#contact" className="bg-amber-600 hover:bg-amber-500 text-white font-bold py-3 px-6 rounded-sm text-sm uppercase tracking-wider shadow-md">
              Оформить
            </a>
          </div>
        </div>
      </section>

      <section id="cases" className="py-24 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex flex-col md:flex-row justify-between items-end mb-16 border-b border-slate-200 pb-8">
            <div className="max-w-3xl">
              <h2 className="font-serif text-3xl md:text-5xl font-bold text-slate-900 mb-6">Практика и результаты</h2>
              <p className="text-lg text-slate-500 font-light">Мы не продаем процесс. Наш KPI — сохраненные активы доверителей. Дела говорят громче слов.</p>
            </div>
          </div>

          <div className="grid md:grid-cols-3 gap-8">
            {[
              { title: "Отбили штраф ФНС на 5,2 млн ₽", text: "Доказали добросовестность контрагентов торговой компании и отменили решение налоговой в досудебном порядке за 2 месяца." },
              { title: "Взыскали 12 млн ₽ дебиторки", text: "Наложили обеспечительные меры на счета должника строительной фирмы, после чего он добровольно выплатил всю сумму и неустойку." },
              { title: "Защитили код IT-стартапа", text: "Взыскали 3 млн ₽ компенсации с бывшего сотрудника за кражу исходного кода благодаря грамотно составленному режиму коммерческой тайны." }
            ].map((kase, idx) => (
              <div key={idx} className="bg-slate-50 rounded-xl p-8 border border-slate-100 hover:border-amber-200 hover:shadow-xl hover:shadow-amber-900/5 transition-all duration-300 group">
                <div className="w-12 h-12 bg-white rounded-full flex items-center justify-center text-amber-600 mb-6 shadow-sm group-hover:scale-110 group-hover:bg-amber-600 group-hover:text-white transition-all">
                  <IconTrendUp />
                </div>
                <h3 className="font-serif text-xl font-bold text-slate-900 mb-4">{kase.title}</h3>
                <p className="text-slate-600 leading-relaxed font-light text-sm">{kase.text}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      <section id="contact" className="py-24 bg-slate-900 relative overflow-hidden">
        {/* Декор CTA */}
        <div className="absolute top-0 right-0 w-1/2 h-full bg-gradient-to-l from-amber-900/20 to-transparent pointer-events-none"></div>
        
        <div className="relative max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-white">
          <div className="inline-flex items-center justify-center px-5 py-2 rounded-full bg-slate-800 text-amber-500 text-xs font-bold uppercase tracking-widest mb-8 border border-slate-700">
            Персональное предложение
          </div>
          <h2 className="font-serif text-4xl md:text-5xl font-bold mb-8">Безопасный тест-драйв</h2>
          <p className="text-xl text-slate-400 mb-12 max-w-2xl mx-auto font-light leading-relaxed">
            Доверие формируется в деле. Оставьте заявку, и мы <strong className="text-white font-medium">бесплатно проведем правовой аудит 1 договора</strong> или разберем текущую претензию от контрагента.
          </p>

          <form className="bg-white rounded-lg p-2 flex flex-col md:flex-row shadow-2xl max-w-2xl mx-auto focus-within:ring-2 focus-within:ring-amber-500 transition-all" onSubmit={(e) => { e.preventDefault(); alert("Заявка принята. С вами свяжется помощник адвоката."); }}>
            <input 
              type="tel" 
              placeholder="Ваш номер телефона или Telegram" 
              aria-label="Номер телефона"
              className="flex-grow bg-transparent border-0 px-6 py-4 text-slate-900 focus:ring-0 placeholder-slate-400 outline-none font-medium"
              required
            />
            <button type="submit" className="mt-2 md:mt-0 bg-amber-600 hover:bg-amber-500 text-white px-8 py-4 rounded-md font-bold uppercase tracking-wide text-sm transition-colors whitespace-nowrap shadow-md">
              Начать работу
            </button>
          </form>
          <p className="text-xs text-slate-500 mt-6 font-light">Нажимая кнопку, вы соглашаетесь с политикой конфиденциальности. Ваши данные защищены адвокатской тайной.</p>
        </div>
      </section>

      <footer className="bg-slate-950 text-slate-500 py-12 border-t border-slate-800 text-sm">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row justify-between items-center pb-24 lg:pb-0">
          <div className="mb-6 md:mb-0 text-center md:text-left">
            <span className="text-amber-700/80 text-[10px] tracking-[0.3em] uppercase font-bold block mb-1">Адвокат</span>
            <span className="text-slate-300 font-serif text-lg md:text-xl font-bold tracking-wide block">Напольских Татьяна Сергеевна</span>
            <span className="font-light mt-2 block text-xs">© {new Date().getFullYear()} Все права защищены.</span>
          </div>
          <div className="flex flex-wrap justify-center gap-6 font-light">
            <a href="#" className="hover:text-amber-500 transition-colors">Реквизиты</a>
            <a href="#" className="hover:text-amber-500 transition-colors">Договор оферты</a>
            <a href="#" className="hover:text-amber-500 transition-colors">Политика конфиденциальности</a>
          </div>
        </div>
      </footer>

    </div>
  );
}
