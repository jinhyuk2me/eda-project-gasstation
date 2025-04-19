<p align="center">
  <img src="https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/banner.png?raw=true" width="80%">
</p>

---

# 서울시 주유소 데이터 분석   
> **Exploratory Data Analysis on Gas Stations in Seoul**


## 📌 프로젝트 개요

서울시 내 주유소들의 **유종별 가격, 브랜드, 운영 시간, 편의시설, 위치** 정보를 분석하여 지역별 가격 편차, 브랜드 특성, 공간 분포 등 **다차원 인사이트를 도출**한 프로젝트입니다.

**`opinet.co.kr` 웹사이트를 `Selenium`으로 자동 크롤링**하고, **Google Maps Geocoding API**를 통해 도로명 주소를 위경도로 변환하여 다양한 통계 분석 및 지도 시각화를 수행하였습니다.

---

## 🌐 데이터 수집 및 전처리

| 항목 | 설명 |
|------|------|
| **출처** | [Opinet](https://www.opinet.co.kr/) |
| **수집 방식** | `Selenium` 기반 웹 자동화 크롤링 |
| **수집 항목** | 주유소명, 주소, 브랜드, 유종별 가격(보통/고급/경유/등유), 24시간 운영 여부, 편의점, 세차장, 충전소, 경정비 가능 여부 |
| **좌표 변환** | Google Maps API (`googlemaps`)를 사용한 주소 → 위경도 변환 |
| **전처리** | 결측값 제거, 이상치 필터링, DataFrame 통합 등 |

---

## 🧠 분석 항목

### 📊 가격 분석
- 자치구별 **유종별 평균 가격 분석**  
- **보통휘발유 가격 기준 상/하위 20개 주유소** 비교  

### 🕒 운영 특성
- 자치구별 **24시간 운영 주유소 수**  
- 자치구별 **편의점 유무 주유소 수**  

### 🗺️ 위치 시각화
- **편의점이 있는 주유소**만 필터링하여 지도 시각화  
- **유종별 가격 분포 지도 시각화 (보통/고급/경유/등유)**

### 🔗 상관관계 분석
- 유종 간 가격 상관관계 분석 (Corr Matrix & Scatter)


---

## 📊 주요 결과 요약

| 항목 | 인사이트 |
|------|----------|
| **자치구별 가격 차이** | 휘발유 가격은 자치구 간 최대 **400원 차이** 발생 |
| **브랜드 경향** | **SK에너지 / GS칼텍스**는 고가, **S-OIL / 알뜰주유소**는 저가 경향 |
| **공간 분포** | 고가 주유소는 도심 밀집, 저가 주유소는 외곽에 분포 |
| **운영 특성** | 24시간 운영 비율은 **중구/동작구/송파구**에서 높음 |
| **유종 상관성** | 가격 간 상관관계 매우 높음 (휘발유↔경유: 0.988 등) |

---

## 🗺️ 시각화 예시

### 📌 일반 주유소 vs 셀프 주유소 가격 비교
![Self vs General](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/self%20vs%20general.png?raw=true)

### 📌 브랜드 및 셀프 여부별 가격 비교
![Brand & Self](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/brand%20self%20price.png?raw=true)

### 📌 자치구별 보통/고급/경유/등유 가격 분포
![Regular Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/regular%20price%20by%20gu.png?raw=true)
![Regular Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/regular%20price%20by%20gu%20bar.png?raw=true)
![Premium Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/premium%20price%20by%20gu.png?raw=true)
![Premium Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/premium%20price%20by%20gu%20bar.png?raw=true)
![Diesel Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/diesel%20price%20by%20gu.png?raw=true)
![Diesel Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/diesel%20price%20by%20gu%20bar.png?raw=true)
![Kerosene Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/kerosene%20price%20by%20gu.png?raw=true)
![Kerosene Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/kerosene%20price%20by%20gu%20bar.png?raw=true)

### 📌 24시간 운영/편의점 유무 분석
![24hr Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/24hour%20ratio%20by%20gu.png?raw=true)
![24hr Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/24hour%20ratio%20by%20gu%20bar.png?raw=true)
![CVS Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/cvs%20ratio%20by%20gu.png?raw=true)
![CVS Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/cvs%20ratio%20by%20gu%20bar.png?raw=true)

### 📌 보통휘발유 가격 상/하위 Top 20
![Expensive Top20 Table](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/most%20expensive%20table.png?raw=true)
![Expensive Top20 Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/most%20expensive%20map.png?raw=true)
![Cheap Top20 Table](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/most%20cheap%20table.png?raw=true)
![Cheap Top20 Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/most%20cheap%20map.png?raw=true)

### 📌 유종 간 가격 상관관계
![Correlation Table](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/fuel%20corr%20table.png?raw=true)
![Correlation Scatter](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/fuel%20corr%20scatter.png?raw=true)

---

## 🛠️ 사용 기술 스택

| 분류 | 도구 |
|------|------|
| 언어 | Python 3 |
| 크롤링 | Selenium |
| 주소 변환 | Google Maps API (`googlemaps`) |
| 데이터 처리 | pandas, numpy |
| 시각화 | matplotlib, seaborn, folium |
| 분석 환경 | Jupyter Notebook, VS Code |

---

## 🙋‍♂️ 기여자

## 🙋‍♂️ 기여자

| 이름 | GitHub |
|------|--------|
| 장진혁 (Jinhyuk Jang) | [@jinhyuk2me](https://github.com/jinhyuk2me) |
