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
- **재현(`demo.html`)은 랜딩에서 빠졌습니다** (2026-09). 파일은 남아 있고
  `/demo.html?demo` 로 직접 열면 전체 화면 재현이 뜨지만, 어디에서도 링크하지 않습니다.
  랜딩과의 리모컨 연동 코드도 랜딩에서 제거됐으니 라벨 계약은 더 이상 없습니다.
  다시 살리려면 git 이력의 랜딩(리모컨 포함)을 되돌리십시오.
- **파일 이름을 바꾸지 마십시오.** `demo.html` 이 `assets/…`, `uploads/…`, `Fonts/…`,
  `_ds/…` 를 상대 경로로 참조하고, `index.html` 도 `Fonts/` 와 `assets/app.ico` 를 씁니다.

## 들어 있는 것

| 경로 | 용도 |
|---|---|
| `index.html` | 랜딩 (자체 완결 — `_ds` 에 의존하지 않습니다) |
| `demo.html` | 재현 — 랜딩에서 빠짐, `/demo.html?demo` 직접 접근만 (`support.js` + `_ds` 필요) |
| `support.js` | 재현 런타임 — 반드시 같은 폴더에 |
| `poster.webp` | 옛 랜딩 히어로 포스터 (33KB) — 지금은 `og:image` 로만 씁니다 |
| `preview.webp` | 8초 애니메이션 (8.6MB) — **아무 데서도 쓰지 않습니다** |
| `uploads/*.mp4` | 재현 배경 온보드 영상 7.6MB |
| `assets/logos/`, `assets/wheel.png` | 재현용 제조사 로고 · 휠 사진 |
| `assets/app.ico`, `assets/icon-256.png` | 파비콘 · 애플 터치 아이콘 |
| `Fonts/` | JetBrains Mono · Pretendard (랜딩 · 재현 공용) |
| `_ds/` | 재현용 디자인 시스템 스타일시트 |
