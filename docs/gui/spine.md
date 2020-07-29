# 骨骼动画 Spine


Spine 播放骨骼动画，支持播放、循环、暂停、恢复

## 插件地址

> [//s.vipkidstatic.com/vf/plugin/spine/0.0.2.js]()

## 类名
> Spine 

## 属性

| 属性名 | 属性类型 | 默认值 | 说明 |
| --- | --- | --- | --- | --- |
| ske_json |any | 无 | spine动画数据(.json) |
| ske_atlas |any | 无 | spine动画数据(.atlas) |
| ske_tex |any | 无 | spine动画数据(.png) |
| autoPlay |boolean | false | 是否自动播放 |
| animationName |string | 无 | 动画名字 |
| loop |boolean | 无 | 是否循环播放 |
| timeScale |number | 无 | 动画速率|

## 方法
| 方法名 | 参数 | 返回值 | 说明 |
| --- | --- | --- | --- | --- |
| play |name:string, loop:boolean | 无 | 播放动画 |
| playQueue |[{name,loop}] | 无 | 播放动画队列 |
| stop | 无 | 无 | 停止动画 |
| pause | 无 | 无 | 暂停动画，可用play（）恢复 |
| gotoAndStopByFrame | frame:number | 无 | 跳转并停止到固定帧 |
| gotoAndPlayByFrame | frame:number | 无 | 从某一帧开始播放 |




## 事件

| 事件名  | 说明 | 参数 |
| --- | --- | --- |
| SPINE_START | 动画开始 | animationName |
| SPINE_COMPLETE | 动画完成 | animationName |
| SPINE_EVENT | 动画中触发的事件 | animationName，event |


## 样式

| 属性名 | 属性类型 | 默认值 | 说明 |
| --- | --- | --- | --- | --- |



> [基础样式](/handbook/style.html#样式)

## 定义
``` typescript
const assets: Assets = {
    [Ids.spine]:{
        type: AssetType.js,
        url: "//s.vipkidstatic.com/vf/plugin/spine/0.0.2.js",
        name: "Spine",
    },
}
const spine = {
    type: "Spine",
    ske_json: Ids.ske_json,
    ske_atlas: Ids.ske_atlas,
    ske_tex: Ids.ske_tex,
    autoPlay: true,
    animationName: "breathe",
    loop: true,
    timeScale: 1,
};
```

## 使用
``` typescript
        {
            id: "eddy",
            libId: Ids.Spine,
            x: 100,
            y: 200,
        }
```

## 示例

> 示例使用的编程方式，在vf中，通过配置方式会有写法差异

> `运行 ⌘ + Enter` 查看修改后的效果

> [弹出](https://vipkid-edu.github.io/vf-gui/play/#example/TestSpine)

<iframe
     src="https://codesandbox.io/embed/spineexample-ffls8?fontsize=14&hidenavigation=1&module=%2Fsrc%2Fcomponents.ts&theme=dark"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="spineExample"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>