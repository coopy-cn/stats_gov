# stats_gov
[统计局网站](http://www.stats.gov.cn/tjsj/tjbz/tjyqhdmhcxhfdm/2019/index.html)2019年的数据汇总。</br>
细粒度，到最后一级(一般为5级，网站上少部分地区为4级)。</br>
数据编码格式为utf8，以便显示名称中的生僻字，请使用合适的文本工具打开。</br>

这里有python爬虫代码和所需库。爬取速度快，网速较好时35分钟左右。</br>

2020.4.3更新了使用代理</br>
统计局网站增加了反爬，通过使用代理爬取，不过因为用的收费的（快代理10rmb），所以代码99行不改成购买的api肯定运行不了。</br>
有需要的可以直接下载提取好的csv文件。</br>
爬虫整个网站需要约80个ip，35分钟，如果改变91行的15，提高池大小，可以改善这个时间，但可能会需要更多ip。</br>

## Results
数据格式，下表为前5行

|province|city|county|town|code1|code2|village|根据code2第一位|
| :---: | :---: | :---: | :---: | :---: | :---: | :--- | :---: |
|上海市|市辖区|嘉定区|华亭镇|310114111001|220|袁家桥社区居委会|0|
|上海市|市辖区|嘉定区|华亭镇|310114111002|121|沁园社区居委会|1|
|上海市|市辖区|嘉定区|华亭镇|310114111003|220|华旺社区居委会|0|
|上海市|市辖区|嘉定区|华亭镇|310114111201|220|联一村村委会|0|
|上海市|市辖区|嘉定区|华亭镇|310114111203|220|联三村村委会|0|

## Prerequisites
代码基于python3.6
- [**python3.6.6**](https://www.python.org/downloads/release/python-366/) ：python 官网下载，选择适合的版本；

使用以下命令下载安装依赖库
``` bash
pip install -r requirements.txt
```

asyncio.Semaphore()值最好设置为较小量(不超过100)，以防网站崩溃。
``` python
sem = asyncio.Semaphore(60)
```

## Run
``` bash
python stats_gov_2.py
```
