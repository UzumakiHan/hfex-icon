# hfex图标库

## Install
```
npm i -D hfex-icon
```
## 主要提供2种使用方式

## 方式一
## 通过svg图标资源，借助unplugin-icons库将svg图标文件生成vue组件，然后通过vue组件的引入方式在vue中使用
## unplugin-icons github 
https://github.com/antfu/unplugin-icons
## 兼容vue2和vue3 

## 在vue.config.js/vue.config.ts的plugins中配置
## Install unplugin-icons

```
npm i -D unplugin-icons
```
```
const Icons = require('unplugin-icons/webpack');
const { FileSystemIconLoader } = require('unplugin-icons/loaders');
module.exports = {
  configureWebpack:{
    plugins:[
        Icons({
            compiler: vue2,//vue2或者vue3，看当前项目
            customCollections: {
                'hfex-icon': FileSystemIconLoader(path.join(process.cwd(), './node_modules/hfex-icon/icons'), svg =>
                    svg.replace(/^<svg /, '<svg fill="currentColor" ')
                )
            }
        })
    ]
  }
}
```
## 在vue入口文件引入注册组件
```
import HfexIcon from 'hfex-icon'
app.use(HfexIcon) //vue3
Vue.use(MfexIcon); //vue2

```
## 使用
```
<hfex-icon name="home" color="#999" size="80px"/>
```
效果展示
![Image text](https://raw.githubusercontent.com/UzumakiHan/static-files/master/images/hfex-icon-show.png)


|   参数    |    类型  |  默认值     |
| :-------: | :------: | :--------: |
|   name    |  string  |    home    |
|   size    |  string  |    28px    |
|   color   |  string  |    #000    |



