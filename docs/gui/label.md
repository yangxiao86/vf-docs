# 文字 Label

Label 可以绘制一段文本

> 手动换行使用 `\n`

> 当文本容器设置宽高后，文字默认会根据文本容器宽高居中.

> 当文本容器设置宽高后，可通过 style.textAlign 进行文字位置调整

## 属性

| 属性名 | 属性类型 | 默认值 | 说明 |
| --- | --- | --- | --- | --- |
| text |  string | '' | 要绘制的文本内容 |
| resolution |  number | '' | 文字绘制分辨率，一般不需要设置 |

## 事件

| 事件名  | 说明 | 参数 |
| --- | --- | --- |
|  CHANGE | text属性改变时触发 | target |

## 方法
| 函数名 | 参数 | 函数返回值 | 说明 |
| release |  |  | 销毁 |

## 样式

(style属性)

| 属性名 | 属性类型 | 默认值 | 说明 |
| --- | --- | --- | --- | --- |
| fillColor |  number , number[] | [r,g,b,a]或[[r,g,b,a],[r,g,b,a]] | 设置字体填充颜色，可以是二维数组渐变色 |
| letterSpacing | number |  | 设置字符间距 |
| wordWrap | boolean | false | 设置自动换行 |
| wordWrapWidth | number |  | 设置换行宽度，多行文本 |
| textAlign | ‘left‘ , ‘right‘ , ‘center‘ | center | 设置对齐方式 多行文本 |
| lineHeight | number |  | 设置行高，多行文本 |
| fontFamily | string , string[] |  | 设置字体，如果是外部字体，需要先嵌入 |
| fontSize | number | 22 | 设置字体大小 |
| fontStyle | ‘normal" , ‘italic‘ , ‘oblique‘ | normal |设置文字或字体斜体样式 |
| fontVariant | ‘normal‘ , ‘small-caps‘ | normal | 设置普通或小型大写字母字体 |
| fontWeight |  ‘normal’ , 'bold' , 'bolder' , 'lighter' , '100' ,'200',<br> '300','400','500','600','700','800','900'  | normal | 设置字体粗细 (vf.gui.Enum.FontWeight)|
| padding |  number  |  | 设置填充值 |
| stroke |  number[r,g,b,a]  |  | 设置描边颜色 |
| strokeThickness |  number  | 0 | 设置描边笔触粗细 |
| dropShadow |  boolean  | false | 设置投影 |
| dropShadowAlpha |  boolean  | false | 设置投影alpha值  |
| dropShadowAngle |  number  | 0 | 设置投影角度 |
| dropShadowBlur |  number  | 0 | 设置投影模糊半径 |
| dropShadowColor |  number  | 0x000000 | 设置投影填充色 |
| dropShadowDistance |  number  | 5 | 设置投影深度 |
| breakWords |  boolean  | true | 设置词换行 |
| textDecoration | ‘None‘ , ‘Overline‘ , ‘LineThrough‘ , ’UnderLine‘ | None | 下划线类型 |
| textDecorationColor | number | 0x000000 | 下划线颜色 |
| fillGradientType | 0 , 1 | 0 | 线性渐变方向，0垂直，1水平 |
| fillGradientStops |  number[]  |  | 线性渐变颜色截止比例   (数组元素区间0~1  不填默认均匀分布) |

> [基础样式](/handbook/style.html#样式)

::: warning ⚠️ font加载注意事项 
1：目前font加载支持ttf，woff，woff2三种格式,受浏览器兼容影响，推荐使用ttf格式。<br>
2：受ios11版本浏览器规范限制，font资源名不可以使用纯数字或纯数字类型字符串<br>
3：ios9及以下版本，第一次使用font才会加载，不能确定加载完成时间。需要业务层按照需求实现（如使用前，预留足够的加载时间，创建使用目标字体的临时文本）。<br>
4：如果是player项目 ,使用的字体需要配置在assets加载列表里面。如果是本地已经安装的字体，加载url设置为空，否则会提示资源问题<br>
:::

## 定义
``` typescript
const label: gui.Label = {
    name: "label",
    type: guiType.Label,
};
```

## 使用
``` typescript
{
id: "label",
libId: ComponentId.label,
text: "这是一段文本",
style: {
        fontSize: 24,
        fontWeight: Style.FontWeight.bold,
        fontFamily: "centuryGothic",
        wordWrap: true,
        wordWrapWidth: 384,
        color: 0x000000,
        lineHeight: 29
    }
}
```

## 示例

> 可点击左上角菜单，查看其他定义类

<iframe
     src="https://codesandbox.io/embed/label-dsnqr?fontsize=14&hidenavigation=1&module=%2Fsrc%2Fcomponents.ts&theme=dark"
     style="width:100%; height:720px; border:0; border-radius: 4px; overflow:hidden;"
     title="label"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
></iframe>