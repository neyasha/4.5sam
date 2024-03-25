<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Империя Грёз</title>
    <style>
        body {
            font-family: Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #6e2a2a;
        }
        .container {
            max-width: 1350px;
            margin: 20px auto;
            padding: 0; 
        }
        h1 {
            text-align: center;
            color: #a3641c;
        }
        .catalog {
            display: grid;
            grid-template-columns: repeat(3, 1fr); 
            gap: 20px; 
            justify-content: center;
            margin-top: 30px;
        }
        .product {
            width: 100%;
            padding: 20px;
            background-color: #9e5d1c;
            color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
            text-align: center;
            position: relative;
            opacity: 0; 
            animation: fadeIn 1s ease-in-out forwards; 
        }
        .product img {
            width: 100%;
            height: auto;
            max-width: 500px;
            max-height: 300px;
            border-radius: 8px;
            margin-bottom: 10px;
        }
        .product h2 {
            color: #4f0a0a;
            margin-bottom: 10px;
        }
        .product p {
            margin-bottom: 10px;
        }
        .product select {
            margin-top: 10px;
            padding: 8px;
            border-radius: 5px;
            border: 1px solid #ffffff;
            width: 100%;
            box-sizing: border-box;
            color: #000000;
            background-color: #ffffff;
        }
        .product .price {
            margin-top: 10px;
            color: #ff0000;
            font-weight: bold;
        }
        .product button {
            margin-top: 10px;
            padding: 10px 20px;
            background-color: #4f0a0a;
            color: #ffffff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .product button:hover {
            background-color: #a3641c;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
    </style>
</head>
<body class="background">
    <div class="container">
        <h1>Каталог фильмов</h1>
        <div class="catalog" id="catalog"></div>
    </div>

    <script>
        const products = [
            { name: 'Лёд 3', image: 'https://s3.afisha.ru/mediastorage/2a/33/d281002d901a4f7d84337489332a.jpg', options: [1, 2, 3, 4], prices: [150, 280, 350, 450] },
            { name: 'Огонь', image: 'https://s2.afisha.ru/mediastorage/d9/92/ce34ba18fb4d4a598babbc2992d9.jpg', options: [1, 2, 3, 4], prices: [170, 300, 450, 600] },
            { name: 'Адам и Ева', image: 'https://s5.afisha.ru/mediastorage/db/7e/7cc9b0384a5d405f8cd0de397edb.jpg', options: [1, 2, 3, 4], prices: [150, 290, 360, 500] },
            { name: 'Текст', image: 'https://sun9-38.userapi.com/impg/c855016/v855016017/17be73/gC_4lN7OqJg.jpg?size=520x0&quality=95&sign=eca48f1d9488c3138e1de0b23b5aa790', options: [1, 2, 3, 4], prices: [170, 310, 470, 680] },
            { name: 'Брат', image: 'https://kudamoscow.ru//uploads/220325124425310.jpg', options: [1, 2, 3, 4], prices: [100, 180, 260, 380] },
            { name: 'Вызов', image: 'https://s1.afisha.ru/mediastorage/67/35/05325e5fca82487fa975ade33567.jpg', options: [1, 2, 3, 4], prices: [190, 320, 480, 670] },
        ];

        function createProductCard(product) {
            const card = document.createElement('div');
            card.className = 'product';

            const image = document.createElement('img');
            image.src = product.image;
            image.alt = product.name;
            card.appendChild(image);

            const title = document.createElement('h2');
            title.textContent = product.name;
            card.appendChild(title);

            const paragraph = document.createElement('p');
            paragraph.textContent = 'Количество билетов:';
            card.appendChild(paragraph);

            const select = document.createElement('select');
            product.options.forEach((option, index) => {
                const optionElement = document.createElement('option');
                optionElement.value = option;
                optionElement.textContent = option;
                optionElement.setAttribute('data-price', product.prices[index]);
                select.appendChild(optionElement);
            });
            card.appendChild(select);

const timeParagraph = document.createElement('p');
timeParagraph.textContent = 'Выберите время сеанса:';
card.appendChild(timeParagraph);

const timeSelect = document.createElement('select');
const times = ['10:00', '13:00', '16:00', '19:00'];
times.forEach(time => {
    const timeOption = document.createElement('option');
    timeOption.value = time;
    timeOption.textContent = time;
    timeSelect.appendChild(timeOption);
});
card.appendChild(timeSelect);
const price = document.createElement('div');
price.className = 'price';
card.appendChild(price);

select.addEventListener('change', function () {
    const selectedOption = this.options[this.selectedIndex];
    const selectedPrice = selectedOption.getAttribute('data-price');
    price.textContent = `Цена:${selectedPrice}₽`;
});
const button = document.createElement('button');
button.textContent = 'Забронировать';
button.addEventListener('click', function () {
    const selectedQuantity = select.value;
    const selectedTime = timeSelect.value;
    const selectedPrice = select.options[select.selectedIndex].getAttribute('data-price');
    let message = `Фильм "${product.name}".`;

    message += ` Количество билетов: ${selectedQuantity}. Время сеанса ${selectedTime}. Общая сумма:${selectedPrice}₽.`;
    alert(message);
});
card.appendChild(button);

return card;
}

const catalog = document.getElementById('catalog');
products.forEach(product => {
catalog.appendChild(createProductCard(product));
});
</script>
</body>
</html>