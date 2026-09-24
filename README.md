# Outer-Ring-Galaxy-DataScience

## 외부고리 은하 영상 분석을 위한 파이썬 기반 데이터 사이언스 콘텐츠

SDSS의 실제 외부고리 은하 영상 데이터를 이용하여  
**데이터 수집·탐색·처리·분석의 전 과정을 Python으로 수행**하도록 개발한 천문 영상 분석 콘텐츠입니다.

전문 천문 영상 분석 도구의 진입장벽을 낮추고,  
학생·교사·시민과학자도 실제 은하 FITS 데이터를 분석할 수 있도록 구성하였습니다.

## 관련 연구

**조훈 · 손정주, 「외부고리 은하 영상 분석을 위한 파이썬 기반 알고리즘 개발」**  
한국지구과학회지, 43(5), 579–590, 2022.  
DOI: **10.5467/JKESS.2022.43.5.579**

연구에서는 개발한 Python 기반 알고리즘의 분석 결과를 기존 IRAF 기반 연구와 비교하여 검증하였으며,  
코드와 SDSS 외부고리 은하 데이터를 교육·연구 자료로 공개하였습니다.

## 저장소 구성

- `coding/외부고리 은하 분류_분석 코드.ipynb` — 메인 Jupyter Notebook
- `coding/click2label.py` — Notebook에서 사용하는 보조 Python 파일
- `ring_galaxy.csv` — 분석 대상 외부고리 은하 목록
- `*_u.fits`, `*_g.fits`, `*_r.fits`, `*_i.fits`, `*_z.fits` — SDSS 다중 필터 FITS 영상 데이터

저장소에는 여러 외부고리 은하의 SDSS `u/g/r/i/z` 필터 영상이 포함되어 있습니다.

## 분석 과정

### 1. 데이터 수집 및 탐색
- 분석 대상 은하 번호 선택
- FITS 헤더 및 데이터 구조 확인
- 기본 통계량 탐색
- 천체 좌표를 이미지 픽셀 좌표로 변환
- 원본 SDSS 영상 시각화

### 2. 데이터 처리
- 분석 대상 은하 영역 추출
- 배경 하늘 밝기 추정 및 제거
- 천체 마스킹
- Gaussian smoothing 적용

### 3. 데이터 분석
- 등광도선(isophote) 분석
- 타원 기하학 기반 중심 좌표 보정
- 광도 윤곽, 타원율, 위치각 변화 분석
- 필요 시 내부 천체 마스킹 및 추가 보정
- Random Forest 기반 보완 분석

## 실행 방법

본 콘텐츠는 **Jupyter Notebook + Windows 환경**을 기준으로 개발되었습니다.

1. 저장소 전체를 내려받습니다.
2. Windows의 `C:\ring_galaxy` 폴더를 생성합니다.
3. 분석에 사용할 FITS 파일과 `ring_galaxy.csv`를 해당 폴더에 둡니다.
4. `C:\ring_galaxy\result` 폴더를 생성합니다.
5. `coding/외부고리 은하 분류_분석 코드.ipynb`를 Jupyter Notebook에서 실행합니다.
6. Notebook 안내에 따라 분석할 은하 번호와 분석 옵션을 입력합니다.

> 원본 Notebook이 Windows의 `C:\ring_galaxy` 경로를 기준으로 작성되어 있으므로 폴더 구조를 유지하는 것을 권장합니다.

## 주요 Python 패키지

- numpy
- pandas
- matplotlib
- astropy
- regions
- photutils
- scikit-learn
- jupyter

Notebook 안에도 필요한 패키지 설치 코드가 포함되어 있습니다.

## 데이터 사이언스 탐구 흐름

**데이터 수집 → 데이터 탐색 → 데이터 처리 → 영상 분석 → 결과 해석 및 보완**

실제 관측 영상의 배경 제거, smoothing, 등광도선 분석과 보완 과정을 직접 수행함으로써  
천문 영상 처리와 데이터 사이언스의 실제 연구 절차를 경험할 수 있습니다.

## 연구·교육 플랫폼

기존 공식 연구자료실:  
https://sites.google.com/view/astronomydatascience/

통합 연구·교육 플랫폼:  
https://GodTANKS.github.io/astronomy-data-science/

## 사용 안내

교육 및 연구 목적으로 활용할 경우 관련 논문과 데이터 출처(SDSS)를 함께 표기해 주세요.
