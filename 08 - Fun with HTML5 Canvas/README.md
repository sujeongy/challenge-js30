# Day 08 - Fun with HTML5 Canvas
<img width="820" alt="image" src="https://github.com/user-attachments/assets/8a4c41cc-bdc9-4899-ab94-16fbe0946df6" />


## 📖 설명
캔버스로 선그리기
- 캔버스 사용 경험이 상대적으로 적어서 영상 먼저 보고 감 익히고 작업
### 결과 코드와 다른점
  - 선의 너비 변경 기능 제외

## 📌 배운 점
- 캔버스의 기본 사용법
- 드래그(drag) 시점을 살리기 위해서, `mousedown`이벤트에 flag 분기를 쳐준다.

## 🧩 주요 코드

```js
const canvas = document.querySelector("#draw");
const ctx = canvas.getContext("2d");
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
ctx.strokeStyle = "#BADA55";
ctx.lineJoin = "round";
ctx.lineCap = "round";
ctx.lineWidth = 100;

let drawing = false;
let lastX = 0;
let lastY = 0;
let hue = 0;
function draw(e) {
  if (drawing) {
    ctx.strokeStyle = `hsl(${hue}, 100%, 50%)`;
    ctx.beginPath();
    ctx.moveTo(lastX, lastY);
    ctx.lineTo(e.offsetX, e.offsetY);
    ctx.stroke();
    [lastX, lastY] = [e.offsetX, e.offsetY]; // 선의 시작점

    hue++;
    if (hue >= 360) {
      hue = 0;
    }
  }
}

canvas.addEventListener("mousedown", (e) => {
  drawing = true;
  [lastX, lastY] = [e.offsetX, e.offsetY]; // 선의 시작점
});
canvas.addEventListener("mousemove", draw);
canvas.addEventListener("mouseup", () => (drawing = false));
canvas.addEventListener("mousemout", () => (drawing = false));
```

## 🔗 링크

- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194129962)
- [MDN - Drawing shapes with canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes#lines)
