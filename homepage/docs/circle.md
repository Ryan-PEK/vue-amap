# 圆

---

## 示例

```html
<div id="demoComponent" class="demo-component">
    <amap id="amap" :zoom="zoom" :center="center">
      <amap-circle v-for="circle in circles" :center="circle.center" :radius="circle.radius" :fillOpacity="circle.fillOpacity" :events="circle.events"></amap-circle>
    </amap>
  </div>
</div>
```

```javascript
export default {
  name: 'demoComponent',
  data () {
    return {
      zoom: 15,
      center: [121.5273285, 31.21515044],
      circles: [
        {
          center: [121.5273285, 31.21515044],
          radius: 200,
          fillOpacity: 0.5,
          events: {
            click() {
              alert('click polygon');
            },
            init(o) {
              console.log(o);
            }
          }
        }
      ]
    }
  }
}
```


<div class="map-present">
  <div id="demoComponent" class="demo-component">
      <amap id="amap" :zoom="zoom" :center="center">
        <amap-circle v-for="circle in circles" :center="circle.center" :radius="circle.radius" :fillOpacity="circle.fillOpacity" :events="circle.events"></amap-circle>
      </amap>
    </div>
  </div>
</div>

<script>
export default {
  name: 'demoComponent',
  data () {
    return {
      zoom: 15,
      center: [121.5273285, 31.21515044],
      circles: [
        {
          center: [121.5273285, 31.21515044],
          radius: 200,
          fillOpacity: 0.5,
          events: {
            click() {
              alert('click polygon');
            },
            init(o) {
              console.log(o);
            }
          }
        }
      ]
    }
  }
}
</script>

## 静态属性
仅且可以初始化配置，不支持响应式。

名称 | 类型 | 说明
---|---|---|
zIndex | Number | 层叠顺序默认zIndex:10
bubble | Boolean | 是否将覆盖物的鼠标或touch等事件冒泡到地图上（自v1.3 新增）默认值：false
strokeColor | String | 线条颜色，使用16进制颜色代码赋值。默认值为#006600
strokeOpacity | Float | 轮廓线透明度，取值范围[0,1]，0表示完全透明，1表示不透明。默认为0.9
strokeWeight | Number | 轮廓线宽度
fillColor | String | 圆形填充颜色,使用16进制颜色代码赋值。默认值为#006600
fillOpacity | Float | 圆形填充透明度，取值范围[0,1]，0表示完全透明，1表示不透明。默认为0.9
strokeStyle | String | 轮廓线样式，实线:solid，虚线:dashed
extData | Any | 用户自定义属性，支持JavaScript API任意数据类型，如Circle的id等

## 动态属性
支持响应式。

名称 | 类型 | 说明
---|---|---|
center | LngLat | 圆心位置
radius | Number | 圆半径，单位:米

## 事件

事件 | 参数 | 说明
---|---|---|
init |[Circle](http://lbs.amap.com/api/javascript-api/reference/overlay/#Circle) | 高德圆覆盖物实例
click | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 鼠标左键单击事件
dblclick | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 鼠标左键双击事件
rightclick | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 右键单击
hide | {type, target} | 隐藏
show | {type, target} | 显示
mousedown | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 鼠标按下
mouseup | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 鼠标抬起
mouseover | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 鼠标经过
mouseout | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 鼠标移出
change | {type, target} | 属性发生变化时
touchstart | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 触摸开始时触发事件，仅适用移动设备
touchmove | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 触摸移动进行中时触发事件，仅适用移动设备
touchend | [MapsEvent](http://lbs.amap.com/api/javascript-api/reference/event/#MapsEvent) | 触摸结束时触发事件，仅适用移动设备