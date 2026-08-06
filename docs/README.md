# docs/ — GitHub Pages

이 폴더가 그대로 Pages 로 서빙됩니다.
**Settings → Pages** → Source: `Deploy from a branch`, Branch: `main` / 폴더 `/docs`.

공개된 페이지는 **랜딩(`index.html`) 하나**입니다. 설치 안내 · 요구 사항 · 문제 신고와,
클릭하면 그 자리에서 실행되는 재현이 들어 있습니다.

## 주의

- **`demo.html` 을 지우지 마십시오.** 어디에서도 링크하지 않지만 랜딩이 이 파일을
  `iframe` 으로 부릅니다 — 지우면 재현이 통째로 죽습니다. 직접 열면
  (`/demo.html?demo`) 재현만 전체 화면으로 뜨는데, 그 주소를 안내하지는 않습니다.
- **파일 이름을 바꾸지 마십시오.** `demo.html` 이 `assets/…`, `uploads/…`, `Fonts/…`,
  `_ds/…` 를 상대 경로로 참조합니다.
- **랜딩의 리모컨은 상태를 들지 않습니다.** 컨트롤 줄은 재현 안에 통째로 있고(`#ctl`),
  `?demo` 모드가 그 줄을 `display:none` 으로 덮을 뿐 지우지 않습니다. 랜딩의 버튼은
  `#ctl` 안의 체크박스·라디오를 **라벨 글자로 찾아**(`data-lb` 값) 대신 눌러 주고
  결과(`checked`)를 읽어 자기 모습을 맞춥니다. 같은 출처라서 성립하는 구조입니다.
  따라서 **재현의 라벨 글자를 바꾸면 그 버튼만 조용히 먹통이 됩니다** — 창 토글
  (`입력`·`Relative`·`Standings`·`날씨`·`바람`·`스포터`·`접근`·`델타`),
  `배치 모드 (파란 외곽선)`, 티어(`T1 · 560×320` 같은 치수 라벨), INPUT 표시
  (`축 라벨`·`속도 · 기어 워터마크`·`입력 바 (CLU · BRK · THR)`·
  `휠 패널 표시`), `원형 림`/`Ascher 사진`, 델타 기준 `PB`/`SB`/`LAST`.
  라벨을 고칠 때는 `index.html` 의 `data-lb` 도 같이 고치십시오.
- **랜딩은 재현을 자동 로드하지 않습니다.** 배경 영상이 8MB 라 포스터(`poster.webp`,
  33KB)만 먼저 띄우고 누른 사람에게만 iframe 을 붙입니다.
- **버전 표시는 GitHub API 에서 읽습니다.** 릴리스를 내면 자동으로 따라옵니다.
- 영상 7.6MB 를 빼려면 `demo.html` 의 `<video src>` 를 외부 URL 로 바꾸십시오 —
  없어도 오버레이는 정상 동작합니다(배경만 검게). 자동재생에 `muted` 가 필요합니다(적용됨).

## 들어 있는 것

| 경로 | 용도 |
|---|---|
| `index.html` | 랜딩 (자체 완결 — `_ds` 에 의존하지 않습니다) |
| `demo.html` | 재현 — 랜딩의 iframe 소스 (`support.js` + `_ds` 필요) |
| `support.js` | 런타임 — 반드시 같은 폴더에 |
| `poster.webp` | 랜딩 히어로 포스터 (33KB) |
| `preview.webp` | 8초 애니메이션 (8.6MB) — **지금은 아무 데서도 쓰지 않습니다** |
| `uploads/*.mp4` | 배경 온보드 영상 7.6MB |
| `assets/logos/`, `assets/wheel.png` | 제조사 로고 20개 · 휠 사진 |
| `Fonts/` | JetBrains Mono · Pretendard |
| `_ds/` | 디자인 시스템 스타일시트 |
