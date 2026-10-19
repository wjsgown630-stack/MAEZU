# HTML · CSS · Codex 기초 학습 정리

## 1. Codex와 Playwright MCP

### 개념

| 용어 | 설명 |
|---|---|
| Codex | AI를 활용해 코딩 작업을 도와주는 도구 |
| MCP | AI가 외부 도구와 연결해 작업할 수 있도록 하는 방식 |
| Playwright | 브라우저를 자동으로 조작할 수 있는 도구 |
| Playwright MCP | AI가 브라우저를 열고 웹페이지를 조작할 수 있도록 연결하는 도구 |

### 사용 흐름

```text
Codex 실행
    ↓
/mcp 입력
    ↓
Playwright MCP 연결 확인
    ↓
AI에게 브라우저 열기 요청
    ↓
원하는 웹사이트 접속
    ↓
AI에게 페이지 분석 및 작업 요청
```

**요청 예시**

- "Playwright MCP로 브라우저를 열어줘."
- "원하는 사이트를 검색해 줘."
- "내가 열어 놓은 페이지가 보이니?"
- "이 페이지의 특정 영역을 분석해 줘."

※ AI가 현재 브라우저 페이지를 볼 수 있는지는 Playwright MCP의 연결 상태와 브라우저 접근 권한에 따라 달라진다.

---

## 2. 개발자 도구로 웹페이지 분석하기

### 사용 순서

```text
웹사이트 접속
     ↓
F12 (개발자 도구)
     ↓
요소 선택 아이콘 클릭
     ↓
분석하고 싶은 영역 클릭
     ↓
HTML 태그 및 클래스 확인
     ↓
CSS 스타일 분석
```

### 확인할 요소

| 항목 | 의미 | CSS 속성 |
|---|---|---|
| 높이 | 요소의 세로 크기 | height |
| 너비 | 요소의 가로 크기 | width |
| 글씨 크기 | 텍스트 크기 | font-size |
| 글씨 두께 | 텍스트 굵기 | font-weight |
| 글씨 색상 | 텍스트 색상 | color |
| 배경 색상 | 요소의 배경색 | background-color |

### AI에게 요청하는 예시

"선택한 영역이 어떤 역할을 하는지 알려줘. 높이, 너비, 글씨 크기, 두께, 색상을 분석하고 가장 짧고 직관적인 클래스명을 추천해 줘."

---

## 3. HTML 기초

### HTML 기본 구조

```html
<html lang="ko">
  <body>
    <div class="container">
      내용 입력
    </div>
  </body>
</html>
```

- `<html lang="ko">` : 문서의 기본 언어가 한국어임을 지정
- `<div>` : 콘텐츠를 묶는 영역
- `<body>` : 화면에 표시되는 문서의 본문

### HTML 태그 사용

```html
<div>내용 입력</div>
```

시작 태그 `>`와 종료 태그 `<` 사이에 내용을 입력한다.

### 주요 태그

| 태그 | 의미 |
|---|---|
| div | 영역을 묶는 컨테이너 |
| nav | 메뉴 및 탐색 영역 |
| ul | 순서가 없는 목록 |
| li | 목록의 항목 |

### 메뉴 구조 예시

```html
<div class="con">
  <nav>
    <ul>
      <li>홈</li>
      <li>소개</li>
      <li>문의</li>
    </ul>
  </nav>
</div>
```

---

## 4. CSS 기초

### 클래스 선택자

CSS에서 클래스를 선택할 때는 클래스명 앞에 `.`을 붙인다.

```css
.container {
  color: black;
}
```

HTML에서는 점을 붙이지 않는다.

```html
<div class="container">
  내용
</div>
```

### Border

`border`는 요소의 테두리를 지정한다.

```css
.box {
  border: 1px solid black;
}
```

---

## 5. Flex와 정렬

| 속성 | 역할 |
|---|---|
| display: flex | Flex 레이아웃 적용 |
| justify-content | 주축 방향 정렬 |
| align-items | 교차축 방향 정렬 |

