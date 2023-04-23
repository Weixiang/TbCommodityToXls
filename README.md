# TbCommodityToXls

## 淘宝商品清单抓取器

### 修改

1. 订单导出包含购买日期、订单号、商家名称。

2. 支持多次、多页导出，无需重复登录。

3. 更新 chromedriver

4. 适配 selenium 4.3+ 版本新语法

###  更新



1. 新版本已支持自动计算差价（通常为运费和税费，也有可能是商家调价）

2. 完善xls输出格式，数字数据以数字形式输出，方便使用Excel进行后续计算和整理

3. 购物车导出单价修改为调价后的最新价格



### 一、项目简介

用于将淘宝购物车/已购商品的信息导出为Excel文档，以方便团队对报表进行归纳整理

此项目诞生于RoboMaster2022备赛过程中，由于整理物资采购BOM表需要详细的商品数据，而电控组购买的物资多而繁杂，手动整理费时费力，为减少不必要的时间浪费，故书写此脚本，将繁杂的工作交给计算机，以便将有限的时间和精力投入项目研发。

欢迎各位大佬为本项目提供建议，如果您觉得此项目对您有所帮助，请移动鼠标至页面右上角，帮我点个Star， 万分感谢!

`TbCommodityToXls.ipynb`、`featureTest.ipynb`用于开发过程中的功能测试，`TbCommodityToXls.py`为测试完毕的脚本文件

### 二、导出数据格式示例

#### （一）已买到的宝贝导出示例



| 时间        | 订单号                 | 店名            | 商品名                        | 商品详情  | 单价   | 数量 | 链接                                                               |   |   |
|-----------|---------------------|---------------|----------------------------|-------|------|----|------------------------------------------------------------------|---|---|
| 2023/2/20 | 3212379252673527042 | 深圳市优信电子科技有限公司 |  原装正品 0603贴片电阻 100R 1%     |       | 0.8  | 1  | https://item.taobao.com/item.htm?id=525741229141&_u=l60611eb02b  |   |   |
| 2023/2/20 | 3212379252673527042 | 深圳市优信电子科技有限公司 |  XH2.54 卧贴SMT连接器 多P数可选     | 卧贴 3P | 1.7  | 1  | https://item.taobao.com/item.htm?id=553190289846&_u=l60611e3ce8  |   |   |
| 2023/2/20 | 3212379252673527042 | 深圳市优信电子科技有限公司 |  0603贴片电容  100NF 104P 50V  |       | 2    | 1  | https://item.taobao.com/item.htm?id=522573286298&_u=l60611e0f85  |   |   |
| 2023/2/20 | 3212379252673527042 | 深圳市优信电子科技有限公司 |  原装正品CH343P QFN-16串口芯片     |       | 4.2  | 2  | https://item.taobao.com/item.htm?id=683699633812&_u=l60611e7011  |   |   |
| 2023/2/20 | 3212379252673527042 | 深圳市优信电子科技有限公司 |  原装正品 ESP32-S2 QFN-56芯片    |       | 14.7 | 2  | https://item.taobao.com/item.htm?id=635409903966&_u=l60611e8c00  |   |   |

#### （二）购物车导出示例

| 商品名                                                       | 商品详情                            | 单价 | 数量 | 链接                                              |
| ------------------------------------------------------------ | ----------------------------------- | ---- | ---- | ------------------------------------------------- |
| 卧贴GH1.25接插件2p  3 4 5 6 7 8 9 10 12p卧式贴片座子带锁扣GHR | 颜色分类：胶壳插头GH1.25-2p（20个） | 1.1  | 17   | https://detail.tmall.com/item.htm?id=615685562093 |
| 卧贴GH1.25接插件2p 3 4 5 6 7 8 9  10 12p卧式贴片座子带锁扣GHR | 颜色分类：胶壳插头GH1.25-3p（20个） | 1.2  | 1    | https://detail.tmall.com/item.htm?id=615685562093 |
| 卧贴GH1.25接插件2p 3 4 5 6 7 8 9  10 12p卧式贴片座子带锁扣GHR | 颜色分类：胶壳插头GH1.25-4p（20个） | 1.6  | 1    | https://detail.tmall.com/item.htm?id=615685562093 |

#### 三、使用说明

双击 `TbCommodityToXls.exe`

按照提示选择需要抓取的页面，登陆淘宝，按提示操作即可

抓取成功后会在目录下生成`data.xls`文件

#### 四、注意事项

1. 项目中使用了chromedriver(版本95.0.4638.17)对浏览器进行数据提取，使用时请确保本机安装有Chrome浏览器，若工具不能正常运行，请检查Chrome浏览器版本，并到[此处](http://npm.taobao.org/mirrors/chromedriver/)下载相应版本的chromedriver替换掉文件夹下原有的chromedriver.exe再尝试运行。
2. 工具首次运行后会在目录下生成`data.xls`文件，下次运行工具时，==请确保此文件处于关闭状态==，不要边Excel中打开`data.xls`边使用工具，否则会导致工具无法正常运行。
3. 商品详情页仅能导出当前页面下的数据，不支持跨页选择
4. 购物车导出商家数最多为30家

#### 五、安全性声明

此工具已开源，为方便大家使用，提供打包好的`TbCommodityToXls.exe`，附带的`chromedriver.exe`来自于[淘宝 NPM 镜像站](http://npm.taobao.org/mirrors/chromedriver/)，源码中不包含任何对个人隐私信息的窃取行为，若您对工具的安全性有任何疑问，请自行阅读源码解释执行。

