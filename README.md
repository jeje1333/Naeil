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
[시연 동영상(Youtube로 이동)](https://www.youtube.com/watch?v=EI1n9bDk5Hs)  
<details>
<summary><strong>📸 전체 화면 미리보기</strong> (클릭하여 보기)</summary>

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/b1f8efcf-b7ba-4fc7-9c8d-9b4a92f717e8" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c2c845e4-255e-4449-8362-f5978cdb5388" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/33d56c5c-f5c9-4308-97e4-037fbff68833" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7653998d-f7aa-445c-9214-eeb8f2a77160" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/08c22b50-0366-49bf-99c0-af63788e7d21" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/2d4c9652-ba6b-40ce-92ac-9713a2ae1913" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/aa23f670-1130-452a-a300-6704a12cf519" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/8c76a899-c54c-470c-a2ee-462c71458099" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/66b2265f-2918-44fd-aeab-d1cb6105a38f" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/992f1b16-f156-45da-a7c9-eb04476f6070" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ee634bef-46bc-40bc-9709-b0d070ff5021" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/387f4718-a7d2-48c2-9213-b058243295a2" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/57afe6cc-9f34-4afb-8f2e-f1ebe73a5e28" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4402c165-1721-4a57-8629-847726825650" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/934382c7-3808-4142-b088-028998c55163" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/3f67ccc2-939c-406c-9e56-b1755da6a238" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/37e8fa49-6c79-469d-93dd-efc4b70c3de9" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c466c3c2-b2d7-4aa3-abd0-16670bef8c4b" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/68cd6c5f-aff0-4d0e-a49a-5bd86b93d154" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/8127af86-5fe2-4c23-a90e-61425a3b8cdb" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/514ccaae-2d5d-48ab-949d-d77334d65336" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/974607d4-7f71-48fd-b05b-db61291bea35" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/67905b24-5f4f-47d3-9293-6e4b59cdba37" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/9fdd6683-b848-40f8-a247-4604cbe0fbac" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/d49283cc-fed5-49f0-a27c-550ed066aa70" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/2bdae283-9fd5-4ad5-9b45-99d1580d8d5c" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/9596b524-e1ed-407b-9f84-e7a25288814a" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/248de305-e1aa-44a5-9e1d-14f1362b9e7a" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/b32297d8-0cb8-445b-85cc-e9532a2574e7" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/17f9cbbb-9bdf-4612-a828-f7ca430dcc17" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/b4b09935-3583-4eca-9190-13aea9b22622" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/6544f0cd-3039-45e5-9dc2-ae076971bae2" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/abff8633-1579-4d76-a181-686c58570ee3" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/56b84325-49f7-4294-9e9b-cccb9bfbc54e" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/2b6d5cf1-3969-4152-9fc8-16a95151b5e5" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c9f452aa-a60d-4e6f-b70c-ffbe4c702f37" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/edbb4550-0764-4ec6-b36b-57a99373689c" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/59495eff-58a1-431e-8188-082d5837add9" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ecfd0be6-8afa-408f-a9cb-64acd192fe82" />
</details>
[프로젝트 ERD](https://drive.google.com/file/d/1_jbFh9ITI2UFuWUXM-cUNz6_ogDomROj/view?usp=drive_link)  
[화면 설계 및 기능 명세서](https://drive.google.com/file/d/1gH8DZr0jSiPdgbyox1OvXi-JcP60-smG/view?usp=drive_link)  
[프로젝트 개발 계획서](https://docs.google.com/document/d/1-Eby-sEILRy170nCE783xbKEqkqOgwbw)  
 
