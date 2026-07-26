# Academic portfolio (HCI)

깔끔한 학술 포트폴리오 사이트입니다. 빌드 도구 없이 순수 HTML/CSS/JS로만 되어 있어서
GitHub Pages에 그대로 올리면 바로 뜹니다.

```
index.html          About / 랜딩 (자기소개 · 연구 키워드 · 연락처)
research.html       연구 관심사 & 비전  ← 강조 페이지
publications.html   논문 목록 (연도별)   ← 강조 페이지
projects.html       프로젝트 카드
styles.css          공용 스타일 (색·폰트 전부 여기서 관리)
main.js             모바일 메뉴 토글
assets/             cv.pdf, 이미지 등을 넣는 폴더
```

## 디자인 컨셉

HCI가 **사람(Human) ↔ 컴퓨터(Computer)** 사이에 있다는 점을 타이포로 표현했습니다.
- **Newsreader (세리프)** — 사람이 읽는 문장, 이름, 제목
- **IBM Plex Sans** — 본문
- **IBM Plex Mono** — 기계·메타데이터 (연도, 학회명, 링크 라벨)
- 흰 배경 · 검정 글씨가 기본, **파랑(`#1747cc`)은 강조에만** 사용

---

## 내 정보로 바꾸기 (체크리스트)

지금은 `Jiwon Kim`이라는 예시 내용이 채워져 있습니다. 아래만 바꾸면 됩니다.

1. **이름** — 네 파일 전부에서 `Jiwon Kim` 을 본인 이름으로 찾아 바꾸기.
   (에디터의 "전체 찾아 바꾸기"로 한 번에 처리 가능)
2. **이메일** — `you@example.com` 을 본인 이메일로.
3. **링크** — `scholar.google.com`, `github.com/yourhandle`,
   `linkedin.com/in/yourhandle` 를 본인 주소로.
4. **소개/연구 내용** — `index.html`의 About, `research.html` 전체를 본인 이야기로.
   `[University]`, `[Your Major]`, `[a sentence about you...]` 같은 대괄호 부분이
   전부 채워 넣어야 할 자리입니다.
5. **논문** — `publications.html`의 각 `<article class="pub">` 블록을 본인 논문으로.
   아직 논문이 없다면 이 페이지는 지워도 됩니다 (아래 "페이지 추가/삭제" 참고).
6. **CV** — 본인 이력서 PDF를 `assets/cv.pdf` 로 저장. (지금은 링크만 있고 파일은 없음)
7. **색을 바꾸고 싶다면** — `styles.css` 맨 위 `:root`에서 `--blue` 값만 바꾸면
   사이트 전체 강조색이 한 번에 바뀝니다.

### 페이지 추가/삭제

- **삭제**: 예) Projects를 빼려면 `projects.html`을 지우고, 나머지 3개 파일의
  상단 `<nav>`에서 `<a href="projects.html">Projects</a>` 줄을 지우세요.
- **추가**: 기존 html 파일 하나를 복사해서 이름만 바꾸고, 모든 파일의 `<nav>`에
  같은 링크를 추가하면 됩니다. (헤더/푸터는 모든 파일에 동일하게 들어 있으니
  하나를 고치면 나머지도 똑같이 맞춰 주세요.)

---

## GitHub Pages로 배포하기

1. GitHub에서 새 저장소를 만듭니다. 개인 사이트로 쓸 거면 이름을
   **`본인아이디.github.io`** 로 하는 걸 추천합니다 (그러면 주소가 그대로 사이트 URL이 됩니다).
2. 이 폴더의 파일들을 저장소 최상단(root)에 올립니다.

   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/본인아이디/본인아이디.github.io.git
   git push -u origin main
   ```

3. 저장소 → **Settings → Pages** 로 이동합니다.
4. **Source**를 `Deploy from a branch`, 브랜치를 `main` / 폴더를 `/ (root)`로 설정하고 저장.
5. 1~2분 뒤 `https://본인아이디.github.io` 에서 사이트가 뜹니다. 🎉

> 저장소 이름을 `본인아이디.github.io`가 아닌 다른 이름(예: `portfolio`)으로 했다면
> 주소는 `https://본인아이디.github.io/portfolio/` 가 됩니다. 이 경우에도 파일 간
> 링크가 상대경로라서 그대로 잘 동작합니다.

---

## 로컬에서 미리 보기

파일을 그냥 브라우저로 열어도 되지만, 폰트/링크까지 실제와 똑같이 보려면
간단한 로컬 서버를 띄우는 게 좋습니다.

```bash
# Python이 있으면
python3 -m http.server 8000
# → 브라우저에서 http://localhost:8000
```

인터넷 연결이 있으면 Google Fonts(Newsreader, IBM Plex)가 자동으로 로드됩니다.
