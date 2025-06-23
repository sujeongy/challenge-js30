# Day 04 - Array Cardio Day 1

<img width="992" alt="image" src="https://github.com/user-attachments/assets/c3c5e932-a1aa-443f-a759-27320d4a7e66" />
<img width="992" alt="image" src="https://github.com/user-attachments/assets/eec82bdf-a4e7-4480-b918-3b52d2baf7b0" />



## 📖 설명

js 기본 배열 함수 다루기 


## 📌 배운 점
- `Array.from()`사용을 꺼렸지만 `node`를 다룰 땐 좋다. (`[...]`으로도 가능)
  - 정적 메서드는 순회 가능 또는 유사 배열 객체에서 얕게 복사된 새로운 Array 인스턴스를 생성합니다.
- `arr.sort((a, b) => a - b)` 이런식으로 많이 써왔는데, a, b 가 숫자일 경우만 쓰고 문자일 경우는 삼항 연산자를 쓰자!
### `sort()` 연산자 더보기
|              | `val2 - val1` | 삼항 연산자                  |
| ------------ | ------------- | ----------------------- |
| 간결함          | ✅ 더 짧음        | ❌ 조금 더 길음               |
| 안전성 (동등한 경우) | ✅ 자동 `0`      | ❌ 직접 처리해야 함             |
| 직관성          | ✅ (숫자 비교에 특화) | ✅ (명시적 조건이라 직관적일 수도 있음) |
 

## 🧩 주요 코드
```js
// 6. create a list of Boulevards in Paris that contain 'de' anywhere in the name
// https://en.wikipedia.org/wiki/Category:Boulevards_in_Paris

const category = document.querySelector('.mw-category');
const links = Array.from(category.querySelectorAll('a'));
const de = links
            .map(link => link.textContent)
            .filter(streetName => streetName.includes('de'));
```


## 🔗 링크
- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194130346)
- [MDN - input range](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input/range)
