# 404Page(w.fastcompus)

<h2>24/02/12(금) 시작 ~ 24/02/12 끝</h2>

데모사이트 - airbnb

<h3>24/02/12</h3>
<h3>svg 이미지</h3>

- fastcompus에서 제공한 svg 파일 html에 가져옴
- html에 각종 요소들의 id가 달려있음 (예 : 별, 외계인 팔, 빔 등등)

<h3>css animation</h3>

- css애니메이션 실제로는 많이 쓰지 않지만 쓰게되면 항상 찾아서 쓰게되는 습관을 강의 통해서 어느정도 개념은 잡힘

```
// 애니메이션 이름부여
@keyframes soaking {
    to {
        transform: translateY(-250px) scale(0);
    }
}

// 애니메이션 이름 사용
#number-0-soaking {
    animation: soaking 2s;
    transform-box: fill-box;
    transform-origin: center;
}
```

<h3>javascript 사용</h3>

- HTML 요소들의 ID를 변경하고 애니메이션의 끝을 기다렸다가 새로운 함수를 호출하여 연결된 다음 애니메이션을 연결작업

```
<script>
    // setZeroAndBeamAppear 함수: 0을 다시 나타내고 빔을 나타나게 함
    const setZeroAndBeamAppear = () => {
        document.getElementById('number-0-soaking').removeEventListener("animationend", setZeroAndBeamAppear)
        document.getElementById('number-0-soaking').setAttribute("id", "number-0")
        document.getElementById('UFO-beam-disappearing').setAttribute("id", "UFO-beam")
        document.getElementById('number-0').addEventListener("animationend", setZeroAndBeamDisapper)
    }

    // setZeroAndBeamDisapper 함수: 0을 다시 숨기고 빔을 사라지게 함
    const setZeroAndBeamDisapper = () => {
        document.getElementById('number-0').removeEventListener("animationend", setZeroAndBeamDisapper)
        document.getElementById('number-0').setAttribute("id", "number-0-soaking")
        document.getElementById('UFO-beam').setAttribute("id", "UFO-beam-disappearing")

        document.getElementById('number-0-soaking').addEventListener("animationend", setZeroAndBeamAppear)
    }
    document.getElementById('number-0').addEventListener("animationend", setZeroAndBeamDisapper)
</script>
```
