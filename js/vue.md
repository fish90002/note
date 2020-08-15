-環境變數
.env.development 測試用 VUE*APP*自訂=內容
.env.production 開發用  
 -讀取 process.env.VUE*APP*設置的自訂

bootstrap
npm install bootstrap jquery popper.js --save

main.js 增加
import 'bootstrap'; // Import js file
import 'bootstrap/dist/css/bootstrap.min.css'; // Import css file

axios
npm install --save axios vue-axios

import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios, axios)

this.\$http.get(api).then((response) => {
console.log(response.data)
})

登入
if (response.data.success) {
vm.\$router.push('/'); // 切換頁面
}

router index.js
// 防止亂打 進入不存在的頁面
{
path: '\*',
redirect: '/'
}

main.js 導航守衛
router.beforeEach((to, from, next) => {
if (to.meta.requiresAuth) {
const vm = this;
const api = `${process.env.VUE_APP_API}/api/user/check`;
axios.post(api).then(response => {
if (response.data.success) { 如果面有加這個需驗證才放行
next();
} else { 其他導回填寫頁面
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
