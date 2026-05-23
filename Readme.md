# INHACK 인코그니토 프로젝트/ AINHA-정시훈, 목진서, 김준서, 구주원
## 본 프로젝트는 AI캐릭터 챗봇 취약점 분석 프로젝트를 위한 AI기반 캐릭터 챗봇 시뮬레이터이다.


### 아래는 도커를 활용한 시뮬레이터 실행 가이드 

🔄 수정 후 반영 절차 (무조건 이 순서대로!)
코드를 수정했으니 다시 도커의 순환 고리를 돌려야 합니다. 이 과정을 생략하면 에러는 사라지지 않습니다.

# 기존 컨테이너 중지 및 삭제
docker rm -f my-safe-ai

# 수정된 app.py를 포함하여 이미지 빌드
docker build -t incognito-ai .

# DB 볼륨을 연결하여 실행 (데이터 보존)
docker run -d -p 8501:8501 --env-file .env -v "${PWD}:/app" --name my-safe-ai incognito-ai

Bash
./ngrok http 8501 (다른 터미널에서)
