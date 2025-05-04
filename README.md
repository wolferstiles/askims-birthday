# askims-birthday
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Doğum Günü Davetiyesi</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            text-align: center;
            padding: 50px;
        }

        .container {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            display: inline-block;
        }

        h1 {
            color: #e91e63;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        button:hover {
            background-color: #45a049;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Doğum Günü Davetiyesi</h1>
        <p>Sevgilim, doğum günüme gelmeni çok istiyorum! Bu anketi doldurur musun?</p>
        <form id="surveyForm">
            <h3>Cumartesi günü saat 6'da buluşmak ister misin?</h3>
            <label><input type="radio" name="time" value="Evet"> Evet</label><br>
            <label><input type="radio" name="time" value="Hayır"> Hayır</label><br><br>
            <button type="submit">Cevapla</button>
        </form>
        <div id="incorrectAnswer" class="hidden">
            <h2>Yanlış cevap! Doğru cevabı ver!</h2>
            <button onclick="reloadPage()">Tekrar Dene</button>
        </div>
        <div id="correctAnswer" class="hidden">
            <h2>Tebrikler! Doğum gününe geliyorsun!</h2>
            <button onclick="continueToNext()">Devam Et</button>
        </div>
    </div>

    <script>
        document.getElementById("surveyForm").addEventListener("submit", function(e) {
            e.preventDefault();
            const selectedAnswer = document.querySelector('input[name="time"]:checked');
            
            if (selectedAnswer && selectedAnswer.value === "Evet") {
                document.getElementById("correctAnswer").classList.remove("hidden");
                document.getElementById("surveyForm").classList.add("hidden");
            } else {
                document.getElementById("incorrectAnswer").classList.remove("hidden");
                document.getElementById("surveyForm").classList.add("hidden");
            }
        });

        function reloadPage() {
            location.reload();
        }

        function continueToNext() {
            window.location.href = "https://www.example.com/next-page"; // Buraya devam etmek istediğin sayfa linkini ekleyebilirsin.
        }
    </script>
</body>
</html>
