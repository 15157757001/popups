# popups

气泡菜单

## 使用方式

**在index.js中**  

~~~
import chunLeiPopups from "@/components/chunLei-popups/chunLei-popups.vue";
components:{chunLeiPopups},
~~~

**在index.vue中**  

~~~
<template>
  <view class="content">
    <chunLei-popups v-model="value" :popData="data" @tapPopup="tapPopup" :x="344" :y="20" placement="top-end">
		</chunLei-popups>
  </view>
</template>
~~~

## OBJECT参数说明

| 参数 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| maskBg | String | 'rgba(0,0,0,0)' | 遮罩层颜色 |
| value | Boolean | false | 是否显示 |
| placement | String | 'default' | 默认值时动态设置三角行方向 top-start top-end bottom-start bottom-end |
| direction | String | 'column' | flex-direction |
| x | Number | 0 | 宽度375下的x |
| y | Number | 0 | 宽度375下的y |
| popData | Array | [] | 数据 |
| theme | String | 'light' | 主题light dark |
| dynamic | Boolean | false | x,y是否动态设置 |
| gap | Number | 20 | 距离屏幕边界的最小距离 |
| triangle | Boolean | true | 三角形是否存在 |


## 事件

| 事件名 | 说明 |
| ---  | --- |
| tapPopup | 点击了popData |

如果觉得插件不错，麻烦给个Star [gitHub](https://github.com/15157757001/popups)
