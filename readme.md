echarts地图版本号：4.2.1-rc1

包含世界地图，中国地图和各省市、自治区地图

+ js使用方法

    ```
    <script>
    import "../utils/china.js";
    ...
    </script>
    ```
    需要注意的是vue使用时echarts的定义，js文件内是`echarts`，vue中定义一般是`this.$echarts`，如果两个定义的不一致，会导致读取不到地图实例，推荐直接使用json，js文件是在json外包了一层exports。

+ json使用方法

    引用文件后直接使用echarts的registerMap方法即可。
    ```
    <script>
    import china from '@/.../china.json' //本地路径

    export default {
      ...
      mounted() {
        this.$echarts.registerMap('china', china)
      },
      ...
    </script>
    ```