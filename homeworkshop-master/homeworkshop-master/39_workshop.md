# 39_workshop

## 문제1

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
  <style>
    img {
      width: 300px;
      height: 300px;
    }
  </style>
</head>
<body>
  <div id="app">
    <button @click="getPosts">Get Posts</button>
    <ul>
      <li v-for="(post, idx) in posts" :key="idx">
        <b>{{ post.title }}</b> - {{ post.body }}
      </li>
    </ul>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      data: {
        posts: [],
      },
      methods: {
        getPosts() {
          axios.get('https://jsonplaceholder.typicode.com/posts')
          .then(res => {
            this.posts = res.data
          })
        }
      }
    })
  </script>
</body>
</html>
```

