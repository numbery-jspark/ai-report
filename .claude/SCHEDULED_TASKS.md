# Scheduled Tasks

## daily-ai-trend-report

매일 오전 8시에 AI & 에이전트 동향 리포트를 자동 생성합니다.

### 설정

- **Schedule**: `0 8 * * *` (매일 오전 8시, 로컬 시간대)
- **Status**: 활성화
- **Location**: Claude Code > Scheduled 탭

### 동작 방식

1. **WebSearch 실행** (1회)
   - 쿼리: `AI agents LLM major news June 2026`
   - 스니펫만 사용 (fetch 없음, 토큰 절약)

2. **HTML 리포트 생성**
   - 파일: `YYYY-MM-DD-ai-report.html`
   - 경로: `C:\Users\Admin\Desktop\ai-report\`
   - 디자인: 다크모드, 반응형

3. **브라우저 자동 오픈**
   - PowerShell: `Start-Process "파일경로"`

### 리포트 구성

```
[헤더] 날짜 + 제목

[섹션 1] 오늘의 핵심 뉴스 (4~5개)
  - 제목, 요약, 2문단 해설, 왜 중요한지

[섹션 2] 오늘의 딥다이브
  - 기술적 배경 + 실용적 의미

[섹션 3] 주목할 오픈소스 & 툴
  - 2~3개 도구/모델 소개

[섹션 4] 주요 AI 기업 동향
  - OpenAI, Anthropic, Google, Meta

[섹션 5] 오늘의 학습 포인트
  - 핵심 개념 3가지

[푸터] 생성 시각
```

### 토큰 최적화

- WebSearch 1회만 실행 (deep-research 워크플로우 미사용)
- 예상 소비: ~3% 일일 한도

### 토큰 사용 한도

- 월간 기준: 100회 실행 × 3% = 300% (초과 방지)
- 실제 계산: 매일 토큰 체크 권장

### 수정 방법

Claude Code > Scheduled 탭 > 이 태스크 편집 > 프롬프트 수정
