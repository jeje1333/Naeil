# Project: 내일 뭐 먹지?
## 화면 보기
<details>
<summary><strong>📸 전체 화면 미리보기</strong> (클릭하여 보기)</summary>

| 구분 | 화면 | 미리보기 |
|------|------|----------|
| 공통 | 로그인 | <img height="300" alt="image" src="https://github.com/user-attachments/assets/eb962efa-8770-4d1f-9f20-31300461ef0e" /> |
| 관리자 | 관리자 메인 | <img height="300" alt="관리자페이지" src="https://github.com/user-attachments/assets/e9390e21-fc57-40cf-93fc-450fa8b5bc49" /> |
| 관리자 | 가게 관리 | <img height="300" alt="가게관리" src="https://github.com/user-attachments/assets/7d6bd95a-baca-4028-9777-993e424b440c" /> |
| 관리자 | 메뉴 관리 | <img height="300" alt="image" src="https://github.com/user-attachments/assets/398c9fd3-d574-416d-a59c-24f3791d90af" /> |
| 관리자 | 예약 확인 | <img height="300" alt="예약확인" src="https://github.com/user-attachments/assets/060e4a7d-a70d-4855-9f5f-7a599f55feb9" /> |
| 사용자 | 유저 메인 | <img height="300" alt="image" src="https://github.com/user-attachments/assets/0c799022-c865-41a0-8a1c-3cfa72eaf60e" /> |
| 사용자 | 예약 | <img height="300" alt="image" src="https://github.com/user-attachments/assets/aa43a009-59de-40aa-adb5-64e45514bc6d" /> |
| 사용자 | 예약 확인 | <img height="300" alt="image" src="https://github.com/user-attachments/assets/69089844-d290-463c-a331-296d40e89f01" /> |
</details>

## 기획 의도
Java Swing 기반 GUI 음식점 예약 시스템  
사용자와 사업자 간 간편한 예약 관리를 지원하는 데스크탑 애플리케이션입니다.  
  
맛집 방문 시 긴 대기시간을 줄이고, 사용자가 원하는 시간대에 식사를 예약할 수 있도록 합니다.  
사업자는 손쉽게 메뉴와 예약을 관리할 수 있으며, 사용자와 사업자 모두의 편의성 향상을 목표로 기획했습니다.

## 개발 개요
프로젝트 기한: 2024.04.14 ~ 2024.04.28 (총 15일)  
팀원 수: 5명

## 개발 소요
로그인 및 회원가입을 통한 회원 관리 시스템  
가게 메뉴 선택 후 예약 시스템  
검색, 별점 순 정렬 기능을 통한 맛집 탐색 기능  
관리자 페이지에서 가게 추가 및 메뉴 수정기능

## 맡은 역할
* 회원가입/로그인 예외처리 고도화

  * 입력 검증(이메일 형식, 비밀번호 정책), 중복 가입 방지, 약관 동의 로직 분리
  * 서버/클라이언트 양쪽에서 에러 메시지 일관화, 예외 코드 표준화
  * 인증 토큰 만료·재발급 플로우 및 보안 헤더 설정

* 메인 화면 기능 개발

  * 추천/신규/인기 섹션 구성, 페이지네이션 및 무한 스크롤 적용
  * 캐시 전략 수립(서버 캐시/브라우저 캐시)로 초기 로딩 개선
  * 공통 UI 컴포넌트(헤더/푸터/알림) 모듈화

* 가게/메뉴 CRUD 및 관리자 화면

  * 메뉴 등록/수정/삭제, 카테고리/옵션 관리, 이미지 업로드 처리
  * 다중 조건 검색(가게명/카테고리/태그)과 정렬, 페이지네이션 구현
  * 관리용 리스트 테이블, 상세/승인 워크플로우 구축

## 사용 기술 스택
| 구분 | 기술 
|------|------|
| 언어: | Java
| GUI: | Java Swing
| DB: | Oracle 18c, JDBC
| IDE: | Eclipse
| 도구: | Figma (UI 설계), draw.io (ERD 설계)


## 발생한 문제점 및 해결

#### 프로젝트 구조 설계 문제
  1차 회의에서 기획한 개발 계획이 끝이 나자, 2차로 회의를 하여 기능을 추가하는 회의를 진행할 때였습니다.  
  다음 기능에 관한 논의들이 오갔고 다양한 추가 기능에 대한 요구사항이 제기되었습니다.  
  하지만 기능 확장성을 고려하지 않은 초기 프로젝트 구조는 새로운 기능들을 담아내기에는 부족하였습니다.  
  기능을 확장하려면 더 많은 회의를 거쳐 DB 스키마 설계와 화면 재구성 등의 업무를 일궈야 했습니다.  
  하지만 이 땐, 프로젝트 설계에 관한 가치에 대해 잘 알지 못 하였으며 경각심 없이 하드코딩을 시작했고  
  결과적으로 이렇게 작성된 코드들은 재작업과 리팩토링을 하는 데에 시간이 더 소요되었으며  
  이 경험을 통해  '빨리 시작하는 것'보다 '제대로 설계하는 것'이 장기적인 관점에서 훨씬 효율적이라는 진리를 몸소 깨달았습니다.   
  특히, 기능 확장과 유지보수를 고려한 유연한 아키텍처를 설계하는 것이 왜 중요한지,  
  그리고 초기 설계 단계에서 충분한 고민과 논의가 얼마나 큰 가치를 지니는지 절실히 느꼈습니다.  

#### 프로그램 유지보수성 저하 코드 발견
프로그램 GUI를 개발 중에 Java WindowBuilder를 사용하였습니다.  
사용자로 하여금 편리하게 레이아웃을 제작할 때 사용하는 기술이었지만 DB에 있는 모든 메뉴 리스트를 불러오기엔 적절하지 않았습니다.  
메뉴 하나를 저장할 수 있는 판넬 20개를 만든다고 가정했을 때 20개 이상의 메뉴는 불러오지 못 하는 등 유지보수에 문제가 있어서  
DB에 있는 메뉴 개수만큼 판넬을 만드는 함수를 개발하였습니다.  
이러한 방식을 사용하니 초기 개발에는 많은 자원이 들어갔지만  
이후 다른 페이지를 만들 때도 이 함수를 참조하여 개발하니  
개발 속도 및 코드 가독성을 챙기고 DB만 관리하면 판넬은 자동으로 생성되니 유지보수성을 챙길 수 있었습니다.  

## 프로젝트 관련 자료 
[시연 동영상](https://drive.google.com/file/d/1kVO33m2BcuHPl55LmJaiDhpm9jkdNTV2/view?usp=drive_link)  
[발표 PPT](https://docs.google.com/presentation/d/1p_OsoSNuF4TKWMCrN96TpJ6Qjzo4gyFD/edit?usp=drive_link&ouid=117757726946514060735&rtpof=true&sd=true)  
[프로젝트 ERD](https://drive.google.com/file/d/1_jbFh9ITI2UFuWUXM-cUNz6_ogDomROj/view?usp=drive_link)    
[화면 설계 및 기능 명세서](https://drive.google.com/file/d/1gH8DZr0jSiPdgbyox1OvXi-JcP60-smG/view?usp=drive_link)    
[프로젝트 개발 계획서](https://docs.google.com/document/d/1-Eby-sEILRy170nCE783xbKEqkqOgwbw)  
 
