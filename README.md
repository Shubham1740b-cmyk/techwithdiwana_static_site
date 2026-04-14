🌐 shoesShowcase

[![License](https://img.shields.io/github/license/Shubham1740b-cmyk/shoesShowcasing)](./LICENSE)  
[![Open in GitHub](https://img.shields.io/badge/GitHub-Repo-black?logo=github)](https://github.com/Shubham1740b-cmyk/shoesShowcasing)  


---
## 🔭 About
My repository contains a Beginner-friendly shoesShowcasing website Just For Hosting Purpose ON AWS Platform.
Built with **HTML / CSS / JS** and designed For Hosting It with **NGINX** on Ubuntu / EC2 ( t3.Micro ) With The Help Of Windows Subsystem for Linux (WSL) . WSL is a Microsoft feature that lets you run a native Linux environment directly on Windows 10/11 without a traditional virtual machine or dual-boot setup. 
It allows Developers to use Linux command-line tools, utilities, and applications (e.g., Ubuntu, Debian, Docker) alongside Windows applications with high performance .

---
## 🏗 Architecture

Browser → **NGINX** → Serve website source files (`index.html`, `css/`, `js/`, `images/`)

---
🚀 My Process Of Deploy My Created shoesShowcasinn E- Commerce Site On AWS (AMAZON WEB SERVICES) (Ubuntu / EC2 / WSL)

---
1. Connect to My Created AWS Instance server :

using bash ->
 
ssh -i "Sh-web-server.pem" ubuntu@ec2-16-170-255-47.eu-north-1.compute.amazonaws.com

<img width="1238" height="732" alt="image" src="https://github.com/user-attachments/assets/3194cd7e-fbff-4276-bb4b-66dc5e8d8057" />



---

2. Install Nginx & Git:
Using bash ->

sudo apt update
sudo apt install -y nginx git

<img width="1115" height="1004" alt="image" src="https://github.com/user-attachments/assets/58e082d6-6a79-4497-9a43-7f6097bc893c" />

<img width="1234" height="1010" alt="image" src="https://github.com/user-attachments/assets/8e8e4239-1470-4590-bf81-7ab4b609edf5" />




---
3. Create webroot & clone repo:


Using bash ->

sudo mkdir -p /var/www/shoesShowcasing
sudo git clone https://github.com/Shubham1740b-cmyk/shoesShowcasing.git /var/www/shoesShowcasing

<img width="1016" height="176" alt="image" src="https://github.com/user-attachments/assets/331ed597-975a-4459-ae08-ba7b9a479074" />



---

4. Set permissions:


Using bash ->

sudo chown -R www-data:www-data /var/www/shoesShowcasing
sudo find /var/www/shoesShowcasing -type d -exec chmod 755 {} \;
sudo find /var/www/shoesShowcasing -type f -exec chmod 644 {} \;


<img width="879" height="99" alt="image" src="https://github.com/user-attachments/assets/945c0ed0-08a5-4e33-a4d0-6387b92dd3bd" />


---

5. Create Nginx site config `/etc/nginx/sites-available/shoesShowcasing`:

<img width="926" height="78" alt="image" src="https://github.com/user-attachments/assets/77f456ee-4d18-48dd-8251-117e05f0bbbf" />
<img width="1375" height="863" alt="image" src="https://github.com/user-attachments/assets/2defed20-e0ce-487d-9411-4c3de123c6a0" />
<img width="1376" height="140" alt="image" src="https://github.com/user-attachments/assets/bac4bd62-19ad-4da7-b6f2-4658f5cb0004" />





---
My nginx Config Code 👇

---

server {
  listen 80;
  server_name 16.170.255.47;

  root /var/www/shoesShowcasing;
  index index.html;

  location / {
    try_files $uri $uri/ =404;
  }

  location ~* \\.(png|jpg|jpeg|svg|css|js)$ {
    expires 7d;
    add_header Cache-Control "public";
  }
}




---
6. Enable site & reload Nginx:

Using bash ->

sudo ln -sf /etc/nginx/sites-available/shoesShowcasing /etc/nginx/sites-enabled/shoesShowcasing
sudo rm -f /etc/nginx/sites-enabled/default
sudo nginx -t
sudo systemctl reload nginx



---
7. Finally, Checking My Created ShoesShowcasing Site and  Is  Succesfully Exposed Through Nginx On Hosting Platform ( AWS THAT I HAVE TO SELECTED FOR MY E-Commerce ShoesShowcasing Site For Deploying It On  Amazon Web Services Cloud Platform ) 


<img width="1024" height="254" alt="image" src="https://github.com/user-attachments/assets/d4c580c5-bc60-4c1c-a313-4be5a1e8f625" />




<img width="1918" height="1033" alt="image" src="https://github.com/user-attachments/assets/80f3d27b-aa90-4413-bcd5-441eeb506863" />





 Output Of Entering < MY Created EC2 PUBLIC IP >  On Web Browser 👇
 
<img width="1917" height="1079" alt="image" src="https://github.com/user-attachments/assets/e8b45851-b44d-4b97-b5ac-14df997fb62f" />








---
📂 My Project structure
Shubham Kumar /  shoesShowcasing Site /

```
shoesShowcasing Files /
├── Images/
├── style.css/
├── script.js/
├── index.html
└── README.md
```

---
🛡 License

This project is MIT licensed — see [LICENSE](./LICENSE).


👨‍🏫 Author & Contact
SHUBHAM KUMAR 

- [Email](mailto:shubhamx0777@gmail.com)
- [Phone](+91 8053986469)

  ✅ LICENSE File (MIT)

Create a file called `LICENSE` in the root of repo with this content:

text


MIT License

Copyright (c) 2026 Shubham Kumar  

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
