## 별첨

- 발표 자료 :
https://docs.google.com/presentation/d/113H8bMFCK-eyZy9Xkkg-2F5YXFxcTPZp/edit?usp=drive_link&ouid=109009094223591979016&rtpof=true&sd=true

- 핵심기술소개서 :
https://docs.google.com/document/d/1xoAS3u7-kuaBvp5TV8JcI_zjfVXGyAoJ/edit?usp=drive_link&ouid=109009094223591979016&rtpof=true&sd=true

---

<img width="732" height="632" alt="웹사이트 썸네일" src="https://github.com/user-attachments/assets/e29d133b-76fd-4bd5-892d-408145ecbd1c" />

## 1. 프로젝트 개요

- **기간**: 2022.11.08 ~ 2022.12.12
- **발표일**: 2022.12.13
- **개발환경/기술스택**:
    - Spring Boot, Java, MyBatis, Thymeleaf
    - JavaMailSender, 외부 API (NAVER Map API, 주소 API)
    - Frontend: HTML/CSS, jQuery, Ajax

## 2. 주요 기능

### (1) 회원관리

- **회원가입**
    - 아이디 중복 체크 (비동기 DB 조회 → 중복 시 안내 문구 표시)
    - 이메일 인증 (JavaMailSender 활용, 인증번호 랜덤 생성·발송)
    - 주소 API 연동 (팝업창 호출 후 입력값 반환)
- **로그인**
    - DB 내 아이디·비밀번호 대조 후 세션 등록
    - 불일치 시 오류 메시지 반환
- **회원정보 수정**
    - 수정 후 DB 업데이트 및 세션 갱신
- **비밀번호 찾기**
    - 아이디·이메일 대조 후 인증번호 발송
    - 인증 성공 시 비밀번호 변경 가능

---

### (2) 쇼핑몰 기능

- **게시판/리뷰**
    - 리뷰 작성 및 수정, 별점 등록 가능
    - 리뷰 평점을 백분율로 계산 후 UI 별 아이콘으로 출력
- **찜하기(좋아요)**
    - 상품 상세 페이지에서 Ajax 기반 비동기 처리
    - 찜 상태에 따라 빈 하트(🤍)/채워진 하트(💗) 토글
    - pick 테이블에 insert/delete로 상태 반영

---

### (3) 차량 관련 기능

- **최근 본 차량**
    - LocalStorage 활용 → 최근 본 차량 최대 4개 표시
    - Ajax로 DB에서 차량 이미지 불러오기
- **차량 검색**
    - 체크박스로 차량 종류 선택
    - 선택값을 JSON으로 전송 → 조건에 맞는 차량 리스트 반환
    - Ajax 비동기 처리로 검색 결과 실시간 반영

---

## 3. 차별화된 기술 포인트

- **Spring Boot + MyBatis 연동**: Controller → Service → DAO → Mapper 구조를 명확히 구현
- **이메일 인증·비밀번호 찾기**: `JavaMailSender`와 랜덤 코드 생성 로직 직접 구현
- **비동기 처리**: Ajax를 적극 활용해 사용자 경험(UX) 강화
- **LocalStorage 활용**: 최근 본 차량 기능 구현으로 사용자 편의성 제공
- **외부 API 연동**: NAVER Map API, 주소 API 활용으로 실제 서비스 완성도 제고

---

## 4. 기대 효과 및 학습 성과

- **엔드 투 엔드(End-to-End) 웹 서비스 구축 경험**
    
    → 회원가입 → 로그인 → 쇼핑몰 기능 → 차량 관리까지 전 기능 구현 경험 축적
    
- **백엔드-프론트엔드 연계 경험**
    
    → Spring Boot 기반 백엔드 로직과 jQuery·Ajax 기반 프론트엔드 상호작용 설계
    
- **확장 가능성**
    
    → 실제 서비스 수준 기능(회원관리, 검색, 찜, 리뷰 등)을 구현하여 상용 서비스와 유사한 구조 학습
