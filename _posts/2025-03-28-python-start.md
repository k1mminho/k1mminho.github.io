---
layout: post
title: "파이썬 시작해보기"
date: 2025-03-28
desc: "3 Steps (2 minutes) to Setup Your Personal Website with Jalpc"
keywords: ""
categories: [HTML]
tags: []
icon: icon-html
---

### VSCode에서 Python 개발 시작하기 (한 번만 설정하면 됨)

1. Python 확장 설치
   VSCode 열고 Extensions 탭 → Python 검색 → 설치

2. Python 인터프리터 선택
   Ctrl + Shift + P → "Python: Select Interpreter"

설치된 Python 경로 선택 (또는 가상환경)

3. 새 파일 만들고 .py 확장자로 저장

```
print("Hello, face!")
```

4. 실행
   파일 열고 Run ▶️ 클릭 or 터미널에서 python 파일명.py

### Mediapipe 프로젝트 개발 흐름

1. VSCode로 프로젝트 폴더 열기

2. main.py에서 Mediapipe로 얼굴 인식 코드 작성

3. requirements.txt 만들어서 패키지 관리

4. FastAPI로 API 서버 구성

5. uvicorn main:app --reload로 실행

6. Postman or RN 앱으로 API 테스트

### pip로 FastAPI 설치하기

1. 터미널에 pip install fastapi uvicorn python-multipart pillow 입력

2. main.py 파일 만들고

```
from fastapi import FastAPI, UploadFile, File
from fastapi.responses import JSONResponse
from PIL import Image
import io

app = FastAPI()

@app.get("/")
def root():
    return {"message": "얼굴 분석 서버 작동 중!"}

@app.post("/analyze_face")
async def analyze_face(file: UploadFile = File(...)):
    image_bytes = await file.read()
    image = Image.open(io.BytesIO(image_bytes))

    # (얼굴형 분석은 나중에 추가!)
    result = {
        "face_shape": "oval",
        "recommended_hairstyle": "long_wave"
    }

    return JSONResponse(content=result)


```
2. FastAPI 실행
```
uvicorn main:app --reload

```
터미널에 입력하면 http://127.0.0.1:8000 
링크 생성 후 접속하면 실행중인 것 확인
