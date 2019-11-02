介绍
我们的项目是基于已成熟项目恶意流量监测系统maltrail中的爬取网页内容的方法，获取到maltrail采集到的网络中各个开源黑样本(包括IP、domain、URL)，利用可视化平台superset展示出我们希望展现并且有意义的数据变化。该项目分为情报收集，情报处理，情报展示三个部分。
工作框架

1.情报收集
1.1 基于maltrail中的feeds
1.2 collector.py得到数据
1.3 将收集到的数据输入到以时间命名的csv中，每天一个csv文件

2.情报处理
2.1 get_blacklist.py从csv中得到可视化所需的数据输入
2.1.1 每天blacklist的数量
输入： 
x轴：时间
y轴：数量
折线图
2.1.2 总共reference的种类个数的占比
输入：reference的种类和对应个数
饼状图
2.1.3 总共info的种类个数占比
输入：info的种类和对应个数
饼状图
2.1.4 新增的reference和info种类个数占比
输入：新增reference和info的种类和个数
饼状图
2.1.5 相邻两天的数据变化
输入： 
x轴：时间
y1：相对于前一天新增ip的数量
y2：相对于前一天减少ip的数量
折线图
2.1.6 总共的ip、domain、url的占比
输入： 
x轴：时间
y轴：ip、domain、url的个数
饼状图
2.1.7 新增内容中ip、domain和url的占比
输入：ip,domain,url的个数
饼状图
2.1.8 出现周期占比
输入：特定出现周期的个数
饼状图

3 .情报展示
3.1 superset可视化平台展示以上数据的变化

3.2 可以以滑动窗口的形式展现每一段特定时间段内以上各种数据的变化情况