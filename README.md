CREATE TABLE IF NOT EXISTS blog_posts1 (
	id SERIAL PRIMARY KEY,
	title VARCHAR(255) NOT NULL,
	description TEXT,
	category VARCHAR(100),
	publication_date VARCHAR(100),
	author VARCHAR(100),
	image_url TEXT,
	display_order INT DEFAULT 0
);

INSERT INTO blog_posts1 (title, description, category, publication_date, author, image_url, display_order)
VALUES 
('Заголовок новости', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce mi elit, egestas ut feugiat id, laoreet volutpat risus.', 'IT', '16 ноября 2021', 'Академия ХОД', 'http://localhost:5173/src/assets/q1.png', 1),
('Заголовок новости', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce mi elit, egestas ut feugiat id, laoreet volutpat risus.', 'IT', '16 ноября 2021', 'Академия ХОД', 'http://localhost:5173/src/assets/q2.png', 2),
('Заголовок новости', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce mi elit, egestas ut feugiat id, laoreet volutpat risus.', 'IT', '16 ноября 2021', 'Академия ХОД', 'http://localhost:5173/src/assets/q3.png', 3),
('Заголовок новости', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce mi elit, egestas ut feugiat id, laoreet volutpat risus.', 'IT', '16 ноября 2021', 'Академия ХОД', 'http://localhost:5173/src/assets/q4.png', 4),
('Заголовок новости', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce mi elit, egestas ut feugiat id, laoreet volutpat risus.', 'IT', '16 ноября 2021', 'Академия ХОД', 'http://localhost:5173/src/assets/q5.png', 5),
('Заголовок новости', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce mi elit, egestas ut feugiat id, laoreet volutpat risus.', 'IT', '16 ноября 2021', 'Академия ХОД', 'http://localhost:5173/src/assets/q6.png', 6);

CREATE TABLE IF NOT EXISTS single_article_content (
	content_id SERIAL PRIMARY KEY,
	introduction_text TEXT,
	main_body_text TEXT NOT NULL,
	conclusion_text TEXT
);

INSERT INTO single_article_content (introduction_text, main_body_text, conclusion_text)
VALUES 
(
	'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce mi elit, egestas ut feugiat id, laoreet volutpat risus. Cras condimentum, ligula eget varius eleifend, massa nibh imperdiet est, vel sagittis quam justo vestibulum eros. Cras dignissim mi quis fringilla feugiat. Proin malesuada luctus diam, vitae faucibus dolor venenatis vel. In hac habitasse platea dictumst.', 
	'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce mi elit, egestas ut feugiat id, laoreet volutpat risus. Cras condimentum, ligula eget varius eleifend, massa nibh imperdiet est, vel sagittis quam justo vestibulum eros. Cras dignissim mi quis fringilla feugiat. Proin malesuada luctus diam, vitae faucibus dolor venenatis vel. In hac habitasse platea dictumst. Vestibulum tristique porta aliquam. Suspendisse blandit et sapien sit amet sagittis. Praesent tristique ante sed lacinia congue. Etiam egestas mauris at arcu gravida interdum. Aliquam feugiat risus lacus, ac rutrum dolor porttitor vitae. Etiam porta, nunc sit amet pellentesque posuere, risus nulla sollicitudin enim, commodo bibendum nulla lacus et lorem. Interdum et malesuada fames ac ante ipsum primis in faucibus.', 
	'Proin sit amet lorem consequat, elementum nibh vitae, congue quam. Nunc sapien sapien, commodo nec lorem a, elementum facilisis tortor. Sed porta ultrices orci, maximus tincidunt est sodales vel. Vestibulum lobortis turpis nibh. Vestibulum eros urna, gravida quis lorem at, facilisis pulvinar felis. In eget hendrerit ex, nec consequat orci. Suspendisse a est porta, fringilla ligula nec, ornare dolor. In tristique sagittis mauris dictum volutpat. Maecenas id risus orci. Fusce faucibus metus a leo tincidunt, in commodo elit sollicitudin. Fusce consectetur nulla vel leo feugiat, a ultrices leo imperdiet. Sed eget est quis felis molestie dictum. Sed consequat malesuada quam, id malesuada augue euismod nec. Phasellus ultrices velit non venenatis sagittis.'
);

CREATE TABLE IF NOT EXISTS users_auth (
	user_id SERIAL PRIMARY KEY,
	user_name VARCHAR(100) NOT NULL,
	user_email VARCHAR(150) UNIQUE NOT NULL,
	user_password TEXT NOT NULL
);

CREATE TABLE IF NOT EXISTS student_reviews (
	review_id SERIAL PRIMARY KEY,
	student_name VARCHAR(150) NOT NULL,
	course_title VARCHAR(150) NOT NULL,
	review_text TEXT NOT NULL,
	review_rating NUMERIC(3, 2) DEFAULT 4.87,
	student_avatar TEXT,
	display_order INT DEFAULT 0
);

INSERT INTO student_reviews (student_name, course_title, review_text, review_rating, student_avatar, display_order)
VALUES 
('Имя Фамилия', 'Студент курса «WEB-разработчик»', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut feugiat nisl at augue dapibus, id tristique lorem placerat. Curabitur pellentesque est bibendum urna facilisis varius. In hac habitasse platea dictumst. In ut dui sodales.', 4.87, 'http://localhost:5173/src/assets/l1.png', 1),
('Имя Фамилия', 'Студент курса «WEB-разработчик»', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut feugiat nisl at augue dapibus, id tristique lorem placerat. Curabitur pellentesque est bibendum urna facilisis varius. In hac habitasse platea dictumst. In ut dui sodales.', 4.87, 'http://localhost:5173/src/assets/l2.png', 2),
('Имя Фамилия', 'Студент курса «WEB-разработчик»', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut feugiat nisl at augue dapibus, id tristique lorem placerat. Curabitur pellentesque est bibendum urna facilisis varius. In hac habitasse platea dictumst. In ut dui sodales, scelerisque eros non, ultrices magna.', 4.87, 'http://localhost:5173/src/assets/l3.png', 3),
('Имя Фамилия', 'Студент курса «WEB-разработчик»', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut feugiat nisl at augue dapibus, id tristique lorem placerat. Curabitur pellentesque est bibendum urna facilisis varius.', 4.87, 'http://localhost:5173/src/assets/l4.png', 4),
('Имя Фамилия', 'Студент курса «WEB-разработчик»', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut feugiat nisl at augue dapibus, id tristique lorem placerat. Curabitur pellentesque est bibendum urna facilisis varius. In hac habitasse platea dictumst. In ut dui sodales.', 4.87, 'http://localhost:5173/src/assets/l1.png', 5),
('Имя Фамилия', 'Студент курса «WEB-разработчик»', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut feugiat nisl at augue dapibus, id tristique lorem placerat. Curabitur pellentesque est bibendum urna facilisis varius.', 4.87, 'http://localhost:5173/src/assets/l2.png', 6);


CREATE TABLE IF NOT EXISTS academy_vacancies (
	vacancy_id SERIAL PRIMARY KEY,
	vacancy_title VARCHAR(150) NOT NULL,
	vacancy_city VARCHAR(100) NOT NULL DEFAULT 'г. Москва',
	vacancy_category VARCHAR(100) NOT NULL,
	vacancy_greeting TEXT NOT NULL,
	vacancy_target TEXT NOT NULL,
	vacancy_duties TEXT NOT NULL,
	vacancy_requirements TEXT NOT NULL,
	vacancy_benefits TEXT NOT NULL,
	vacancy_footer TEXT NOT NULL,
	display_order INT DEFAULT 0
);

INSERT INTO academy_vacancies (
	vacancy_title, vacancy_city, vacancy_category, vacancy_greeting, vacancy_target, vacancy_duties, vacancy_requirements, vacancy_benefits, vacancy_footer, display_order
) VALUES 
(
	'Дизайнер',
	'г. Москва',
	'3D-моделирование и дизайн',
	'Привет!',
	'Сейчас мы стремительно растем, поэтому ищем нам очень нужен старший Influence marketing менеджер!',
	'подбирать и работать с лидерами мнений в Instagram, YouTube, Telegram и Twitch от бриффинга и планирования, до реализации и измерения эффективности;;самостоятельно искать и анализировать референсы, изучать стратегии других брендов, строить, проверять и масштабировать гипотезы;;ставить задачи партнерским агентствам на поиск и подбор инфлюенсеров и релевантных каналов, контролировать соблюдение таймингов и качество рекламных интеграций, следить за эффективностью;;создавать креативные идеи, механики активаций и стратегии рекламных кампаний в области influence-маркетинга;;управлять командой influence маркетинговых менеджеров (впоследствии добор команды).',
	'опыт работы в influence маркетинге от 4-х лет;;опыт работы на руководящей должности в инфлюенсе от 1-го года;;глубокое погружение в сферу и понимание трендов индустрии;;знание и понимание метрик каналов;;умение проводить анализ эффективности рекламы в инструментах Google Analytics, Яндекс.Метрика;;понимание работы моделей атрибуции в интернет-маркетинге;;сильные навыки в подборе лидеров мнений;;умение аргументировать свои решения и выбор;;сильные коммуникационные навыки, дипломатия.',
	'профессиональная команда, готовая вдохновлять и делиться опытом (мы общаемся на равных, ценим открытость и честность и всегда прислушиваемся друг к другу);;удобная среда для работы и отдыха (комфортный офис в центре, гибкое начало рабочего дня, современная техника, отсутствие дресс-кода и уютная кухня, где всегда можно найти свежий кофе и что-нибудь вкусное);;все для профессионального развития (бесплатный доступ к курсам GeekBrains и наших партнеров);;ДМС сразу после прохождения испытательного срока;;а еще полезные скидки от наших партнеров и практически круглосуточная поддержка наших заботливых эйчаров!',
	'Хочешь к нам в команду? Скорее откликайся, мы тебя очень ждем! А если ты еще и расскажешь немного о себе в сопроводительном письме, мы будем рады твоему отклику вдвойне :)',
	1
),
(
	'Разработчик игр',
	'г. Москва',
	'Создание игр',
	'Привет, будущий коллега!',
	'Мы расширяем команду геймдева и ищем опытного разработчика, готового создавать крутые игровые миры.',
	'Разработка и оптимизация игровых механик на Unity/Unreal Engine;;Проектирование архитектуры клиентской части игр;;Взаимодействие с 3D-художниками и геймдизайнерами;;Участие в планировании спринтов и код-ревью.',
	'Опыт коммерческой разработки игр от 2 лет;;Отличное знание C# или C++;;Понимание принципов объектно-ориентированного программирования;;Опыт работы с системами контроля версий Git.',
	'Работа над амбициозными игровыми проектами;;Гибкий график и возможность удаленной работы;;Современное железо для разработки;;Оплата профильного обучения и курсов.',
	'Если ты любишь игры так же, как и мы, присылай свое портфолио!',
	2
),
(
	'Веб-разработчик',
	'г. Москва',
	'Web-разработка',
	'Здравствуйте!',
	'Наша команда разработки ищет Fullstack или Frontend специалиста для развития образовательной платформы.',
	'Разработка пользовательских интерфейсов на React;;Интеграция с внутренними и внешними API сервисами;;Оптимизация скорости загрузки и производительности страниц;;Написание чистого, тестируемого и поддерживаемого кода.',
	'Уверенные знания HTML5, CSS3, JavaScript (ES6+);;Опыт работы с React и экосистемой (Redux/Zustand);;Опыт адаптивной и кроссбраузерной верстки;;Понимание базовых принципов работы веб-серверов.',
	'Сильная команда разработчиков готовая делиться опытом;;Официальное оформление и белая заработная плата;;Комфортный офис со всеми удобствами;;Участие в профильных ИТ-конференциях.',
	'Откликайся, проходи техническое собеседование и присоединяйся к нам!',
	3
),
(
	'Дизайнер',
	'г. Москва',
	'3D-моделирование и дизайн',
	'Привет!',
	'Сейчас мы стремительно растем, поэтому ищем нам очень нужен старший Influence marketing менеджер!',
	'подбирать и работать с лидерами мнений в Instagram, YouTube, Telegram и Twitch от бриффинга и планирования, до реализации и измерения эффективности;;самостоятельно искать и анализировать референсы, изучать стратегии других брендов, строить, проверять и масштабировать гипотезы;;ставить задачи партнерским агентствам на поиск и подбор инфлюенсеров и релевантных каналов, контролировать соблюдение таймингов и качество рекламных интеграций, следить за эффективностью;;создавать креативные идеи, механики активаций и стратегии рекламных кампаний в области influence-маркетинга;;управлять командой influence маркетинговых менеджеров (впоследствии добор команды).',
	'опыт работы в influence маркетинге от 4-х лет;;опыт работы на руководящей должности в инфлюенсе от 1-го года;;глубокое погружение в сферу и понимание трендов индустрии;;знание и понимание метрик каналов;;умение проводить анализ эффективности рекламы в инструментах Google Analytics, Яндекс.Метрика;;понимание работы моделей атрибуции в интернет-маркетинге;;сильные навыки в подборе лидеров мнений;;умение аргументировать свои решения и выбор;;сильные коммуникационные навыки, дипломатия.',
	'профессиональная команда, готовая вдохновлять и делиться опытом (мы общаемся на равных, ценим открытость и честность и всегда прислушиваемся друг к другу);;удобная среда для работы и отдыха (комфортный офис в центре, гибкое начало рабочего дня, современная техника, отсутствие дресс-кода и уютная кухня, где всегда можно найти свежий кофе и что-нибудь вкусное);;все для профессионального развития (бесплатный доступ к курсам GeekBrains и наших партнеров);;ДМС сразу после прохождения испытательного срока;;а еще полезные скидки от наших партнеров и практически круглосуточная поддержка наших заботливых эйчаров!',
	'Хочешь к нам в команду? Скорее откликайся, мы тебя очень ждем! А если ты еще и расскажешь немного о себе в сопроводительном письме, мы будем рады твоему отклику вдвойне :)',
	4
),
(
	'Разработчик игр',
	'г. Москва',
	'Создание игр',
	'Привет, будущий коллега!',
	'Мы расширяем команду геймдева и ищем опытного разработчика, готового создавать крутые игровые миры.',
	'Разработка и оптимизация игровых механик на Unity/Unreal Engine;;Проектирование архитектуры клиентской части игр;;Взаимодействие с 3D-художниками и геймдизайнерами;;Участие в планировании спринтов и код-ревью.',
	'Опыт коммерческой разработки игр от 2 лет;;Отличное знание C# или C++;;Понимание принципов объектно-ориентированного программирования;;Опыт работы с системами контроля версий Git.',
	'Работа над амбициозными игровыми проектами;;Гибкий график и возможность удаленной работы;;Современное железо для разработки;;Оплата профильного обучения и курсов.',
	'Если ты любишь игры так же, как и мы, присылай свое портфолио!',
	5
),
(
	'Веб-разработчик',
	'г. Москва',
	'Web-разработка',
	'Здравствуйте!',
	'Наша команда разработки ищет Fullstack или Frontend специалиста для развития образовательной платформы.',
	'Разработка пользовательских интерфейсов на React;;Интеграция с внутренними и внешними API сервисами;;Оптимизация скорости загрузки и производительности страниц;;Написание чистого, тестируемого и поддерживаемого кода.',
	'Уверенные знания HTML5, CSS3, JavaScript (ES6+);;Опыт работы с React и экосистемой (Redux/Zustand);;Опыт адаптивной и кроссбраузерной верстки;;Понимание базовых принципов работы веб-серверов.',
	'Сильная команда разработчиков готовая делиться опытом;;Официальное оформление и белая заработная плата;;Комфортный офис со всеми удобствами;;Участие в профильных ИТ-конференциях.',
	'Откликайся, проходи техническое собеседование и присоединяйся к нам!',
	6
);

CREATE TABLE IF NOT EXISTS academy_founders (
	founder_id SERIAL PRIMARY KEY,
	founder_name VARCHAR(150) NOT NULL,
	founder_role VARCHAR(150) NOT NULL,
	founder_avatar TEXT,
	interview_paragraph_1 TEXT NOT NULL,
	interview_paragraph_2 TEXT NOT NULL,
	interview_source VARCHAR(255) NOT NULL,
	display_order INT DEFAULT 0
);

INSERT INTO academy_founders (
	founder_name, 
	founder_role, 
	founder_avatar, 
	interview_paragraph_1, 
	interview_paragraph_2, 
	interview_source, 
	display_order
) VALUES (
	'Имя Фамилия',
	'Основатель Академии будущего ХОД',
	'http://localhost:5173/src/assets/av1.png',
	'«Все началось с любви к шахматам. Я хотел предвидеть ход противника, хотел просчитать его действия, хотел побеждать. Я не стал гением шахмат, но стратег и психолог из меня неплохой» - смеется Иван Иванович. Идея открыть Академию шахмат пришла к нему в 2020 году, когда в период полного локдауна он вдруг вспомнил про хобби - игру в шахматы. Оказалось, что для игры в шахматы сейчас и доска-то не обязательна, все есть в телефоне. Племянник (сын?) Ивана Ивановича большую часть дня проводил в стрелялках на планшете.',
	'«Я показал ему шахматы. К июню он уже был неплохим соперником» - Вскоре идея небольшой академии шахмат превратилась в план создания Академии Будущего, где дети смогут учиться тому, что им нравится, а взрослые попытаются изменить жизнь. Уж очень это сейчас актуально".',
	'Из интервью с основателем Академии Будущего Ивановым И.И.',
	1
);

CREATE TABLE IF NOT EXISTS teachers_reviews (
	teacher_id SERIAL PRIMARY KEY,
	teacher_name VARCHAR(150) NOT NULL,
	teacher_info_1 TEXT NOT NULL,
	teacher_info_2 TEXT NOT NULL,
	teacher_avatar TEXT,
	display_order INT DEFAULT 0
);

INSERT INTO teachers_reviews (teacher_name, teacher_info_1, teacher_info_2, teacher_avatar, display_order)
VALUES 
('Имя Фамилия', 'Выпускница Гарвардского Университета.', 'Более 10 лет играет в шахматы и участвует в турнирах.', 'http://localhost:5173/src/assets/zt1.png', 1),
('Имя Фамилия', 'Выпускник Гарвардского Университета.', 'Более 10 лет играет в шахматы и участвует в турнирах.', 'http://localhost:5173/src/assets/zt2.png', 2),
('Имя Фамилия', 'Выпускница Гарвардского Университета.', 'Более 10 лет играет в шахматы и участвует в турнирах.', 'http://localhost:5173/src/assets/zt3.png', 3),
('Имя Фамилия', 'Выпускник Гарвардского Университета.', 'Более 10 лет играет в шахматы и участвует в турнирах.', 'http://localhost:5173/src/assets/zt4.png', 4),
('Имя Фамилия', 'Выпускник Гарвардского Университета.', 'Более 10 лет играет в шахматы и участвует в турнирах.', 'http://localhost:5173/src/assets/zt5.png', 5);
