> We’ll start by setting up a div with an “ng-app” attribute

"ng-app" 애트리뷰트가 있는 div 태그로 시작하겠습니다.

```html
<!DOCTYPE html>
<html>
 <head>
   <title>AngularJS Tutorials</title>
   <link rel="stylesheet" href="vendor/foundation.min.css">
 </head>
 <body>

   <div ng-app="">

   </div>

   <script type="text/javascript" src="vendor/angular.js"></script>
 </body>
</html>
```

> This attribute says that this element (the div) and everything inside of it belongs to this app. Binding can be represented in AngularJS using the ng-bind directive or with double curly brackets. We can test this out by trying some expressions in our div:

여기서 애트리뷰트 ng-app 는 그것이 들어간 div 엘레멘트로 싸인 모든 것에 적용되는 app 이름을 값으로 받는다. 앵귤러에서 바인딩은 ng-bind 디렉티브 곧 이중 중괄호 {{ }} 로 표현합니다. 지금 있는 div 안에 뭘 넣어서 시험을 해보겠습니다.


```html
<div ng-app="">
  {{1 + 1}}
  {{"john" + "lindquist"}}
  {{3 * 3}}
</div>
```

> You should keep logic in the view to a minimum. Binding is most useful when you create an input or a way for the user to interact with the site of your app. Let’s create an input with an attribute ng-model which is set to “data.message” and then bind it inside our div.

뷰에는, 로직을 최대한 조금 두는 것이 좋습니다. 입력과 같이 사용자가 웹페이지와 상호작용하는 수단을 만드는 데에 가장 유용한 것이 바로 이 바인딩 입니다. 값이 "data.message"인 애트리뷰트 ng-model 가 있는 input 태그를 만들어서 여기 div 안에 바인드를 해봅시다.

```html
<div ng-app="">
  <input type="text" ng-model="data.message">
  <h1>{{data.message}}</h1>
</div>
```

> Now when we load the page, if we start typing in the input field, you will see that the model has been bound and our text will start showing up as we type. If we add ‘+ “ world”’ into the binding we get “hello world” when we refresh and type hello into the input.

이제부터는 페이지를 열고서 입력 필드에 무엇을 넣으면 그 모델이 바인드 되어 있어서 타자하는 대로 나타나 보이는 것을 알 수 있습니다. `+ " world"` 를 바인딩 안에 추가하면 hello 를 입력했을 때 "hello world" 와 같이 됩니다.

```html
<div ng-app="">
  <input type="text" ng-model="data.message">
  <h1>{{data.message + " world"}}</h1>
</div>
```

> We can get a bit crazy and create a div with a class attribute of “” and say “Wrap me with a foundation component”

더 나아가서 class 애트리뷰트 "" 가 있는 div 에 “Wrap me with a foundation component” 라고 적읍시다. 

```html
<div ng-app="">
  <input type="text" ng-model="data.message">
  <h1>{{data.message + " world"}}</h1>
  <div class="{{data.message}}">
    Wrap me in a foundation component
  </div>
</div>
```

> Now we can type foundation classes into the input box, such as “panel” “alert-box” and “label” we can see that it actually changes the class of the div and the div gets styled differently so we can really manipulate a lot of the dom using binding, not just presenting simple text.

이제는 입력 박스에 파운데이션에 있는 CSS 클래스 이름들을 넣을 때마다 지금 있는 div 의 class 가 그대로 바뀌어서 스타일이 다르게 나타나는 것을 볼 수 있습니다. 그러니까 말하자면 바인딩을 이용해서 웬만한 dom 을 조작할 수가 있다는 것입니다.
