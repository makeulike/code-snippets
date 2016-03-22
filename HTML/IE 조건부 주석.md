# Internet Explorer 조건 부 주석문
조건부 주석문은 Internet Explorer 10 미만에서만 작동하는 조건문으로 CSS3 의 transition 등 과 같은 애니메이션 지원여부, Legacy Browser( 6,7,8 )에 대한 구분을 명확하게 할 수 있다.

## Basic
```HTML
<!--[if condition]> 
	HTML 코드
<![endif]-->
```

## Usage
```HTML
<!DOCTYPE html>
<!--[if lt IE 7]>
	<html class="ie-legacy lt-ie7" lang="ko">
<![endif]-->
<!--[if IE 7]>
	<html class="ie7 lt-ie8" lang="ko">
<![endif]-->
<!--[if IE 8]>
	<html class="ie8 lt-ie9" lang="ko">
<![endif]-->
<!--[if IE 9]>
	<html class="ie9 lt-ie10" lang="ko">
<![endif]-->
<!--[if (gt IE 9)|!(IE)]><!-->
	<html class="no-js" lang="ko">
<!--<![endif]-->
```