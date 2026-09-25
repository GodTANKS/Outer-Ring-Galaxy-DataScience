# 🔵 외부고리 은하 영상 분석 · Python Data Science

SDSS의 실제 외부고리 은하 FITS 영상을 Python으로 처리·분석하는 연구 및 교육용 저장소입니다.  
배경 하늘 제거, smoothing, 등광도선(isophote) 분석, 형태학적 특성 추출 등 **실제 천문 영상 분석 절차**를 경험할 수 있습니다.

> **권장 대상:** Python/Jupyter를 한 번이라도 사용해 본 학생·예비교사·교사·연구자  
> **권장 환경:** Windows + Jupyter Notebook  
> **주의:** FITS 파일이 많아 저장소 전체 용량이 큽니다.

---
## ▶ 가장 쉬운 실행: Google Colab

**[🚀 Colab에서 실행](https://colab.research.google.com/github/GodTANKS/Outer-Ring-Galaxy-DataScience/blob/main/colab/%EC%99%B8%EB%B6%80%EA%B3%A0%EB%A6%AC%20%EC%9D%80%ED%95%98%20%EC%98%81%EC%83%81%EB%B6%84%EC%84%9D_Colab_%EC%9B%90%EB%B3%B8%EB%B0%98%EC%98%81%ED%8C%90.ipynb)**

Python/Jupyter 설치나 `C:\\ring_galaxy` 폴더 생성 없이 실행할 수 있습니다.

1. 위 Colab 링크를 엽니다.
2. 첫 셀부터 순서대로 실행합니다.
3. 분석할 은하 번호를 선택합니다. 처음에는 **1010**을 권장합니다.
4. 필요한 `ring_galaxy.csv`와 해당 은하의 `u/g/r/i/z` FITS 5개는 GitHub에서 자동 다운로드됩니다.
5. i-band 영상에서 **첫 번째 클릭으로 장축 방향 끝점**, **두 번째 클릭으로 단축 방향 끝점**을 선택합니다.
6. 잘못 클릭하면 **오른쪽 클릭 또는 초기화 버튼**, 맞으면 **선택 확정**을 누릅니다.
7. 장축 반경·단축 반경·타원율·위치각이 자동 계산됩니다.
8. 분석이 끝나면 결과 CSV/JPG를 ZIP으로 내려받을 수 있습니다.

> Colab에서는 `%matplotlib widget`을 사용하지 않습니다. 브라우저의 실제 클릭 좌표를 JavaScript로 받아 Python 좌표로 변환하는 방식이라 별도 interactive Matplotlib backend가 필요하지 않습니다.

> **형식:** Google Colab용 Notebook (`.ipynb`)

---



## 📥 실습 파일 다운로드

- **[📥 Colab용 파일 다운로드](https://raw.githubusercontent.com/GodTANKS/Outer-Ring-Galaxy-DataScience/main/downloads/outer-ring-colab.zip)** — Colab Notebook + 분석 목록 CSV
- **[📓 Jupyter Notebook용 파일 다운로드](https://raw.githubusercontent.com/GodTANKS/Outer-Ring-Galaxy-DataScience/main/downloads/outer-ring-jupyter.zip)** — Jupyter Notebook + `click2label.py` + 분석 목록 CSV + 예제 1010 은하 FITS 5개
- **[📦 전체 코드·데이터 ZIP 다운로드](https://github.com/GodTANKS/Outer-Ring-Galaxy-DataScience/archive/refs/heads/main.zip)** — 전체 SDSS FITS 포함

**실행 형식**
- Google Colab용: 브라우저에서 실행
- Jupyter Notebook용: 로컬 Python/Jupyter에서 실행

> 전체 저장소 ZIP은 FITS 영상이 포함되어 용량이 큽니다. 코드 실습만 필요하면 위의 Colab용 또는 Jupyter Notebook용 ZIP을 이용하세요.

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
| `coding/외부고리 은하 분류_분석 코드.ipynb` | 연구용 원본 Jupyter Notebook |
| `colab/외부고리 은하 영상분석_Colab_원본반영판.ipynb` | Google Colab용 Notebook |
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

논문 PDF는 코드 저장소에 중복 보관하지 않고 **통합 논문 모음**에서 관리합니다.

**[📚 통합 논문 모음에서 보기](https://GodTANKS.github.io/astronomy-data-science/papers/)**


---

## 🌐 통합 연구·교육 플랫폼

**AI · 데이터 사이언스로 탐구하는 천문학**  
https://GodTANKS.github.io/astronomy-data-science/

기존 연구 아카이브:  
https://sites.google.com/view/astronomydatascience/

---

## 📌 사용 안내

교육·연구 활용 시 관련 논문과 SDSS 데이터 출처를 함께 표기해 주세요.

---

## 📘 교육·학습 목적 이용 조건

이 저장소에서 **공개된 코드·노트북·교육 자료**는 원저자·원본 저장소·관련 논문 출처를 명시하는 조건으로 **교육·학습 및 비상업적 연구 목적의 복제·수정·재배포가 가능합니다.**

**상업적 판매·유료 서비스·출처 삭제·타인의 독창적 연구 결과인 것처럼 사용하는 행위는 허용하지 않습니다.**

자세한 조건: [EDUCATIONAL_USE_NOTICE.md](EDUCATIONAL_USE_NOTICE.md)

