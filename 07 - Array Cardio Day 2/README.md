# Day 07 - Array Cardio Day 2

<img width="445" alt="image" src="https://github.com/user-attachments/assets/500f58a3-8974-48f0-8c5c-d07931541c32" />

## 📖 설명

JS Array 함수 익히기 2


## 📌 배운 점
- `indexOf` 를 자주 썼는데 `findIndex`를 오랜만에 쓴다
  - 배열에 단순 값이 있는지 확인할 때 👉 indexOf
  - 객체에서 조건으로 찾을 때 👉 findIndex
### 요약
| 항목    | `indexOf`            | `findIndex`                            |
| ----- | -------------------- | -------------------------------------- |
| 비교 대상 | 값 자체 (===)           | 조건 함수                                  |
| 객체 탐색 | ❌ 안 됨                | ✅ 가능                                   |
| 리턴값   | 첫 일치 인덱스 or -1       | 조건 만족하는 첫 인덱스 or -1                    |
| 사용 예  | `[1,2,3].indexOf(2)` | `[obj].findIndex(obj => obj.id === 2)` |

## 🧩 주요 코드
```js
const now = new Date();
const year = now.getFullYear();
// Some and Every Checks
// Array.prototype.some() // is at least one person 19 or older?
const answer1 = people.some((person) => year - person.year > 18);
console.log("1.", answer1);
// Array.prototype.every() // is everyone 19 or older?
const answer2 = people.every((person) => year - person.year > 18);
console.log("2.", answer2);
// Array.prototype.find()
// Find is like filter, but instead returns just the one you are looking for
// find the comment with the ID of 823423
// Array.prototype.find()
const answer3 = comments.find((comment) => comment.id === 823423);
console.log("3.", answer3);

// Array.prototype.findIndex()
// Find the comment with this ID
const answer4 = comments.findIndex((comment) => comment.id === 823423);
// delete the comment with the ID of 823423
comments.splice(answer4, 1);
console.log("4.", answer4, comments);
```


## 🔗 링크
- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194130101)
