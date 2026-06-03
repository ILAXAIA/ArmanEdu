# ArmanEdu
привет жемини, я должен сделать проект, и я выбрал сайт по подготовке к ЕНТ, у меня уже есть код, но его нужно будет доработывать, давай я тебе буду писать что нужно будет включать в этот код, а ты будешь добавлять. 
У меня уже есть код, отправлю по полом, ведь тебе весь код почему то не отправляется
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ArmanEdu | Подготовка к ЕНТ</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- FontAwesome для иконок -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-fontawesome/6.4.0/css/all.min.css">
</head>
<body class="bg-gray-50 text-gray-900 font-sans">

    <!-- Навигация -->
    <nav class="bg-white shadow-md sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16">
                <div class="flex items-center">
                    <span class="text-2xl font-bold text-blue-600 cursor-pointer" onclick="navigateTo('main')">
                        <i class="fa-solid fa-graduation-cap mr-2"></i>ArmanEdu
                    </span>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#" onclick="navigateTo('main'); event.preventDefault();" class="nav-link text-blue-600 font-semibold">Главная</a>
                    <a href="#" onclick="scrollToSection('calc-section'); event.preventDefault();" class="nav-link text-gray-600 hover:text-blue-600 font-medium">Калькулятор ЕНТ</a>
                    <a href="#" onclick="scrollToSection('subjects'); event.preventDefault();" class="nav-link text-gray-600 hover:text-blue-600 font-medium">Предметы</a>
                    <a href="#" onclick="scrollToSection('quiz-section'); event.preventDefault();" class="nav-link text-gray-600 hover:text-blue-600 font-medium">Пробные тесты</a>
                    <a href="#" onclick="scrollToSection('faq-section'); event.preventDefault();" class="nav-link text-gray-600 hover:text-blue-600 font-medium">FAQ</a>

                    <div id="auth-zone">
                        <button onclick="openAuthModal()" class="bg-blue-600 text-white px-5 py-2 rounded-lg hover:bg-blue-700 transition font-medium cursor-pointer">Войти</button>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <!-- СТРАНИЦА 1: ГЛАВНАЯ (ОБЕРТКА) -->
    <div id="page-main">
        <!-- Героический блок -->
        <header class="bg-gradient-to-r from-blue-600 to-indigo-700 text-white py-16 px-4 text-center">
            <div class="max-w-4xl mx-auto">
                <span class="bg-blue-500/30 text-blue-100 text-sm font-semibold px-3 py-1 rounded-full mb-4 inline-block">Формат ЕНТ 2026</span>
                <h1 class="text-4xl md:text-5xl font-extrabold mb-4">Подготовка к ЕНТ на 140 баллов</h1>
                <p class="text-lg md:text-xl mb-8 text-blue-100">Выбирай нужные предметы, смотри видео-разборов и щелкай тесты как орешки.</p>
            </div>
        </header>

        <!-- СЕКЦИЯ: КАЛЬКУЛЯТОР КОМБИНАЦИЙ -->
        <section id="calc-section" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
            <div class="bg-white rounded-3xl shadow-sm border border-gray-200 p-6 md:p-10 flex flex-col lg:flex-row gap-10">
                <div class="w-full lg:w-2/5">
                    <span class="text-blue-600 font-bold text-xs uppercase bg-blue-50 px-2.5 py-1 rounded-md">Профориентация</span>
                    <h2 class="text-2xl md:text-3xl font-extrabold text-gray-900 mt-2 mb-4">Калькулятор профессий</h2>
                    <p class="text-gray-500 text-sm mb-6">Укажи свои профильные предметы ЕНТ, чтобы мгновенно узнать, на какие специальности и гранты ты сможешь претендовать.</p>

                    <div class="space-y-4">
                        <div>
                            <label class="block text-xs font-bold uppercase tracking-wider text-gray-500 mb-1.5">Первый профильный предмет</label>
                            <select id="subject1" onchange="updateCombination()" class="w-full bg-gray-50 border border-gray-300 rounded-xl px-4 py-3 text-sm font-medium focus:outline-none focus:border-blue-500 focus:bg-white transition cursor-pointer">
                                <option value="">Выберите предмет...</option>
                                <option value="math">Математика</option>
                                <option value="physics">Физика</option>
                                <option value="informatics">Информатика</option>
                                <option value="chemistry">Химия</option>
                                <option value="biology">Биология</option>
                                <option value="geography">География</option>
                                <option value="world-hist">Всемирная история</option>
                                <option value="kaz-lit">Казахская литература</option>
                            </select>
                        </div>

                        <div>
                            <label class="block text-xs font-bold uppercase tracking-wider text-gray-500 mb-1.5">Второй профильный предмет</label>
                            <select id="subject2" onchange="updateCombination()" class="w-full bg-gray-50 border border-gray-300 rounded-xl px-4 py-3 text-sm font-medium focus:outline-none focus:border-blue-500 focus:bg-white transition cursor-pointer">
                                <option value="">Выберите предмет...</option>
                                <option value="math">Математика</option>
                                <option value="physics">Физика</option>
                                <option value="informatics">Информатика</option>
                                <option value="chemistry">Химия</option>
                                <option value="biology">Биология</option>
                                <option value="geography">География</option>
                                <option value="world-hist">Всемирная история</option>
                                <option value="kaz-lit">Казахская литература</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="w-full lg:w-3/5 border-t lg:border-t-0 lg:border-l border-gray-100 pt-8 lg:pt-0 lg:pl-10 flex flex-col">
                    <h3 class="text-lg font-bold text-gray-800 mb-4 flex items-center gap-2">
                        <i class="fa-solid fa-graduation-cap text-blue-500"></i> Доступные направления и специальности
                    </h3>
                    <div id="calc-results" class="flex-grow space-y-3 overflow-y-auto max-h-[350px] pr-2">
                        <div class="text-center py-12 text-gray-400 text-sm border-2 border-dashed border-gray-100 rounded-2xl">
                            <i class="fa-solid fa-wand-magic-sparkles text-3xl mb-2 text-gray-300"></i>
                            <p>Выберите оба предмета, чтобы увидеть список профессий.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="score-calc-section" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6">
            <div class="bg-gradient-to-br from-gray-900 to-indigo-950 rounded-3xl shadow-xl p-6 md:p-10 text-white flex flex-col md:flex-row gap-8 items-center">

                <div class="w-full md:w-1/2 space-y-4">
                    <div>
                        <span class="text-blue-400 font-bold text-xs uppercase bg-blue-500/10 px-2.5 py-1 rounded-md">Подсчет результатов</span>
                        <h2 class="text-2xl md:text-3xl font-extrabold mt-2 mb-2">Калькулятор баллов ЕНТ</h2>
                        <p class="text-gray-400 text-xs mb-4">Введи свои ожидаемые баллы по предметам, чтобы узнать общий итог.</p>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-gray-400 mb-1">История Казахстана (макс. 20)</label>
                            <input type="number" id="calc-score-hist" min="0" max="20" placeholder="0" oninput="calculateTotalScore()" class="w-full bg-white/10 border border-white/20 rounded-xl px-3 py-2.5 text-sm font-semibold text-white focus:outline-none focus:border-blue-500 focus:bg-white/20 transition">
                        </div>
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-gray-400 mb-1">Мат. грамотность (макс. 10)</label>
                            <input type="number" id="calc-score-math-lit" min="0" max="10" placeholder="0" oninput="calculateTotalScore()" class="w-full bg-white/10 border border-white/20 rounded-xl px-3 py-2.5 text-sm font-semibold text-white focus:outline-none focus:border-blue-500 focus:bg-white/20 transition">
                        </div>
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-gray-400 mb-1">Грамотность чтения (макс. 10)</label>
                            <input type="number" id="calc-score-read-lit" min="0" max="10" placeholder="0" oninput="calculateTotalScore()" class="w-full bg-white/10 border border-white/20 rounded-xl px-3 py-2.5 text-sm font-semibold text-white focus:outline-none focus:border-blue-500 focus:bg-white/20 transition">
                        </div>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 pt-2">
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-gray-400 mb-1">1-й Профильный предмет (макс. 50)</label>
                            <input type="number" id="calc-score-prof1" min="0" max="50" placeholder="0" oninput="calculateTotalScore()" class="w-full bg-white/10 border border-white/20 rounded-xl px-3 py-2.5 text-sm font-semibold text-white focus:outline-none focus:border-blue-500 focus:bg-white/20 transition">
                        </div>
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-gray-400 mb-1">2-й Профильный предмет (макс. 50)</label>
                            <input type="number" id="calc-score-prof2" min="0" max="50" placeholder="0" oninput="calculateTotalScore()" class="w-full bg-white/10 border border-white/20 rounded-xl px-3 py-2.5 text-sm font-semibold text-white focus:outline-none focus:border-blue-500 focus:bg-white/20 transition">
                        </div>
                    </div>
                </div>

                <div class="w-full md:w-1/2 flex flex-col items-center justify-center text-center p-6 bg-white/5 rounded-2xl border border-white/10 h-full min-h-[220px]">
                    <p class="text-sm font-medium text-gray-400 uppercase tracking-widest">Твой суммарный балл</p>
                    <div id="calc-score-total" class="text-6xl md:text-7xl font-black text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-indigo-400 my-2">0</div>
                    <p class="text-xs font-semibold text-gray-400">из 140 возможных</p>

                    <div id="calc-score-status" class="mt-4 px-4 py-1.5 rounded-full text-xs font-bold bg-gray-800 text-gray-400">
                        Введи баллы для анализа
                    </div>
                </div>

            </div>
        </section>

        <!-- СЕКЦИЯ ВЫБОРА ПРЕДМЕТОВ -->
        <section id="subjects" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
            <div class="mb-8">
                <h2 class="text-2xl md:text-3xl font-bold text-gray-800">Выбери предмет для подготовки</h2>
                <p class="text-gray-500 mt-1">Все обязательные предметы и профильные дисциплины ЕНТ.</p>
            </div>

            <div class="flex flex-wrap gap-2 mb-10">
                <button onclick="filterBySubject('all')" class="subject-btn active-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-blue-600 bg-blue-600 text-white cursor-pointer">
                    <i class="fa-solid fa-list"></i> Все
                </button>
                <button onclick="filterBySubject('hist-kaz')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-book-atlas text-amber-600"></i> История Казахстана
                </button>
                <button onclick="filterBySubject('read-lit')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-book-open text-blue-400"></i> Грамотность чтения
                </button>
                <button onclick="filterBySubject('math-lit')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-calculator text-red-500"></i> Мат. грамотность
                </button>
                <button onclick="filterBySubject('math')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-square-root-variable text-blue-500"></i> Математика
                </button>
                <button onclick="filterBySubject('physics')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-atom text-purple-500"></i> Физика
                </button>
                <button onclick="filterBySubject('chemistry')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-flask text-emerald-500"></i> Химия
                </button>
                <button onclick="filterBySubject('biology')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-dna text-teal-600"></i> Биология
                </button>
                <button onclick="filterBySubject('geography')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-earth-americas text-cyan-600"></i> География
                </button>
                <button onclick="filterBySubject('world-hist')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-landmark text-orange-600"></i> Всемирная история
                </button>
                <button onclick="filterBySubject('english')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-language text-indigo-500"></i> Английский язык
                </button>
                <button onclick="filterBySubject('kaz-lit')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                    <i class="fa-solid fa-feather text-rose-500"></i> Каз. литература
                </button>
            </div>

            <div id="course-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8"></div>
        </section>

        <!-- СЕКЦИЯ ТЕСТИРОВАНИЯ -->
        <section id="quiz-section" class="bg-gray-100 border-t border-b border-gray-200 py-16 px-4">
            <div class="max-w-3xl mx-auto">
                <div class="text-center mb-10">
                    <span class="bg-blue-100 text-blue-700 text-xs font-bold uppercase tracking-wider px-3 py-1 rounded-full">Интерактивный тренажер</span>
                    <h2 class="text-3xl font-bold text-gray-800 mt-2">Мини-тест ЕНТ</h2>
                    <p class="text-gray-500 mt-2">Проверь свои знания прямо сейчас. За каждый правильный ответ — 1 балл.</p>
                </div>

                <div class="bg-white rounded-2xl shadow-sm border border-gray-200 p-6 md:p-8">
                    <form id="quiz-form" onsubmit="handleQuizSubmit(event)">
                        <div id="quiz-questions-container" class="space-y-8"></div>
                        <div class="mt-8 pt-6 border-t border-gray-100 flex flex-col sm:flex-row items-center justify-between gap-4">
                            <div id="quiz-status-text" class="text-sm text-gray-500 font-medium">Ответьте на все вопросы, чтобы узнать результат</div>
                            <button type="submit" id="quiz-submit-btn" class="w-full sm:w-auto bg-blue-600 hover:bg-blue-700 text-white font-medium px-6 py-3 rounded-xl transition shadow-sm cursor-pointer">
                                Проверить результаты
                            </button>
                            <button type="button" onclick="resetQuiz()" id="quiz-reset-btn" class="w-full sm:w-auto bg-gray-200 hover:bg-gray-300 text-gray-700 font-medium px-6 py-3 rounded-xl transition hidden cursor-pointer">
                                Пройти заново
                            </button>
                        </div>
                    </form>

                    <div id="quiz-result-card" class="mt-6 p-6 rounded-xl border hidden text-center">
                        <h4 id="quiz-result-title" class="text-xl font-bold mb-1">Итоговый результат</h4>
                        <p id="quiz-result-score" class="text-3xl font-extrabold text-blue-600 my-2">0 / 0</p>
                        <p id="quiz-result-desc" class="text-sm text-gray-600 font-medium"></p>
                    </div>
                </div>
            </div>
        </section>

        <!-- СЕКЦИЯ: FAQ -->
        <section id="faq-section" class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="text-center mb-12">
                <span class="bg-blue-50 text-blue-600 font-bold text-xs uppercase px-2.5 py-1 rounded-md">База знаний</span>
                <h2 class="text-3xl font-extrabold text-gray-900 mt-2">Часто задаваемые вопросы</h2>
                <p class="text-gray-500 text-sm mt-2">Всё, что нужно знать о правилах, баллах и формате проведения ЕНТ.</p>
            </div>
            <div id="faq-container" class="space-y-4"></div>
        </section>
    </div>


    <!-- СТРАНИЦА 2: ЛИЧНЫЙ КАБИНЕТ (СКРЫТА ПО УМОЛЧАНИЮ) -->
    <div id="page-dashboard" class="hidden max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10">
        <div class="flex flex-col lg:flex-row gap-8">

            <!-- Боковая панель профиля -->
            <div class="w-full lg:w-1/4 bg-white rounded-2xl border border-gray-200 p-6 shadow-xs h-fit">
                <div class="text-center pb-6 border-b border-gray-100">
                    <div id="db-avatar" class="w-20 h-20 rounded-full bg-blue-600 text-white text-3xl font-bold flex items-center justify-center mx-auto uppercase shadow-sm mb-3">U</div>
                    <h3 id="db-username" class="text-xl font-bold text-gray-900">Пользователь</h3>
                    <p id="db-email" class="text-xs text-gray-400 font-medium mt-0.5">user@mail.com</p>
                    <span class="inline-block bg-green-100 text-green-700 text-xs font-bold px-2.5 py-1 rounded-full mt-3"><i class="fa-solid fa-shield mr-1"></i> Аккаунт активен</span>
                </div>

                <!-- Настройки предметов ученика -->
                <div class="mt-6">
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-3">Мой профиль ЕНТ</h4>
                    <div class="space-y-3">
                        <div>
                            <label class="block text-xs font-semibold text-gray-500 mb-1">Предмет 1</label>
                            <select id="db-pref-s1" onchange="saveProfileSettings()" class="w-full bg-gray-50 border border-gray-200 rounded-lg p-2 text-xs font-medium focus:outline-none focus:border-blue-500">
                                <option value="math">Математика</option>
                                <option value="physics">Физика</option>
                                <option value="chemistry">Химия</option>
                                <option value="biology">Биология</option>
                                <option value="geography">География</option>
                                <option value="world-hist">Всемирная история</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-gray-500 mb-1">Предмет 2</label>
                            <select id="db-pref-s2" onchange="saveProfileSettings()" class="w-full bg-gray-50 border border-gray-200 rounded-lg p-2 text-xs font-medium focus:outline-none focus:border-blue-500">
                                <option value="physics">Физика</option>
                                <option value="math">Математика</option>
                                <option value="chemistry">Химия</option>
                                <option value="biology">Биология</option>
                                <option value="geography">География</option>
                                <option value="world-hist">Всемирная история</option>
                            </select>
                        </div>
                    </div>
                </div>

                <button onclick="logoutUser()" class="w-full mt-8 bg-gray-100 hover:bg-red-50 hover:text-red-600 text-gray-600 font-medium py-2.5 rounded-xl transition text-xs flex items-center justify-center gap-2 cursor-pointer">
                    <i class="fa-solid fa-arrow-right-from-bracket"></i> Выйти из системы
                </button>
            </div>

            <!-- Главная панель ЛК -->
            <div class="w-full lg:w-3/4 space-y-6">
                <!-- Приветствие -->
                <div class="bg-gradient-to-r from-blue-600 to-indigo-600 rounded-2xl p-6 md:p-8 text-white shadow-sm flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
                    <div>
                        <h2 class="text-2xl md:text-3xl font-extrabold">С возвращением, <span id="db-welcome-name">Студент</span>!</h2>
                        <p class="text-blue-100 text-sm mt-1">До ЕНТ-2026 осталось совсем немного времени. Твой ежедневный план занятий готов.</p>
                    </div>
                    <button onclick="navigateTo('main')" class="bg-white/20 hover:bg-white text-white hover:text-blue-700 font-semibold px-4 py-2.5 rounded-xl text-sm transition backdrop-blur-xs cursor-pointer">
                        <i class="fa-solid fa-play mr-1.5"></i>Продолжить учиться
                    </button>
                </div>

                <!-- Карточки статистики -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                    <div class="bg-white border border-gray-200 rounded-xl p-5 shadow-xs flex items-center gap-4">
                        <div class="w-12 h-12 bg-blue-50 text-blue-600 rounded-xl flex items-center justify-center text-xl"><i class="fa-solid fa-square-poll-vertical"></i></div>
                        <div>
                            <p class="text-xs font-medium text-gray-400 uppercase tracking-wider">Тест ЕНТ</p>
                            <h4 id="db-stat-quiz" class="text-xl font-bold text-gray-800 mt-0.5">Не пройден</h4>
                        </div>
                    </div>
                    <div class="bg-white border border-gray-200 rounded-xl p-5 shadow-xs flex items-center gap-4">
                        <div class="w-12 h-12 bg-purple-50 text-purple-600 rounded-xl flex items-center justify-center text-xl"><i class="fa-regular fa-circle-play"></i></div>
                        <div>
                            <p class="text-xs font-medium text-gray-400 uppercase tracking-wider">Лекции</p>
                            <h4 class="text-xl font-bold text-gray-800 mt-0.5">3 / 8 уроков</h4>
                        </div>
                    </div>
                    <div class="bg-white border border-gray-200 rounded-xl p-5 shadow-xs flex items-center gap-4">
                        <div class="w-12 h-12 bg-emerald-50 text-emerald-600 rounded-xl flex items-center justify-center text-xl"><i class="fa-solid fa-fire"></i></div>
                        <div>
                            <p class="text-xs font-medium text-gray-400 uppercase tracking-wider">Ударный темп</p>
                            <h4 class="text-xl font-bold text-gray-800 mt-0.5">2 дня подряд</h4>
                        </div>
                    </div>
                </div>

                <!-- Рекомендуемый контент на основе выбранных предметов -->
                <div class="bg-white border border-gray-200 rounded-2xl p-6 shadow-xs">
                    <h3 class="text-lg font-bold text-gray-800 mb-4 flex items-center gap-2"><i class="fa-solid fa-star text-amber-500"></i> Персональные рекомендации</h3>
                    <div id="db-recommended-grid" class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <!-- Сюда JS выведет видео-лекции по выбранным в ЛК предметам -->
                    </div>
                </div>
            </div>

        </div>
    </div>


    <!-- МОДАЛЬНОЕ ОКНО: Вход / Регистрация -->
    <div id="auth-modal" class="fixed inset-0 bg-black/70 flex items-center justify-center z-50 hidden opacity-0 transition-opacity duration-300">
        <div class="bg-white rounded-2xl overflow-hidden max-w-md w-full mx-4 shadow-2xl relative p-8">
            <button onclick="closeAuthModal()" class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 p-2 rounded-full cursor-pointer">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
            <div class="text-center mb-6">
                <h3 id="auth-modal-title" class="text-2xl font-bold text-gray-900">Войти в аккаунт</h3>
                <p id="auth-modal-subtitle" class="text-gray-500 text-sm mt-1">Введите свои данные для доступа к урокам</p>
            </div>
            <form id="auth-form" onsubmit="handleAuthSubmit(event)" class="space-y-4">
                <input type="hidden" id="auth-mode" value="login">
                <div id="name-field-group" class="hidden">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Ваше имя</label>
                    <div class="relative">
                        <span class="absolute inset-y-0 left-0 flex items-center pl-3 text-gray-400">
                            <i class="fa-solid fa-user"></i>
                        </span>
                        <input type="text" id="auth-name" class="w-full pl-10 pr-4 py-2.5 border border-gray-300 rounded-xl focus:outline-none focus:border-blue-500 text-sm" placeholder="Ronaldo Messi">
                    </div>
                </div>
                <div>
                    <label class="block text-sm font-medium text-gray-700 mb-1">E-mail</label>
                    <div class="relative">
                        <span class="absolute inset-y-0 left-0 flex items-center pl-3 text-gray-400">
                            <i class="fa-solid fa-envelope"></i>
                        </span>
                        <input type="email" id="auth-email" required class="w-full pl-10 pr-4 py-2.5 border border-gray-300 rounded-xl focus:outline-none focus:border-blue-500 text-sm" placeholder="example@mail.com">
                    </div>
                </div>
                <div>
                    <label class="block text-sm font-medium text-gray-700 mb-1">Пароль</label>
                    <div class="relative">
                        <span class="absolute inset-y-0 left-0 flex items-center pl-3 text-gray-400">
                            <i class="fa-solid fa-lock"></i>
                        </span>
                        <input type="password" id="auth-password" required minlength="8" class="w-full pl-10 pr-4 py-2.5 border border-gray-300 rounded-xl focus:outline-none focus:border-blue-500 text-sm" placeholder="••••••••">
                    </div>
                </div>
                <div id="auth-error" class="text-red-500 text-xs hidden font-medium mt-1"></div>
                <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-medium py-3 rounded-xl transition shadow-sm text-sm cursor-pointer mt-2">
                    <span id="auth-submit-text">Войти</span>
                </button>
            </form>
            <div class="text-center mt-6 pt-4 border-t border-gray-100 text-sm">
                <span id="auth-switch-desc" class="text-gray-500">Еще нет аккаунта?</span>
                <button onclick="toggleAuthMode()" id="auth-switch-btn" class="text-blue-600 font-semibold hover:underline ml-1 cursor-pointer">Создать аккаунт</button>
            </div>
        </div>
    </div>

    <!-- Модальное окно для видео -->
    <div id="video-modal" class="fixed inset-0 bg-black/70 flex items-center justify-center z-50 hidden opacity-0 transition-opacity duration-300">
        <div class="bg-white rounded-xl overflow-hidden max-w-3xl w-full mx-4 shadow-2xl relative">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-white bg-gray-800/50 hover:bg-gray-800 p-2 rounded-full z-10 cursor-pointer">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
            <div class="aspect-video bg-black">
                <iframe id="modal-video" class="w-full h-full" src="" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
            <div class="p-6">
                <h3 id="modal-title" class="text-2xl font-bold mb-2">Название урока</h3>
                <p id="modal-desc" class="text-gray-600">Описание...</p>
            </div>
        </div>
    </div>

    <script>
        // Глобальное состояние сессии пользователя
        let currentUser = JSON.parse(localStorage.getItem('ent_user_session')) || null;

        // База данных видео-уроков под ЕНТ
        const entCourses = [
            { id: 1, title: "Казахстан в период XIX века", subject: "hist-kaz", subjectName: "История Казахстана", lessons: 18, image: "https://images.unsplash.com/photo-1461360370896-922624d12aa1?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/pCHYclgD4MI", description: "Национально-освободительные восстания (Кенесары Касымов, Исатай и Махамбет). Разбор дат и контекстов." },
            { id: 2, title: "Анализ скрытого смысла текста", subject: "read-lit", subjectName: "Грамотность чтения", lessons: 8, image: "https://images.unsplash.com/photo-1506880018603-83d5b814b5a6?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/snL1BbeW2M4", description: "Учимся быстро определять основную мысль автора, тип текста и ключевые тезисы без потери времени." },
            { id: 3, title: "Текстовые задачи и логика", subject: "math-lit", subjectName: "Мат. грамотность", lessons: 12, image: "https://images.unsplash.com/photo-1610824352934-c10d8706f83c?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/gU9U6gT776A", description: "Разбор задач на движение, работу, проценты и логику. Секретные лайфхаки для быстрого решения на ЕНТ." },
            { id: 4, title: "Тригонометрия: Формулы и Уравнения", subject: "math", subjectName: "Математика", lessons: 24, image: "https://images.unsplash.com/photo-1509228468518-180dd4864904?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/5mE0mFfscB8", description: "Всё от тригонометрического круга до отбора корней в сложных уравнениях из профильного ЕНТ." },
            { id: 5, title: "Кинематика и Законы Ньютона", subject: "physics", subjectName: "Физика", lessons: 15, image: "https://images.unsplash.com/photo-1532094349884-543bc11b234d?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/8-Psh_1c-0c", description: "Разбираем векторы, ускорение, силы в природе и алгоритмы решения задач на динамику." },
            { id: 6, title: "Органическая химия: Углеводороды", subject: "chemistry", subjectName: "Химия", lessons: 20, image: "https://images.unsplash.com/photo-1532187863486-abf9d39d6618?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/gXpM26n3q_Q", description: "Алканы, алкены, алкины. Номенклатура, химические свойства и цепочки превращений веществ." },
            { id: 7, title: "Генетика и Молекулярная биология", subject: "biology", subjectName: "Биология", lessons: 16, image: "https://images.unsplash.com/photo-1530026405186-ed1ea0ac7a63?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/9N4S1qD_eU4", description: "Законы Менделя, Моргана, биосинтез белка и решение генетических задач из ЕНТ." },
            { id: 8, title: "Физическая география Земли", subject: "geography", subjectName: "География", lessons: 14, image: "https://images.unsplash.com/photo-1524661135-423995f22d0b?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/8rYVnC9_4tY", description: "Литосфера, атмосфера, климатические пояса и геохронологическая таблица. То, на чем часто теряют баллы." },
            { id: 9, title: "Эпоха Просвещения и Революции", subject: "world-hist", subjectName: "Всемирная история", lessons: 11, image: "https://images.unsplash.com/photo-1562673005-7693bd6d6e54?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/snL1BbeW2M4", description: "Разбор ключевых событий Нового времени: Английская и Французская буржуазные революции." },
            { id: 10, title: "Времена глагола и Active/Passive Voice", subject: "english", subjectName: "Английский язык", lessons: 22, image: "https://images.unsplash.com/photo-1451226428352-cf66bf8a0317?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/snL1BbeW2M4", description: "Вся грамматика временной сетки английского языка, которая проверяется в контекстных заданиях ЕНТ." },
            { id: 11, title: "XV-XVIII ғғ. жыраулар поэзиясы", subject: "kaz-lit", subjectName: "Казахская литература", lessons: 15, image: "https://images.unsplash.com/photo-1457369804613-52c61a468e7d?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/snL1BbeW2M4", description: "Асан Қайғы, Қазтуған, Доспамбет жыраулардың шығармашылықтары мен ЕНТ-да келетін негізгі сұрақтар." }
        ];

        // База данных для тестов
        const quizQuestions = [
            { id: 1, subject: "Математическая грамотность", question: "В семье 5 сыновей. У каждого из них есть одна сестра. Сколько всего детей в семье?", options: ["5", "6", "10", "11"], correct: 1 },
            { id: 2, subject: "История Казахстана", question: "В каком году произошло восстание под предводительством Кенесары Касымов?", options: ["1812-1820 гг.", "1824-1828 гг.", "1837-1847 гг.", "1855-1860 гг."], correct: 2 },
            { id: 3, subject: "Физика", question: "Как изменится сила гравитационного притяжения между двумя телами, если расстояние между ними увеличить в 2 раза?", options: ["Увеличится в 2 раза", "Увеличится в 4 раза", "Уменьшится в 2 раза", "Уменьшится в 4 раза"], correct: 3 },
            { id: 4, subject: "Химия", question: "Какой из перечисленных углеводородов относится к классу алканов?", options: ["C2H2", "C2H4", "C2H6", "C6H6"], correct: 2 }
        ];

        // База данных для калькулятора комбинаций
        const entCombinations = {
            "math+informatics": [
                { code: "B057", name: "Информационные технологии (IT, Разработка, Computer Science)", threshold: 75 },
                { code: "B058", name: "Информационная безопасность", threshold: 75 },
                { code: "B011", name: "Подготовка учителей информатики", threshold: 75 }
            ],
            "math+physics": [
                { code: "B064", name: "Механика и металлообработка", threshold: 50 },
                { code: "B062", name: "Электротехника и энергетика", threshold: 50 },
                { code: "B071", name: "Горное дело и добыча полезных ископаемых", threshold: 50 }
            ],
            "math+geography": [
                { code: "B046", name: "Финансы, экономика, аудит и управление", threshold: 50 },
                { code: "B044", name: "Менеджмент и маркетинг", threshold: 50 },
                { code: "B145", name: "Государственный аудит", threshold: 50 }
            ],
            "biology+chemistry": [
                { code: "B086", name: "Общая медицина (Врач, Хирург, Педиатр)", threshold: 75 },
                { code: "B087", name: "Стоматология", threshold: 75 },
                { code: "B088", name: "Фармация", threshold: 75 }
            ],
            "geography+world-hist": [
                { code: "B034", name: "История", threshold: 50 },
                { code: "B134", name: "Археология и этнология", threshold: 65 }
            ],
            "world-hist+kaz-lit": [
                { code: "B042", name: "Юриспруденция / Право", threshold: 75 },
                { code: "B023", name: "Режиссура, арт-менеджмент", threshold: 75 }
            ]
        };

        const faqData = [
            { id: 1, question: "Сколько всего баллов можно набрать на ЕНТ в 2026 году?", answer: "Максимальное количество баллов на ЕНТ составляет 140. Экзамен состоит из 3 обязательных предметов (История Казахстана, Грамотность чтения, Математическая грамотность) и 2 профильных предметов на выбор." },
            { id: 2, question: "Каков минимальный пороговый балл для поступления в ВУЗы?", answer: "Для поступления в национальные ВУЗы необходимо набрать не менее 65 баллов, в другие ВУЗы — не менее 50 баллов. По отдельным направлениям (педагогика, медицина, право) порог выше — от 75 баллов. Также по каждому предмету обязательно набрать не менее 5 баллов." },
            { id: 3, question: "Сколько времени длится тестирование?", answer: "Общее время проведения ЕНТ составляет 4 часа (240 минут). Для детей с особыми образовательными потребностями предоставляется дополнительное время — еще 40 минут." },
            { id: 4, question: "Можно ли пересдать ЕНТ, если не набрал пороговый балл?", answer: "Да, ЕНТ проводится несколько раз в год (январь, март, май-июнь, август). Для участия в конкурсе на государственный грант учитываются результаты основного ЕНТ (май-июнь), а январские и мартовские сессии позволяют поступить на платное отделение." },
            { id: 5, question: "Что разрешено брать с собой в аудиторию тестирования?", answer: "При запуске на тестирование при себе необходимо иметь только удостоверение личности. Ручка, бумага для черновиков, калькулятор и периодическая таблица Менделеева/растворимости (в электронном виде на экране компьютера) предоставляются на месте." }
        ];

        // --- СИСТЕМА ОДНОСТРАНИЧНОЙ НАВИГАЦИИ (SPA) ---
        window.navigateTo = function(page) {
            const mainPage = document.getElementById('page-main');
            const dashboardPage = document.getElementById('page-dashboard');

            if (page === 'dashboard') {
                if (!currentUser) {
                    openAuthModal();
                    return;
                }
                mainPage.classList.add('hidden');
                dashboardPage.classList.remove('hidden');
                syncDashboardUI();
                window.scrollTo({ top: 0, behavior: 'smooth' });
            } else {
                // Если переходим на main (Главную) — активируем главную и скрываем ЛК
                dashboardPage.classList.add('hidden');
                mainPage.classList.remove('hidden');
            }

            // Смена активных стилей в меню
            updateActiveNavLinks(page);
        }

        // Новая функция: Умный скролл к секциям с учетом ЛК
        window.scrollToSection = function(sectionId) {
            const mainPage = document.getElementById('page-main');

            // Если пользователь в ЛК, сначала возвращаем его на главную
            if (mainPage.classList.contains('hidden')) {
                navigateTo('main');
            }

            // Небольшой таймаут, чтобы браузер успел отобразить главную страницу перед расчетом координат скролла
            setTimeout(() => {
                const targetSection = document.getElementById(sectionId);
                if (targetSection) {
                    const navHeight = document.querySelector('nav').offsetHeight;
                    const targetPosition = targetSection.getBoundingClientRect().top + window.pageYOffset - navHeight;

                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                }
            }, 50);
        }

        // Вспомогательная функция для подсветки активных ссылок
        function updateActiveNavLinks(currentPage) {
            document.querySelectorAll('.nav-link').forEach(link => {
                // Проверяем, куда ведет ссылка по ее onclick атрибуту, это надежнее текста
                const onClickAttr = link.getAttribute('onclick') || '';

                if (currentPage === 'main' && onClickAttr.includes("navigateTo('main')")) {
                    link.className = "nav-link text-blue-600 font-semibold";
                } else {
                    link.className = "nav-link text-gray-600 hover:text-blue-600 font-medium";
                }
            });
        }

        // Отрисовка курсов на главной
        function renderContent(subjectFilter = 'all') {
            const grid = document.getElementById('course-grid');
            grid.innerHTML = '';
            const filtered = subjectFilter === 'all' ? entCourses : entCourses.filter(c => c.subject === subjectFilter);
            filtered.forEach(course => {
                grid.innerHTML += `
                    <div class="bg-white rounded-2xl shadow-sm border border-gray-100 overflow-hidden hover:shadow-lg transition flex flex-col">
                        <img class="h-44 w-full object-cover" src="${course.image}" alt="${course.title}">
                        <div class="p-5 flex flex-col flex-grow">
                            <span class="text-xs font-bold uppercase tracking-wide text-blue-600 bg-blue-50 px-2.5 py-1 rounded-md inline-block self-start mb-3">${course.subjectName}</span>
                            <h3 class="text-xl font-bold text-gray-900 mb-2">${course.title}</h3>
                            <p class="text-gray-600 text-sm mb-4 flex-grow">${course.description}</p>
                            <div class="pt-4 border-t border-gray-100 flex justify-between items-center mt-auto">
                                <span class="text-sm font-medium text-gray-500"><i class="fa-regular fa-file-video mr-1 text-blue-500"></i> ${course.lessons} видео</span>
                                <button onclick="openModal(${course.id})" class="text-white bg-blue-600 hover:bg-blue-700 px-4 py-2 rounded-xl text-sm font-medium transition shadow-sm cursor-pointer">Смотреть урок</button>
                            </div>
                        </div>
                    </div>
                `;
            });
        }

        function filterBySubject(subject) {
            renderContent(subject);
            document.querySelectorAll('.subject-btn').forEach(btn => {
                if(btn.outerHTML.includes(`'${subject}'`)) {
                    btn.className = "subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-blue-600 bg-blue-600 text-white cursor-pointer";
                } else {
                    btn.className = "subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer";
                }
            });
        }

        window.openModal = function(id) {
            const course = entCourses.find(c => c.id === id);
            if (!course) return;
            document.getElementById('modal-title').innerText = course.title;
            document.getElementById('modal-desc').innerText = course.description;
            document.getElementById('modal-video').src = course.videoUrl;
            const modal = document.getElementById('video-modal');
            modal.classList.remove('hidden');
            setTimeout(() => modal.classList.remove('opacity-0'), 10);
        }

        window.closeModal = function() {
            const modal = document.getElementById('video-modal');
            modal.classList.add('opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
                document.getElementById('modal-video').src = "";
            }, 300);
        }

        window.updateCombination = function() {
            const s1 = document.getElementById('subject1').value;
            const s2 = document.getElementById('subject2').value;
            const resultsContainer = document.getElementById('calc-results');

            if (!s1 || !s2) return;
            if (s1 === s2) {
                resultsContainer.innerHTML = `<div class="text-center py-12 text-red-500 text-sm border-2 border-dashed border-red-100 bg-red-50 rounded-2xl"><i class="fa-solid fa-triangle-exclamation text-3xl mb-2"></i><p>Профильные предметы не могут быть одинаковыми!</p></div>`;
                return;
            }
            const professions = entCombinations[`${s1}+${s2}`] || entCombinations[`${s2}+${s1}`];
            if (professions) {
                let html = '';
                professions.forEach(prof => {
                    html += `<div class="flex items-start gap-3 bg-gray-50 border border-gray-200 p-4 rounded-xl hover:border-blue-300 hover:bg-white transition shadow-xs"><span class="bg-blue-600 text-white text-xs font-bold px-2 py-1 rounded-md mt-0.5">${prof.code}</span><div><h4 class="text-sm font-bold text-gray-900">${prof.name}</h4><span class="text-xs text-green-600 font-medium"><i class="fa-solid fa-circle-check mr-1"></i> Есть государственные гранты</span></div></div>`;
                });
                resultsContainer.innerHTML = html;
            } else {
                resultsContainer.innerHTML = `<div class="text-center py-12 text-gray-500 text-sm border-2 border-dashed border-gray-100 rounded-2xl"><i class="fa-solid fa-hourglass-half text-3xl mb-2 text-blue-500"></i><p class="font-semibold">Комбинация поддерживается ЕНТ!</p></div>`;
            }
        }

        // --- КАЛЬКУЛЯТОР БАЛЛОВ ЕНТ С УЧЕТОМ МИНИМАЛЬНОГО ПОРОГА ---
        window.calculateTotalScore = function() {
            const histInput = document.getElementById('calc-score-hist');
            const mathLitInput = document.getElementById('calc-score-math-lit');
            const readLitInput = document.getElementById('calc-score-read-lit');
            const prof1Input = document.getElementById('calc-score-prof1');
            const prof2Input = document.getElementById('calc-score-prof2');

            // Функция валидации максимума
            const validateInput = (input, max) => {
                let val = parseInt(input.value);
                if (isNaN(val)) return null; // Если поле пустое, возвращаем null
                if (val < 0) val = 0;
                if (val > max) {
                    val = max;
                    input.value = max;
                }
                return val;
            };

            // Проверяем и получаем значения (null означает, что абитуриент еще не ввел балл)
            const hist = validateInput(histInput, 20);
            const mLit = validateInput(mathLitInput, 10);
            const rLit = validateInput(readLitInput, 10);
            const prof1 = validateInput(prof1Input, 50);
            const prof2 = validateInput(prof2Input, 50);

            // Считаем сумму только по введенным полям
            const total = (hist || 0) + (mLit || 0) + (rLit || 0) + (prof1 || 0) + (prof2 || 0);

            // Выводим результат на экран
            document.getElementById('calc-score-total').innerText = total;

            const statusBlock = document.getElementById('calc-score-status');

            // Проверяем, завалена ли минимальная планка (меньше 5 баллов)
            // Проверку делаем только для тех полей, где уже введены данные (не равны null)
            const hasFailedSubject =
                (hist !== null && hist < 5) ||
                (mLit !== null && mLit < 5) ||
                (rLit !== null && rLit < 5) ||
                (prof1 !== null && prof1 < 5) ||
                (prof2 !== null && prof2 < 5);

            // Если все поля пустые
            if (hist === null && mLit === null && rLit === null && prof1 === null && prof2 === null) {
                statusBlock.innerText = "Введи баллы для анализа";
                statusBlock.className = "mt-4 px-4 py-1.5 rounded-full text-xs font-bold bg-gray-800 text-gray-400";
                return;
            }

            // Логика вывода статуса
            if (hasFailedSubject) {
                statusBlock.innerText = "⚠️ Не набран мин. балл (меньше 5 по предмету) — Грант недоступен";
                statusBlock.className = "mt-4 px-4 py-1.5 rounded-full text-xs font-bold bg-red-600 text-white border border-red-700 animate-bounce";
            } else if (total < 50) {
                statusBlock.innerText = "Ниже общего порогового балла (нужно минимум 50)";
                statusBlock.className = "mt-4 px-4 py-1.5 rounded-full text-xs font-bold bg-red-950 text-red-400 border border-red-900";
            } else if (total >= 50 && total < 65) {
                statusBlock.innerText = "Порог пройден (Платное отделение в регионы)";
                statusBlock.className = "mt-4 px-4 py-1.5 rounded-full text-xs font-bold bg-amber-950 text-amber-400 border border-amber-900";
            } else if (total >= 65 && total < 100) {
                statusBlock.innerText = "Доступны Национальные ВУЗы и некоторые гранты";
                statusBlock.className = "mt-4 px-4 py-1.5 rounded-full text-xs font-bold bg-blue-950 text-blue-400 border border-blue-900";
            } else if (total >= 100 && total < 130) {
                statusBlock.innerText = "Отличный результат! Высокий шанс на грант";
                statusBlock.className = "mt-4 px-4 py-1.5 rounded-full text-xs font-bold bg-emerald-950 text-emerald-400 border border-emerald-900";
            } else {
                statusBlock.innerText = "🔥 Будущий обладатель Алтын Белгі / Топ ВУЗы!";
                statusBlock.className = "mt-4 px-4 py-1.5 rounded-full text-xs font-bold bg-purple-950 text-purple-300 border border-purple-800 animate-pulse";
            }
        }

        // Логика теста
        function renderQuiz() {
            const container = document.getElementById('quiz-questions-container');
            container.innerHTML = '';
            const savedAnswers = JSON.parse(localStorage.getItem('ent_quiz_answers'));
            const isCompleted = savedAnswers !== null;

            quizQuestions.forEach((q, qIndex) => {
                let optionsHtml = '';
                q.options.forEach((opt, oIndex) => {
                    const isChecked = isCompleted && savedAnswers[q.id] === oIndex;
                    optionsHtml += `
                        <label class="flex items-center gap-3 p-3.5 border border-gray-200 rounded-xl hover:bg-blue-50/50 cursor-pointer transition option-label">
                            <input type="radio" name="question-${q.id}" value="${oIndex}" ${isChecked ? 'checked' : ''} ${isCompleted ? 'disabled' : ''} required class="w-4 h-4 text-blue-600 border-gray-300 focus:ring-blue-500">
                            <span class="text-sm font-medium text-gray-700">${opt}</span>
                        </label>
                    `;
                });
                container.innerHTML += `
                    <div class="quiz-question-block border-b border-gray-100 pb-6 last:border-b-0 last:pb-0" data-qid="${q.id}">
                        <div class="flex items-center gap-2 mb-2">
                            <span class="text-xs font-bold text-blue-600 bg-blue-50 px-2 py-0.5 rounded">${q.subject}</span>
                            <span class="text-xs text-gray-400 font-semibold">Вопрос ${qIndex + 1}</span>
                        </div>
                        <h3 class="text-base md:text-lg font-bold text-gray-900 mb-4">${q.question}</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            ${optionsHtml}
                        </div>
                    </div>
                `;
            });
            if (isCompleted) showQuizResults(savedAnswers);
        }

        window.handleQuizSubmit = function(event) {
            event.preventDefault();
            const answersToSave = {};
            quizQuestions.forEach(q => {
                const selectedOption = document.querySelector(`input[name="question-${q.id}"]:checked`);
                answersToSave[q.id] = parseInt(selectedOption.value);
            });
            localStorage.setItem('ent_quiz_answers', JSON.stringify(answersToSave));
            showQuizResults(answersToSave);

            // Обновляем показатели ЛК в реальном времени, если юзер в системе
            if(currentUser) syncDashboardUI();
        }

        function showQuizResults(answers) {
            let score = 0;
            const total = quizQuestions.length;
            quizQuestions.forEach((q) => {
                const questionBlock = document.querySelector(`div[data-qid="${q.id}"]`);
                const labels = questionBlock.querySelectorAll('.option-label');
                const selectedValue = answers[q.id];
                labels.forEach((label, oIndex) => {
                    if (oIndex === q.correct) {
                        label.className = "flex items-center gap-3 p-3.5 border-2 border-emerald-500 bg-emerald-50 rounded-xl text-emerald-900 font-medium option-label";
                    } else if (oIndex === selectedValue && selectedValue !== q.correct) {
                        label.className = "flex items-center gap-3 p-3.5 border-2 border-red-500 bg-red-50 rounded-xl text-red-900 font-medium option-label";
                    } else {
                        label.className = "flex items-center gap-3 p-3.5 border border-gray-100 rounded-xl opacity-60 option-label";
                    }
                });
                if (selectedValue === q.correct) score++;
            });
            document.getElementById('quiz-result-score').innerText = `${score} из ${total} баллов`;
            document.getElementById('quiz-result-card').classList.remove('hidden');
            document.getElementById('quiz-submit-btn').classList.add('hidden');
            document.getElementById('quiz-status-text').classList.add('hidden');
            document.getElementById('quiz-reset-btn').classList.remove('hidden');
        }

        window.resetQuiz = function() {
            localStorage.removeItem('ent_quiz_answers');
            renderQuiz();
            document.getElementById('quiz-result-card').classList.add('hidden');
            document.getElementById('quiz-submit-btn').classList.remove('hidden');
            document.getElementById('quiz-status-text').classList.remove('hidden');
            document.getElementById('quiz-reset-btn').classList.add('hidden');
            if(currentUser) syncDashboardUI();
        }

        // --- ЛОГИКА ДЛЯ СЕКЦИИ FAQ (НОВАЯ) ---
        function renderFAQ() {
            const container = document.getElementById('faq-container');
            container.innerHTML = '';

            faqData.forEach(item => {
                container.innerHTML += `
                    <div class="bg-white border border-gray-200 rounded-2xl overflow-hidden transition shadow-xs">
                        <!-- Кнопка вопроса -->
                        <button onclick="toggleFAQ(${item.id})" class="w-full text-left px-6 py-4 font-bold text-gray-800 hover:bg-gray-50 flex justify-between items-center gap-4 transition cursor-pointer select-none">
                            <span>${item.question}</span>
                            <i id="faq-icon-${item.id}" class="fa-solid fa-plus text-blue-600 transition-transform duration-300"></i>
                        </button>
                        <!-- Панель ответа -->
                        <div id="faq-answer-${item.id}" class="max-h-0 overflow-hidden transition-all duration-300 ease-in-out bg-gray-50/50">
                            <div class="px-6 py-4 text-sm text-gray-600 leading-relaxed border-t border-gray-100">
                                ${item.answer}
                            </div>
                        </div>
                    </div>
                `;
            });
        }

        window.toggleFAQ = function(id) {
            const answerBlock = document.getElementById(`faq-answer-${id}`);
            const icon = document.getElementById(`faq-icon-${id}`);

            // Проверяем, открыт ли текущий элемент
            if (answerBlock.style.maxHeight && answerBlock.style.maxHeight !== '0px') {
                // Закрываем
                answerBlock.style.maxHeight = '0px';
                icon.className = "fa-solid fa-plus text-blue-600 transition-transform duration-300";
            } else {
                // Сначала закрываем все остальные открытые FAQ (эффект классического аккордеона)
                faqData.forEach(item => {
                    const otherAnswer = document.getElementById(`faq-answer-${item.id}`);
                    const otherIcon = document.getElementById(`faq-icon-${item.id}`);
                    if (otherAnswer) otherAnswer.style.maxHeight = '0px';
                    if (otherIcon) otherIcon.className = "fa-solid fa-plus text-blue-600";
                });

                // Открываем текущий элемент
                // scrollHeight возвращает высоту контента внутри блока в пикселях
                answerBlock.style.maxHeight = answerBlock.scrollHeight + "px";
                icon.className = "fa-solid fa-minus text-blue-600 transition-transform duration-300 rotate-180";
            }
        }

        // --- СИНХРОНИЗАЦИЯ ДАННЫХ И ИНТЕРФЕЙСА ЛК ---
        function syncDashboardUI() {
            if (!currentUser) return;

            // Заполнение текстовых полей ЛК
            document.getElementById('db-username').innerText = currentUser.name;
            document.getElementById('db-welcome-name').innerText = currentUser.name;
            document.getElementById('db-email').innerText = currentUser.email;
            document.getElementById('db-avatar').innerText = currentUser.name.charAt(0);

            // Синхронизация селекторов предметов
            document.getElementById('db-pref-s1').value = currentUser.subject1 || 'math';
            document.getElementById('db-pref-s2').value = currentUser.subject2 || 'physics';

            // Подсчет результатов тестов для карточки ЛК
            const savedAnswers = JSON.parse(localStorage.getItem('ent_quiz_answers'));
            const statQuizBlock = document.getElementById('db-stat-quiz');
            if (savedAnswers) {
                let score = 0;
                quizQuestions.forEach(q => { if(savedAnswers[q.id] === q.correct) score++; });
                statQuizBlock.innerText = `${score} из ${quizQuestions.length} правильных`;
                statQuizBlock.className = "text-xl font-bold text-emerald-600 mt-0.5";
            } else {
                statQuizBlock.innerText = "Не сдан";
                statQuizBlock.className = "text-xl font-bold text-gray-400 mt-0.5";
            }

            // Отрендерить рекомендованные курсы
            renderDashboardRecommendations();
        }

        // Вывод курсов в ЛК на основе выбранных профилей
        function renderDashboardRecommendations() {
            const recGrid = document.getElementById('db-recommended-grid');
            recGrid.innerHTML = '';

            const s1 = currentUser.subject1 || 'math';
            const s2 = currentUser.subject2 || 'physics';

            // Фильтруем курсы, подходящие под выбранные профили
            const filtered = entCourses.filter(c => c.subject === s1 || c.subject === s2);

            if(filtered.length === 0) {
                recGrid.innerHTML = `<div class="col-span-full text-center p-6 text-gray-400 text-xs">Выберите ваши профильные предметы слева, чтобы сформировать список лекций.</div>`;
                return;
            }

            filtered.forEach(course => {
                recGrid.innerHTML += `
                    <div class="flex items-center gap-4 bg-gray-50 border border-gray-100 p-3 rounded-xl hover:bg-white transition hover:shadow-xs">
                        <img src="${course.image}" class="w-16 h-16 object-cover rounded-lg shrink-0">
                        <div class="min-w-0 flex-grow">
                            <span class="text-[10px] font-bold text-blue-600 uppercase bg-blue-50 px-1.5 py-0.5 rounded">${course.subjectName}</span>
                            <h4 class="text-xs font-bold text-gray-800 truncate mt-1">${course.title}</h4>
                            <p class="text-[11px] text-gray-500 truncate mt-0.5">${course.description}</p>
                        </div>
                        <button onclick="openModal(${course.id})" class="text-blue-600 hover:bg-blue-50 p-2 rounded-lg transition shrink-0 cursor-pointer"><i class="fa-solid fa-arrow-right text-sm"></i></button>
                    </div>
                `;
            });
        }

        window.saveProfileSettings = function() {
            if(!currentUser) return;
            currentUser.subject1 = document.getElementById('db-pref-s1').value;
            currentUser.subject2 = document.getElementById('db-pref-s2').value;
            localStorage.setItem('ent_user_session', JSON.stringify(currentUser));
            renderDashboardRecommendations();
        }


        /* --- МОДЕРНИЗИРОВАННАЯ АВТОРИЗАЦИЯ --- */
        window.handleAuthSubmit = function(event) {
            event.preventDefault();
            const mode = document.getElementById('auth-mode').value;
            const email = document.getElementById('auth-email').value;
            const password = document.getElementById('auth-password').value;
            const errorBlock = document.getElementById('auth-error');

            // Теперь JS и HTML валидация синхронны (8 символов)
            if (password.length < 8) {
                errorBlock.innerText = "Пароль должен быть не менее 8 символов.";
                errorBlock.classList.remove('hidden');
                return;
            }

            let name = mode === 'register' ? document.getElementById('auth-name').value.trim() : email.split('@')[0];

            // Формируем объект пользователя
            currentUser = { name: name, email: email, subject1: 'math', subject2: 'physics' };
            localStorage.setItem('ent_user_session', JSON.stringify(currentUser));

            loginUserUI();
            closeAuthModal();

            // Автоматически перенаправляем в личный кабинет после успешного входа/регистрации
            navigateTo('dashboard');
        }

        window.openAuthModal = function() {
            const modal = document.getElementById('auth-modal');
            document.getElementById('auth-form').reset();
            document.getElementById('auth-error').classList.add('hidden');
            modal.classList.remove('hidden');
            setTimeout(() => modal.classList.remove('opacity-0'), 10);
        }

        window.closeAuthModal = function() {
            const modal = document.getElementById('auth-modal');
            modal.classList.add('opacity-0');
            setTimeout(() => modal.classList.add('hidden'), 300);
        }

        window.toggleAuthMode = function() {
            const modeInput = document.getElementById('auth-mode');
            const nameField = document.getElementById('name-field-group');
            const modalTitle = document.getElementById('auth-modal-title');
            const submitText = document.getElementById('auth-submit-text');
            const switchBtn = document.getElementById('auth-switch-btn');

            if (modeInput.value === 'login') {
                modeInput.value = 'register';
                nameField.classList.remove('hidden');
                document.getElementById('auth-name').required = true;
                modalTitle.innerText = 'Регистрация';
                submitText.innerText = 'Зарегистрироваться';
                switchBtn.innerText = 'Войти';
            } else {
                modeInput.value = 'login';
                nameField.classList.add('hidden');
                document.getElementById('auth-name').required = false;
                modalTitle.innerText = 'Войти в аккаунт';
                submitText.innerText = 'Войти';
                switchBtn.innerText = 'Создать аккаунт';
            }
        }

        window.handleAuthSubmit = function(event) {
            event.preventDefault();
            const mode = document.getElementById('auth-mode').value;
            const email = document.getElementById('auth-email').value;
            const password = document.getElementById('auth-password').value;
            const errorBlock = document.getElementById('auth-error');

            if (password.length < 8) {
                errorBlock.innerText = "Пароль должен быть не менее 8 символов.";
                errorBlock.classList.remove('hidden');
                return;
            }

            let name = mode === 'register' ? document.getElementById('auth-name').value.trim() : email.split('@')[0];

            // Формируем объект пользователя
            currentUser = { name: name, email: email, subject1: 'math', subject2: 'physics' };
            localStorage.setItem('ent_user_session', JSON.stringify(currentUser));

            loginUserUI();
            closeAuthModal();
        }

        function loginUserUI() {
            if (!currentUser) return;
            const authZone = document.getElementById('auth-zone');
            authZone.innerHTML = `
                <div class="flex items-center gap-3">
                    <button onclick="navigateTo('dashboard')" class="flex items-center gap-2 bg-gray-100 hover:bg-blue-50 hover:border-blue-300 px-3 py-1.5 rounded-xl border border-gray-200 transition cursor-pointer">
                        <div class="w-7 h-7 rounded-full bg-blue-600 text-white flex items-center justify-center font-bold text-xs uppercase">
                            ${currentUser.name.charAt(0)}
                        </div>
                        <span class="text-sm font-semibold text-gray-700">${currentUser.name}</span>
                    </button>
                </div>
            `;
        }

        window.logoutUser = function() {
            currentUser = null;
            localStorage.removeItem('ent_user_session');
            document.getElementById('auth-zone').innerHTML = `<button onclick="openAuthModal()" class="bg-blue-600 text-white px-5 py-2 rounded-lg hover:bg-blue-700 transition font-medium cursor-pointer">Войти</button>`;
            navigateTo('main');
        }

        // Автоматическая проверка авторизации на старте страницы
        if (currentUser) {
            loginUserUI();
        }

        // Первичный запуск всего контента при загрузке страницы
        renderContent();
        renderQuiz();
        renderFAQ();
    </script>
</body>
</html>
