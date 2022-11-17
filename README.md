# tailwindPlayground

取り敢えず tailwind をして...

後の`next.js`などはハッキリ他のレポでします

## install

```shell
npm install -D tailwindcss postcss autoprefixer
```

## tailwind initialize with postcss

```shell
npx tailwindcss init -p
```

`postcss.config.js`, `tailwind.config.js` 가 생성됨

전자는 기본적으로 간단한 설정이 되어있음

## Set `tailwind.config.js`

`content` field 에서는, 어느 경로에서의 어느 파일에 `tailwind` 를 적용할 것인지 설정

```js
// tailwind.config.js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./pages/**/*.{js,jsx,ts,tsx}",
    "./components/**/*.{js,jsx,tx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

이후, `tailwind`를 사용할 것이므로 `next.js` 에서 기본적으로 설치되는 _global.css_ 파일의 내용은 삭제해주고, 아래의 내용으로 대체한다

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
