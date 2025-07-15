# Day 01 - JavaScript Drum Kit
<img width="979" height="726" alt="image" src="https://github.com/user-attachments/assets/b5d3c850-d2bb-445e-8605-40019be289a6" />

## 📖 설명
키보드로 치는 드럼

## 📌 배운 점

- 디테일한 오디오 동작 방법
  - `selectedAudio.currentTime = 0; // # 계속 처음부터 소리가 나도록 도와준다.`

## 🧩 주요 코드

```js
function resetKeys(e) {
  e.target.classList.remove("playing");
}
function playing(e) {
  const code = e.keyCode;
  const curr = document.querySelector(`div[data-key="${code}"]`);
  const selectedAudio = document.querySelector(
    `audio[data-key="${code}"]`
  );
  if (!curr) return;
  curr.classList.add("playing"); // error handlings
  selectedAudio.currentTime = 0; // # 계속 처음부터 소리가 나도록 도와준다.
  selectedAudio.play();
}
const keys = document.querySelectorAll(".keys");
keys.forEach((key) => key.addEventListener("transitionend", resetKeys)); // # transitionend: CSS transition 이 완료되면 발생
window.addEventListener("keydown", playing);
```

## 🔗 링크

- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194130650)
