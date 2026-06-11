# AI & 에이전트 동향 리포트

매일 오전 8시에 최신 AI 및 에이전트 동향을 심층 분석하여 HTML 리포트로 자동 생성하는 프로젝트입니다.

## 개요

- **실행 시간**: 매일 오전 8시 (자동)
- **보고 형식**: HTML (다크모드, 브라우저 자동 오픈)
- **저장 위치**: `C:\Users\Admin\Desktop\ai-report\`
- **주요 섹션**: 핵심 뉴스, 딥다이브 분석, 오픈소스 & 툴, 기업 동향, 학습 포인트

## 파일 구조

```
ai-report/
├── README.md                 # 이 파일
├── ISSUES.md                 # 추적 중인 작업 목록
├── .gitignore                # Git 제외 파일
├── LICENSE                   # MIT 라이선스
├── .claude/
│   ├── settings.local.json   # Claude Code 설정
│   └── skills/               # 커스텀 스킬
├── YYYY-MM-DD-ai-report.html # 일일 리포트 (자동 생성)
```

## 설정

### 스케줄 에이전트 (Claude Code)

매일 오전 8시에 다음을 자동 실행:
1. AI 관련 뉴스 웹 검색 (1회)
2. HTML 리포트 생성
3. 브라우저에서 자동 오픈

**스케줄 ID**: `daily-ai-trend-report`  
**실행 시간**: `0 8 * * *` (매일 오전 8시, 로컬 시간대)

### 필수 요구사항

- Claude Code 또는 Claude 데스크톱 앱
- GitHub CLI (`gh`) 설치 및 인증

## 생성되는 리포트

각 리포트는 다음을 포함합니다:

- **오늘의 핵심 뉴스**: 3~5개 주요 뉴스 + 심층 해설
- **오늘의 딥다이브**: 기술적 배경이 포함된 1개 주제 분석
- **주목할 오픈소스 & 툴**: 새 모델/프레임워크 소개
- **주요 AI 기업 동향**: OpenAI, Anthropic, Google, Meta 등
- **오늘의 학습 포인트**: 3가지 핵심 개념

## 스킬

### github-issue-tracker

저장소 문제점을 파악하고 GitHub Issues에 자동 등록합니다.

```bash
/github-issue-tracker
저장소 경로: C:\Users\Admin\Desktop\ai-report
```

## 라이선스

MIT License - 자유롭게 사용, 수정, 배포 가능
