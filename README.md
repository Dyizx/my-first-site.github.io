<!DOCTYPE HTML>
<head>
<script src="https://code.jquery.com/jquery-3.6.4.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vue@3"></script> <!-- Подключение Vue.js -->
<!-- Подключение jQuery UI -->
  <link rel="stylesheet" href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
  <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.min.js"></script>
  <style>
    #animatedDiv {
      width: 200px;
      height: 100px;
      background-color: orange;
      display: none; /* Элемент скрыт изначально */
    }
    #slider {
      margin-top: 20px;
    }
  </style>

</head>

<script>
   window.onload = function () {
        document.getElementById("searchBtn").onclick = function () {
            let input = document.getElementById("searchInput").value.toLowerCase();
            let table = document.querySelector("table tbody");
            let rows = Array.from(table.rows);

            rows.forEach(row => {
                let cells = Array.from(row.cells);
                let found = cells.some(cell => cell.textContent.toLowerCase().includes(input));
                row.style.display = found ? "" : "none";
            });
        };

        document.getElementById("addPlusBtn").onclick = function () {
            let plusList = document.querySelector("ol");
            let newItem = document.createElement("li");
            newItem.innerHTML = "<b>Новый плюс:</b> Количество часов прохождения";
            plusList.appendChild(newItem);
        };

        document.getElementById("addMinusBtn").onclick = function () {
            let minusList = document.querySelector("ul");
            let newItem = document.createElement("li");
           newItem.innerHTML = "<b>Новый минус:</b> Может быть сложно для новичков";
            minusList.appendChild(newItem);
        };

        
        document.getElementById("shrinkTableBtn").onclick = function () {
            let table = document.querySelector("table");
            let currentWidth = parseFloat(window.getComputedStyle(table).width);
            table.style.width = currentWidth * 0.9 + "px";
        };

        document.getElementById("deleteTableBtn").onclick = function () {
            let table = document.querySelector("table");
            if (table) {
                table.remove();
            } else {
                
                alert("Таблица уже удалена!");
            }
        };
    };
    window.onbeforeunload = function () {
        return "Вы уверены, что хотите покинуть страницsу?";
    };

    window.onbeforeunload = function (event) {
    event.preventDefault(); 

    return "Изменения могут не сохраниться. Вы уверены, что хотите перезагрузить страницу?";
    };



