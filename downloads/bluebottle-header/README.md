# Blue Bottle 헤더 구현 자료

원본: https://kr.bluebottlecoffee.com/
Playwright로 현재 페이지를 측정하고 헤더 내부 에셋을 추출했습니다. 단위는 CSS px입니다.

## 측정값
| 항목 | PC | 모바일 |
|---|---|---|
| 측정 브라우저 viewport | 1715 × 836 | 390 × 844 |
| 실제 콘텐츠 너비 (스크롤바 제외) | 1700 | 375 |
| 헤더 높이 | 80 | 65 |
| 헤더 padding | 0 60px | 0 20px |
| 배경 | #FDFBF7 | #FDFBF7 |
| 테두리 | 없음 | 없음 |
| 로고 | 23 × 57 | 23 × 57 |
| 검색/계정/카트 SVG 표시 크기 | 각각 20 × 20 | 각각 20 × 20 |
| 아이콘 버튼 | 각각 40 × 40 | 각각 40 × 40 |
| 카트 버튼 margin-right | -12 | -12 |
| 메뉴 | 가로 나열 | 햄버거로 대체 |

PC 메뉴 글꼴: Noto Sans KR, 14px, 500, line-height 19.6px, letter-spacing 0.28px.
메뉴 색상과 주요 아이콘 색상: #333333. 로고 색상: #00A9E0.
메뉴 항목 사이 gap: 40px. 메뉴 margin/padding: 0.
PC 레이아웃: display:grid; grid-template-columns:repeat(3,1fr); align-items:center.
왼쪽 메뉴 / 중앙 로고 / 오른쪽 아이콘. 로고는 전체 헤더 가로 중앙에 배치됩니다.
로고 링크 padding은 7.5px이고, PC 클릭 영역은 약 38 × 72px입니다.
오른쪽 버튼 사이 gap은 없고, 40px 버튼이 연속 배치되어 중심 사이 거리가 40px입니다.
카트의 -12px 마진 때문에 오른쪽 그룹의 레이아웃 너비는 약 108px이며 버튼이 12px 돌출됩니다.
PC 로고 위아래 여유는 각각 약 11.5px입니다.
모바일 메뉴 아이콘의 SVG 표시 박스는 20 × 20px이며 원본 viewBox는 20 × 10입니다.

## 파일
- logo.svg: 중앙 병 로고
- search.svg / account.svg / cart.svg: 헤더 주요 아이콘
- menu.svg / close.svg / caret.svg / arrow.svg: 모바일 및 메뉴 드로어
- search-modal.svg / close-modal.svg: 모달 검색·닫기
- naver.svg / kakao.svg: 로그인 모달 소셜 버튼 (원본 55 × 55)
- PNG/JPG 10개: 헤더 DOM의 검색 추천 영역에 포함된 상품/호버 이미지, URL에 지정된 width=1066 버전
- image-sources.json: 상품 이미지 URL과 대체 텍스트
- measurements-desktop.json: 상세 측정값
- example.html: 바로 열어볼 수 있는 정적 헤더 구현 예시

SVG는 원본 인라인 도형을 추출하고 현재 계산된 fill/stroke를 적용했습니다.
특히 원본 마크업의 white 값이 CSS로 덮어써지는 부분을 실제 표시 색상으로 저장했습니다.
중복 아이콘은 대표 파일로 묶었습니다. 헤더 본체에는 래스터 로고가 없고 SVG 로고를 사용합니다.

## 구현 예시의 범위
example.html은 site-nav 계열 클래스로 구현한 정적 예시입니다.
모바일 전환점 990px은 예시 구현 선택값이며 원본 CSS의 정확한 분기점을 확인한 값은 아닙니다.
모바일에서도 검색/계정/카트 버튼 세 개가 표시되는 것은 실제 화면 측정으로 확인했습니다.
Noto Sans KR은 예시에서 Google Fonts로 불러오므로 인터넷 연결이 필요합니다.
메뉴 드로어, 검색, 로그인, 카트 동작 및 스크롤/호버 상태는 예시에 연결하지 않았습니다.
측정값은 현재 기본 화면 상태 기준이며 다른 상태의 색상·크기는 별도 검증이 필요합니다.

