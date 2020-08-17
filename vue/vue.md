
安裝
---
- npm install -g @vue/cli  //cli安裝

- npm install -g @vue/cli-service-global  //快速原型開發

**原型開發指令**
- vue serve index.vue
- vue build index.vue

環境變數
---
### 測試用  
- .env.development  
### 開發用
- .env.production  
> VUE_APP_自訂=內容
### 讀取
- process.env.VUE_APP_設置的自訂

常用依賴
---
### bootstrap
- npm install bootstrap jquery popper.js --save 

- main.js 增加 
> - import 'bootstrap';
> - import 'bootstrap/dist/css/bootstrap.min.css'; // Import css file


### axios

- npm install --save axios vue-axios

> - import axios from 'axios'
> - import VueAxios from 'vue-axios'
> - Vue.use(VueAxios, axios)

> #### 使用方法
```js
this.$http.get(api).then((response) => {
  console.log(response.data)
})
```


vue-router
---

- 切換路由
```js
this.$router.push('/路徑'); // 切換到指定頁面
```



- router index.js
```js
// 防止進入不存在的頁面
{
  path: '*',
  redirect: '/'
},

```

- main.js 導航守衛
```js
router.beforeEach((to, from, next) => {
  if (to.meta.requiresAuth) {
    const vm = this;
    const api = `${process.env.VUE_APP_API}/api/user/check`;
    axios.post(api).then(response => {
      if (response.data.success) { //如果面有加這個需驗證才放行
        next();
      } else { //其他導回填寫頁面
        next({
          path: '/login' 
        });
      }
    });
  } else {
    next();放行
  }
});

  {
    path: '/about',
    name: 'About',
    component: () => import('../views/About.vue'),
    meta: { requiresAuth: true } //確認是否要阻擋
  },
  ```
