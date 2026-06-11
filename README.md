# AI & 에이전트 동향 리포트

매일 오전 8시 최신 AI/에이전트 뉴스를 분석하여 HTML 리포트로 자동 생성합니다.

## 구조

```
.
├── README.md                      # 이 파일
├── LICENSE                        # MIT
├── .gitignore
├── 2026-06-11-ai-report.html     # 일일 리포트 (자동 생성)
└── .claude/
    ├── PROJECT.md                 # 설정 & 철학
    ├── settings.local.json        # 권한 (WebSearch만)
    └── skills/
        ├── github-issue-tracker/  # 저장소 문제 분석
        └── auto-issue-resolver/   # 이슈 자동 해결
```

## 실행

### 스케줄 에이전트
- **시간:** 매일 오전 8시
- **동작:** WebSearch 1회 → HTML 생성 → 브라우저 오픈
- **파일:** `YYYY-MM-DD-ai-report.html`

### 스킬

```bash
# 저장소 문제 파악 & 이슈 등록
/github-issue-tracker repo_path: C:\path\to\repo

# 이슈 자동 해결 (분석 → 댓글 → 파일 생성 → 커밋 → 닫기)
/auto-issue-resolver repo_path: C:\path\to\repo
```

## 설정

- 토큰 한도: 일일 3% (월 ~36%)
- 필요시 `.claude/PROJECT.md` 참고
