# Project Configuration & Philosophy

## 핵심 원칙

**효율성** | 토큰 3%/일로 365일 자동화  
**신뢰성** | 15~20분 심층 분석 + 출처 명시  
**지속성** | 매일 8시 자동, 자동화된 워크플로우  
**학습** | 매일 3개 핵심 개념으로 AI 전문화  

## 스케줄 에이전트

| 항목 | 값 |
|------|-----|
| 이름 | daily-ai-trend-report |
| 시간 | 0 8 * * * (매일 오전 8시) |
| 검색 | WebSearch 1회 (스니펫만) |
| 출력 | HTML 리포트 + 브라우저 오픈 |

**리포트 구성:** 핵심 뉴스(4~5) → 딥다이브(1) → 오픈소스(2~3) → 기업 동향 → 학습 포인트(3)

## 스킬 설명

### github-issue-tracker
저장소 분석 → 문제점 목록화 → GitHub Issues 자동 등록
- README.md/LICENSE/.gitignore 존재 여부
- 과다 권한 설정 (예: WebFetch)
- 중복 이슈 자동 체크

### auto-issue-resolver  
OPEN 이슈 분석 → 댓글(처리 계획) → 파일 생성 → 커밋 → 이슈 닫기
- 이슈 타입별 자동 파일 생성
- Git 자동 커밋 & 푸시
- 모든 이슈 일괄 처리

## 개발 가이드

### HTML 리포트
- 배색: 배경 #0f1117, 카드 #1a1d27, 강조 #6c63ff
- 폰트: Inter (Google Fonts)
- 반응형 다크모드 디자인

### 커밋 메시지
```
type: 설명 (한 줄)

상세 설명 (필요시)

Co-Authored-By: Claude Haiku 4.5 <noreply@anthropic.com>
```
타입: feat, fix, docs, refactor

### 토큰 최적화
- WebSearch 1회만 (fetch 최소)
- 불필요한 대화 제거
- 구체적 지시 우선
- 월간 36% 한도 관리

## 문제 해결

| 문제 | 해결 |
|------|------|
| 스킬 안 인식 | Claude Code 재시작 |
| 리포트 미생성 | Scheduled 탭 확인 |
| 토큰 초과 | WebSearch 회수 감소 |
| 이슈 미처리 | auto-issue-resolver 실행 |

## 1년 목표

- ✅ 366일 연속 리포트 생성
- ✅ AI 동향 심층 이해 형성
- ✅ 스킬 다른 프로젝트 활용
- ✅ 토큰 효율성 유지 (36%)

---

**철학:** 효율성과 신뢰성의 균형. 매일 조금씩, 자동으로, 흔들리지 않게.
