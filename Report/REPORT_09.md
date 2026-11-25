# 第9回 Webエンジニアリング演習 レポート
## 学籍番号
4724214
## Stateの一覧と役割
titleは自分が入力したTODOを保持する。
todosはtodo listの中身を保持する。
## 完了ボタンから画面更新まで
```
<TodoList todos={todos} onToggle={toggleTodo} />
```
完了ボタンを押すと、toggleTodoが呼び出される

## 空白入力を防ぐコードと確認結果
```
import { type SubmitEvent, useState } from "react";
import type { Todo } from "./types";
import { todos as initialTodos } from "./data";
import { TodoList } from "./components/TodoList";
export default function App() {
  const [todos, setTodos] = useState<Todo[]>(initialTodos);
  const [title, setTitle] = useState<string>("");
  const [debugMsg, setMsg] = useState<string>("");

  // ---------
  function handleSubmit(event: SubmitEvent<HTMLFormElement>) {
  event.preventDefault();
  const trimTitle: string = title.trim();
  if (trimTitle === ""){
    setTitle("");
    return setMsg("Error: You cannot add a TODO that consists only of spaces.")
  }
  if (title != trimTitle){
    setMsg("Warn: Remove space from TODO")
  } else {
    setMsg("Success: The TODO item was created successfully.")
  }
  const newTodo: Todo = {
  id: Date.now(), title, completed: false,
  };
  setTodos((current) => [...current, newTodo]);
  setTitle("");
  }

  // ------------
  const toggleTodo = (id: number) => {
    setTodos((current) => current.map((todo) =>
      todo.id === id
      ? { ...todo, completed: !todo.completed }
      : todo
    ));
  };

  return (
  <main>
    <h1>React TODO</h1>
      <form onSubmit={handleSubmit}>
        <label>
        新しいTODO
        <input value={title} onChange={(event) => setTitle(event.target.value)} />
        </label>
        <button type="submit">追加</button>
        {debugMsg !== "" && <p style={{fontWeight: "bold" }}>{debugMsg}</p>}
      </form>
      <p>入力中：{title}</p>
    <TodoList todos={todos} onToggle={toggleTodo} />
  </main>
  );
}
```