</script>

    
    </style>
    <meta charset="UTF-8">
    <title>Баха</title>
   <style>
   .text-block {
    border: 1px solid darkslategray; /* Изменен цвет границы */
    margin-left: 3cm;
    margin-right: 1cm;
    margin-top: 2cm;
    margin-bottom: 2cm;
    font-family: "Times New Roman", Times, serif;
    font-size: 14pt;
    background-color: #d3d3d3; /* Изменен фон на светло-голубой */
    text-indent: 1.5cm;
    color: black;
    }

    .text-block::first-letter {
    font-size: 18pt;
    }




    /* Стиль для таблицы */
    table {
        width: 80%;
        border-collapse: collapse;
    }

    table th {
        text-align: center;
        background-color:black; /* Изменен фон заголовков таблицы */
        color: white; /* Цвет текста заголовков */
    }

    table td {
        border: 1px solid darkslategray;
        padding: 10px;
    }

    table td:first-child {
        text-align: justify;
    }

    table td:nth-child(2) {
        text-align: center;
    }

    table tr:nth-child(even) {
        background-color: #800080; /* Изменен цвет четных строк на светлsq */
    }

    table tr:nth-child(odd) {
        background-color: white; 
        color: black;
    }

    /* Изображение с обтеканием текста */
    img {
        float: left;
        margin: 0 20px 20px 0;
    }

    
    /* Основной стиль для h1 */
    h1 {
        color: blue; /* Инд иго цвет заголовка */
    }

    /* Основной стиль для h1 и h2 */
    h1, h2 {
        font-family: Arial, sans-serif; /* Шрифт для обоих заголовков */
    }
    h2{
        color: green;
    }
    /* Стили для списков */
    ul, ol {
        margin-left: 2px;
    }

    /* Стили для ссылок */
    a {
        color: #1e90ff; /* Изменен цвет ссылок */
        text-decoration: none;
    }

    a:hover {
        color: #ff4500; /* Изменен цвет при наведении */
    }

    /* Применение CSS3 (например, тени и градиенты) */
    h1 {
        text-shadow: 2px 2px 5px gray;
    }

     input[type="submit"] {
        border: none;
        padding: 10px 20px;
        color: white; /* Цвет текста кнопки */
        cursor: pointer;
        font-weight: bold; /* Жирный шрифт для текста кнопки */
        border-radius: 10px; /* Скругленные углы */
        transition: transform 0.3s ease; /* Плавный переход для трансформации */
    }

    input[type="submit"]:hover {
        background: linear-gradient(to right, #ff4500, #ff7f50); /* Обратный градиент при наведении */
        transform: scale(1.1); /* Увеличение кнопки при наведении */
    }

    input[type="submit"]:active {
        transform: scale(0.95); /* Уменьшение кнопки при нажатии */
    }

.fixed-element{
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: blue;
    padding: 10px;
}
    </style>

<body background="https://wallscloud.net/img/resize/1600/900/MM/2016-09-30-steam-game-logo-2-W73E.png">
    <font color="white">
    <h1 style="color: red;">Добро пожаловать на страницу про новинки из видеоигр</h1>
    
    <h2 id="editableTitle">Обзор</h2>
    <button id="editContentBtn">Изменить контент</button>
    <div class = "text-block"><p>Сегодняшний обзор будет про игру <mark><b>Black Myth: Wukong.</b></mark> — компьютерная игра в жанре ролевой экшн, основанная на классическом китайском романе <i>«Путешествие на Запад»</i>. Разработчиком игры выступила китайская студия Game Science. Проект был выпущен 20 августа 2024 года. Игра получила высокие оценки от профильной прессы и поставила рекорд среди одиночных игр по одновременной игре в Steam.</p> </div>

    <h2>Скриншот из игры</h2>
<img src="https://www.mirf.ru/backend/wp-content/uploads/2024/09/2qBHKG8wPTqY1kpF6NtwEDcRjVomiYqc4EIdzN5N/x1536-y0.webp" alt="Пример изображения" width="700" height="400">
<p>Этот текст обтекает изображение слева. Здесь ты можешь описать изображение или продолжить рассказывать о других аспектах игры. Убедись, что текст достаточно длинный, чтобы обтекание было заметно.</p>

    <h2>Трейлер игры Black Myth: Wukong</h2>
    <video width="700" height="400" controls>
        <source src="videoplayback.mp4" type="video/mp4">
    </video>

    <h2>Плюсы и минусы игры</h2>

    <h3>Плюсы</h3>
    <ol>
        <li><b>Инновационная и богатая китайская мифология:</b> Игра глубоко погружается в китайскую мифологию, основываясь на знаменитом эпосе "Путешествие на Запад".</li>
        <li><b>Впечатляющая графика и визуальные эффекты:</b> Black Myth: Wukong выделяется своими потрясающими визуальными эффектами.</li>
        <li><b>Интересный и разнообразный геймплей:</b> Игра предлагает разнообразные механики и элементы геймплея, такие как уникальные боевые системы.</li>
    </ol>

    <h3>Минусы</h3>
    <ul>
        <li><b>Сложность восприятия без культурного контекста:</b> Без знания китайской мифологии и культурных отсылок игрокам может быть трудно понять сюжет.</li>
        <li><b>Запутанный и перегруженный сюжет:</b> Сюжетная линия может показаться сложной для восприятия.</li>
        <li><b>Отсутствие гибкости в управлении контентом:</b> Некоторые элементы управления могут быть ограничены.</li>
    </ul>

   <div id="app">
    <h2>{{ message }}</h2>

    <!-- Кнопки для добавления плюсов и минусов -->
    <button @click="addPlusBtn">Добавить плюс</button>
    <button @click="addMinusBtn">Добавить минус</button>

    <!-- Списки плюсов и минусов -->
    <ol>
        <li v-for="plus in pluses" :key="plus">{{ plus }}</li>
    </ol>
    <ul>
        <li v-for="minus in minuses" :key="minus">{{ minus }}</li>
    </ul>

    <!-- Кнопка для показа/скрытия дополнительной информации -->
    <button @click="toggleInfo">Тыкни если хочешь узнать секрет в игре</button>

    <!-- Информация, которая скрывается/открывается при клике -->
    <div v-if="isInfoVisible">
        <p>Как получить артефакт «Огненная накидка»
Возвращаясь к колоколу, вы можете взаимодействовать с волком на дереве, чтобы получить артефакт «Огненная накидка» — ваш первый артефакт. Его можно активировать нажатием клавиши T. Накидка временно обеспечивает полную защиту от огня и постепенно увеличивает очки концентрации. Этот артефакт полезен в определенных локациях и против огненных врагов, значительно увеличивая сопротивление огню и защищая от лавы.</p>
    </div>
</div>



    <button id="addPlusBtn">Добавить плюс</button>
    <button id="addMinusBtn">Добавить минус</button>
    <button id="shrinkTableBtn">Уменьшить таблицу</button>
    <button id="deleteTableBtn">Удалить таблицу</button>
    <button id="showDivBtn">Факты про игру</button>
<div id="animatedDiv">Эта игра не рекламировалась как другие игры,но популярность обрела с первого дня релиза</div>


    <h2>Поиск по таблице</h2>
    <input type="text" id="searchInput" placeholder="Введите значение для поиска">
    <button id="searchBtn">Искать</button>

    <h2>Четыре элемента игры</h2>
    <table border="1" width="70%" cellpadding="5" cellspacing="0">
        <thead>
            <tr>
                <th>Элементы</th>
                <th>Результат</th>
                <th>Элементы</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><b>Сюжет и мифология:</b> Игра основана на китайском эпосе "Путешествие на Запад".</td>
                <td rowspan="2"><img src="https://upload.wikimedia.org/wikipedia/ru/a/a6/Black_Myth_Wukong_cover_art.jpg" alt="Пример изображения" width="300" height="300"></td>
                <td><b>Графика и визуальный стиль:</b> Black Myth: Wukong выделяется своей визуальной презентацией.</td>
            </tr>
            <tr>
                <td><b>Геймплей и боевые механики:</b> Основной фокус игры — это боевой процесс.</td>
                <td><b>Исследование и взаимодействие:</b> Игра включает в себя открытый мир и элементы исследования.</td>
            </tr>
            <tr>
                <td colspan="3"><b>Black Myth: Wukong</b> сочетает эти четыре элемента, создавая комплексное и многослойное игровое произведение.</td>
            </tr>
        </tbody>
    </table>

    <h2>Форма обратной связи</h2>

    <form>
        <label for="username">Имя:</label>
        <input type="text" id="username" name="username" required placeholder="Введите ваше имя"><br><br>

        <label for="email">Электронная почта:</label>
        <input type="email" id="email" name="email" required placeholder="Введите вашу почту"><br><br>

        <input type="submit" value="Отправить">
    </form>

    <h2>Дополнительная информация</h2>
    <p>Приобрести игру <a href="https://store.steampowered.com/app/2358720/Black_Myth_Wukong/" title="сайта">Black Myth: Wukong</a>.</p>

    <h2>Обзор от популярного летсплейщика</h2>
    <p><a href="https://youtu.be/Z7ncjjPhsIQ?si=HhZ6rtW_P_1c9Ryv" title="Перейти">The Brain Dit</a></p>

    <h2>Веб-сайт разработчиков игры</h2>
    <p><a href="https://www.gamesci.com.cn/" title="сайта">GameScience</a></p>

    <h2>Ассортимент моего веб-магазина периферийных устройств</h2>
    <a href="второй.html">Ассортимент наушников</a>

    <div class="fixed-element">Спасибо за посещение</div>


    
<script>
    $(document).ready(function () {
        
        // Изменение контента кнопки при нажатии
        $("#addPlusBtn").click(function () {
            let plusList = $("ol");
            let newItem = $("<li>").html("<b>Новый плюс:</b> Уникальная боевка");
            plusList.append(newItem);

            // Визуальный эффект появления
            newItem.hide().fadeIn(500);
        });

        $("#addMinusBtn").click(function () {
            let minusList = $("ul");
            let newItem = $("<li>").html("<b>Новый минус:</b> Высокая цена игры");
            minusList.append(newItem);

            // Визуальный эффект появления
            newItem.hide().slideDown(500);
        });

           $("#shrinkTableBtn").click(function () {
        $("table").animate({ width: "10%" }, 300); // Уменьшение до 10%
    });


        $("#deleteTableBtn").click(function () {
    $("table").fadeOut(500, function () {
        $(this).remove(); // Удаление после анимации
    });
});


        // Поиск по таблице
        $("#searchBtn").click(function () {
            let input = $("#searchInput").val().toLowerCase();
            $("table tbody tr").each(function () {
                let rowText = $(this).text().toLowerCase();
                $(this).toggle(rowText.includes(input));
            });
        });

        // Пример визуального эффекта - появление блока
        $("#showDivBtn").click(function () {
            $("#animatedDiv").toggle("slow");
        });
    });

     $(document).ready(function () {
        $("#editContentBtn").click(function () {
            let newContent = prompt("Введите новый текст для заголовка:");
            if (newContent) {
                $("#editableTitle").text(newContent);
            }
        });
    });
</script>


<script>
   const app = Vue.createApp({
    data() {
        return {
            message: "Управление списками через Vue.js",
            pluses: [
                "Инновационная мифология",
                "Потрясающая графика",
                "Разнообразный геймплей"
            ],
            minuses: [
                "Сложный сюжет",
                "Высокие системные требования"
                "Китайская мифология"
            ],
            isInfoVisible: false // Флаг для отображения дополнительной информации
        };
    },
    methods: {
        addPlusBtn() {
            this.pluses.push("Сохранение всех ценностей ориентаций на то время");
        },
        addMinusBtn() {
            this.minuses.push("Игру могут позволить себе не все");
        },
        toggleInfo() {
            this.isInfoVisible = !this.isInfoVisible; // Переключаем видимость информации
        }
    }
});

app.mount("#app");

</script>

 <h1>Пример с плагином jQuery</h1>
  
  <div>
    <button id="toggle-text-btn">Оцени сайт</button>
    <p id="resizable-text">Спасибо♥</p>
    <div id="slider"></div>
    <p>Оценка: <span id="slider-value">0</span></p>
</div>

<h1>Демонстрация работы с jQuery UI</h1>
    

    <!-- Datepicker -->
    <label for="dateInput">Выберите дату:</label>
    <input type="text" id="dateInput">

     <script>
        $(document).ready(function () {
            // Инициализация datepicker
            $("#dateInput").datepicker({
                dateFormat: "dd-mm-yy",
                showAnim: "slideDown"
            });
        });
    </script>

<script>
    $(function () {
        // Инициализация слайдера
        $("#slider").slider({
            min: 10,
            max: 100,
            value: 50,
            slide: function (event, ui) {
                $("#slider-value").text(ui.value); // Обновление отображаемого значения
                $("#resizable-text").css("font-size", ui.value + "px"); // Изменение размера текста
            }
        });

        // Показать/Скрыть текст при нажатии на кнопку
        $("#toggle-text-btn").click(function () {
            const textElement = $("#resizable-text");
            if (textElement.is(":visible")) {
                textElement.hide(); // Скрыть текст
                $(this).text("Оцени сайт"); // Изменить текст кнопки
            } else {
                textElement.show(); // Показать текст
                $(this).text("Оцени сайт"); // Изменить текст кнопки
            }
        });
    });
</script>
</script>

  
</body>
</html>
