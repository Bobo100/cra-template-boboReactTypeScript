# cra-template-boboReactTypeScript

## Create your own React Scaffold

## 建立自己的腳手架 (我喜歡叫做模板)

因為自己在做一些小小練習的時候，每次都要重新建立一次React環境。雖然有官方的好用指令

```text
npx create-react-app my-app --template typescript
```

但是，裡面有很多我不想要的內容，都還要一直刪刪減減。
於是乎就上網找資料如何建立自己的模板。

最終給我測試出來了。

如果有更好的方法請一定要告知我，目前Webpack我還在研究中。
***

## 步驟

可以直接下載我的檔案去做更改，後面會教你怎麼做

資料夾結構
```txt
cra-template-boboReactTypeScript
│  package.json
│  README.md
│  template.json
│
└─template
    │  gitignore
    │  package.json
    │  README.md
    │
    ├─public
    │      404.html
    │      index.html
    │
    └─src
        │  App.css
        │  App.tsx
        │  index.css
        │  index.tsx
        │
        └─pages
                Error.tsx
                Home.tsx
```

1. 建立一個空的資料夾名稱為cra-template-{your-template-name}，並且cd進去這個資料夾
2. 輸入

    ```txt
    npm init
    ```

3. 安裝你需要的package
4. 建立一個template.json，放入package與script資訊

    template.json範例

    ```json
   {
    "package": {
            "dependencies": {
            "@testing-library/jest-dom": "^5.16.5",
            "@testing-library/react": "^13.4.0",
            "@testing-library/user-event": "^13.5.0",
            "@types/jest": "^27.5.2",
            "@types/node": "^16.18.12",
            "@types/react": "^18.0.27",
            "@types/react-dom": "^18.0.10",
            "gh-pages": "^5.0.0",
            "react": "^18.2.0",
            "react-dom": "^18.2.0",
            "react-router-dom": "^6.8.1",
            "react-scripts": "5.0.1",
            "typescript": "^4.9.5",
            "web-vitals": "^2.1.4"
            },
            "scripts": {
            "start": "react-scripts start",
            "build": "react-scripts build",
            "test": "react-scripts test",
            "eject": "react-scripts eject"
            },
            "eslintConfig": {
            "extends": [
                "react-app",
                "react-app/jest"
                ]
            }
        }
    }
   ```

5. 再建立一個template資料夾
6. 把外面的package.json，與.gitignore複製過來
7. 若有之後需要的內容都放在這邊，例如我需要public資料夾與旗下的index.html與404.html
8. 回到外層的package.json刪除這一行

   ```txt
   "private": true,
   ```

   並修改npm name(這會是你的npm包名稱) "name": "{your-template-name}",
   這無法跟別人重複，若都無法取可以考慮使用scope name 也就是 "name": "{@yourname/your-template-name}",若使用scope name之後發布要多加一個指令

   ```txt
   {
    "name": "cra-template-boboreacttypescript",
    "version": "0.1.3",
    "files": [
            "template",
            "template.json"
        ],
    "dependencies": {
        "@testing-library/jest-dom": "^5.16.5",
        "@testing-library/react": "^13.4.0",
        "@testing-library/user-event": "^13.5.0",
        "@types/jest": "^27.5.2",
        "@types/node": "^16.18.12",
        "@types/react": "^18.0.27",
        "@types/react-dom": "^18.0.10",
        "gh-pages": "^5.0.0",
        "react": "^18.2.0",
        "react-dom": "^18.2.0",
        "react-router-dom": "^6.8.1",
        "react-scripts": "5.0.1",
        "typescript": "^4.9.5",
        "web-vitals": "^2.1.4"
    },
    "scripts": {
        "start": "react-scripts start",
        "build": "react-scripts build",
        "test": "react-scripts test",
        "eject": "react-scripts eject"
    },
    "eslintConfig": {
        "extends": [
        "react-app",
        "react-app/jest"
        ]
    },
    "browserslist": {
        "production": [
        ">0.2%",
        "not dead",
        "not op_mini all"
        ],
        "development": [
        "last 1 chrome version",
        "last 1 firefox version",
        "last 1 safari version"
        ]
    }
   }

   ```

9. 登入npm，沒有帳號的請註冊 [註冊連結](https://www.npmjs.com/signup)

    ```txt
    npm login
    ```

10. 發佈到npm上

    ```txt
    npm publish
    ```

    若有使用scope name，則使用下面的指令來發佈

    ```txt
    npm publish -- access public
    ```

11. 使用自己的模組
12. 使用指令

    ```txt
    npx create-react-app {要創立的資料夾名稱} --template {你的npm包名稱}
    ```  

***

### 直接使用我的檔案去修改成你的npm包
