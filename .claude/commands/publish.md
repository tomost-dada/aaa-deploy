스터디 아카이브 사이트를 업데이트하고 배포해줘.

## 실행 절차

### 1. 콘텐츠 동기화
vault의 공개 폴더를 Quartz 프로젝트로 복사:
```bash
bash /Users/dada/PJ/AAA/selfish-aaa-site/sync-content.sh
```

### 2. Quartz 빌드 테스트
```bash
cd /Users/dada/PJ/AAA/selfish-aaa-site && npx quartz build
```
에러가 있으면 수정 후 다시 빌드.

### 3. 커밋 & Push
```bash
cd /Users/dada/PJ/AAA/selfish-aaa-site
git add content/
git commit -m "콘텐츠 업데이트"
git push origin v4
```

Push하면 GitHub Actions가 자동으로 GitHub Pages에 배포합니다.

### 4. 결과 확인
배포 URL: https://selfishclub-all.github.io/aaa-archive/
