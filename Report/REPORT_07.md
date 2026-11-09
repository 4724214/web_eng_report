# 第7回 Webエンジニアリング演習 レポート
## 学籍番号
4724214
## 2画面の見出しと本文
```
window.addEventListener("hashchange", () => {
    const page = location.hash;
    switch (page) {
        case "#compare":
            title = "これは比較ページです。";
            messeage = "#compareから遷移しました。";
            break;
        case "#detail":
            title = "これは詳細ページです。";
            messeage = "#detailから遷移しました。";
            break;
        default:
            title = "Unknown page";
            messeage = "";
    }
    app.innerHTML = `
        <h1>${title}</h1>
        <p>${messeage}</p>
    `;
});
```
## クリック後のURLとNetworkの確認
```
csr/	200	document	Other	2.3 kB	545 ms
app.js	200	script	csr/:2	1.5 kB	359 ms
js.js	200	script	content.js:338	1.4 kB	17 ms
dom.js	200	script	content.js:338	1.8 kB	9 ms
js.js	200	script	content.js:338	1.4 kB	9 ms
よって新たなサーバとの通信はない
```
## 画面を切り替える処理の要点

あらたにhtmlを取得するのではなくて、SPAで実装する。
