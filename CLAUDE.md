# Claude Code Configuration

## 프로젝트 개요

**AI & 에이전트 동향 리포트** — 매일 오전 8시 최신 AI/에이전트 뉴스를 분석하여 HTML 리포트로 자동 생성하는 프로젝트입니다.

## 핵심 원칙

### 1. 토큰 최소화
- 웹 검색 1회만 실행 (deep-research 미사용)
- 필요한 것만 fetch (스니펫 중심)
- 불필요한 대화/설명 제거
- 예상 일일 소비: 3% 한도

### 2. 자동화
- 매일 오전 8시 자동 실행
- 스킬 기반 워크플로우
- 사용자 개입 최소화

### 3. 품질 유지
- 심층 분석 포함 (15~20분 읽을 분량)
- 신뢰할 수 있는 소스 인용
- 한국어로 작성

## 파일 구조

```
.claude/
├── CLAUDE.md              ← 이 파일
├── settings.local.json    ← 권한 설정 (WebSearch만)
├── SCHEDULED_TASKS.md     ← 스케줄 에이전트 설명
└── skills/
    ├── github-issue-tracker/   # 저장소 문제 분석
    └── auto-issue-resolver/    # 이슈 자동 해결
```

## 스케줄 에이전트

**이름:** `daily-ai-trend-report`  
**실행:** 매일 오전 8시 (0 8 * * *)  
**동작:**
1. WebSearch 실행 (1회)
2. HTML 리포트 생성
3. 브라우저 자동 오픈

## 스킬 가이드

### github-issue-tracker
저장소의 문제점(README, .gitignore, LICENSE, 과다 권한)을 파악하고 GitHub Issues로 등록합니다.
```
/github-issue-tracker repo_path: <경로>
```

### auto-issue-resolver
OPEN 이슈를 분석하고, 댓글 작성 → 파일 생성 → 커밋 → 이슈 닫기를 자동화합니다.
```
/auto-issue-resolver repo_path: <경로>
```

## 개발 가이드라인

### HTML 리포트 생성
- 다크모드 디자인 (배경 #0f1117, 카드 #1a1d27)
- 섹션: 핵심 뉴스 → 딥다이브 → 오픈소스 → 기업 동향 → 학습 포인트
- 파일명: `YYYY-MM-DD-ai-report.html`

### 커밋 메시지
- 형식: `type: 설명`
- 타입: feat, fix, docs, refactor
- 예: `feat: Add daily AI trend report generator`

### 토큰 최적화
- 간단한 질문엔 짧게 답변
- 불필요한 설명 제거
- 구체적인 지시 우선

## 문제 해결

**스킬이 인식 안 됨:** Claude Code 재시작 필요

**리포트 생성 안 됨:** 스케줄 에이전트 실행 상태 확인 (Scheduled 탭)

**토큰 초과:** WebSearch 회수 줄이기, 불필요한 fetch 제거

## 참고 자료

- README.md — 프로젝트 사용법
- SCHEDULED_TASKS.md — 스케줄 설정 상세
- ISSUES.md — 완료된 이슈 추적
