# Day 03 - CSS Variables

<img width="822" alt="image" src="https://github.com/user-attachments/assets/1c29b4cc-0472-44f3-b594-6005fd836032" />


## 📖 설명

`input`동작으로 다양한 css 반영하기
### 결과 코드와 다른점
  - `h1` JS 글씨색 변경 기능 제외
  - `css` 수정하지 않고 `js`로만 구현


## 📌 배운 점
- `this.dataset` 가 `data-*` 값을 가져오는 것!
- `:root`에 있는 `css 변수`를 js 로 변경하는 방법
 

## 🧩 주요 코드
```css
:root {
  --base: #ffc600;
  --spacing: 10px;
  --blur: 10px;
}

img {
  padding: var(--spacing);
  background: var(--base);
  filter: blur(var(--blur));
}

.hl {
  color: var(--base);
}
```
```js
const inputs = document.querySelectorAll(".controls input");

function handleUpdate() {
  const suffix = this.dataset.sizing || "";
  document.documentElement.style.setProperty(
    `--${this.name}`,
    this.value + suffix
  );
}
```


## 🔗 링크
- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194130480)
- [MDN - input range](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input/range)
- [MDN - blur](https://developer.mozilla.org/ko/docs/Web/CSS/filter-function/blur)
- [MDN - :root](https://developer.mozilla.org/ko/docs/Web/CSS/:root)
- [MDN - CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)
