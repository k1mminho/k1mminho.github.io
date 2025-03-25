---
layout: post
title:  "얼굴 랜드마크 감지 구현해보기 1일차"
date:   2025-03-25
desc: "Quick test on writing code snippets in a blog post"
keywords: "blog"
categories: [HTML]
tags: [googleAI]
icon: icon-html
---
  1. 헤어 추천 어플을 만들기 위해 구글 AI for Developers 를 통한
    얼굴 랜드마크 감지 기능을 알아보기

    <img src=''>

    - node js 기본 설정
    ```
    npm init 
    npm init -y
    npm install express 
    ```
    ```
    const express = require('express')
    const app = express()
    const port = 3000
    app.get('/', (req,res) =>{
        res.send('hello world')
    })

    app.listen(port, () =>{
        console.log(Example app listening on port 'http://localhost:${port}'`)
    })
    ```


    ```npm install @mediapipe/tasks-vision```
        입력하여 패키지 설치
    - 