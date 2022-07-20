### 起因

在echarts5版本中没有china.js,不能正常使用中国地图

echarts5 移除了内置的 geoJSON（原先在 echarts/map 文件夹下），如果使用者仍然需要他们，可以去从老版本中得到（下载文件中的map文件，引入本地），或者自己寻找更合适的数据然后通过 registerMap 接口注册到 ECharts 中

### 老版本

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

### 另附

aliyun定制地图：
[http://datav.aliyun.com/portal/school/atlas/area_selector](http://datav.aliyun.com/portal/school/atlas/area_selector)