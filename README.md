# 📦 AI 고객 관리 및 마케팅 자동화 시스템

**30년간 축적된 프린터/복합기 소모품 고객 데이터를 기반으로, AI를 활용하여 구매 주기를 예측하고 타겟 마케팅을 자동화하여 매출을 극대화하는 시스템입니다.**

---

## 🎯 프로젝트 목표

- **데이터 자산화**: 300만 건의 엑셀 파일을 체계적인 데이터베이스로 전환
- **업무 효율화**: 분산된 고객 정보를 중앙에서 통합 관리하여 직원들의 업무 부담 경감
- **매출 증대**: AI 기반 구매 주기 예측을 통해 적시 타겟 마케팅 수행
- **고객 이탈 방지**: 이탈 가능성이 높은 고객을 사전에 감지하고 선제적 대응

---

## ✨ 주요 기능

### 1. 📈 메인 대시보드
- 실시간 핵심 지표(총 고객 수, 신규 고객, 주문 건수) 시각화
- AI가 분석한 **'오늘의 마케팅 대상'** 자동 추천
  -  Toner/Ink 교체 임박 고객 리스트
  - 장기 미구매로 인한 이탈 위험 고객 리스트

### 2. 🗂️ 통합 고객 관리
- 강력한 통합 검색 (거래처명, 전화번호, 담당자명 등)
- 고객별 상세 정보 및 전체 주문 내역 조회

### 3. 🧠 AI 인사이트 (고객 상세 페이지)
- **다음 구매 예측**: 고객별/제품별 다음 구매 예상일을 자동으로 계산 (`예: 삼성 MLT-D111S 토너, 약 15일 뒤 구매 예상`)
- **스마트 추천**: 과거 구매 패턴을 분석하여 교차 판매(Cross-selling) 상품 추천 (`예: 이 고객은 포토용지도 함께 구매할 확률이 75%입니다.`)
- **고객 등급 분석**: RFM 분석 기반의 고객 등급 자동 분류 (VIP, 충성, 일반, 이탈위험)

### 4. 🚀 대용량 데이터 마이그레이션
- **엑셀 파일 업로드**: 기존 300만 건 엑셀 파일을 웹페이지에서 간편하게 업로드
- **백그라운드 처리**: 대용량 데이터 처리 중에도 웹페이지가 멈추지 않는 비동기 방식 적용
- **실시간 진행 상황 모니터링**: 데이터 이전 작업의 진행률을 실시간으로 확인

---

## 🛠️ 기술 스택 (Tech Stack)

| 구분           | 기술                                | 목적                                  |
| -------------- | ----------------------------------- | ------------------------------------- |
| **Backend**    | `Python`, `Flask`                   | 웹 서버 및 API 개발                   |
| **Frontend**   | `HTML`, `CSS`, `JavaScript`         | 사용자 인터페이스(UI) 구축            |
| **Database**   | `PostgreSQL`                        | 대용량 데이터 저장 및 관리            |
| **Async Task** | `Celery`, `Redis`                   | 데이터 이전, AI 분석 등 무거운 작업 처리 |
| **Data/AI**    | `Pandas`, `Scikit-learn`            | 데이터 정제 및 머신러닝 모델링        |
| **ORM/Migrate**| `Flask-SQLAlchemy`, `Flask-Migrate` | DB 테이블 관리 및 구조 변경 자동화    |

---

## 🚀 시작하기 (Getting Started)

이 프로젝트를 로컬 환경에 설치하고 실행하는 방법입니다.

### 1. 사전 준비 (Prerequisites)
- Python 3.8 이상
- PostgreSQL
- Redis

### 2. 설치 (Installation)

1. **GitHub 저장소 복제:**
   ```bash
   git clone https://github.com/[사장님_GitHub_ID]/customer-ai-system.git
   cd customer-ai-system

# 가상환경 생성
python -m venv venv

# 가상환경 활성화 (macOS/Linux)
source venv/bin/activate

# 가상환경 활성화 (Windows)
.\venv\Scripts\activate

pip install -r requirements.txt

# 예시: config.py
SQLALCHEMY_DATABASE_URI = 'postgresql://[DB_USER]:[DB_PASSWORD]@[DB_HOST]/[DB_NAME]'

flask db init
flask db migrate -m "Initial migration."
flask db upgrade

redis-server

celery -A run.celery worker --loglevel=info

python run.py





   
