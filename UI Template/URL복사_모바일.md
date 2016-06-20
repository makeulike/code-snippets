# URL 복사!
모바일에서는 Flash를 사용하지 않음에 따라 클립보드를 복사할 수 없다. 
(일부 JavaScript API를 이용하여 복사가 가능한 게 있지만 브라우저 특성을 타버리는 바람에.. 사용하는것을 지양)

이에따라 우리가 흔히 모바일에서 행동하는 경험을 토대로 한 간편한 URL 복사 방법에 대한 내용을 소개한다.

## HTML
```
<div class="url-copy">
    <a href="https://youtu.be/j8vTKtduetE" onclick="return false">
      http://github.com/makeulike
    </a>
</div>
```

## CSS
``` CSS
.url-copy{
	display:block;
    /**
     * Any Styling
     */
}
.url-copy > a{
	display:block;
    /**
     * Any Styling
     */
}
```

## JavaScript
```JavaScript
// Return true?
```

모바일 브라우저에서 `http://github.com/makeulike` 부분을 누르고 있으면 브라우저의 System DialogUI에서 `복사하기` 라는 메뉴가 나오며 복사를 보다 더 쉽게 할 수 있다.

input 폼에 URL입력 후 복사하게 되면 선택도 해야하고 드래드고 해야하고 등등,, 번거로운 작업을 그나마 편리하게 할 수 있게 해준다.