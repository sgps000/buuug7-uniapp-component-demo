# 简单的日期时间选择器

只支持选择日期和时间，只支持选择到分钟。

## 用法

在template中：
```vue
<simple-datetime-picker
    ref="myPicker"
    @submit="handleSubmit"
    :start-year="2000"
    :end-year="2030"
></simple-datetime-picker>
```

在javascript中：

```javascript
import simpleDatetimePicker from '../../components/simple-datetime-picker.vue';
export default {
  components: {
    simpleDatetimePicker,
  },
  data () {
    return {
      birthday: '',
    }
  },
  methods: {
    // 打开picker
    openDatetimePicker () {
      this.$refs.myPicker.show();
    },
    
    // 关闭picker
    closeDatetimePicker() {
      this.$refs.myPicker.hide();
    },

    handleSubmit (e) {
      console.log(e);
      // {year: "2019", month: "07", day: "17", hour: "15", minute: "21"}
      
      this.birthday = `${e.year}-${e.month}-${e.day} ${e.hour}:${e.minute}`;
    },
  },
}
```

可以参考压缩包下面pages/index/index.vue中例子，通常情况下打开picker需要调用`this.$refs.refName.show()`，在选择完毕后picker会自动隐藏，不需要调用`this.$refs.refName.hide()`来手动隐藏。

别把插件放在其它组件里面去用，放最外层view下就行，例如不要把组件放swiper里面的,放v-for里面等。

## 属性说明

+ `start-year`，类型 `number`，选择开始年份
+ `end-year`，类型 `number`, 选择结束年份
+ `@submit`, 类型 `function`, 监听选择事件，
+ `ref`，指定该picker的引用，方便打开关闭

## CHANGELOG

+ 1.0.0 (2019-07-17)
    + 首次发部，直至选择日期时间，精确到分钟
    
    
## 插件目录    
