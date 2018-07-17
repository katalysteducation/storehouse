## Learning React/Redux

## 📚 Resources
Before starting make yourself comfortable with ReactJS terminology and basic concepts:
 - [React.js Documentation](https://reactjs.org/docs/getting-started.html)
 - [The Beginner's Guide to React](https://egghead.io/courses/the-beginner-s-guide-to-react)
 - [Redux Documentation](https://redux.js.org/)
 - [Getting Started with Redux](https://egghead.io/courses/getting-started-with-redux)
 - [React-Router Documentation](https://reacttraining.com/react-router/)
 - [Styled-Components Documentation](https://www.styled-components.com/)

### 🌄 Career Map's React specific ecosystem
To complete this task you can use only the (React's) libraries used in Career Map:

 #### ReactJS:
 - react
 - react-dom
 - react-router
 - react-router-dom
 - styled-components


 #### Redux:
 - redux
 - react-redux
 - reselect

### ⭐️ The Task ⭐️

The goal of this task is to create simple app that:
1. Allows to fetch all occupations from the Career Map
2. Allows users to search for occupations
3. Allows to display occupation statistics
4. (Advanced A.) Add occupations to favourites
5. (Advanced B.) Display favourites occupations

### 📝 Rrequirements

1. Use **JavaScript ES2015** (ES6) syntax
2. Use only libraries that are specified above as the one in Career Map ecosystem
3. Use `styled-components` to style your app
4. Write as modular code as possible, learn about what is a component and how it can helps you
5. Final code need to be cleaned up and easy to understand by other developers
6. Take the **mobile first** approach. Desktop layout is not required
7. App need to be available under public URL so others team members can test in on their mobile phones

### 📐 Startup Guidelines

1. Install [NodeJS](https://nodejs.org/en/) with npm
2. Inslall [Parcel](https://en.parceljs.org/) by runing in your termimal command `npm install -g parcel-bundler`
3. Create project directory, anter it and create a new **package.json** file `npm init -y`
4. Install CM's ecosystem:
```
npm install -S react react-dom react-router react-router-dom styled-components redux react-redux reselect
```
5. Create two files **index.html** and **index.js** and link *.js* file into *.html*.
6. Add **start** and **build** scripts into **package.json**
```
"scripts": {
    ...
    "start": "parcel index.html -p 8080",
    "build": "parcel build index.html --public-url ./"    
  },
```
7. Run `npm start` and in your boreser open url `http://localhost:8080/`

### 🔌 Career Map API References
Below you can find information about Career Map API and the specific method required to accomplish the task.

#### Requests

All request sends to CM need to be configured as shown below:
```
{
  mode: "cors",
  method: "post",    
  credentials: "include"
}
```


#### Authorization
In order to get access to CM's data you need to authorize with the link below:

```
Request:
https://mapakarier.org/backend/www/api/v1/auth/login/User/DE2w42N!@/male`

Response:
{
  "gender": "male"
}
```

The last part of the URL is **gender** parameter. It can be set to `male` or `fem` to get occupations with desired gender. Authorization should to be set only once when the app is booting up.


#### Get all occupation

```
Request:
https://mapakarier.org/backend/www/api/v1/occupation/getResults/name/ascending/name

Response:
[
  {
    "id": "415",
    "name": "Administrator baz danych",
    "photo": "avatars/paths/administrator-baz-danych-m.jpg",
    "avatar": "avatars/cityscape/administrator-baz-danych-m.png",
    "salary": 6983,
    "demand": 3,
    "trend": 0,
    "future_job": false,
    "duration": 17.02,
    "level": 7
  },
  ...
]
```

**TIP** If you want to display images like *avatar* or *photo* you need to prepend the *avatar/photo url* with `https://mapakarier.org/app/assets/` prefix. E.g.: `https://mapakarier.org/app/assets/avatars/paths/administrator-baz-danych-m.jpg`


#### Get occupation's statistics
Detail data about occupations are served in small chunks hidden behind specific methods like e.g. `getJobStatistics`. This method gest only one parameter that is `:id` of the occupation. The `:id` is a placeholder for occupation id number like `415`. E.g. `https://mapakarier.org/backend/www/api/v1/occupation/getJobStatistics/415`

```
Request:
https://mapakarier.org/backend/www/api/v1/occupation/getJobStatistics/:id

Response:
{
  "id": "415",
  "salary": {
    "value": "6983",
    "count": 5
  },
  "market": {
    "value": "ŚREDNI",
    "count": 3
  },
  "demand": {
    "value": "ŚREDNIE",
    "count": 3
  },
  "duration": {
    "value": "17 lat 2 miesiące",
    "count": 5
  }
}
```
