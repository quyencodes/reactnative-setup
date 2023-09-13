# React Native App with TypeScript, Expo and NativewindCSS

## Table of Contents

- [React Native App with TypeScript, Expo and NativewindCSS](#react-native-app-with-typescript-expo-and-nativewindcss)
  - [Table of Contents](#table-of-contents)
  - [Tech Stack](#tech-stack)
  - [Step-by-step (from scratch) Instructions](#step-by-step-from-scratch-instructions)
  - [Quickstart Instructions](#quickstart-instructions)

## Tech Stack

<div align="left" width="100%">
  <img src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React Badge"/>
  <img src="https://img.shields.io/badge/TypeScript-3178C6.svg?style=for-the-badge&logo=TypeScript&logoColor=white" alt="TypeScript Badge"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E.svg?style=for-the-badge&logo=JavaScript&logoColor=black" alt="JavaScript Badge"/>
  <img src="https://img.shields.io/badge/HTML5-E34F26.svg?style=for-the-badge&logo=HTML5&logoColor=white" alt="HTML Badge"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6.svg?style=for-the-badge&logo=CSS3&logoColor=white" alt="CSS Badge"/>
  <img src="https://img.shields.io/badge/Tailwind%20CSS-06B6D4.svg?style=for-the-badge&logo=Tailwind-CSS&logoColor=white" alt="CSS Tailwind Badge"/>
  <img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js Badge"/>
  <img src="https://img.shields.io/badge/Next.js-000000.svg?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js Badge"/>
</div>

## Step-by-step (from scratch) Instructions

1. Open your Windows powershell or MacOS terminal and write the following command. A survey will pop up to ask for your <a href="https://docs.expo.dev/guides/typescript/">Expo</a> project name:

   ```bash
   npx create-expo-app -t expo-template-blank-typescript
   ```

2. If you're on iOS, download Xcode for the iOS Simulator. I watched this <a href="https://www.youtube.com/watch?v=Ws-wnDywtMI">YouTube video here</a>.
3. Follow the instructions <a href="https://www.nativewind.dev/quick-starts/expo">here</a> to add NativewindCSS to your Expo project.

4. After completing the instructions and changing your `App.tsx` to the below, you'll run into an error.

<img src="https://github.com/quyencodes/s3-streetwear/assets/104607182/59306ef4-6b4b-41ea-a594-3e84011e1bb5">

5. To fix the error hovering `className`:

```
No overload matches this call.
  Overload 1 of 2, '(props: ViewProps | Readonly<ViewProps>): View', gave the following error.
...
```

Create a new file called `app.d.ts` and add the a triple-slash directive referencing the types (<a href="https://github.com/marklawlor/nativewind/issues/77" target="_blank">source</a>):

```
/// <reference types="nativewind/types" />
```

In addition, to fix the error (<a href="https://stackoverflow.com/questions/76688256/getting-error-use-processcss-thencb-to-work-with-async-plugins" target="_blank">source</a>). Seems like there is a version error when adding nativewind earlier

```
Use process(css).then(cb) to work with async plugins:
```

Run the following command:

```bash
yarn add nativewind
yarn add --dev tailwindcss@3.3.2
```

If you run into an error, downgrading tailwindcss and installing it with npm may help:

```bash
npm install tailwindcss@3.3.2 --save-dev
```

Finally, run `npm i` to make sure node_modules is up to date

## Quickstart Instructions

1. Open the terminal with `ctrl + backtick mark`, make sure to <b>change to the correct directory</b> and write the following command (install NPM packages):
   ```bash
   npm run start
   ```
2. Open a seperate terminal window and write the following command:
   ```bash
   npm run dev
   i (open iOS simulator)
   ```
3. Open the simulator app and you should see your Expo application up and ready to go
