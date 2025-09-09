# EC2 + Docker + Nginx 실습 (Day1~Day2)

AWS EC2 환경에서 Docker를 활용해 Nginx 웹 서버를 실행하고,
사용자 정의 HTML을 배포하는 실습 프로젝트입니다.

## 📌 프로젝트 개요

- AWS EC2 인스턴스 생성 및 SSH 접속
- Docker 설치 및 Nginx 컨테이너 실행
- 보안 그룹에서 80 포트 개방
- index.html 커스텀 페이지 배포

---

## 🏗️ 디렉토리 구조

```bash
ec2-docker-nginx-tutorial/
├── app.py
├── Dockerfile
├── index.html
├── README.md
└── images/

⚡ 실행 방법
1. EC2 인스턴스 접속
ssh -i my-key.pem ubuntu@<EC2_PUBLIC_IP>

2. Nginx 실행
sudo docker run -d -p 80:80 nginx

3. HTML 커스터마이징
echo "<h1>Hello from EC2 + Docker + Nginx!</h1>" > index.html

sudo docker run -d -p 80:80 \
  -v $(pwd)/index.html:/usr/share/nginx/html/index.html \
  nginx

4. 브라우저 확인

접속 주소: http://<EC2_PUBLIC_IP>

📷 실행 화면
EC2 인스턴스 생성

<img width="1313" height="393" alt="image" src="https://github.com/user-attachments/assets/3289d72d-3683-4c4b-8bff-c6d6caeac5e3" />


Nginx 페이지 접속 성공

<img width="655" height="352" alt="image" src="https://github.com/user-attachments/assets/73f0a957-f226-422b-ab4d-2914e15ce033" />


커스텀 HTML 적용

<img width="655" height="352" alt="image" src="https://github.com/user-attachments/assets/3cc0cc9c-0eb7-44ec-bae5-cce300afc11b" />

<img width="742" height="190" alt="image" src="https://github.com/user-attachments/assets/b8f74bd9-82ad-4379-96c7-0a0be692d108" />


```
