!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hola Jade</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: pink;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
            position: relative;
        }
        h1 {
            color: white;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background-color: #ff69b4;
            color: white;
        }
        button:hover {
            background-color: #ff1493;
        }
        .flower {
            position: absolute;
            width: 50px;
            height: 50px;
            background-image: url('https://www.transparenttextures.com/patterns/floral.png');
            background-size: cover;
        }
        .flower1 {
            top: 20px;
            left: 20px;
        }
        .flower2 {
            top: 20px;
            right: 20px;
        }
        .flower3 {
            bottom: 20px;
            left: 20px;
        }
        .flower4 {
            bottom: 20px;
            right: 20px;
        }
        .back-button {
            position: absolute;
            top: 20px;
            left: 20px;
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background-color: #ff69b4;
            color: white;
        }
        .back-button:hover {
            background-color: #ff1493;
        }
    </style>
</head>
<body>
    <!-- Página 1 -->
    <div id="page1">
        <h1>Hola Jade, mi preciosa bella, te tengo una pregunta...</h1>
        <button onclick="nextPage()">Siguiente</button>
    </div>

    <!-- Página 2 -->
    <div id="page2" style="display: none;">
        <h1>¿Quieres ser mi Valentín este 14?</h1>
        <button onclick="yesPage()">Sí</button>
        <button onclick="noPage()">No</button>
    </div>

    <!-- Página 3 -->
    <div id="page3" style="display: none;">
        <h1>No te vas a arrepentir, te quiero ❤️</h1>
    </div>

    <!-- Página 4 -->
    <div id="page4" style="display: none;">
        <h1>Bueno, está bien, pero siempre recuerda que te quiero.</h1>
    </div>

    <!-- Flores decorativas -->
    <div class="flower flower1"></div>
    <div class="flower flower2"></div>
    <div class="flower flower3"></div>
    <div class="flower flower4"></div>

    <!-- Botón de regresar -->
    <button class="back-button" onclick="goBack()" style="display: none;">Regresar</button>

    <script>
        function nextPage() {
            document.getElementById('page1').style.display = 'none';
            document.getElementById('page2').style.display = 'block';
            document.querySelector('.back-button').style.display = 'block';
        }

        function yesPage() {
            document.getElementById('page2').style.display = 'none';
            document.getElementById('page3').style.display = 'block';
            document.querySelector('.back-button').style.display = 'block';
        }

        function noPage() {
            document.getElementById('page2').style.display = 'none';
            document.getElementById('page4').style.display = 'block';
            document.querySelector('.back-button').style.display = 'block';
        }

        function goBack() {
            const currentPage = document.querySelector('div[id^="page"]:not([style*="none"])');
            if (currentPage.id === 'page2') {
                document.getElementById('page1').style.display = 'block';
                document.getElementById('page2').style.display = 'none';
            } else if (currentPage.id === 'page3' || currentPage.id === 'page4') {
                document.getElementById('page2').style.display = 'block';
                document.getElementById(currentPage.id).style.display = 'none';
            }
            if (document.getElementById('page1').style.display === 'block') {
                document.querySelector('.back-button').style.display = 'none';
            }
        }
    </script>
</body>
</html>
