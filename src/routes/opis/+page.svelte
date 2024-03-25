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
        .product .description {
            display: none;
            margin-top: 10px;
            color: #ffffff;
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
        <h1>Описание</h1>
        <div class="catalog" id="catalog"></div>
    </div>

    <script>
      let films = [
    { title: "Лед 3", description: "Захватывающее продолжение серии о профессиональном фигуристе, который сталкивается с новыми вызовами и соперниками на пути к олимпийской славе.", image: "https://s3.afisha.ru/mediastorage/2a/33/d281002d901a4f7d84337489332a.jpg", showDescription: false },
    { title: "Огонь", description: "Эмоциональная драма, рассказывающая о жизни пожарных и их героических поступках в условиях сложных пожаров и несправедливости.", image: "https://s2.afisha.ru/mediastorage/d9/92/ce34ba18fb4d4a598babbc2992d9.jpg", showDescription: false },
    { title: "Адам и Ева", description: "Романтическая комедия о необычной паре, которая встречается в современном мире, но сталкивается с трудностями, проистекающими из своего непривычного происх", image: "https://s5.afisha.ru/mediastorage/db/7e/7cc9b0384a5d405f8cd0de397edb.jpg", showDescription: false },
    { title: "Текст", description: "Таинственный триллер о том, как группа людей пытается разгадать загадочные послания и секреты, скрытые в текстовых сообщениях, которые приводят их к неожиданным открытиям и опасностям", image: "https://sun9-38.userapi.com/impg/c855016/v855016017/17be73/gC_4lN7OqJg.jpg?size=520x0&quality=95&sign=eca48f1d9488c3138e1de0b23b5aa790", showDescription: false },
    { title: "Брат", description: "Эпическая драма о двух братьях, чьи жизни разделяются судьбой и различными идеалами в период турбулентного времени истории.", image: "https://kudamoscow.ru//uploads/220325124425310.jpg", showDescription: false },
    { title: "Вызов", description: "Напряженный триллер о группе друзей, которые принимают смертельный вызов, в результате чего они оказываются в смертельной игре, где ставки высоки и нет выхода.", image: "https://s1.afisha.ru/mediastorage/67/35/05325e5fca82487fa975ade33567.jpg", showDescription: false }
  ];
  function toggleDescription(index) {
        const descriptionElement = document.getElementById(`description-${index}`);
        const buttonElement = document.getElementById(`button-${index}`);
        const showDescription = descriptionElement.style.display == 'none';

        descriptionElement.style.display = showDescription ? 'block' : 'none';
        buttonElement.textContent = showDescription ? 'Скрыть описание' : 'Прочитать описание';
      }


const catalogDiv = document.getElementById('catalog');
      films.forEach((film, index) => {
        const productDiv = document.createElement('div');
        productDiv.classList.add('product');

        const img = document.createElement('img');
        img.src = film.image;
        productDiv.appendChild(img);

        const title = document.createElement('h2');
        title.textContent = film.title;
        productDiv.appendChild(title);

        const description = document.createElement('p');
        description.textContent = film.description;
        description.classList.add('description');
        description.id = `description-${index}`;
        productDiv.appendChild(description);

        const button = document.createElement('button');
        button.textContent = 'Прочитать описание';
        button.id = `button-${index}`;
        button.onclick = () => toggleDescription(index);
        productDiv.appendChild(button);

        catalogDiv.appendChild(productDiv);
      });
</script>
</body>
</html>

  
  
  