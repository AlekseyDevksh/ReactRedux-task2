# Task 2

To start, solve the **Task 1**:
https://github.com/AlekseyDevksh/ReactRedux-task1.

After the **Task 1**, you have already implemented an application that can display the following pages:

- **/** - home
- **/login** - login and password page
- **/profile** - dashboard

### Backend

The application uses a backend which is located on heroku:
https://dry-ravine-12282.herokuapp.com/api

***

### Profile

After successful login and redirect to the **Profile** page, you need to make a **GET** request, and get detailed information about the current user:
```sh
https://dry-ravine-12282.herokuapp.com/api/user/1 (GET)
```

Answer: 
```
{
    status: "ok",
    data: {
        userId: 1,
        notifications: 3,
        emails: 10,
        overview: {
            visited: 1231,
            sale: 1446,
            growth: 65
        },
        activity: [
            {
                operation: "new comment",
               time: "4"
            },
            {
                operation: "ordered 2 items",
                time: "20"
            },
           {
            operation: "ordered 1 item",
            time: "30"
            },
            {
                operation: "sended message",
                time: "55"
            },
            {
                operation: "signed out",
                time: "60"
            },
            {
                operation: "ordered 2 items",
                time: "90"
            },
            {
                operation: "ordered 1 item",
                time: "105"
            }
        ]
    }
}
```

The received data, put in the store, and display on the **Profile** page:
https://app.zeplin.io/project/5d23235c76cacb3757c84836/screen/5d284764e3302b4bf917d0bb

You also need to handle the situation when the user is not found:
```
https://dry-ravine-12282.herokuapp.com/api/user/2  (GET)
```

Answer: 
```
{
    status: "err",
    message: "user not found"
}
```

### Additional requirements
- For asynchronous requests use redux-thunk.
- While the **Login/Profile** page is loaded - show the preloader (use reducer and action from the redux).
- In the **Login** form, use standard email validation (by input type, or by regular expression).
