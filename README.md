# π μλ κ°λ μλΉμ€, **AutoWatch**

---

μμ¬ μλΉμ€μΈ Auto_Watchλ νμκ³΅μ  νλ«νΌμ μ΄μ©ν κ°μ λ° μνμμ μΌκΈ°λλ μ§μ€λ ₯, μ°Έμ¬λ μ ν λ° λΆμ νμ λ±μ λ¬Έμ λ₯Ό ν΄κ²°νλ λͺ©μ μΌλ‘ μ κ³΅λλ **μλ κ°λ μλΉμ€**μλλ€.

  
![Untitled (1)](https://user-images.githubusercontent.com/48875061/129481137-89a0d230-487c-4abe-b799-ace285464958.png)

## DEMO

---

κ°λ° vlog μ¬μ΄νΈ - [https://www.youtube.com/watch?v=uV2hKfhYfDs](https://www.youtube.com/watch?v=uV2hKfhYfDs)

λ°λͺ¨ μ¬μ΄νΈ - https://118.67.131.138:30000/  
(*λ³΄λ€ μνν μ μμ μν΄ https://118.67.131.138:30010/ μ μ μ, thisisunsafe μλ ₯ ν μμ₯ λ°λλλ€.*)

κ°λ° λ¬Έμ μ¬μ΄νΈ - [https://spiced-flax-f90.notion.site/36e9c573c45c488bb933613313b14894](https://www.notion.so/36e9c573c45c488bb933613313b14894)
## π€·β Service Needs

---

##### μ½λ‘λ 19 νμ°μΌλ‘ μ¨λΌμΈμ μ΄μ©ν λΉλλ©΄μ΄ μΌλ°νλ μΈννΈ μλλ₯Ό λ§μ΄νμ΅λλ€.

##### μΈννΈ κ΅μ‘ λ¬Έν β μΊ μ€ν°λ λ±μ₯/ μ¨λΌμΈ μμ λ±μ₯ β μ§μ€λ ₯ μ ν

![Untitled (2)](https://user-images.githubusercontent.com/48875061/129481173-dc50b323-5729-4c6f-9634-bef9f108bee0.png)
![Untitled (3)](https://user-images.githubusercontent.com/48875061/129481174-b6ab2e6e-ce43-4951-b7e9-625092cfc14d.png)  


  
### μΈννΈ μν λ¬Έν β μ¨λΌμΈ μν λ±μ₯ β λΆμ νμ      
  

![Untitled (4)](https://user-images.githubusercontent.com/48875061/129481194-7315384b-7803-4962-a562-4de6f63b869f.png)


## π Core Service Logic

---

νμ κ³΅μ λ₯Ό ν΅ν

β  μν κ°λ

β‘ μ¨λΌμΈ μμ λ° μ€ν°λ κ°λ

λΆμ νμ λ° μ§μ€λ ₯, μ°Έμ¬λ μ ν λ±μ λ¬Έμ λ₯Ό ν΄κ²°νκΈ° μν **μλ κ°λ μλΉμ€**
![Untitled (5)](https://user-images.githubusercontent.com/48875061/129481207-1dac459e-ed90-45dd-84ab-2669c3fbdb47.png)
![Untitled (6)](https://user-images.githubusercontent.com/48875061/129481208-6abbd940-7d8c-48bd-962b-0686dd074a93.png)



## π₯Tech

---

1. **Eye-Tracking**
2. **μλ¦¬ μ΄ν νμΈ**
3. **νΉμ  App μ°¨λ¨**
4. **λ³ΈμΈ νμΈ**

## π» Development Stack

---

![Untitled (7)](https://user-images.githubusercontent.com/48875061/129481217-b0934a69-9bee-465b-bcf8-90c8cc30f60a.png)

## π¨π»βπ»Client

---

1. **Realtime Client ::** WebRTCκ° μ€νλλ React νκ²½   
           Eye-tracking λμΆμ  μΈμ κΈ°λ₯  `Node.js`    

                           
                              

1. **Android Client** :: AndroidStudio μ± μ κΈ κΈ°λ₯, μ¬λ μΈμ κΈ°λ₯

## π©π»βπ»Server

---

μλ² λΆνλΆμ°μ μν΄ MSA λμ, λ€μκ³Ό κ°μ μλ²λ€λ‘ κ΅¬μ±

1. **Realtime Server** :: WebRTCλ₯Ό μν μκ·Έλλ§ μλ²Β `Node.js` 
2. **Management Server**Β :: νμ μ λ³΄ & room μ λ³΄ κ΄λ¦¬ μλ²Β `Django`  
                            νμκ°μ, λ‘κ·ΈμΈ, ν ν° λ±μ λ©€λ² μ λ³΄ κ΄λ¦¬   
                            & room μμ₯, roomμ κ° λ©€λ²μ μν νΈλνΉνλ μλ²

## π οΈ Service Architecture

---

![image](https://user-images.githubusercontent.com/48875061/129487780-58fb3e39-f6f4-4955-9b3a-1d6a029b4e7b.png)


## π οΈ MSA Architecture

---

![Untitled (9)](https://user-images.githubusercontent.com/48875061/129481256-bdb71cd1-3726-40b5-b52c-370cc7388c05.png)


## πAPI

---

1. WebRTCμλ²:: μ€μκ° μμ μ μ‘ μλ² (socket)
2. WebRTC β Node Adapting Server

    κΈ°λ³Έ url :: [https://118.67.131.138:30010](https://118.67.131.138:30010/)

    `POST` / λ°© μμ₯ μ socket connection μ€μ  μν offer λ§λ€μ ν ν° μ κ³΅

    `DEL` / λ°© ν΄μ₯ μ socket connection ν΄μ 

    `POST` / Join room id μ€λ³΅κ²μ¬ , λ°©(UserData) μμ₯

    `POST`/ offer μμ²­ν μ°κ²°, λλ₯Ό μ μΈν μ μ²΄ μ¬μ©μμκ² μ°κ²° μμ²­

    `POST` / getoffer μμ²­ λ°μ μ°κ²°, λμκ² λ€μ΄μ¨ μ°κ²° μμ²­

    `POST` /message μ€μκ° μ±νμ μν μ°κ²°

    `POST` / gazealert μ€μκ° λΆμ νμ μλμ μν μ°κ²°

3. ManageServer

    κΈ°λ³Έ url :: [https://118.67.131.138:30000](https://118.67.131.138:30010/)

    `POST` /  β μ¬μ©μ μμ΄λ μ€λ³΅ μ²΄ν¬ λ° λΉλ°λ²νΈ μ¬μλ ₯ νμΈ μμ²­

    `POST` / login β μ¬μ©μ μμ΄λ λ° λΉλ°λ²νΈ μμ²­

    `GET` / logout β λ‘κ·Έμμ

    `POST` / makeroom β STUDY/EXAM λͺ¨λμ λ°λΌ λ°©μμ±

    `POST` / makeroom/success β λ°© μμ± μ±κ³΅ ν λ°© μ λ³΄ λμ΄

    `POST` / enteroom/exam1 β EXAM λͺ¨λ μ± μ°¨λ¨ μ¬λΆ μμ²­

    `POST` / enteroom/exam2 β EXAM λͺ¨λ μΌκ΅΄ μΈμ νμΈ μμ²­

    `POST` / enteroom/exam3 β EXAM λͺ¨λ WebRTC μμ₯ κ°λ₯ μ¬λΆ μμ²­ 

    `POST` / enteroom/study1 β STUDY λͺ¨λ μ± μ°¨λ¨ μ¬λΆ μμ²­

    `POST` / enteroom/study2 β STUDY λͺ¨λ WebRTC μμ₯ κ°λ₯ μ¬λΆ μμ²­

    `GET` / roomout/<int:time>/<str:mode> β modeκ° STUDY μΌλ ν΄λΉ μ¬μ©μμ Analyticsμ timeμ΄ μ μ₯λ¨

    `POST` / roomout/<int:time>/<str:mode> β App μ κ·Ό μ°¨λ¨μ ν΄μ  νμλμ§ μμ²­ & modeκ° STUDY μΌλ μ μ₯λ€ time, app, person λ³μλ₯Ό λ°νμΌλ‘ level, rateλ₯Ό μΈ‘μ νκ³  Analytics λͺ¨λΈμ μ μ₯ 

    `GET` / roomout/study β sessionμμ μ¬μ©μ μ λ³΄λ₯Ό κ°μ Έμ Analytics λͺ¨λΈμ κ°μ₯ λ§μ§λ§ rowλ₯Ό DBμμ κ°μ Έμμ μ§μ€λ κ·Έλνλ₯Ό κ·Έλ¦Ό 

    `POST` / roomout/exam β μνμ΄ μ±κ³΅μ μΌλ‘ μ’λ£ λλμ§ μμ²­

    `GET` / list/room β Room DBμμ μ¬μ©μ μ΄λ¦μΌλ‘ λ§λ€μ΄μ§ Roomμ           QuerySetμΌλ‘ λ°νν list λνλ

    `GET` / list/analytics β Analytics DBμμ μ¬μ©μ μ΄λ¦μΌλ‘ λ§λ€μ΄μ§ Analyticsλ₯Ό QuerySetμΌλ‘ λ°νν list λνλ

    `POST`/ list/analytics/<int:pk> β Analytics Listμμ μ νν QuerySet κ°μ²΄μ 

    Primary Key κ°κ³Ό κ°μ rowλ₯Ό DBμμ κ°μ Έμ μ§μ€λ κ·Έλνλ₯Ό κ·Έλ €μ€ 

## πΎRole

---

@κΉνμ 

- *NCP μλ² κ΅¬μΆ*
- *kubernetes μ¬μ©ν HTTPS λ°°ν¬*
- *GazeCloudAPIλ₯Ό ν΅ν eye-tracking λμΆμ  & λ°©μ΄ν λΆμ νμ μλ¦Ό*
- *luxand APIλ₯Ό μ΄μ©ν Examλ°© μμ₯ μ λ³ΈμΈνμΈ*
- *Exam λͺ¨λ μμμ λͺλ¨ μμνμΌ μ²λ¦¬*

@κΉμ€μ 

- Realtime Client *Layout κ΅¬μΆ*
- *WebSocket tokenμ νμ©ν peer connection*
- *λΆμ νμ μ€μκ° μλκΈ°λ₯ κ΅¬μΆ*
- *λ°±μλ μ€μκ° ν΅μ  κ΅¬μΆ*
- *Redux νμ©ν SettingData(Gaze,λ§μ΄ν¬ ,λΉλμ€ on/off) λ° UserData μν κ΄λ¦¬*
- *μ±ν λ° νμν΅μ  κΈ°λ° [socket.io](http://socket.io) ν΅μ *
- *WebSocket tokenμ νμ©ν peer connection*

@ν©νμ 

- *django UI/UX μ μ²΄ frontend κ°λ°*
- *django Rest API μ€κ³ λ° κ°λ°*
- Luxand API μΌκ΅΄μΈμμ ν΅ν μ¬μ©μ μΈμ¦ κΈ°λ₯ κ°λ°
- *λ‘κ·ΈμΈ/νμκ°μ κ°λ°*
- *μ¬μ©μ μ΄λ―Έμ§ λ³κ²½μ΄ κ°λ₯ν my page κ°λ°*
- *Class μμ± λ° μμ₯ κ°λ°*
- *μ§μ€λ ν΅κ³μλ£ κ·Έλν κΈ°λ₯ κ°λ°*

@κΉμ λ¦Ό 

- *android μ μ²΄ Layout κ΅¬μΆ*
- *SQLite λ‘κ·ΈμΈν μ¬μ©μ μ μ₯*
- *study, examλͺ¨λ λ³λ‘ λ°© μμ± (examλͺ¨λ μμ± μ νμΌ[νμλͺλ¨] μλ‘λ νμ)*
- *retrofit μ¬μ©νμ¬ μλ²μ ν΅μ *
- *exam λ°© μμ₯μ μΉ΄λ©λΌ μ΄¬μ λ° μ΄λ―Έμ§ ν΅μ *
- *μλλ‘μ΄λ NDK + OpenCVλ₯Ό νμ©ν μ¬λ μΈμ§ κΈ°λ₯*
- *νΉμ  μ± μ°¨λ¨ κ΅¬ν*


### License
```
MIT License

Copyright (ν΄λͺ½μ μ) [2021-08-15] [HyeWon Kim, JunYoung Kim, YuLim Kim, HanSik Hwang]

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
