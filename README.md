## Frontend Developer Challenge

Using the following endpoint : https://testing.pushbots.com/api

Build an application to authiticate and list apps with the following layout. (Use material UI)

![UI](https://user-images.githubusercontent.com/13505298/43805654-e567b8b6-9aa0-11e8-8813-a261cc15f010.jpg)

## Requirements and Output

- User sees a screen to enter his username and password then clicks login to be redirected to his dashboard page.
- Display all apps as responsive grid of cards as the image above
- Display the total number active/completed/in-setup/all apps

### Features

- User should be able to see all apps
- User should paginate apps using our api endpoints


## Conditions
- You should consume the api endpoint mention and not use it as internal json file
- You should build this application in ECMAScript 6 or later, you are free to use any javascript framework preffared (React).
- You should use state management solution like (Redux)
- Implement [travis](https://travis-ci.org) or [scrutinizer-ci](https://scrutinizer-ci.com) or any other CI tool for the project, Add the build status badges to your project README file
- Use [codeclimate](https://codeclimate.com) or any alternative to estimate the code quality and add it's badge to your project README file

## API endpoints:
Please note that our api is secured using jwt so you have to get a token for `/api/auth/login` then set `Authorization` with `bearer <-USERTOKEN->` for all api endpoints

- `POST https://testing.pushbots.com/api/auth/login`
  - Payload:
    ```json
    {
    "email": "codechallenge@gmail.com",
    "passwword":"secret"
    }
    ```
  - Response:
    ```json
    {
      "access_token": "...",
      "token_type": "bearer",
      "user": {
          "_id": "5aee2fde9a89200d1a4b45e2",
          "name": "Code Challenge",
          "email": "codechallenge@gmail.com",
          "..":"..."
        },
      }
    ```
- `GET https://testing.pushbots.com/api/?filter=complete` filter query string param can also accept `inprogress`, `shared` and `active`
  - Response:
    ```json
    {
    "apps": {
        "current_page": 1,
        "data": [
            {
                "_id": "58.....",
                "title": "Sample App",
                "secret": ".....",
                "userid": ".....",
                "updated_at": "2018-07-07 15:49:20",
                "created_at": "2016-11-11 07:59:32",
                "devicesNum": {
                    "safari": 123,
                    "opera": 448,
                    "firefox": 1167,
                    "chrome": 22606,
                    "android": 11663,
                    "ios": 10852,
                    "t": 46859 // total number of devices
                },
                "platforms": {
                    "ios": {
                      "...":"..."
                    },
                    "safari": {
                        "...":"..."
                    },
                    "android": {
                       "...":"..."
                    },
                    "chrome": {
                       "...":"..."
                    },
                    "firefox": {
                       "...":"..."
                    }
                },
                "shared_by": "Pushbots user"
            }
        ],
        "first_page_url": "/?page=1", // this one and next 9 are used for pagination
        "from": 1,
        "last_page": 1,
        "last_page_url": "/?page=1",
        "next_page_url": null,
        "path": "/",
        "per_page": 10,
        "prev_page_url": null,
        "to": 1,
        "total": 1
    },
    "appsFilter": "active", // use it to select the active filter
    "totalApps": 21,
    "completedApps": 16,
    "inProgressApps": 5,
    "sharedApps": 0,
    "activeApps": 1
}
 ```

## What we are looking for

- **Simple, clear, readable code** How well structured it is? Clear separation of concerns? Can anyone just look at it and get the idea to
what is being done? Does it follow any standards?
- **Correctness** Does the application do what it promises? Can we find bugs or trivial flaws?
- **Testing** How well tested your application is? Can you give some metrics?


## Questions & Delivery

If you have any questions to this challenge, please do reach out to us.

The challenge should be delivered as a link to a public git repository (github.com or bitbucket.com are preferred).

## Checklist

Before submitting, make sure that your program

- [ ] Code accompanies the Unit Tests
- [ ] Usage is clearly mentioned in the README file, This including setup the project, how to run it, how to run unit test, examples,etc
- [ ] Uses the endpoint directly

## Note

Implementations focusing on **quality over feature completeness** will be highly appreciated,  don’t feel compelled to implement everything and even if you are not able to complete the challenge, please do submit it anyways.

