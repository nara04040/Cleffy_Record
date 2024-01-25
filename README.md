# Cleffy 정리
실 서비스를 제공하는 프로젝트이기에 제품 코드를 공유하지 못하여 제가 담당한 부분을 정리해봤습니다.

<br>
<br>


## 프로젝트 소개
Cleffy는 사용자가 음악 파일이나 URL을 제공하면, 인공지능이 그 음악을 분석하여 악보로 변환해주는 서비스입니다. 

<br>
<br>

## 작업 관리
- Notion, Gather를 통해 진행상황, Task정리
- 주간회의를 진행하여 계획수립, 진행상황 공유
- Figma를 활용한 UI개발, 화면 설계
- Swagger API를 활용한 백엔드와 소통

<br>
<br>

## 프론트엔드 기술스택
[![stackticon](https://firebasestorage.googleapis.com/v0/b/stackticon-81399.appspot.com/o/images%2F1706102654921?alt=media&token=3c703047-746c-4b30-990f-32a4b234614d)](https://github.com/msdio/stackticon)

<br>
<br>

## 프로젝트 담당 

### 1. **로그인**

https://github.com/nara04040/Cleffy_Record/assets/83911617/96202690-cfac-4631-949b-610deb8b6e08

- 이메일 유효성 검사를 통해 정확한 정보의 유저만이 서비스를 이용할 수 있도록 구현.
- 로그아웃시 로컬 저장소의 토큰 값과 사용자 정보를 삭제하고 초기화면 라우팅 구현.
- react-oauth라이브러리를 활용한 google 로그인 기능을 구현.
	- 브라우저 언어를 탐지하여 국가에 맞는 언어 제공

<br>
<br>

### **2. 회원가입**

https://github.com/nara04040/Cleffy_Record/assets/83911617/14ec090f-3253-48c6-97d0-710d6e2aba24

<img width="916" alt="회원가입" src="https://github.com/nara04040/Cleffy_Record/assets/83911617/5819307b-f0ae-4918-adb8-59e5c7f17621">

- 회원가입 시 AccessToken을 발급하여 보안을 강화
- 회원가입이후 본인확인을 위한 이메일 증명처리
	- 이메일 확인이 되었다면 로그인 페이지로 리다이렉팅 처리
- 이메일 주소와 비밀번호를 입력하면 입력창에서 바로 유효성 검사가 진행되고 통과하지 못한 경우 각 경고 문구가표시
-  비밀번호가 8자 미만, 20자 이상일 경우에는 경구 문구 등장
- 작성이 완료된 후, 유효성 검사가 통과된 경우 다음 버튼이 활성화되며, 버튼을 클릭하면 프로필 설정 화면이 나타납니다.

<br>
<br>

###  **2-1. Protected Router 구현**
- 이메일 유효성 검사를 진행하지 않은 유저들은 서비스를 제공하지 않기 위해 Protected Router기능을 채택했습니다.
- 유저의 접근 레벨에 따라 다른 라우팅을 제공하여, 사용자별 맞춤형 서비스를 제공하였습니다.

<br>
<br>

### 3. **쿠키 수집 동의를 위한 처리**

<img width="1274" alt="쿠키수집동의" src="https://github.com/nara04040/Cleffy_Record/assets/83911617/39a06cc4-02c5-4392-8dc9-259efcdfea0a">

- cookie 수집을 위해 사용자 동의가 필요성이 높아져 첫 화면 렌더링시 쿠키 수집을 동의하도록 구현했습니다.


<br>
<br>

### **4. 서비스 이용시 썸네일, 음악 정보, 결제 제공**

<img width="1232" alt="스크린샷 2023-09-10 오후 11 59 38" src="https://github.com/nara04040/Cleffy_Record/assets/83911617/35d5923a-130b-4ec9-913b-0edddb630974">


- 사용자가 음악파일을 제공하였을 때 썸네일, 음악정보, 결제가 보여져야 했습니다.
 - 유튜브,soundcloud에서 url을 제공했을 시 썸네일, 음악정보, 음악 길이, 결제버튼을 구현
 - 음악파일을 제공할 시 음악정보, 길이, 결제버튼을 구현

<br>
<br>

### **5. 채보가 완료된 악보 제공**

<img width="799" alt="채보 악보" src="https://github.com/nara04040/Cleffy_Record/assets/83911617/4d0d5909-f059-48d9-8266-a3f6de8c7ecb">


<img width="839" alt="음악 리스트" src="https://github.com/nara04040/Cleffy_Record/assets/83911617/e30ed4b4-a858-41ef-b2cc-8638356ec6c9">

- 서비스를 이용한 노래들을 보여주는 리스트를 제공
- 현재 채보 중임을 나타내기 위해 채보 상태를 제공
- 선택한 곡 삭제 기능 구현

<br>
<br>

### **6. 다양한 결제 시스템 구현**

<img width="1053" alt="크레딧" src="https://github.com/nara04040/Cleffy_Record/assets/83911617/c67743d9-c802-44a4-ba34-48ff37290073">


<img width="890" alt="페이팔" src="https://github.com/nara04040/Cleffy_Record/assets/83911617/c013796f-7b6d-467f-892f-89ab1fd93c3e">

- 해외 서비스를 계획하였기 때문에 해외 결제의 필요성
	- 브라우저 접근 언어를 감지 이후 tosspayments paypal활용하여 구현
	- 결제 완료한 유저를 대상으로 songList로 리다이렉트







