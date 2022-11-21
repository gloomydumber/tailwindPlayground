# Tour of Tailwind

`Utility-first` CSS Framework임

*Utility*는 아주 많은 클래스 네임을 지니고 있음을 의미

즉, _flex_, _pt-4_, _text-center_ 같은 여러 클래스 네임이 *Utility*이고, 이를 조합해서 사용하는 방식

`vscode`의 _Tailwind CSS IntelliSense_ Extension을 이용하면 자동완성 등의 기능을 활용할 수 있음

## Test Drive

간단한 예제를 만들어보며 `tailwind` 문법 사용해봄

## Modifiers

`hover`와 같은 state를 타겟으로 하여 CSS를 적용하고 싶을 때 사용

`viewport` 설정으로 모바일이나 큰 스크린을 다룰 때에도 사용한다

또, *dark mode*를 위한 `modifier`도 존재한다

## Transitions

`transition` 도 간단하게 클래스명으로 설정 가능

## Modifiers for Lists

기존 `CSS`에서와 같이 `last`, `first`, `even`, `odd`, `only` 등의 옵션을 적용 가능

*list*의 경우, `react`에서 빈 `element`를 출력할 때에, `tailwind`에서는 _empty:hidden_ 처리하는 경우가 많다

## Modifiers for Forms

`group` 을 설정하여 `CSS` 를 적용할 수 있음

가령, 어떤 요소가 아닌 다른 요소에서 `hover` 가 발생했을 때, 어떤 요소의 `CSS` 속성을 변경하는 것이 `group`을 통해 가능

한편, `peer modifier`를 이용하면, 예를 들면, _span_ 요소의 스타일을 _input_ 요소의 상태에 따라 결정 할 수 있음

이 때, `react`의 `state` 등의 도움 없이 가능함

_input_ 요소에 부적절한 형식으로 입력되어있다면, `peer modifier`를 통해 _span_ 에 형식에 맞지 않은 입력이라고 알려주는 식

## More Modifiers

## Responsive Modifiers

반응형 디자인을 하기 위한 `Responsive Modifier`

`tailwind` 에서는, 모바일 화면을 위한 선택자를 따로 가지지 않는다

일반적으로는, 데스크톱 화면을 먼저 디자인하고 난 후에 모바일의 디자인을 구성하는 반면,

`tailwind` 의 경우에는 모바일 부터 구성하는 식이다

아래와 같은 `responsive modifier` 를 이용하면 반응형 디자인을 할 수 있다

- sm
- md
- lg
- xl
- 2xl
- portrait
- landscape

위의 `responsive modifier` 는 가장 최근의 스타일 설정이 적용된다

가령, 가장 작은 화면에서 설정한 값 다음으로 설정한 값이 있다면, 그 이후의 사이즈에서는 전부 그 설정값을 따른다

(이에 의해서 모바일부터 스타일을 구성하고 나서야 데스크탑의 스타일이 구성된다는 의미)

## Dark Mode

기본적으로 `tailwind`는 디바이스 세팅 값을 따라 다크모드를 활성화함

다크모드는 `dark` `modifier(선택자)` 만 이용하면 쉽게 적용할 수 있음

사이트 자체적으로 `dark` 모드 토글 버튼을 제공하기 위해서,

즉, 리액트나 JS를 통해 직접 토글시켜주기 위해서는 `tailwind.config.js` 에서 설정할 수 있음

```js
// tailwind.config.js
module.exports = {
  // 클래스를 기준으로 다크모드 적용 (최상위 부모에 dark클래스 지정)
  darkMode: "class",
  // @media(prefers-color-scheme)를 기준으로 다크모드 적용 (기본 값)
  darkMode: "media",
};
```

토클로 변경하려면, dark 선택자를 쓰는 *부모요소*에 dark 클래스명을 추가해주도록 JS로 구현하면 됨

가령, document의 가장 상위인 root component에 dark 클래스네임을 추가하는 식으로 구현

## Just In Time Compiler

`tailwind`는 클래스명을 실시간으로 생성하여 적용함

이것을 `Just in Time Compiler` 가 수행해줌

`tailwind` 가 제공하는 사이즈가 아닌 사이즈도 `Just in Time Compiler`를 통해 적용할 수 있게 됨