기본 설정인 `flex-direction: row`에서는 다음과 같다.

- justify-content → 가로 방향
- align-items → 세로 방향

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

※ `flex-direction: column`이면 주축이 세로로 바뀌므로 정렬 방향도 달라진다.

---

## 6. Margin과 여백

`margin`은 요소의 바깥쪽 여백을 의미한다.

```css
.box {
  margin-left: auto;
  margin-right: auto;
}
```

좌우 여백을 자동으로 계산해 요소를 가로 가운데 정렬할 수 있다.

단, 일반적인 블록 요소에서 너비가 부모보다 작게 지정되어 있는 등의 조건이 필요하다.

### 정렬 도식화

```text
┌─────────────────────────────┐
│                             │
│      ┌──────────────┐       │
│ auto │     BOX      │ auto  │
│      └──────────────┘       │
│                             │
└─────────────────────────────┘
```

- Flex는 여러 요소의 배치와 정렬에 활용
- Margin은 요소 사이의 간격이나 특정 요소의 위치 조정에 활용
- 모든 정렬에 Grid나 Flex가 반드시 필요한 것은 아님

---

## 7. 웹폰트 적용하기

### 눈누 폰트 사용 순서

```text
눈누 웹사이트 접속
       ↓
원하는 폰트 선택
       ↓
웹폰트 사용 코드 복사
       ↓
CSS 파일 상단에 붙여넣기
       ↓
body에 font-family 지정
```

### CSS 예시

```css
/* 눈누에서 복사한 웹폰트 선언을 위에 작성 */

body {
  font-family: 'Pretendard', sans-serif;
}
```

※ 실제 `font-family` 이름은 복사한 웹폰트 코드에 선언된 이름과 일치해야 한다.

---

## 8. CSS 선택자 구조

HTML 구조가 다음과 같을 때

```html
<div class="con">
  <nav>
    <ul>
      <li>메뉴</li>
    </ul>
  </nav>
</div>
```

CSS에서 다음과 같이 선택할 수 있다.

```css
.con > nav > ul {
  /* 스타일 입력 */
}
```

### 선택자 해석

```text
.con
 └── nav
      └── ul
           └── li
```

- `.con` : con 클래스를 가진 요소
- `>` : 바로 아래에 있는 자식 요소 선택
- `nav` : 탐색 영역
- `ul` : 목록

---

## 9. VS Code 및 터미널 단축키

| 단축키 | 기능 |
|---|---|
| Ctrl + / | 주석 처리 및 해제 |
| Ctrl + ` | VS Code 터미널 열기 및 닫기 |
| F12 | 브라우저 개발자 도구 열기 |

### 터미널 관리

- 작업에 사용한 터미널은 필요에 따라 종료하거나 삭제할 수 있다.
- 터미널을 삭제해도 프로젝트 파일이 삭제되는 것은 아니다.
- Codex의 `/permissions`에서 권한 설정을 확인할 수 있다.
- Full Access는 강력한 접근 권한이므로 필요한 경우에만 사용한다.

---

## 10. 오늘의 핵심 요약

- Codex는 AI 기반 코딩 도구이다.
- Playwright MCP는 AI가 브라우저를 조작하도록 도와준다.
- F12로 개발자 도구를 열어 웹페이지 구조와 스타일을 분석할 수 있다.
- HTML은 웹페이지의 구조를 만든다.
- CSS는 웹페이지의 디자인과 배치를 담당한다.
- CSS에서 클래스 선택자는 `.`으로 시작한다.
- Flex의 기본 방향에서 justify-content는 가로, align-items는 세로 정렬이다.
- margin은 요소의 바깥쪽 여백이다.
- 웹폰트는 CSS에 폰트 코드를 추가한 뒤 font-family로 적용한다.
- `.con > nav > ul`은 자식 요소를 단계적으로 선택하는 CSS 선택자이다.
