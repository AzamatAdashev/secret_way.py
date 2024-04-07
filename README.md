from flask import Flask
import random
app = Flask(__name__)
facts_list = ['Большинство людей, страдающих технологической зависимостью, испытывают сильный стресс, когда они находятся вне зоны покрытия сети или не могут использовать свои устройства.', 'Согласно исследованию, проведенному в 2018 году, более 50% людей в возрасте от 18 до 34 лет считают себя зависимыми от своих смартфонов.', 'Изучение технологической зависимости является одной из наиболее актуальных областей научных исследований в настоящее время.']
@app.route("/")
def hello_world():
    return f'<h1>http://127.0.0.1:5000/random_fact</h1>'


@app.route("/random_fact")
def facts():
    return f'<p>{random.choice(facts_list)}</p>'
@app.route('/password')
def password():
    parts = "+-/*!&$#?=@<>"
password = ""
pass_length = int(input("Enter pass length: "))

for i in range(pass_length):
    password += random.choice(parts)

print(password)
app.run(debug=True)    
