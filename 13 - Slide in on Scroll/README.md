# Day 13 - Slide in on Scroll
<img width="774" height="720" alt="image" src="https://github.com/user-attachments/assets/8dc12b19-ea74-4023-837b-2411b439ae89" />

## 📖 설명
스크롤시 이미지 노출
### 결과 코드와 다른점
- 노출 시점: 본인은 화면에 이미지가 존재할 경우 이미지 노출, 아래에서 위로 다시 올라올때 트렌지션 적용 안함

## 📌 배운 점
- offsetTop 등 스크롤 높이 관련된 프로퍼티

## 🧩 주요 코드

```js
const sliderImages = document.querySelectorAll('.slide-in');

function checkSlide() {
  sliderImages.forEach(sliderImage => {
    // half way through the image
    const slideInAt = (window.scrollY + window.innerHeight) - sliderImage.height / 2;
    // bottom of the image
    const imageBottom = sliderImage.offsetTop + sliderImage.height;
    const isHalfShown = slideInAt > sliderImage.offsetTop;
    const isNotScrolledPast = window.scrollY < imageBottom;
    if (isHalfShown && isNotScrolledPast) {
      sliderImage.classList.add('active');
    } else {
      sliderImage.classList.remove('active');
    }
  });
}
```

## 🔗 링크

- [원본 강의](http://courses.wesbos.com/account/access/68525af9003a1d49a04fd4c6/view/194129539)
- [MDN-innerHeihgt](https://developer.mozilla.org/en-US/docs/Web/API/Window/innerHeight)
- [debounce](https://www.freecodecamp.org/korean/news/debounce-dibaunseu-javascripteseo-hamsureul-jiyeonsikineun-bangbeob-js-es6-yeje/)
