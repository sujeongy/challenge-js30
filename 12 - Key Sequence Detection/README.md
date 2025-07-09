# Day 12 - Key Sequence Detection
<img width="1154" alt="image" src="https://github.com/user-attachments/assets/f9afc216-b069-4a10-86b4-a749df99d1f5" />


## 📖 설명
키보드 입력값으로 비밀키(secretCode)와 동일할 때 화면에 이미지 추가와 콘솔에 결과 찍기

## 📌 배운 점

- slice: 더 간단하고 직관적 / let로 재할당 필요 / 새 배열 생성 → immutability 지향 코드에서 선호
- splice: 기존 배열을 mutate / 메모리 측면에서 기존 배열 유지 가능 / const로 선언해도 splice로 내부 요소 변경 가능.

## 🧩 주요 코드

```js
// slice
let pressed = [];
const secretCode = "krystal";

window.addEventListener("keyup", (e) => {
  console.log(e.key);
  pressed.push(e.key);
  pressed = pressed.slice(-secretCode.length);
  if (pressed.join("").includes(secretCode)) {
    console.log("DING DONG DANG!");
    cornify_add();
  }
  console.log(pressed);
});

// splice
const pressed = [];
const secretCode = "wesbos";

window.addEventListener("keyup", (e) => {
  console.log(e.key);
  pressed.push(e.key);
  pressed.splice(
    -secretCode.length - 1,
    pressed.length - secretCode.length
  );
  if (pressed.join("").includes(secretCode)) {
    console.log("DING DING!");
    cornify_add();
  }
  console.log(pressed);
});
```

## 🔗 링크

- [원본 강의](http://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194129539)
- [cornify](https://www.cornify.com/)
