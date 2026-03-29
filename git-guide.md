# aaa 레포지토리 Git 사용 가이드

터미널에서 커밋 & 푸시하는 방법을 설명합니다.

---

## 1. 처음 설정 (최초 1회만)

### 레포지토리 클론
```bash
git clone https://github.com/selfishclub-all/aaa.git
cd aaa
```

### 이름 & 이메일 설정
```bash
git config --global user.name "본인이름"
git config --global user.email "깃허브이메일@example.com"
```

---

## 2. GitHub 인증 설정

터미널에서 푸시할 때는 **Personal Access Token(PAT)**이 필요합니다.
(GitHub는 비밀번호 인증을 더 이상 지원하지 않습니다.)

### PAT 발급 방법
1. GitHub → 우측 상단 프로필 → **Settings**
2. 좌측 하단 **Developer settings** → **Personal access tokens** → **Tokens (classic)**
3. **Generate new token (classic)** 클릭
4. `repo` 항목 체크 후 생성
5. 발급된 토큰 복사 (창을 닫으면 다시 볼 수 없음)

### 토큰 등록
아래 명령어 실행 후 비밀번호 입력란에 **토큰을 붙여넣기**
```bash
git push origin main
# Username: 깃허브 아이디
# Password: (토큰 붙여넣기)
```

한 번 인증하면 맥 키체인에 저장되어 이후에는 자동 로그인됩니다.

---

## 3. 매일 사용하는 기본 흐름

### 작업 전: 최신 내용 받아오기
```bash
git pull origin main
```

### 파일 수정 후: 변경사항 확인
```bash
git status
```

### 변경된 파일 스테이징
```bash
# 특정 파일만
git add 파일명.md

# 전체 변경사항
git add .
```

### 커밋 메시지 작성
```bash
git commit -m "커밋 내용을 여기에 작성"
```

### 푸시
```bash
git push origin main
```

---

## 4. 한 번에 실행하기

```bash
git pull origin main
git add .
git commit -m "작업 내용"
git push origin main
```

---

## 5. 자주 쓰는 명령어 모음

| 명령어 | 설명 |
|--------|------|
| `git status` | 변경된 파일 목록 확인 |
| `git log --oneline` | 커밋 히스토리 간략히 보기 |
| `git diff` | 수정 내용 상세 비교 |
| `git pull origin main` | 원격 최신 내용 받아오기 |
| `git push origin main` | 원격에 업로드 |

---

## 6. 주의사항

- `.obsidian/`, `.DS_Store`, `.omc/` 파일은 `.gitignore`에 등록되어 있어 자동으로 제외됩니다.
- 푸시 전에 항상 `git pull`로 최신 상태를 받아오세요. 충돌을 예방할 수 있습니다.
- 커밋 메시지는 **무엇을 했는지** 알 수 있게 작성해주세요. (예: `"흐민 Week_01 미션 제출"`)
