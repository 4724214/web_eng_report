# 第5回 Webエンジニアリング演習 レポート
## 学籍番号
4724214
## TODO配列のコード
```
const myTodos = [
    { id: 1, title: "レポート", completed: true },
    { id: 2, title: "小テスト", completed: false },
    { id: 3, title: "期末試験", completed: false },
    { id: 4, title: "プレゼンテーション", completed: false },
];
```

## TODOを更新した条件

```
const isCompletedBefore = myTodos.filter((todo) => todo.completed).length;

console.log(isCompletedBefore);

for (const myTodo of myTodos){
    if(myTodo.completed === false){
        myTodo.completed = true;
        console.log(`更新後: ${myTodo.title} [完了]`);
    }
}

const isCompletedAfter = myTodos.filter((todo) => todo.completed).length;

console.log(isCompletedAfter);
```

## 完了件数の更新前後の実行結果

```
1
更新後: 小テスト [完了]
更新後: 期末試験 [完了]
更新後: プレゼンテーション [完了]
4
```
