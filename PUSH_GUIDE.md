# GitHub 푸시 가이드

이 가이드를 따라하면 `kill-or-ship` 저장소를 GitHub에 공개할 수 있습니다.

---

## STEP 1. GitHub에서 빈 저장소 만들기

1. [github.com/new](https://github.com/new) 접속.
2. **Repository name**: `kill-or-ship`.
3. **Description** (선택): `PMF 검증과 마케팅 전략에 대한 구조적 피드백을 제공하는 자기 진화형 Claude 스킬`.
4. **Public** 선택.
5. **"Add a README file" 등 모든 옵션 체크 해제**. 이미 README가 준비되어 있음.
6. **"Create repository"** 클릭.

---

## STEP 2. 로컬에서 푸시

다운로드 받은 `kill-or-ship-public` 폴더를 열고, 터미널에서 그 폴더 안으로 이동한 뒤 아래 명령어를 순서대로 실행합니다.

`YOUR_USERNAME` 부분은 GitHub 사용자명으로 바꿔주세요.

```bash
# 폴더로 이동 (다운로드 위치에 맞게 조정)
cd ~/Downloads/kill-or-ship-public

# Git 초기화
git init

# 모든 파일 staging
git add .

# 첫 커밋
git commit -m "Initial commit: kill-or-ship v0.1.0"

# main 브랜치로 설정
git branch -M main

# 원격 저장소 연결 (YOUR_USERNAME 교체)
git remote add origin https://github.com/YOUR_USERNAME/kill-or-ship.git

# 푸시
git push -u origin main
```

---

## STEP 3. (선택) Release 만들기

`.skill` 파일을 다른 사람이 쉽게 다운로드 받게 하려면 GitHub Release를 만드세요.

1. 저장소 페이지에서 **"Releases"** 클릭.
2. **"Create a new release"** 클릭.
3. **Tag**: `v0.1.0`.
4. **Title**: `v0.1.0 - Initial Release`.
5. **Description**: 첫 릴리즈 메모 작성.
6. **Attach binaries**: `releases/kill-or-ship.skill` 파일 첨부.
7. **"Publish release"** 클릭.

---

## 푸시 후 할 일

- [ ] README에 적힌 클론 URL의 `[사용자]` 부분을 실제 사용자명으로 수정 후 재푸시.
- [ ] Repository에 Topics 추가 (예: `claude`, `claude-skills`, `marketing`, `pmf`, `validation`).
- [ ] About 섹션에 한 줄 설명 추가.
- [ ] (선택) Issues 템플릿, PR 템플릿 추가.

---

## 문제 해결

**"remote: Permission denied" 에러가 나면**
- GitHub 인증 필요. [Personal Access Token](https://github.com/settings/tokens) 발급해서 사용.

**"main vs master" 에러가 나면**
- `git branch -M main` 명령어 한 번 더 실행.

**파일이 너무 많아서 푸시가 느리면**
- 정상입니다. 첫 푸시는 시간이 좀 걸려요.
