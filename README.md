# 🔵 외부고리 은하 영상 분석 · Python Data Science

SDSS의 실제 외부고리 은하 FITS 영상을 Python으로 처리·분석하는 연구 및 교육용 저장소입니다.  
배경 하늘 제거, smoothing, 등광도선(isophote) 분석, 형태학적 특성 추출 등 **실제 천문 영상 분석 절차**를 경험할 수 있습니다.

> **권장 대상:** Python/Jupyter를 한 번이라도 사용해 본 학생·예비교사·교사·연구자  
> **권장 환경:** Windows + Jupyter Notebook  
> **주의:** FITS 파일이 많아 저장소 전체 용량이 큽니다.

---

## 🚀 처음 사용하는 분을 위한 빠른 시작

### 1. 저장소 전체 받기
GitHub 화면에서 **Code → Download ZIP**을 누릅니다.

직접 링크:  
https://github.com/GodTANKS/Outer-Ring-Galaxy-DataScience/archive/refs/heads/main.zip

파일이 많기 때문에 다운로드와 압축 해제에 시간이 걸릴 수 있습니다.

### 2. Python/Jupyter 준비
Python이 설치되어 있다면 터미널 또는 명령 프롬프트에서:

```bash
pip install -r requirements.txt
jupyter notebook
```

### 3. 분석 폴더 만들기
원본 Notebook은 Windows의 다음 경로를 기준으로 작성되어 있습니다.

```text
C:\ring_galaxy
C:\ring_galaxy\result
```

- `C:\ring_galaxy` 폴더를 만듭니다.
- 그 안에 분석할 FITS 파일과 `ring_galaxy.csv`를 넣습니다.
- 결과 저장용 `C:\ring_galaxy\result` 폴더도 만듭니다.

### 4. Notebook 열기
`coding/외부고리 은하 분류_분석 코드.ipynb`를 Jupyter Notebook에서 엽니다.

### 5. 셀을 위에서부터 순서대로 실행
처음에는 **object number 1010**처럼 저장소에 실제 FITS 파일이 존재하는 한 개 은하만 선택해 전체 과정을 시험해 보는 것을 권장합니다.

---

## 🧪 실습에서 무엇을 하나요?

### 1) 데이터 수집 및 탐색
- 분석 대상 은하 번호 선택
- FITS 헤더와 데이터 구조 확인
- 기본 통계량 탐색
- 적경·적위를 이미지 픽셀 좌표로 변환
- 원본 SDSS 영상 확인

### 2) 데이터 처리
- 분석 대상 은하 영역 추출
- 배경 하늘 밝기 추정
- background subtraction
- 천체 마스킹
- Gaussian smoothing

### 3) 영상 분석
- 등광도선(isophote) 분석
- 타원 기하학 기반 중심 좌표 보정
- 타원율과 위치각 등 형태 특성 분석
- 필요 시 내부 천체 마스킹 및 재분석
- Random Forest 기반 보완 분석

---

## 📁 저장소 구성

| 파일/폴더 | 설명 |
|---|---|
| `coding/외부고리 은하 분류_분석 코드.ipynb` | 메인 분석 Notebook |
| `coding/click2label.py` | Notebook 보조 Python 파일 |
| `ring_galaxy.csv` | 분석 대상 은하 목록 |
| `*_u.fits` | SDSS u-band 영상 |
| `*_g.fits` | SDSS g-band 영상 |
| `*_r.fits` | SDSS r-band 영상 |
| `*_i.fits` | SDSS i-band 영상 |
| `*_z.fits` | SDSS z-band 영상 |
| `requirements.txt` | 실행 패키지 목록 |

---

## 📦 주요 Python 패키지

- numpy
- pandas
- matplotlib
- astropy
- regions
- photutils
- scikit-learn
- jupyter

---

## ❓ 자주 발생하는 문제

**Q. FITS 파일을 찾을 수 없다고 나옵니다.**  
A. `C:\ring_galaxy` 안에 선택한 object number의 u/g/r/i/z FITS 파일이 모두 있는지 확인하세요.

**Q. result 폴더 관련 오류가 납니다.**  
A. `C:\ring_galaxy\result` 폴더를 직접 만들어 주세요.

**Q. `click2label`을 찾지 못한다고 나옵니다.**  
A. Notebook은 `coding` 폴더 안에서 실행하고, 같은 폴더에 `click2label.py`가 있는지 확인하세요.

**Q. 설치 중 photutils/astropy 오류가 납니다.**  
A. 먼저 `python -m pip install --upgrade pip`를 실행한 뒤 다시 `pip install -r requirements.txt`를 실행해 보세요.

---

## 📄 관련 연구

**조훈 · 손정주, 「외부고리 은하 영상 분석을 위한 파이썬 기반 알고리즘 개발」**  
한국지구과학회지, 43(5), 579–590, 2022.  
DOI: https://doi.org/10.5467/JKESS.2022.43.5.579

---

## 🌐 통합 연구·교육 플랫폼

**AI · 데이터 사이언스로 탐구하는 천문학**  
https://GodTANKS.github.io/astronomy-data-science/

기존 연구 아카이브:  
https://sites.google.com/view/astronomydatascience/

---

## 📌 사용 안내

교육·연구 활용 시 관련 논문과 SDSS 데이터 출처를 함께 표기해 주세요.
