# Day 10 - Hold Shift and Check Checkboxes
<img width="820" alt="image" src="https://github.com/user-attachments/assets/8bd5350c-ad90-49dd-b75e-b43287e5f36f" />

## 📖 설명

체크리스트에 shift + check 기능으로 복수 선택기능 추가

## 📌 배운 점

- 기능 분석으로 간단한 복수선택 구현으로 오해함
  - shift 키로 복수 선택이 아니라, 선택된 체크박스가 있다면 그 사이에 선택하는 기능을 추가해야함
- 습관적으로 index를 직접찾아 또 for문을 돌렸다. [참고 - LEETCODE](https://github.com/sujeongy/LeetCodeHub/blob/main/0121-best-time-to-buy-and-sell-stock/NOTE.md)

## 🧩 주요 코드

```js
function handleCheck(e) {
  // Check if they had the shift key down
  // AND check that they are checking it
  let inBetween = false;
  if (e.shiftKey && this.checked) {
    // go ahead and do what we please
    // loop over every single checkbox
    checkboxes.forEach(checkbox => {
      console.log(checkbox);
      if (checkbox === this || checkbox === lastChecked) {
        inBetween = !inBetween;
        console.log('Starting to check them in between!');
      }

      if (inBetween) {
        checkbox.checked = true;
      }
    });
  }

  lastChecked = this;
}
```

## 🔗 링크

- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194129765)
- [MDN - NodeList.item()](https://developer.mozilla.org/ko/docs/Web/API/NodeList/item)
