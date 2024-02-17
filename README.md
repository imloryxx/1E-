<!DOCTYPE html>
<html>
<head>
    <title>Login e Registrazione</title>
</head>
<body>
    <h1>Login</h1>
    <form id="loginForm">
        <label for="username">Nome utente:</label>
        <input type="text" id="username" name="username">
        <label for="password">Password:</label>
        <input type="password" id="password" name="password">
        <input type="submit" value="Login">
    </form>

    <h1>Registrazione</h1>
    <form id="registrationForm">
        <label for="newUsername">Nome utente:</label>
        <input type="text" id="newUsername" name="newUsername">
        <label for="newPassword">Password:</label>
        <input type="password" id="newPassword" name="newPassword">
        <input type="submit" value="Registrati">
    </form>

    <script>
    document.getElementById('loginForm').addEventListener('submit', function(event) {
        event.preventDefault();
        var username = document.getElementById('username').value;
        var password = document.getElementById('password').value;
        // Qui puoi aggiungere il codice per inviare il nome utente e la password al tuo server
        console.log(username, password);
    });

    document.getElementById('registrationForm').addEventListener('submit', function(event) {
        event.preventDefault();
        var newUsername = document.getElementById('newUsername').value;
        var newPassword = document.getElementById('newPassword').value;
        // Qui puoi aggiungere il codice per inviare il nuovo nome utente e la password al tuo server
        console.log(newUsername, newPassword);
    });
    </script>
</body>
</html>



<!DOCTYPE html>
<html>
<head>
    <title>Lamentele Anonime</title>
    <style>
        body {
            font-family: 'Times New Roman', serif; /* Cambia qui per usare un font diverso */
            margin: 0;
            padding: 0;
            background: url('https://images.unsplash.com/photo-1487621167305-5d248087c724?q=80&w=3432&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D') no-repeat center center fixed; 
            -webkit-background-size: cover;
            -moz-background-size: cover;
            -o-background-size: cover;
            background-size: cover;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #fff; /* testo bianco */
        }
        input, textarea {
            width: 100%;
            padding: 10px;
            box-sizing: border-box;
            border-radius: 5px;
            border: 1px solid #ddd;
        }
        button {
            background-color: #000; /* colore legno */
            color: #fff;
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            display: block;
            margin-top: 20px;
        }
        .complaint {
            background-color: #808080; /* colore grigio */
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0px 0px 10px rgba(0,0,0,0.1);
            margin-bottom: 20px;
            color: #fff; /* testo bianco */
        }
        .complaint h3, .complaint p {
            margin: 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 style="text-align: center; margin-top: 50px; color: #fff;">Lamentele Anonime</h1> <!-- titolo bianco -->
        <form id="complaintForm">
            <div class="form-group">
                <label for="professorName">Nome del Professore:</label>
                <input type="text" id="professorName" name="professorName">
            </div>
            <div class="form-group">
                <label for="complaint">Inserisci la tua lamentela qui:</label>
                <textarea id="complaint" name="complaint"></textarea>
            </div>
            <button type="submit">Invia Lamentela</button>
        </form>
        <div id="complaints"></div>
    </div>

    <script>
    document.getElementById('complaintForm').addEventListener('submit', function(event) {
        event.preventDefault();
        var professorName = document.getElementById('professorName').value;
        var complaint = document.getElementById('complaint').value;
        var complaintsDiv = document.getElementById('complaints');
        var newComplaintDiv = document.createElement('div');
        newComplaintDiv.className = 'complaint';
        newComplaintDiv.innerHTML = "<h3>" + professorName + "</h3><p>" + complaint + "</p>";
        complaintsDiv.appendChild(newComplaintDiv);
        document.getElementById('professorName').value = '';
        document.getElementById('complaint').value = '';
    });
    </script>
</body>
</html>
