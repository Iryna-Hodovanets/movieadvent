# movieadvent
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>🎄 Різдвяний Адвент-Календар Фільмів</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px;
        }
        .calendar {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 10px;
            max-width: 900px;
            margin: 0 auto;
        }
        .day {
            background-color: #34495e;
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.3s;
        }
        .day:hover {
            transform: scale(1.05);
        }
        .movie-title {
            display: none;
            margin-top: 10px;
            font-weight: bold;
        }
        .day:hover .movie-title {
            display: block;
        }
    </style>
</head>
<body>
    <h1>🎬 Різдвяний Адвент-Календар Фільмів</h1>
    <div class="calendar" id="calendar"></div>

    <script>
        const movies = [
            'Сам удома', 
            'Сам удома 2', 
            'Дух Різдва', 
            'Грінч', 
            'Як Грінч викрав Різдво', 
            'Полярний експрес', 
            'Клаус', 
            'Крампус', 
            'Чарлі та шоколадна фабрика', 
            'Кошмар перед Різдвом', 
            'Реальне кохання', 
            'Хлопчик на імʼя Різдво', 
            'Чорне дзеркало: Біле Різдво', 
            'Інтуїція', 
            'Різдвяна історія', 
            'Місія різдвяний порятунок', 
            'Крижане серце', 
            'Вартові легенд', 
            'Людина яка винайшла Різдво', 
            'Пара на свята', 
            'Чотири Різдва', 
            'Різдвяні хроніки', 
            'Старий Новий Рік', 
            'Ельф', 
            'Новорічний корпоратив', 
            'Любіть Куперів', 
            'Щасливого Різдва', 
            'Поки ти спав', 
            'Ноель', 
            'Сімʼянин',
            'Труп нареченої'
        ];

        // Перемішування фільмів
        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
            return array;
        }

        const shuffledMovies = shuffleArray([...movies]);

        // Встановлення "Трупа нареченої" на останній день
        shuffledMovies[30] = 'Труп нареченої';

        const calendar = document.getElementById('calendar');

        shuffledMovies.forEach((movie, index) => {
            const day = document.createElement('div');
            day.classList.add('day');
            day.innerHTML = `
                <div>${index + 1}</div>
                <div class="movie-title">${movie}</div>
            `;
            calendar.appendChild(day);
        });
    </script>
</body>
</html>
