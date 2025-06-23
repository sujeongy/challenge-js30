# Day 02 - JS and CSS Clock

<img width="820" alt="image" src="https://github.com/user-attachments/assets/b90a3c59-0b45-4a92-9d81-190a008f211e" />

## 📖 설명

아날로그 시계의 바늘 각도 계산 공식을 이용하기


## 📌 배운 점


| 바늘 | 공식                               |
| -- | -------------------------------- |
| 초침 | `(초 / 60) * 360`                 |
| 분침 | `(분 / 60) * 360 + (초 / 60) * 6`  |
| 시침 | `(시 / 12) * 360 + (분 / 60) * 30` |


## 🧩 주요 코드

```js
function setTime() {
    const now = new Date();

    const seconds = now.getSeconds();
    const secondsDegrees = ((seconds / 60) * 360) + 90;
    secondHand.style.transform = `rotate(${secondsDegrees}deg)`;

    const mins = now.getMinutes();
    const minsDegrees = ((mins / 60) * 360) + ((seconds/60)*6)+ 90;
    minHand.style.transform = `rotate(${minsDegrees}deg)`;

    const hour = now.getHours();
    const housrDegrees = ((hour / 12) * 360) + ((mins / 60) * 30) + 90;
    hourHand.style.transform = `rotate(${housrDegrees}deg)`;
  }
```

## 🐛 트러블슈팅

- 문제점
  - 사실 많이 헤맸다. 직접 시계구현은 오랜만이라.
  - 초침이 움직이면 분침도 계산해야 하고, 분침이 움직이면 시침을 추가로 움직이는 부분을 생각하지 못했다.
- 해결 방법
  - 구글 검색
  - 완료 소스 참고

🔗 링크
- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194130581)
