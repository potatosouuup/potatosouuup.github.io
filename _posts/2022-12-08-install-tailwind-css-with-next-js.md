---
layout: single
title: "Install tailwind CSS with Next.js"
categories: PotatoSouuup
tag: []
toc: true
---

## 1) Create Next app

```
npx create-next-app project-name
```

Set up with TypeScript

```
npx create-next-app project-name --typescript
```

> If you want to create empty tsconfig.json? >> [Link](https://nextjs.org/learn/excel/typescript/create-tsconfig)

## 2) Install Tailwind css

```
npm install -D tailwindcss@latest postcss@latest autoprefixer@latest
```

- Check package.json > devDependencies

```
"devDependencies": {
    ...
    "autoprefixer": "^10.4.0",
    "postcss": "^8.4.5",
    "tailwindcss": "^3.0.7",
    ...
  }
```

- Generating postcss.config.js & tailwind.config.js

```
npx tailwindcss init -p
```

> If you want Tailwind's default configuration file,

```
npx tailwindcss init --full
```

- Add the paths in tailwind.config.js.

```
module.exports = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

- Add the Tailwind directives to global.css

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 3) Run project

```
npm run build
npm run dev
```

> After Editing tailwind.config.js, you need to do `npm run build`

## 4) Useful Extension

- Tailwind CSS IntelliSense >> [Link](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
  - Preview tailwind css class name.

## extra) Unknown at rule @tailwind css Issue

- global.css에 아래와 같이 tailwind를 import 했을 때
  _unknown at rule @tailwind css_ 경고문 발생.

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

- VS Code 내장 목록에 의해 제공되는 규칙. 로더를 사용하지 않으면 오류 발생
- 가장 빠르고 쉬운 해결 방법
  --> **PostCSS Language Support** Plugin Install [링크](https://marketplace.visualstudio.com/items?itemName=csstools.postcss) - 현재 위의 방법으로 해결 완료
- .vue 등에서는 작동하지 않는다는 의견 있으므로,
  그 외 해결 방안은 [링크](https://stackoverflow.com/questions/47607602/how-to-add-a-tailwind-css-rule-to-css-checker) 참고

---

### Official documents

> [Typescript](https://www.typescriptlang.org/download)  
> [Tailwind with Next](https://tailwindcss.com/docs/guides/nextjs)

---

입사하고 회사에서 맨 처음 썼던 wiki.  
내가 쓰고 매번 회사 계정으로 들어가서 확인하기 번거로워 백업해두기!
