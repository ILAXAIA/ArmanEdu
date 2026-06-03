# ArmanEdu
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ENT-Prep | Подготовка к ЕНТ</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-fontawesome/6.4.0/css/all.min.css">
</head>
<body class="bg-gray-50 text-gray-900 font-sans">

    <nav class="bg-white shadow-md sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16">
                <div class="flex items-center">
                    <span class="text-2xl font-bold text-blue-600 cursor-pointer" onclick="filterBySubject('all')">
                        <i class="fa-solid fa-graduation-cap mr-2"></i>ENT-Prep
                    </span>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#" class="text-gray-600 hover:text-blue-600 font-medium">Главная</a>
                    <a href="#subjects" class="text-gray-600 hover:text-blue-600 font-medium">Предметы</a>
                    <a href="#quiz-section" class="text-gray-600 hover:text-blue-600 font-medium">Пробные тесты</a>

                    <div id="auth-zone">
                        <button onclick="openAuthModal()" class="bg-blue-600 text-white px-5 py-2 rounded-lg hover:bg-blue-700 transition font-medium cursor-pointer">Войти</button>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <header class="bg-gradient-to-r from-blue-600 to-indigo-700 text-white py-16 px-4 text-center">
        <div class="max-w-4xl mx-auto">
            <span class="bg-blue-500/30 text-blue-100 text-sm font-semibold px-3 py-1 rounded-full mb-4 inline-block">Формат ЕНТ 2026</span>
            <h1 class="text-4xl md:text-5xl font-extrabold mb-4">Подготовка к ЕНТ на 140 баллов</h1>
            <p class="text-lg md:text-xl mb-8 text-blue-100">Выбирай нужные предметы, смотри видео-разборы и щелкай тесты как орешки.</p>
        </div>
    </header>

    <section id="subjects" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
        <div class="mb-8">
            <h2 class="text-2xl md:text-3xl font-bold text-gray-800">Выбери предмет для подготовки</h2>
            <p class="text-gray-500 mt-1">Все обязательные предметы и профильные дисциплины ЕНТ.</p>
        </div>

        <div class="flex flex-wrap gap-2 mb-10">
            <button onclick="filterBySubject('all')" class="subject-btn active-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-blue-600 bg-blue-600 text-white cursor-pointer">
                <i class="fa-solid fa-list"></i> Все
            </button>
            <button onclick="filterBySubject('math-lit')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                <i class="fa-solid fa-calculator text-red-500"></i> Мат. грамотность
            </button>
            <button onclick="filterBySubject('hist-kaz')" class="subject-btn flex items-center gap-2 px-4 py-2.5 rounded-xl font-medium shadow-sm transition text-sm border-2 border-gray-200 bg-white text-gray-700 hover:border-blue-500 cursor-pointer">
                <i class="fa-solid fa-book-atlas text-amber-600"></i> История Казахстана
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
        </div>

        <div id="course-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            </div>
    </section>

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
                        <input type="text" id="auth-name" class="w-full pl-10 pr-4 py-2.5 border border-gray-300 rounded-xl focus:outline-none focus:border-blue-500 text-sm" placeholder="Иван Иванов">
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
                        <input type="password" id="auth-password" required minlength="6" class="w-full pl-10 pr-4 py-2.5 border border-gray-300 rounded-xl focus:outline-none focus:border-blue-500 text-sm" placeholder="••••••••">
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
        // База данных видео-уроков под ЕНТ
        const entCourses = [
            { id: 1, title: "Текстовые задачи и логика", subject: "math-lit", subjectName: "Мат. грамотность", lessons: 12, image: "https://images.unsplash.com/photo-1610824352934-c10d8706f83c?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/gU9U6gT776A", description: "Разбор задач на движение, работу, проценты и логику. Секретные лайфхаки для быстрого решения на ЕНТ." },
            { id: 2, title: "Казахстан в период XIX века", subject: "hist-kaz", subjectName: "История Казахстана", lessons: 18, image: "https://images.unsplash.com/photo-1461360370896-922624d12aa1?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/pCHYclgD4MI", description: "Национально-освободительные восстания (Кенесары Касымов, Исатай и Махамбет). Разбор дат и контекстов." },
            { id: 3, title: "Тригонометрия: Формулы и Уравнения", subject: "math", subjectName: "Математика (профиль)", lessons: 24, image: "https://images.unsplash.com/photo-1509228468518-180dd4864904?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/5mE0mFfscB8", description: "Всё от тригонометрического круга до отбора корней в сложных уравнениях из профильного ЕНТ." },
            { id: 4, title: "Кинематика и Законы Ньютона", subject: "physics", subjectName: "Физика", lessons: 15, image: "https://images.unsplash.com/photo-1532094349884-543bc11b234d?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/8-Psh_1c-0c", description: "Разбираем векторы, ускорение, силы в природе и алгоритмы решения задач на динамику." },
            { id: 5, title: "Органическая химия: Углеводороды", subject: "chemistry", subjectName: "Химия", lessons: 20, image: "https://images.unsplash.com/photo-1532187863486-abf9d39d6618?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/gXpM26n3q_Q", description: "Алканы, алкены, алкины. Номенклатура, химические свойства и цепочки превращений веществ." },
            { id: 6, title: "Генетика и Молекулярная биология", subject: "biology", subjectName: "Биология", lessons: 16, image: "https://images.unsplash.com/photo-1530026405186-ed1ea0ac7a63?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/9N4S1qD_eU4", description: "Законы Менделя, Моргана, биосинтез белка и решение генетических задач из ЕНТ." },
            { id: 7, title: "Физическая география Земли", subject: "geography", subjectName: "География", lessons: 14, image: "https://images.unsplash.com/photo-1524661135-423995f22d0b?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/8rYVnC9_4tY", description: "Литосфера, атмосфера, климатические пояса и геохронологическая таблица. То, на чем часто теряют баллы." },
            { id: 8, title: "Эпоха Просвещения и Революции", subject: "world-hist", subjectName: "Всемирная история", lessons: 11, image: "https://images.unsplash.com/photo-1562673005-7693bd6d6e54?w=500&auto=format&fit=crop&q=60", videoUrl: "https://www.youtube.com/embed/snL1BbeW2M4", description: "Разбор ключевых событий Нового времени: Английская и Французская буржуазные революции." }
        ];

        // --- БАЗА ДАННЫХ ДЛЯ ТЕСТА ---
        const quizQuestions = [
            {
                id: 1,
                subject: "Математическая грамотность",
                question: "В семье 5 сыновей. У каждого из них есть одна сестра. Сколько всего детей в семье?",
                options: ["5", "6", "10", "11"],
                correct: 1 // Индекс правильного ответа ("6")
            },
            {
                id: 2,
                subject: "История Казахстана",
                question: "В каком году произошло восстание под предводительством Кенесары Касымова?",
                options: ["1812-1820 гг.", "1824-1828 гг.", "1837-1847 гг.", "1855-1860 гг."],
                correct: 2 // "1837-1847 гг."
            },
            {
                id: 3,
                subject: "Физика",
                question: "Как изменится сила гравитационного притяжения между двумя телами, если расстояние между ними увеличить в 2 раза?",
                options: ["Увеличится в 2 раза", "Увеличится в 4 раза", "Уменьшится в 2 раза", "Уменьшится в 4 раза"],
                correct: 3 // "Уменьшится в 4 раза"
            },
            {
                id: 4,
                subject: "Химия",
                question: "Какой из перечисленных углеводородов относится к классу алканов?",
                options: ["C2H2", "C2H4", "C2H6", "C6H6"],
                correct: 2 // "C2H6" (Этан)
            }
        ];

        // Функция отрисовки карточек предметов
        function renderContent(subjectFilter = 'all') {
            const grid = document.getElementById('course-grid');
            grid.innerHTML = '';
            const filtered = subjectFilter === 'all' ? entCourses : entCourses.filter(c => c.subject === subjectFilter);
            if(filtered.length === 0) {
                grid.innerHTML = `<div class="col-span-full text-center py-12 text-gray-500">Курсы по этому предмету скоро добавятся!</div>`;
                return;
            }
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
            const buttons = document.querySelectorAll('.subject-btn');
            buttons.forEach(btn => {
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

        /* --- ЛОГИКА ТЕСТОВОЙ СЕКЦИИ (НОВАЯ) --- */

        function renderQuiz() {
            const container = document.getElementById('quiz-questions-container');
            container.innerHTML = '';

            quizQuestions.forEach((q, qIndex) => {
                let optionsHtml = '';
                q.options.forEach((opt, oIndex) => {
                    optionsHtml += `
                        <label class="flex items-center gap-3 p-3.5 border border-gray-200 rounded-xl hover:bg-blue-50/50 cursor-pointer transition option-label">
                            <input type="radio" name="question-${q.id}" value="${oIndex}" required class="w-4 h-4 text-blue-600 border-gray-300 focus:ring-blue-500">
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
        }

        window.handleQuizSubmit = function(event) {
            event.preventDefault();

            let score = 0;
            const total = quizQuestions.length;

            quizQuestions.forEach((q) => {
                const selectedOption = document.querySelector(`input[name="question-${q.id}"]:checked`);
                const questionBlock = document.querySelector(`div[data-qid="${q.id}"]`);
                const labels = questionBlock.querySelectorAll('.option-label');

                const selectedValue = parseInt(selectedOption.value);

                // Подсвечиваем результаты на UI
                labels.forEach((label, oIndex) => {
                    const radio = label.querySelector('input');
                    // Блокируем радиокнопки после отправки
                    radio.disabled = true;

                    if (oIndex === q.correct) {
                        // Правильный ответ красим в зеленый
                        label.className = "flex items-center gap-3 p-3.5 border-2 border-emerald-500 bg-emerald-50 rounded-xl text-emerald-900 font-medium option-label";
                    } else if (oIndex === selectedValue && selectedValue !== q.correct) {
                        // Неправильный выбор пользователя красим в красный
                        label.className = "flex items-center gap-3 p-3.5 border-2 border-red-500 bg-red-50 rounded-xl text-red-900 font-medium option-label";
                    } else {
                        // Остальные тускнеют
                        label.className = "flex items-center gap-3 p-3.5 border border-gray-100 rounded-xl opacity-60 option-label";
                    }
                });

                if (selectedValue === q.correct) {
                    score++;
                }
            });

            // Вывод карточки результатов
            const resultCard = document.getElementById('quiz-result-card');
            const resultScore = document.getElementById('quiz-result-score');
            const resultDesc = document.getElementById('quiz-result-desc');

            resultScore.innerText = `${score} из ${total} баллов`;
            resultCard.classList.remove('hidden');

            // Порог прохождения (например, больше половины правильных)
            if (score === total) {
                resultCard.className = "mt-6 p-6 rounded-xl border-2 border-emerald-500 bg-emerald-50/50 text-center text-emerald-900";
                resultDesc.innerText = "💥 Потрясающе! 140 баллов на ЕНТ уже близко!";
            } else if (score >= total / 2) {
                resultCard.className = "mt-6 p-6 rounded-xl border-2 border-blue-500 bg-blue-50/50 text-center text-blue-900";
                resultDesc.innerText = "👍 Хороший результат, пороговый балл пройден! Посмотри видео-уроки, чтобы улучшить балл.";
            } else {
                resultCard.className = "mt-6 p-6 rounded-xl border-2 border-red-500 bg-red-50/50 text-center text-red-900";
                resultDesc.innerText = "📉 Порог не пройден. Рекомендуем повторить темы в наших видео-лекциях.";
            }

            // Переключаем кнопки управления тестом
            document.getElementById('quiz-submit-btn').classList.add('hidden');
            document.getElementById('quiz-status-text').classList.add('hidden');
            document.getElementById('quiz-reset-btn').classList.remove('hidden');
        }

        window.resetQuiz = function() {
            // Перерендериваем чистый тест
            renderQuiz();

            // Скрываем карточку результатов
            document.getElementById('quiz-result-card').classList.add('hidden');

            // Возвращаем кнопки в исходное
            document.getElementById('quiz-submit-btn').classList.remove('hidden');
            document.getElementById('quiz-status-text').classList.remove('hidden');
            document.getElementById('quiz-reset-btn').classList.add('hidden');
        }

        /* --- ИСХОДНАЯ ЛОГИКА АВТОРИЗАЦИИ --- */
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
            const modalSubtitle = document.getElementById('auth-modal-subtitle');
            const submitText = document.getElementById('auth-submit-text');
            const switchDesc = document.getElementById('auth-switch-desc');
            const switchBtn = document.getElementById('auth-switch-btn');
            document.getElementById('auth-error').classList.add('hidden');

            if (modeInput.value === 'login') {
                modeInput.value = 'register';
                nameField.classList.remove('hidden');
                document.getElementById('auth-name').required = true;
                modalTitle.innerText = 'Регистрация';
                modalSubtitle.innerText = 'Создайте аккаунт для сохранения прогресса';
                submitText.innerText = 'Зарегистрироваться';
                switchDesc.innerText = 'Уже есть аккаунт?';
                switchBtn.innerText = 'Войти';
            } else {
                modeInput.value = 'login';
                nameField.classList.add('hidden');
                document.getElementById('auth-name').required = false;
                modalTitle.innerText = 'Войти в аккаунт';
                modalSubtitle.innerText = 'Введите свои данные для доступа к урокам';
                submitText.innerText = 'Войти';
                switchDesc.innerText = 'Еще нет аккаунта?';
                switchBtn.innerText = 'Создать аккаунт';
            }
        }

        window.handleAuthSubmit = function(event) {
            event.preventDefault();
            const mode = document.getElementById('auth-mode').value;
            const email = document.getElementById('auth-email').value;
            const password = document.getElementById('auth-password').value;
            const errorBlock = document.getElementById('auth-error');
            errorBlock.classList.add('hidden');

            if (password.length < 6) {
                errorBlock.innerText = "Пароль должен быть не менее 6 символов.";
                errorBlock.classList.remove('hidden');
                return;
            }

            if (mode === 'login') {
                if (email === "wrong@mail.ru") {
                    errorBlock.innerText = "Неверный логин или пароль.";
                    errorBlock.classList.remove('hidden');
                    return;
                }
                const userName = email.split('@')[0];
                loginUser(userName);
            } else {
                const name = document.getElementById('auth-name').value.trim();
                if (!name) {
                    errorBlock.innerText = "Пожалуйста, введите имя.";
                    errorBlock.classList.remove('hidden');
                    return;
                }
                loginUser(name);
            }
        }

        function loginUser(username) {
            const authZone = document.getElementById('auth-zone');
            authZone.innerHTML = `
                <div class="flex items-center gap-4">
                    <div class="flex items-center gap-2 bg-gray-100 px-3 py-1.5 rounded-xl border border-gray-200">
                        <div class="w-8 h-8 rounded-full bg-blue-500 text-white flex items-center justify-center font-bold text-sm uppercase">
                            ${username.charAt(0)}
                        </div>
                        <span class="text-sm font-medium text-gray-700 hidden lg:inline">${username}</span>
                    </div>
                    <button onclick="logoutUser()" class="text-gray-400 hover:text-red-500 transition text-sm cursor-pointer" title="Выйти">
                        <i class="fa-solid fa-arrow-right-from-bracket text-lg"></i>
                    </button>
                </div>
            `;
            closeAuthModal();
        }

        window.logoutUser = function() {
            document.getElementById('auth-zone').innerHTML = `<button onclick="openAuthModal()" class="bg-blue-600 text-white px-5 py-2 rounded-lg hover:bg-blue-700 transition font-medium cursor-pointer">Войти</button>`;
        }

        // Первичный запуск курсов и тестов
        renderContent();
        renderQuiz();
    </script>
</body>
</html>
