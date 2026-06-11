---
name: auto-issue-resolver
description: GitHub 저장소의 열린 이슈를 자동 분석하고 해결 계획을 댓글로 작성한 후 필요한 파일을 생성해 이슈를 닫는 스킬. 신규 프로젝트 문서화, README/LICENSE/.gitignore 추가 등 반복적인 초기 셋업 작업 자동화. 저장소 경로만 제공하면 이슈 분석→댓글→파일 생성→커밋→이슈 닫기를 일괄 처리.
---

## 개요

GitHub 저장소의 열린 이슈를 자동으로 해결합니다.

## 동작 흐름

### 1단계: 이슈 확인
```powershell
gh issue list
```
OPEN 상태인 모든 이슈 조회

### 2단계: 이슈별 분석 및 댓글 작성
각 이슈의 제목과 설명을 파악하여:
- 해결 계획 수립
- 우선순위 판단 (High/Medium/Low)
- 댓글로 처리 계획 작성

```powershell
gh issue comment <NUMBER> -b "처리 계획..."
```

### 3단계: 파일 생성
이슈 타입에 따라 자동 생성:

| 이슈 | 생성 파일 | 내용 |
|------|---------|------|
| Add README | README.md | 프로젝트 개요, 설정, 사용법 |
| Add .gitignore | .gitignore | 제외할 파일/폴더 목록 |
| Add LICENSE | LICENSE | MIT/Apache 라이선스 |
| Save Configuration | 설정문서.md | 프로젝트 설정 정보 |

### 4단계: Git 커밋 & 푸시
```powershell
git add .
git commit -m "docs: 자동 생성된 파일"
git push
```

### 5단계: 이슈 닫기
```powershell
gh issue close <NUMBER>
```

## 입력

- **repo_path**: 로컬 저장소 경로
  - 예: `C:\Users\Admin\Desktop\ai-report`

## 출력

- 처리된 이슈 목록 (번호, 제목)
- 생성된 파일 목록
- GitHub 커밋 해시

## 사용 예시

**입력:**
```
저장소 경로: C:\Users\Admin\Desktop\my-project
```

**출력:**
```
✓ #1 Add README.md → README.md 생성
✓ #2 Add .gitignore → .gitignore 생성  
✓ #3 Add LICENSE → LICENSE 생성

총 3개 이슈 해결
커밋: abc1234def5678
```

## 기술 요구사항

- gh CLI 설치 및 인증
- Git 설치 및 설정 완료
- 저장소에 쓰기 권한

## 주의사항

- 이미 닫힌 이슈는 제외
- 중복 파일 생성 방지
- 커밋 전 기존 파일 백업 권장
