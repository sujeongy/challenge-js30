# Day 05 - Flex Panel Gallery

<img width="1028" alt="image" src="https://github.com/user-attachments/assets/62d5a6c6-df7d-4bb4-9ee6-02d390209ed4" />


## 📖 설명
CSS FLEX 이용하여 다이나믹 이미지 페이지 만들기

## 📌 배운 점
- `flex` 속성 제대로 사용하기(정확히는 `flex-grow`)
  - `flex: 증가너비 감소너비 기본너비;`
- 자연스러운 변경을 표현하기 위해서 `transitionend` 이벤트 잡기


## 🧩 주요 코드
```css
.panel {
  background: #6B0F9C;
  box-shadow: inset 0 0 0 5px rgba(255,255,255,0.1);
  color: white;
  text-align: center;
  align-items: center;
  /* Safari transitionend event.propertyName === flex */
  /* Chrome + FF transitionend event.propertyName === flex-grow */
  transition:
    font-size 0.7s cubic-bezier(0.61,-0.19, 0.7,-0.11),
    flex 0.7s cubic-bezier(0.61,-0.19, 0.7,-0.11),
    background 0.2s;
  font-size: 20px;
  background-size: cover;
  background-position: center;
  flex: 1; /* 필요성을 깜빡하고 있었다. */
  justify-content: center;
  display: flex;
  flex-direction: column;
}
```
```js
const panels = document.querySelectorAll(".panel");
function clickAction() {
  this.classList.toggle("open");
}
function transitionAction(e) {
  if (e.propertyName === "flex-grow") {
    this.classList.toggle("openActive");
  }
}
panels.forEach((panel) => panel.addEventListener("click", clickAction));
panels.forEach((panel) =>
  panel.addEventListener("transitionend", transitionAction)
);
```


## 🔗 링크
- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194130264)
- [CSS Flex 완벽 가이드](https://www.heropy.dev/p/Ha29GI)
- [CSS Flexbox Layout](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
