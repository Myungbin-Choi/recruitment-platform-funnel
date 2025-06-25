# 채용 플랫폼 유저 이탈 개선 프로젝트 
## _'지원 미완료 초기 이탈 유저'_ 개선을 위한 데이터 분석
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white"> <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=MySQL&logoColor=white">


## 프로젝트 개요
### 분석 목적
채용 플랫폼 유저 이탈 지점을 식별하고, 사용 개선을 위한 인사이트 제시
- '지원 미완료 유저'의 이탈 지점을 식별하고, '지원 완료' 유저의 이용 패턴과 비교하여 주요 이탈 원인을 파악한다
- 플랫폼 초기 리텐션 및 전환율을 향상시킬 수 있는 개선 제안을 도출한다


### 활용 데이터
**유저 로그 데이터 (6개월 내 플랫폼 신규 가입 유저 총 539명의 로그 데이터)**
- 보유 컬럼 : 유저ID, 로그 생성 시점, 로그 생성일, URL, HTTP 응답 코드, HTTP 요청 메소드
- 보조 활용 데이터 : 기업 정보 데이터, 채용 공고 정보 데이터, 채용 공고 북마크 정보 데이터, 유저 지원 데이터 등


### 타겟 유저 페르소나
![persona](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/images/persona.png)


### 수행 역할
- 유저 로그데이터 URL 분류를 통한 퍼널 단계 설정
- pandas, matplotlib, seaborn을 활용한 데이터 분석 및 시각화
- A/B테스트 설계
---

## 분석 과정 및 주요 결과
### 주요 결과 요약
1) **이력서 수정 빈도**가 높은 유저는 플랫폼 내에서 더 활발한 탐색 및 지원 활동으로 이어진다
2) **이력서에 기본 정보만 입력**하는 유저는 이후 지원서 작성 단계로의 전환율이 유의미하게 낮다
3) 지원 공고에 대한 클릭이 잦은 유저그룹은 최종 단계에 도달하는 비율이 높다


### 진행 프로세스 및 주요 분석 과정
![process](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/images/process.png)


### 주요 분석 결과
#### 1. 퍼널 단계별 이탈률
![funnel](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/funnel.png)
- **__2단계 개인 이력서 작성 단계의 경우, 이탈률은 낮으나 후속 단계 전환에 지속적인 영향을 미칠 수 있다고 판단하여 해당 단계에 대한 현황 분석 진행__**


#### 2. 주요 이탈구간 현황 파악
![funnel_analytics](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/images/funnel_analytics.png)
- 단계별 체류시간이 짧을수록 다음 단계로의 전환이 낮다
- 개인 이력서에 대한 확인 및 수정이 잦은 유저의 이탈률이 낮다
- 관련 공고 불러오기 클릭이 잦을수록 다음 단계로의 전환이 높다 등 가설 검증


#### 3. 유저 여정 분석
![user_journey](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/images/user_journey.png)
![user_journey_differences](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/images/user_journey_differences.png)
- 이력서를 간단히 작성한 유저일수록 탐색 단계에서 빠르게 이탈하는 경향이 있다
- 즉, 플랫폼 내 이력서 작성 경험이 지원서 작성으로 이어지도록 충분히 동기부여되지 못했다
  
   
### 개선제안
- 채용 플랫폼 이용에 있어 '이력서 작성' 단계의 경우, 퍼널 단계 중 이탈률은 낮은 편이나 이 단계에서의 경험이 이후 단계에서의 전환에 큰 영향을 미치고 있으므로, 이력서 작성에 대한 동기 유발 설계를 강화할 필요성 도출
![abtest](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/images/abtest.png)
---

## directory structure
```bash
├── README.md                     <- 프로젝트 요약 설명
├── recruitment_funnel.ipynb      <- 분석 통합 파일 (preview 용)
├── recruitment_funnel.py         <- 분석 통합 파일 (code 공유용)
├── 채용플랫폼_요약포트폴리오.pdf        <- 프로젝트 2page 요약 파일
├── 채용플랫폼_포트폴리오.pdf           <- 프로젝트 보고서 요약 파일
├── images                        <- 주요 이미지 파일
│   ├── abtest.png       
│   ├── funnel.png      
│   ├── funnel_anlalytics.png   
│   └── persona.png            
│   └── process.png           
│   └── user_journey.png        
│   └── user_journey_differences.png           
```
