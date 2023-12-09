## 封装
```js
import axios from 'axios'

// 导入Nprogress
import NProgress from 'nprogress'
import 'nprogress/nprogress.css'

const api = axios.create({
   baseURL : 'http://127.0.0.1:8888/api/private/v1/',
   timeout:5000,
})

api.interceptors.request.use((config) => { 
	NProgress.start()
	config.headers.Authorization=window.sessionStorage.getItem('token')
	return config
})

// 隐藏进度条
api.interceptors.response.use(config =>{
  NProgress.done()
  return config
})

export default api
```

## token
> **header里面放Authorization，就是为了验证用户身份。**
> 使用拦截器在每一次请求之前将token添加到头部

## 挂载
```js
import api from './server'
Vue.prototype.$http = api
```

## token
### 登录
```js
login() {
	 this.$refs.loginFormRef.validate(async (valid) => {//elementUI表单验证
		if (!valid) return
		const { data: res } = await this.$http.post('login', this.loginForm)
		if (res.meta.status !== 200) return this.$message.error('登录失败')
		this.$message.success('登录成功')
		// 保存token到sessionStorage
		window.sessionStorage.setItem('token', res.data.token)
		// 跳转到主页/home
		this.$router.push('/home')
	 })
},
```
**使用sessionStorage**

### 登录验证
**路由守卫(见下)**
**拦截器增加header内容（见上）**