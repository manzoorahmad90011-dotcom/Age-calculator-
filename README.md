# Age-calculator-
"Free Online Age Calculator. Calculate your exact age in years, months, and days in seconds. Simple, fast, and accurate tool. No sign-up required."  Keywords: Free, Online, Age Calculator, Exact Age, Years, Months, Days
<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mera Age Calculator</title>
    <style>
        /* YEH NASA KA HISSA HAI (CSS) - Yeh website ko sundar banata hai */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f0f8ff; /* Halka blue background */
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto; /* Center mein laata hai */
            background: white; /* White box */
            padding: 30px;
            border-radius: 10px; /* Box ke corners round karta hai */
            box-shadow: 0 0 10px rgba(0,0,0,0.1); /* Box ko shadow deta hai */
        }
        h1 {
            color: #2c3e50; /* Heading ka color */
        }
        input[type="date"] {
            padding: 10px;
            font-size: 16px;
            margin: 10px;
            border: 2px solid #3498db; /* Input box ki border */
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #3498db; /* Button ka blue color */
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer; /* Hand dikhata hai cursor ko */
        }
        button:hover {
            background-color: #2980b9; /* Button par hover karne par color badalta hai */
        }
        #result {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
            color: #e74c3c; /* Result ka red color */
        }
    </style>
</head>
<body>
    <!-- YEH NASA KA HISSA HAI (HTML) - Yeh website ka structure hai -->
    <div class="container">
        <h1>आयु कैलकुलेटर</h1>
        <p>अपनी जन्म तिथि डालें और बटन दबाएं</p>

        <!-- Date choose karne ka input -->
        <input type="date" id="birthdate">
        <br>
        <!-- Calculation shuru karne ka button -->
        <button onclick="calculateAge()">उम्र Calculate करें</button>

        <!-- Result yahan ayega -->
        <div id="result"></div>
    </div>

    <script>
        // YEH NASA KA HISSA HAI (JavaScript) - Yeh calculation karega
        function calculateAge() {
            // User ki entered date ko uthayo
            let birthdate = new Date(document.getElementById('birthdate').value);
            let today = new Date(); // Aaj ki date

            // Check karo agar user ne date enter ki hai
            if (isNaN(birthdate)) {
                alert("कृपया सही तारीख डालें!");
                return;
            }

            // Basic age calculation
            let age = today.getFullYear() - birthdate.getFullYear();
            let monthDiff = today.getMonth() - birthdate.getMonth();

            // Agar abhi tak birthday nahi aaya iss saal, toh 1 saal kam karo
            if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birthdate.getDate())) {
                age--;
            }

            // Result ko screen par dikhao
            document.getElementById('result').innerHTML = "आपकी उम्र है: <span style='color: #e74c3c;'>" + age + " साल</span>";
        }
    </script>
</body>
</html>
