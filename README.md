#项目构建: 使用 cnpm init webpack (project)
##引入初始化css用rem做适配: ~styles/reset.css
###引入fastclick做点击事件处理: cnpm install fastclick --save
//mian.js引入 fastclick  import fastClick from 'fastclick fastClick.attach(document.body)
####用了axios做数据传输 使用全局axios  import axios from 'axios' //添加到vue原型上面 Vue.prototype.$http = axios
//全局使用 this.$http.get(url).then( (response)=> { console.log(response) } )
####接下来配置mock本地数据上线版本的时候设置接口访问位置/api/data.json 配置如下
config/index.js 添加到assetsPublicPat后面
  proxyTable: {
      '/api': {
        target: 'http://localhost:8080',
        pathRewrite: {
          '^/api': '/static/mock'
        }
      }
    },
 使用方式 this,$http.get('/api/data.json').then()
 
 # 开发中.......
 
