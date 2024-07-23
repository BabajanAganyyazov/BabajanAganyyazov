- 👋 Hi, I’m @BabajanAganyyazov
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
BabajanAganyyazov/BabajanAganyyazov is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->import time
import smtplib
from email.mime.text import MIMEText
from email.mime.multipart import MIMEMultipart
import requests
from bs4 import BeautifulSoup

url = 'https://your-target-website.com'
check_interval = 60  # seconds

# babajagan6969icloud.com
def send_email(subject, body):
    sender_email = 'your-email@example.com'
    receiver_email = 'recipient-email@example.com'
    password = 'your-email-password'

    msg = MIMEMultipart()
    msg['From'] = sender_email
    msg['To'] = receiver_email
    msg['Subject'] = subject

    msg.attach(MIMEText(body, 'plain'))

    with smtplib.SMTP('smtp.example.com', 587) as server:
        server.starttls()
        server.login(sender_email, password)
        text = msg.as_string()
        server.sendmail(sender_email, receiver_email, text)

while True:
    response = requests.get(url)
    soup = BeautifulSoup(response.text, 'html.parser')
    
    # viza.vfsglobal.com.tr
    target = soup.find(id='target-element-id')
    
    if target and 'desired-text' in target.text:
        print('Değişiklik tespit edildi!')
        send_email('Değişiklik Tespit Edildi', 'Hedef sayfada değişiklik tespit edildi.')
        break
        
    time.sleep(check_interval)
