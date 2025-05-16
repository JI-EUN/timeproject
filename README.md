# ✨ 1만시간의 법칙

시멘틱 마크업, 접근성, CSS 변수, 반응형 웹 등 **웹 표준과 유지보수성**을 고려하여 구축한 퍼블리싱 프로젝트입니다.

> 🔗 **배포 링크**: [https://incredible-chaja-0b3014.netlify.app/](https://incredible-chaja-0b3014.netlify.app/)

---

## ✅ 주요 구현 포인트

### 1. ✅ 시멘틱 마크업

HTML5 시멘틱 태그를 적극적으로 사용하여 구조적이고 의미 있는 마크업을 구성했습니다.  
`header`, `nav`, `main`, `section`, `article`, `footer` 등을 활용하여 **화면 구조와 콘텐츠의 역할을 명확하게 구분**했습니다.

```html
<header class="site-header">
  <nav class="main-nav">
    <ul>
      <li><a href="#about">소개</a></li>
      <li><a href="#features">특징</a></li>
    </ul>
  </nav>
</header>

<main>
  <section id="about">
    <h1>우리는 웹 표준을 따릅니다</h1>
  </section>
</main>
```

> 📌 시멘틱 마크업은 SEO와 스크린리더 사용자 모두에게 이점을 제공합니다.

---

### 2. 🧏 웹 접근성을 위한 `text-ir` 기법 적용

시각적으로 숨기되 스크린리더가 읽을 수 있도록 `text-ir` 기법을 사용했습니다.

```css
.text-ir {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
```

```html
<h1 class="text-ir">접근성을 고려한 제목입니다</h1>
```

> 📌 스크린리더는 해당 텍스트를 정상적으로 읽을 수 있습니다.

---

### 3. 🎨 CSS 변수(`:root`)를 통한 컬러 시스템 구성

컬러 재사용 및 유지보수를 위해 CSS 변수(`:root`)를 활용했습니다.

```css
:root {
  --color-primary: #4a90e2;
  --color-secondary: #f5a623;
  --color-text: #333;
  --color-bg: #fff;
}

body {
  background-color: var(--color-bg);
  color: var(--color-text);
}
```

> 🎯 컬러 일관성을 유지하고, 다크모드 전환 시도에도 유연하게 대응 가능!

---

### 4. 📛 CSS 클래스 네이밍: 케밥 케이스(kebab-case) 적용

CSS 클래스 이름은 모두 `kebab-case` 방식으로 작성하여 **가독성을 높이고 일관성 있는 코드 스타일**을 유지했습니다.

```html
<section class="hero-section">
  <h2 class="hero-title">웹 퍼블리싱을 쉽게!</h2>
</section>

<footer class="site-footer">
  <p class="footer-text">© 2025 퍼블리셔</p>
</footer>
```

> ✅ kebab-case는 HTML/CSS 작성 시 일반적으로 가장 널리 쓰이는 네이밍 컨벤션입니다.

---

### 5. 🧩 모든 해상도 대응을 위한 `clamp()` 활용

모든 화면 사이즈(모바일~데스크탑)에서도 콘텐츠가 **너무 작거나, 커서 깨지는 문제 없이 자연스럽게 표현되도록**  
CSS `clamp()` 함수를 적극 활용해 **유연하고 안정적인 크기 조절**을 구현했습니다.

#### ✅ 예시: 모바일 입력창 너비

```css
input[type="text"] {
  width: clamp(13rem, 40vw, 15.6rem);
}
```

- **최소값**: `13rem` 이하로 작아지지 않음  
- **가변값**: `40vw` – 화면 너비에 따라 자연스럽게 변화  
- **최대값**: `15.6rem` 이상 커지지 않음

> 📌 breakpoints 없이도 다양한 해상도에서 자연스럽게 대응 가능!

---

## 🧠 기술 요약

- **HTML5**: 시멘틱 태그로 구조화
- **CSS3**: `:root` 변수, clamp, text-ir 기법 활용
- **접근성**: 스크린리더 대응 텍스트 처리, alt, aria 고려
- **반응형**: clamp 및 모바일 퍼스트 설계
- **네이밍**: kebab-case로 일관된 클래스 네이밍
- **배포**: Netlify
  
---
