# 20210217

*from [https://nomadcoders.co/react-native-fundamentals](https://nomadcoders.co/react-native-fundamentals)*

### expo?

- create-react-app 같이 세팅이 되어 있음
- 내 폰으로 바로 테스트 할 수 있음!
- windows로 ios앱을 빌드할 수도 있음

### react native CLI

- 더 native한 부분을 건드릴 수 있음

---

- expo init <프로젝트명> 으로 프로젝트 생성할 수 있음
- npm start를 하면 qr코드가 나오는데 그걸 찍어서 내 폰으로 실행 가능
- 폰을 흔들면 개발자 메뉴 볼 수 있음
- npm expo eject 로 expo가 아닌 android studio, xcode에서 작업할 수 있음

---

- android, ios 모두 js 엔진이 있음
- react native는 이 엔진을 이용해서 ios, android의 네이티브 엔진에게 메시지를 보냄
- 브릿지로 서로 커뮤니케이션
- 많은 데이터는 속도가 느려질 수 있음(3d 게임 등은 부적합)
- 모든건 view안에 집어넣어야 함