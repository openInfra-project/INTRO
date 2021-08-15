# 🔍 자동 감독 서비스, **AutoWatch**

---

자사 서비스인 Auto_Watch는 화상공유 플랫폼을 이용한 강의 및 시험에서 야기되는 집중력, 참여도 저하 및 부정행위 등의 문제를 해결하는 목적으로 제공되는 **자동 감독 서비스**입니다.

  
![Untitled (1)](https://user-images.githubusercontent.com/48875061/129481137-89a0d230-487c-4abe-b799-ace285464958.png)

## DEMO

---

개발 vlog 사이트 - [https://www.youtube.com/watch?v=uV2hKfhYfDs](https://www.youtube.com/watch?v=uV2hKfhYfDs)

데모 사이트 - https://118.67.131.138:30000/  
(*보다 원활한 접속을 위해 https://118.67.131.138:30010/ 에 접속, thisisunsafe 입력 후 입장 바랍니다.*)

개발 문서 사이트 - [https://spiced-flax-f90.notion.site/36e9c573c45c488bb933613313b14894](https://www.notion.so/36e9c573c45c488bb933613313b14894)
## 🤷‍ Service Needs

---

##### 코로나 19 확산으로 온라인을 이용한 비대면이 일반화된 언택트 시대를 맞이했습니다.

##### 언택트 교육 문화 → 캠스터디 등장/ 온라인 수업 등장 → 집중력 저하

![Untitled (2)](https://user-images.githubusercontent.com/48875061/129481173-dc50b323-5729-4c6f-9634-bef9f108bee0.png)
![Untitled (3)](https://user-images.githubusercontent.com/48875061/129481174-b6ab2e6e-ce43-4951-b7e9-625092cfc14d.png)  


  
### 언택트 시험 문화 → 온라인 시험 등장 → 부정행위      
  

![Untitled (4)](https://user-images.githubusercontent.com/48875061/129481194-7315384b-7803-4962-a562-4de6f63b869f.png)


## 🔑 Core Service Logic

---

화상 공유를 통한

① 시험 감독

② 온라인 수업 및 스터디 감독

부정행위 및 집중력, 참여도 저하 등의 문제를 해결하기 위한 **자동 감독 서비스**
![Untitled (5)](https://user-images.githubusercontent.com/48875061/129481207-1dac459e-ed90-45dd-84ab-2669c3fbdb47.png)
![Untitled (6)](https://user-images.githubusercontent.com/48875061/129481208-6abbd940-7d8c-48bd-962b-0686dd074a93.png)



## 🔥Tech

---

1. **Eye-Tracking**
2. **자리 이탈 확인**
3. **특정 App 차단**
4. **본인 확인**

## 💻 Development Stack

---

![Untitled (7)](https://user-images.githubusercontent.com/48875061/129481217-b0934a69-9bee-465b-bcf8-90c8cc30f60a.png)

## 👨🏻‍💻Client

---

1. **Realtime Client ::** WebRTC가 실행되는 React 환경   
           Eye-tracking 눈추적 인식 기능  `Node.js`    

                           
                              

1. **Android Client** :: AndroidStudio 앱 잠금 기능, 사람 인식 기능

## 👩🏻‍💻Server

---

서버 부하분산을 위해 MSA 도입, 다음과 같은 서버들로 구성

1. **Realtime Server** :: WebRTC를 위한 시그널링 서버 `Node.js` 
2. **Management Server** :: 회원 정보 & room 정보 관리 서버 `Django`  
                            회원가입, 로그인, 토큰 등의 멤버 정보 관리   
                            & room 입장, room의 각 멤버의 상태 트래킹하는 서버

## 🛠️ Service Architecture

---

![image](https://user-images.githubusercontent.com/48875061/129487780-58fb3e39-f6f4-4955-9b3a-1d6a029b4e7b.png)


## 🛠️ MSA Architecture

---

![Untitled (9)](https://user-images.githubusercontent.com/48875061/129481256-bdb71cd1-3726-40b5-b52c-370cc7388c05.png)


## 🌐API

---

1. WebRTC서버:: 실시간 영상 전송 서버 (socket)
2. WebRTC — Node Adapting Server

    기본 url :: [https://118.67.131.138:30010](https://118.67.131.138:30010/)

    `POST` / 방 입장 시 socket connection 설정 위한 offer 마다의 토큰 제공

    `DEL` / 방 퇴장 시 socket connection 해제

    `POST` / Join room id 중복검사 , 방(UserData) 입장

    `POST`/ offer 요청한 연결, 나를 제외한 전체 사용자에게 연결 요청

    `POST` / getoffer 요청 받은 연결, 나에게 들어온 연결 요청

    `POST` /message 실시간 채팅을 위한 연결

    `POST` / gazealert 실시간 부정행위 알람을 위한 연결

3. ManageServer

    기본 url :: [https://118.67.131.138:30000](https://118.67.131.138:30010/)

    `POST` /  → 사용자 아이디 중복 체크 및 비밀번호 재입력 확인 요청

    `POST` / login → 사용자 아이디 및 비밀번호 요청

    `GET` / logout → 로그아웃

    `POST` / makeroom → STUDY/EXAM 모드에 따라 방생성

    `POST` / makeroom/success → 방 생성 성공 후 방 정보 나열

    `POST` / enteroom/exam1 → EXAM 모드 앱 차단 여부 요청

    `POST` / enteroom/exam2 → EXAM 모드 얼굴 인식 확인 요청

    `POST` / enteroom/exam3 → EXAM 모드 WebRTC 입장 가능 여부 요청 

    `POST` / enteroom/study1 → STUDY 모드 앱 차단 여부 요청

    `POST` / enteroom/study2 → STUDY 모드 WebRTC 입장 가능 여부 요청

    `GET` / roomout/<int:time>/<str:mode> → mode가 STUDY 일때 해당 사용자의 Analytics에 time이 저장됨

    `POST` / roomout/<int:time>/<str:mode> → App 접근 차단을 해제 하였는지 요청 & mode가 STUDY 일때 저장돤 time, app, person 변수를 바탕으로 level, rate를 측정하고 Analytics 모델에 저장 

    `GET` / roomout/study → session에서 사용자 정보를 가져와 Analytics 모델의 가장 마지막 row를 DB에서 가져와서 집중도 그래프를 그림 

    `POST` / roomout/exam → 시험이 성공적으로 종료 됐는지 요청

    `GET` / list/room → Room DB에서 사용자 이름으로 만들어진 Room을           QuerySet으로 반환후 list 나타냄

    `GET` / list/analytics → Analytics DB에서 사용자 이름으로 만들어진 Analytics를 QuerySet으로 반환후 list 나타냄

    `POST`/ list/analytics/<int:pk> → Analytics List에서 선택한 QuerySet 객체의 

    Primary Key 값과 같은 row를 DB에서 가져와 집중도 그래프를 그려줌 

## 🐾Role

---

@김혜원 

- *NCP 서버 구축*
- *kubernetes 사용한 HTTPS 배포*
- *GazeCloudAPI를 통한 eye-tracking 눈추적 & 방이탈 부정행위 알림*
- *luxand API를 이용한 Exam방 입장 시 본인확인*
- *Exam 모드 응시자 명단 엑셀파일 처리*

@김준영 

- Realtime Client *Layout 구축*
- *WebSocket token을 활용한 peer connection*
- *부정행위 실시간 알람기능 구축*
- *백엔드 실시간 통신 구축*
- *Redux 활용한 SettingData(Gaze,마이크 ,비디오 on/off) 및 UserData 상태 관리*
- *채팅 및 화상통신 기반 [socket.io](http://socket.io) 통신*
- *WebSocket token을 활용한 peer connection*

@황한식 

- *Manage-server 전체 UI/UX*
- *django 풀 스택*

@김유림 

- *전체 Layout 구축*
- *SQLite 로그인한 사용자 저장*
- *study, exam모드 별로 방 생성 (exam모드 생성 시 파일[회원명단] 업로드 필수)*
- *retrofit 사용하여 서버와 통신*
- *exam 방 입장시 카메라 촬영 및 이미지 통신*
- *안드로이드 NDK + OpenCV를 활용한 사람 인지 기능*
- *특정 앱 차단 구현*


### License
```
MIT License

Copyright (해몽유식) [2021-08-15] [HyeWon Kim, JunYoung Kim, YuLim Kim, HanSik Hwang]

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
```
