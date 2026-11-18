# docs/ — GitHub Pages

이 폴더가 그대로 Pages 로 서빙됩니다.
**Settings → Pages** → Source: `Deploy from a branch`, Branch: `main` / 폴더 `/docs`.

공개된 페이지는 **랜딩(`index.html`) 하나**입니다. 창 소개 · 요구 사항 · 문제 신고와
다운로드 버튼이 들어 있고, **영문 기본 · 한국어 토글**(EN/KO)입니다.

## 주의

- **랜딩은 영어가 기본입니다.** 본문은 `.en`/`.ko` 스팬 쌍으로 나란히 들어 있고
  `html[lang]` 이 한쪽만 보여줍니다 — 문구를 고칠 때는 **두 언어를 같이** 고치십시오.
  스크립트가 만드는 글자(다운로드 버튼 · 메타 · `<title>`)는 스크립트 안 사전에 있습니다.
  선택은 `localStorage("dno-lang")` 에 저장됩니다.
- **버전 표시는 GitHub API 에서 읽습니다.** 릴리스를 내면 자동으로 따라옵니다.
  `/releases/latest` 는 프리릴리즈를 건너뛰므로 목록에서 초안 아닌 첫 항목을 씁니다.
- **웹 재현(`demo.html`)은 저장소에서 지웠습니다** (2026-11-18, 정식 출시 전까지 보류). 앱 2.0 과 모양이
  어긋나 있었습니다. 되살리려면 git 이력에서 `demo.html` · `support.js` · `_ds/` · `uploads/` ·
  `assets/logos/` · `assets/wheel.png` 와 TTF/OTF 폰트를 함께 되돌리십시오.
- **파일 이름을 바꾸지 마십시오.** `index.html` 이 `Fonts/` · `assets/` · `downloads/` 를 상대 경로로 씁니다.

## 들어 있는 것

| 경로 | 용도 |
|---|---|
| `index.html` | 랜딩. 앱 디자인 시스템(앱 저장소 `DESIGN.md`)의 블랙 테마 · 글자 세 단 · Exo 2 를 씁니다 |
| `poster.webp` | 옛 랜딩 히어로 포스터 (33KB) — 지금은 `og:image` 로만 씁니다 |
| `preview.webp` | 8초 애니메이션 (8.6MB) — **아무 데서도 쓰지 않습니다** |
| `assets/app.ico`, `assets/icon-256.png` | 파비콘 · 애플 터치 아이콘 — 앱과 같은 트레이스 그래프 N 로고(앱 `src/DotNetOverlay/assets/app.ico` 그대로) |
| `downloads/` | SimHub 대시 · 플러그인 — 앱 릴리스와 따로 둔다(릴리스로 만들면 랜딩 버튼 · 앱 업데이터가 앱으로 착각한다) |
| `assets/logo-32.svg` | 랜딩 헤더 로고 — 앱 저장소 `tools/out/logo-refine/final` 의 32px 판 |
| `Fonts/` | `.woff2` — Exo 2 Tnum 400 · 600 · 700, JetBrains Mono, Pretendard(한글 범위만). 원본은 앱 저장소 `src/DotNetOverlay/Fonts`, 변환은 fontTools(`flavor='woff2'`). Exo 2 라이선스 `OFL-Exo2.txt` |
