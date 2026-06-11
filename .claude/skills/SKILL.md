---
name: github-issue-tracker
description: GitHub 저장소의 문서, 설정, 라이선스 문제점을 파악하고 자동으로 GitHub Issues에 등록하는 스킬. 신규 프로젝트 초기화, 코드 리뷰 시 구조적 문제 추출, 팀 프로젝트 표준 준수 확인에 사용. 저장소 경로나 URL만 지정하면 README, .gitignore, LICENSE, 권한 설정 문제를 자동 분석하고 이슈로 등록.
---

## 개요

GitHub 저장소의 구조적 문제점을 분석하고 자동으로 이슈로 등록합니다.

## 동작 방식

### 1단계: 저장소 분석
다음을 검사합니다:
- README.md 존재 여부
- .gitignore 존재 여부  
- LICENSE 파일 존재 여부
- .claude/ 설정 파일 상태
- WebFetch 등 과다 권한 설정

### 2단계: 문제 목록화
발견된 각 문제를 다음 형식으로 정리:
```
## [제목]
**Priority:** High/Medium/Low
**Description:** 상세 설명
```

### 3단계: GitHub Issues 자동 등록
gh CLI를 사용해 각 문제를 이슈로 자동 등록합니다.

## 입력
- **repo_path**: 로컬 경로 또는 GitHub URL (예: `C:\Users\Admin\Desktop\ai-report` 또는 `numbery-jspark/ai-report`)
- **check_items** (선택): 검사 항목 지정 (기본: 전체)

## 출력
- 생성된 GitHub Issues 링크 목록
- 각 이슈 번호와 제목

## 사용 예시

**입력:**
```
저장소 경로: C:\Users\Admin\Desktop\my-project
```

**출력:**
```
✓ Issue #1: Add README.md
✓ Issue #2: Add .gitignore  
✓ Issue #3: Add LICENSE
```

## 기술 요구사항
- gh CLI 설치 필요 (PATH 등록됨)
- GitHub 인증 필수 (`gh auth login`)
- 중복 이슈 자동 체크
