<h1 align="center">
  <br>
  <a href="https://github.com/WalleDong/ChickenFarm"><img src="./docs/images/logo.png" alt="Chicken Farm"></a>
</h1>
<h4 align="center">一家小小的养鸡场 </h4>


<p align="center">
    <a>
      <img alt="env" src="https://img.shields.io/badge/macOS-passing-green?logo=apple" />
    </a>
    <a>
      <img alt="Python" src="https://img.shields.io/badge/Python-3.7-blue?logo=python&logoColor=white" />
    </a>
    <a href="https://github.com/WalleDong/ChickenFarm/graphs/commit-activity">
      <img alt="commit-activity" src="https://img.shields.io/github/last-commit/WalleDong/ChickenFarm.svg?logo=github&logoColor=white" />
    </a>
    <a href="https://github.com/WalleDong/ChickenFarm/issues">
      <img alt="Issues" src="https://img.shields.io/github/issues/WalleDong/ChickenFarm?style=flat&color=%23FFA24E&label=Issues&logo=github" />
    </a>
  </p>


<p align="center">
  <a href="#Features">Features</a> •
  <a href="#Installation">Installation</a> •
  <a href="#Usage">Usage</a> •
  <a href="#Todo">Todo</a> •
  <a href="#Contribute">Contribute</a> •
  <a href="#Community">Community</a> •
  <a href="#License">License</a>
</p>
​		非专业养鸡场:baby_chick::hatched_chick::hatching_chick:，统计购买和卖出操作，分析持仓和收益，爬取基金净值，使用各种定投算法回测分析，生成投资策略。所有功能一键式全自动完成。


# Features
- 全自动数据采集（天天基金购买记录、最新持仓采集）
- 爬取最新基金净值
- 个人数据分析
- 定投回测分析


# Installation

零、请自备数据库

一、初次使用需要添加环境变量
echo "export PYTHONPATH=$PYTHONPATH:/Users/zhangdong/Desktop" >> ~/.bash_profile
echo "export FARM_CONFIG_PATH=" >> ~/.bash_profile
source ~/.bash_profile

# Usage

二、新买一个基金需要将基金的历史数据上传至数据库中
1、将基金代码写入 position.csv 中
2、执行                    python cronjob.py 


三、每周末需要做

1、手动处理支付宝里卖的
2、填写支付宝里的持仓，填写csv
3、一键更新


1、更新净值数据库(一键)                         python cli/farm.py -n                   
2、将本周的交易记录下来   
  0) 先把支付宝里卖的手动处理，填写csv后                
  1) 自动记录本周交易操作                       python cli/farmer.py -roa
  2) 自动记录最新持仓                           python cli/farmer.py -pa
被选:

    1）处理加仓，一条一条基金执行                   python cli/farmer.py -b -c <code> -a <amount>
    2）处理卖出，一条一条基金执行                   python cli/farmer.py -s -c <code> -a <amount>
    3）更新持仓，现将基金的最新持仓维护至 position.csv 中，然后运行  python cli/farmer.py -pl              
3、统计并记录本周各个领域的投入、持仓、收益(一键)    python cli/farmer.py -record
4、导出个人数据统计表(一键)                       python cli/farmer.py -tables
5、导出个人数据统计图(一键)                       python cli/farmer.py -charts                 
6、更新回测分析数据(一键)                        python cli/farmer.py -bt
7、导出回测分析图表(一键)                        python cli/farmer.py -draw

### 个人数据统计图

![personal_data_statistics](./docs/images/personal_data_statistics.jpg)

### 定投分析图

![aip_backtest](./docs/images/aip_backtest.jpg)


# Todo

- [ ] 支持目标止盈、移动止盈等多种投资算法
- [ ] 自动生成投资策略


# Contribute

Contributions are always welcome!
Please read the [contribution guidelines](https://github.com/WalleDong/ChickenFarm/blob/main/docs/contribution.md).:relaxed:

# Community

[![Chat](https://img.shields.io/badge/Chat%20on-Wechat-green?logo=wechat&style=social)](./docs/images/wechat.JPG)

# License

[![License](https://img.shields.io/github/license/WalleDong/ChickenFarm?color=blue&label=license)](https://github.com/WalleDong/ChickenFarm/blob/main/LICENSE)

Copyright © 2021 [Walle Dong](https://github.com/WalleDong). All rights reserved.
