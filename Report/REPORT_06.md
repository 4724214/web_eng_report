# 第6回 Webエンジニアリング演習 レポート
## 学籍番号
4724214
## `Todo`型の定義
```
export type Todo = {
    id: number;
    title: string;
    completed: boolean;
    dueDate?: string;
}
```

## 未完了件数を返す関数の引数と戻り値の型
```
# todo-service.ts

export async function countUnfinishedTask(): Promise<number>{
    const currentTodos = await fetchTodos();
    const incompletedTodos = currentTodos.filter(
        (todo) => !todo.completed,
    );
    return incompletedTodos.length;
}

# index.ts

console.log( await countUnfinishedTask());
```

## 未完了件数の実行結果
```
@4724214 ➜ /workspaces/web-eng-typescript (class-06-functions) $ pnpm run start
$ tsx src/index.ts
[
  { id: 1, title: '型を定義する', completed: true },
  { id: 2, title: '関数を作る', completed: false }
]
関数を作る
1
```
