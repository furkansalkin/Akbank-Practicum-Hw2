# Akbank-Practicum-Hw2
Hands on Task (Intermediate Level): Build and Deploy a To-Do List

```Solidity

pragma solidity ^0.8.7;
//SPDX-License-Identifier: MIT

contract TodoList {

    //Our todo object
    struct Todo {
        string text;
        bool completed;
    }

    //Array of todos
    Todo [] public todos;

    //With this function we creating new todo and pushing it to Todo Array
    function create(string calldata _text) external {
        todos.push(Todo({
            text : _text,
            completed : false
        }));
    }

    //Updates the todo in the index number we entered
    function updateText(uint _index, string calldata _text) external {
        todos[_index].text = _text;
    }

    //Retuns the todo the index number we entered
    function get(uint _index) external view returns (string memory,bool) {

        Todo memory todo = todos[_index];
        return(todo.text, todo.completed);
    }

    //Function that change value of comleted
    function toogleCompleted(uint _index) external {
         todos[_index].completed = !todos[_index].completed;
    }
}
```
