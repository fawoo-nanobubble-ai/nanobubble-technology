# Design Guide — FAWOO NANOTECH (화우나노텍)

> 이 문서는 이 프로젝트의 디자인 기준이다.
> 모든 화면, 문서, 인포그래픽/도면은 이 문서를 먼저 읽고 따른다.
> 규칙과 어긋나면 만들기 전에 멈추고 나에게 물어본다.

## 1. Overview
- 브랜드명: FAWOO NANOTECH (화우나노텍)
- 한 문장: 초고농도 나노버블 생성 기술로 반도체·농업·환경 분야의 새로운 글로벌 표준을 제시하는 기술 리더
- 무드 키워드: 정밀한 / 신뢰감 있는 / 산업·엔지니어링 중심 / 데이터 기반
- 느낌 비교: 기술 백서·엔지니어링 스펙시트 같은 절제된 테크니컬 톤 O · 마케팅스러운 화려한 색감·과한 그래픽 X
- 근거 문서: `README.md`, `Application_Cases.md`, `Comparison_Analysis.md` (제품 스펙·수치는 항상 이 문서들과 일치시킨다)

## 2. Colors
- Navy (주 브랜드/헤더/제목): `#12365c`
- Teal (보조 포인트/eyebrow 라벨): `#0e7490`
- Ink (본문 텍스트): `#16202c`
- Sub (보조 텍스트): `#475569`
- Muted (캡션·최소 강조): `#7b8794`
- Line (구분선/테두리): `#dbe2ea`
- Card: `#ffffff` · Page Background: `#eef1f5`
- 의미 기반 색상 (수치/도면에서 항목 구분용, 임의 변경 금지)
  - Cathode/H₂ 계열 (파랑): `#2563eb` / fill `#dbeafe` / soft `#eff6ff`
  - Anode/O₂ 계열 (빨강): `#dc2626` / fill `#fee2e2` / soft `#fef2f2`
  - Membrane 계열 (호박색): `#d97706` / fill `#fde68a`
  - 구조재 계열 (슬레이트): `#64748b` / fill `#cbd5e1`
  - 이온/전기 계열 (보라): `#7c3aed` / soft `#f5f3ff`
  - 긍정/OK (초록): `#15803d` / soft `#f0fdf4`
  - 경고/WARN (적갈): `#b91c1c` / soft `#fdf2f2`
- 규칙: 색은 위계와 의미에만 사용한다. 브랜드색(Navy/Teal)은 제목·라벨·CTA에만, 카드 배경은 항상 중립(흰색/연회색)으로 유지한다. 의미 기반 색상은 문서 전체에서 같은 항목에 항상 같은 색을 쓴다 (예: H₂=파랑 고정, O₂=빨강 고정).

## 3. Typography
- 폰트: `"Malgun Gothic", "맑은 고딕", "Apple SD Gothic Neo", sans-serif` (한/영 혼용 문서 기준. 웹 전용 산출물에서는 Pretendard로 대체 가능하나 임의 혼용 금지, 프로젝트당 하나만 사용)
- Title(H2급) 18.5px / 800 / Navy / letter-spacing -.01em
- Eyebrow(라벨) 11.5px / 800 / Teal / uppercase / letter-spacing .12em
- Lead(부제) 13.5px / Regular / Sub
- 본문 12.3~13.5px / Regular / Sub, 강조는 `<b>`로 Ink
- 캡션 12px / Regular / Muted
- 행간: 본문 1.5~1.6, word-break: keep-all (한글 줄바꿈 어색함 방지)
- 규칙: 위계는 크기·굵기·색(Navy/Teal/Ink/Sub/Muted)으로만 표현한다. 폰트 종류를 늘리지 않는다.

## 4. Layout
- 콘텐츠 최대 너비: 1000px (`.wrap`)
- 기본 패딩: 36px 40px (컨테이너), 카드 내부 26px 28px 22px
- 카드 간 여백: 30px
- 규칙: 위 값 기준에서 크게 벗어나는 어중간한 여백을 쓰지 않는다. 여백이 좁아 답답해 보이는 것보다 넉넉한 여백을 우선한다.

## 5. Elevation & Depth
- 카드: `0 1px 2px rgba(16,32,44,.04), 0 8px 24px rgba(16,32,44,.06)` (은은한 이중 그림자)
- 콜아웃/노트 박스: 그림자 없음 — 1px 라인(`--line`)과 좌측 4px 컬러 스트라이프로만 구분
- 규칙: 그림자를 과하게 쓰지 않는다. 카드 하나 정도의 부유감만 허용하고, 나머지는 면과 라인으로 위계를 만든다.

## 6. Shapes
- 카드: 14px 라운드
- 콜아웃/노트: 8~10px 라운드
- 뱃지/태그: pill (완전 둥글게), 범례 스와치: 4px 라운드
- 규칙: 라운드 값은 위 세 단계(14 / 8~10 / pill)로만 통일한다.

## 7. Components
- 카드(`.info`): 흰 배경, 14px 라운드, 1px 라인 테두리, 이중 그림자. eyebrow(Teal) → title(Navy) → lead(Sub) 순서 고정.
- 콜아웃(`.callout`): 좌측 4px 컬러 스트라이프 + 해당 색의 옅은 배경(`*-soft`/`*-fill`). 헤더는 아이콘/의미색, 본문은 Sub, 강조어만 Ink.
- 태그/뱃지(`.tag`): 짙은 의미색 배경 + 흰 글자, pill, 작은 캡션용.
- 표(`.dtab`): 헤더 배경 연한 블루그레이(`#eef3f8`) + Navy 글자, 셀 테두리는 `--line`.
- 노트 박스(`.note`): 연회색 배경(`#f7f9fb`), Navy 제목 + Sub 본문.
- 범례(`.legend`): 상단 라인 구분 후 색 스와치 + 라벨 나열.
- 규칙: 새 컴포넌트를 추가할 때도 이 5종(카드/콜아웃/태그/표/노트)의 톤을 벗어나지 않는다.

## 8. Do's and Don'ts
- 폰트 2종 이상 혼용 금지
- 브랜드색(Navy/Teal) 외의 색을 장식으로 남용 금지 — 색은 항상 의미(H₂/O₂/격막/OK/WARN 등)를 가져야 한다
- 카드 배경을 알록달록하게 채색 금지 (중립면 + 콜아웃 좌측 스트라이프로만 색 구분)
- 과한 그라데이션, 진한 그림자, 불필요한 장식 아이콘 금지
- 수치·스펙은 항상 `README.md` / `Comparison_Analysis.md`와 일치시키고, 임의로 수치를 만들거나 반올림하지 않는다
- 새 도면/인포그래픽 작업 시 `~/.claude/skills/hwawoo-infographic`의 규칙(도형=SVG, 텍스트=CSS 박스, 오버플로우 검증)을 그대로 따른다
