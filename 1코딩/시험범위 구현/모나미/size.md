현재 열린 MONAMI 페이지를 Playwright로 확인한 값입니다. 브라우저 표시 폭 1365px, 실제 페이지 폭 1350px 기준이며, 아래 수치는 화면에서 측정한 CSS 픽셀입니다.

| 영역 | 크기와 위치 | 구현에 필요한 값 |
|---|---|---|
| .head_top | 가로 1350px, 세로 59px | 높이 58px + 아래 테두리 1px #eaeaea. 배경은 흰색 |
| .conwrap | 가로 1269px, 좌우 여백 40.5px | 화면 폭 1450px 이하에서 width: 94%, 최대 너비 1400px, 가운데 정렬 |
| 왼쪽 .links | 왼쪽 x=40.5px, 위 y=14px | 언어 선택과 SNS 아이콘을 가로로 배치 |
| 오른쪽 .topmenu | 오른쪽 끝 x=1309.5px, 위 y=20px | 오른쪽 정렬, 높이 20px |

구성 요소

- 언어 선택: KOR 버튼은 88 × 30px입니다. 테두리 1px solid #eaeaea, 모서리 반경 10px. 글자는 Montserrat 11px, 검정 #000. 클릭해 펼치면 ENG가 나타납니다.
- SNS: Facebook, Instagram, YouTube 아이콘이 각각 30 × 30px입니다. 아이콘 사이 간격은 7px이며, 첫 아이콘은 언어 선택 상자 오른쪽에서 약 12px 떨어져 있습니다.
- 오른쪽 메뉴: HOME · SITE MAP · CONTACT US 순서입니다. 글자는 Montserrat 11px, 색상 #9b9a9a. 각 항목의 왼쪽에는 margin-left: 10px와 padding-left: 12px가 적용되고, 항목 사이에 작은 구분선 이미지가 들어갑니다. 첫 항목에는 구분선이 없습니다.

배치는 대략 다음과 같습니다.

┌─ KOR ▾   ○ ○ ○                         HOME  │  SITE MAP  │  CONTACT US ─┐
│        왼쪽 여백 3%                          오른쪽 여백 3%             │
└────────────────────── 높이 59px, 아래쪽 1px 테두리 ──────────────────────┘

아이콘과 작은 장식은 원본에서 이미지로 처리합니다: MONAMI 공통 CSS, Facebook, Instagram, YouTube.