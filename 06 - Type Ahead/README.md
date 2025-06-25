# Day 06 - Type Ahead
<img width="1028" alt="image" src="https://github.com/user-attachments/assets/08308e88-7a65-47ce-a872-2e533dddf3dc" />

## 📖 설명

미국 도시, 주 검색하기
- 대소문자 관계없이 검색되며, 리스트내 검색 키워드와 동일한 텍스트는 하이라이트 처리하기

## 📌 배운 점
- js30 풀때 일단 주어진 스타일이나 마크업을 전체적으로 확인한다. (단순 클래스 추가나 css 작업 진행 필요 여부 확인)
- 정규식이 아직도 어렵다.
  - `const regex = new RegExp(wordToMatch, 'gi');`: 주어진 키워드(wordToMatch) 대소문자 관게 없이 맞는 것을 찾아준다.
- 직접 마크업을 넣다보니 오타(`</li>` 닫는 마크업 누락)를 잡는데 시간 소요
### 작업 순서
1. fetch() 동작 확인
2. 시점 잡기, 동작 확인 - input 에 글씨가 쓰여졌을때, `change`, `keyup`으로 잡음
3. `input`에 키워드 작성했을때 결과 노출확인
4. 키워드 대소문자 관계없이 결과 노출확인
5. 리스트내 검색 키워드와 동일한 글자 색 변경(클래스 `hl`추가하기)

## 🧩 주요 코드

```js
 const regex = new RegExp(keyword, "gi");
  cityName = cityName.replace(
    regex,
    (match) => `<span class="hl">${match}</span>`
  );
  stateName = stateName.replace(
    regex,
    (match) => `<span class="hl">${match}</span>`
  );
```

## 🔗 링크
- [원본 강의](https://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194130156)
