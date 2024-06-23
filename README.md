- 👋 Hi, I’m @fathy31
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
fathy31/fathy31 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---># backend - Django
from django.contrib.auth.models import User
from django.contrib.auth import authenticate, login

def register_user(request):
    if request.method == 'POST':
        username = request.POST['username']
        password = request.POST['password']
        user = User.objects.create_user(username=username, password=password)
        user.save()
        login(request, user)
        return redirect('dashboard')
        <!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Investment Platform</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="root"></div>
    <script src="app.js"></script>
</body>
</html>
/* styles.css */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}
// app.js - React.js example
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
# app.py - Flask example
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/register', methods=['POST'])
def register_user():
    data = request.get_json()
    username = data['username']
    password = data['password']
    # تخزين المستخدم في قاعدة البيانات
    return jsonify({'message': 'User registered successfully'})

if __name__ == '__main__':
    app.run(debug=True)
    # app.py - Flask API example
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/investments', methods=['GET'])
def get_investments():
    # جلب الاستثمارات من قاعدة البيانات
    investments = [{'id': 1, 'name': 'Investment 1', 'amount': 1000}]
    return jsonify(investments)

if __name__ == '__main__':
    app.run(debug=True)
    // Fetch API example
fetch('http://localhost:5000/investments')
    .then(response => response.json())
    .then(data => console.log(data));
    # استخدام Flask-JWT-Extended للمصادقة
from flask_jwt_extended import JWTManager, create_access_token

app.config['JWT_SECRET_KEY'] = 'your_secret_key'
jwt = JWTManager(app)

@app.route('/login', methods=['POST'])
def login():
    username = request.json.get('username', None)
    password = request.json.get('password', None)
    if username != 'test' or password != 'test':
        return jsonify({"msg": "Bad username or password"}), 401
    access_token = create_access_token(identity=username)
    return jsonify(access_token=access_token)
    
