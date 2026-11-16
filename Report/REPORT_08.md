# 第8回 Webエンジニアリング演習 レポート
## 学籍番号
4724214
## コンポーネント構成
```
@4724214 ➜ /workspaces/web-eng-react-practice/src (main) $ tree
.
├── App.tsx
├── assets
│   ├── hero.png
│   ├── react.svg
│   └── vite.svg
├── components
│   ├── TodoItem.tsx
│   └── TodoList.tsx
├── data.ts
├── main.tsx
└── types.ts

3 directories, 9 files
@4724214 ➜ /workspaces/web-eng-react-practice/src (main) $ pwd
/workspaces/web-eng-react-practice/src
@4724214 ➜ /workspaces/web-eng-react-practice/src (main) $ 
```

## `TodoItem`のProps型
```
export const todos: Todo[] = [
    { id: 1, title: "Reactを学ぶ", completed: true, dueDate: "2026-10-15"},
    { id: 2, title: "Propsを確認する", completed: false, dueDate: "2026-12-24"},
    { id: 3, title: "Stateを更新する", completed: false },
]
```

## 期限あり・なしの画面確認結果
```
export function TodoItem({ todo }: TodoItemProps){
    const isOverdue = todo.dueDate ? new Date(todo.dueDate) < new Date() : false;
    return (
        <li>
            <strong>{todo.title}</strong>
            <span>{todo.completed ? "(完了)" : "(未完了)"}</span>
            <span style={{ color: isOverdue ? "red" : undefined}}>{todo.dueDate}</span>
        </li>
    )
}
```
