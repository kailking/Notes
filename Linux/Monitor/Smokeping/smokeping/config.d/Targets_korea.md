韩国监控项配置如下：
```
*** Targets ***

probe = FPing

menu = Top
title = Network Latency Grapher
remark = Welcome to the SmokePing website of Linekong Korea Company. \
? ? ? ? ?Here you will learn all about the latency of our network.

+Korea
menu = Korea
title = Korea Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++Korea_SK
menu = Korea_SK
title = Korea_SK Monitor

+++Korea_SK01
menu = SK_121.254.171.1
title = SK_121.254.171.1
host = 121.254.171.1

++Korea_LG
menu = Korea_LG
title = Korea_LG Monitor

+++Korea_LG01
menu = LG_164.124.101.31
title = 164.124.101.31
host = 164.124.101.31

+++Korea_LG
menu = LG_203.248.240.31
title = LG_203.248.240.31
host = 203.248.240.31

++Korea_KT
menu = Korea_KT
title = Korea_KT Monitor

+++Korea_KT01
menu = KT_168.126.63.1
title = KT_168.126.63.1
host = 168.126.63.1

+++Korea_KT02
menu = KT_112.175.234.1
title = KT_112.175.234.1
host = 112.175.234.1

++Korea_DACOM
menu = Korea_DACOM
title = Korea_DACOM Monitor

+++Korea_DACOM01
menu = DACOM_211.234.125.1
title = DACOM_211.234.125.1
host = 211.234.125.1

++Korea_ONSE
menu = Korea_ONSE
title = Korea_ONSE Monitor

+++Korea_ONSE01
menu = ONSE_210.118.170.1
title = ONSE_210.118.170.1
host = 210.118.170.1

++Korea_NEWWORD
menu = Korea_NEWWORD
title = Korea_NEWWORD Monitor

+++Korea_NEWWORD01
menu = NEWWORD_121.170.178.254
title = NEWWORD_121.170.178.254
host = 121.170.178.254

++Korea_KIDC
menu = Korea_KIDC
title = Korea_KIDC Monitor

+++Korea_KIDC01
menu = KIDC_211.234.125.15
title = KIDC_211.234.125.15
host = 211.234.125.15

+Taiwan
menu = Taiwan
title = Taiwan Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++Taiwan_01
menu = 168.95.1.1
title = 168.95.1.1
host = 168.95.1.1

++Taiwan_02
menu = 168.95.192.1
title = 168.95.192.1
host = 168.95.192.1

+Macao
menu = Macao
title = Macao Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++Macao_01
menu = 202.175.3.8
title = 202.175.3.8
host = 202.175.3.8

++Macao_02
menu = 202.175.3.3
title = 202.175.3.3
host = 202.175.3.3

+HongKong
menu = HongKong
title = HongKong Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++HongKong_01
menu = 205.252.144.228
title = 205.252.144.228
host = 205.252.144.228

++HongKong_02
menu = 202.181.202.140
title = 202.181.202.140
host = 202.181.202.140

+Thailand
menu = Thailand
title = Thailand Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++Thailand_01
menu = 202.44.8.34
title = 202.44.8.34
host = 202.44.8.34

++Thailand_02
menu = 202.44.8.2
title = 202.44.8.2
host = 202.44.8.2

+Malaysia
menu = Malaysia
title = Malaysia Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++Malaysia_01
menu = 60.48.181.1
title = 60.48.181.1
host = 60.48.181.1

+Japan
menu = Japan
title = Japan Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++Japan_01
menu = 202.12.27.33
title = 202.12.27.33
host = 202.12.27.33

+Britain
menu = Britain
title = Britain Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++Britain_01
menu = 193.0.14.129
title = 193.0.14.129
host = 193.0.14.129

+India
menu = India
title = India Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++India_01
menu = 202.138.96.2
title = 202.138.96.2
host = 202.138.96.2


+earth
menu = The earth
title = World NetWord Monitor
alerts= NetWork_Disruption,Disruption_Recover,Critical_Loss,Warnning_Loss,Network_Latency

++asia
menu = Asia
title =亚洲

+++inbom02
menu = 孟买
title = 印度_孟买
host = 103.29.232.128

+++inblr01
menu = 班加罗尔
title = 印度_班加罗尔
host = 103.29.233.80

+++inicd01
menu = 新德里
title = 印度_新德里
host = 103.29.234.43

+++idjkt02
menu = 雅加达
title = 印度尼西亚_雅加达
host = 103.31.44.31

+++mykul02
menu = 吉隆坡
title = 马来西亚_吉隆坡
host = 111.90.146.93

+++cnsha02
menu = 上海
title = 中国_上海
host = 114.80.200.125

+++thbkk02
menu = 曼谷
title = 泰国_曼谷
host = 124.109.1.181

+++ilktm01
menu = 基尔亚特-马特隆
title = 以色列_基尔亚特-马特隆
host = 185.18.204.162

+++aedxb01
menu = 迪拜
title = 阿拉伯联合酋长国_迪拜
host = 185.56.88.74

+++trist02
menu = 伊斯坦布尔
title = 土耳其_伊斯坦布尔
host = 185.84.181.140

+++hkhkg01
menu = 香港特别行政区
title = 中国_香港特别行政区
host = 203.142.29.40

+++vnsgn01
menu = 胡志明市
title = 越南_胡志明市
host = 221.132.34.183

+++cnhgh01
menu = 杭州
title = 中国_杭州
host = 42.121.107.3

+++saruh01
menu = 利雅得
title = 沙特阿拉伯_利雅得
host = 46.151.210.118

+++sgsin03
menu = 新加坡
title = 新加坡_新加坡
host = 52.76.98.151

+++jptok02
menu = 东京
title = 日本_东京
host = 54.92.24.136

+++krsel01
menu = 首尔
title = 韩国_首尔
host = 66.232.145.38

++north_america
menu = North_America
title =北美

+++uschi02
menu = 芝加哥
title = 美国_芝加哥
host = 166.78.103.87

+++usdal02
menu = 达拉斯
title = 美国_达拉斯
host = 166.78.63.246

+++usbos01
menu = 波士顿
title = 美国_波士顿
host = 173.237.206.122

+++camtr02
menu = 蒙特利尔
title = 加拿大_蒙特利尔
host = 198.100.146.37

+++usphx01
menu = 菲尼克斯
title = 美国_菲尼克斯
host = 198.143.145.2

+++cacal01
menu = 卡尔加里
title = 加拿大_卡尔加里
host = 199.204.215.216

+++usnyc01
menu = 纽约州
title = 美国_纽约州
host = 208.85.4.114

+++uschi04
menu = 芝加哥
title = 美国_芝加哥
host = 216.104.36.90

+++usaus02
menu = 奥斯汀
title = 美国_奥斯汀
host = 216.139.225.45

+++cavan03
menu = 温哥华
title = 加拿大_温哥华
host = 216.187.110.142

+++usclt02
menu = 夏洛特
title = 美国_夏洛特
host = 216.249.110.98

+++uslax02
menu = 洛杉矶
title = 美国_洛杉矶
host = 23.109.89.106

+++usatl02
menu = 亚特兰大
title = 美国_亚特兰大
host = 23.82.53.98

+++usabn07
menu = 阿什伯恩
title = 美国_阿什伯恩
host = 52.2.187.184

+++ussfo02
menu = 旧金山
title = 美国_旧金山
host = 64.151.112.148

+++usscz03
menu = 圣克拉拉
title = 美国_圣克拉拉
host = 64.15.187.2

+++usstl01
menu = 圣路易斯
title = 美国_圣路易斯
host = 65.175.71.138

+++ussea03
menu = 西雅图
title = 美国_西雅图
host = 66.150.174.237

+++usorl01
menu = 奥兰多
title = 美国_奥兰多
host = 66.35.77.107

+++usmia02
menu = 迈阿密
title = 美国_迈阿密
host = 67.215.160.7

+++cator02
menu = 多伦多
title = 加拿大_多伦多
host = 70.33.239.181

+++usslc01
menu = 盐湖城
title = 美国_盐湖城
host = 70.99.242.33

+++ussan01
menu = 圣地亚哥
title = 美国_圣地亚哥
host = 71.6.150.144

+++uswbu01
menu = 博尔德
title = 美国_博尔德
host = 72.18.213.17

+++usphl01
menu = 费城
title = 美国_费城
host = 76.8.52.242

++south_america
menu = South_America
title = 南美

+++brrio01
menu = 里约热内卢
title = 巴西_里约热内卢
host = 177.47.100.51

+++brpoa01
menu = 阿雷格里港
title = 巴西_阿雷格里港
host = 187.1.142.186

+++crsjo01
menu = 圣约瑟
title = 哥斯达尼加_圣约瑟
host = 190.10.9.27

+++papty01
menu = 巴拿马市
title = 马拿马_巴拿马市
host = 190.123.47.234

+++arbue01
menu = 布宜诺斯艾利斯
title = 阿根廷_布宜诺斯艾利斯
host = 200.85.154.161

+++brsao04
menu = 圣保罗
title = 巴西_圣保罗
host = 54.94.254.9

++europe
menu = Europe
title = 欧洲

+++gblon01
menu = 伦敦
title = 英国_伦敦
host = 109.73.76.170

+++demuc02
menu = 慕尼黑
title = 德国_慕尼黑
host = 148.251.186.102

+++itrom02
menu = 罗马
title = 意大利_罗马
host = 151.1.182.96

+++esmad02
menu = 马德里
title = 西班牙_马德里
host = 164.138.213.6

+++plwrs01
menu = 华沙
title = 波兰_华沙
host = 178.250.45.77

+++plgdn01
menu = 格丹斯克
title = 波兰_格丹斯克
host = 188.116.4.188

+++gbmnc01
menu = 曼彻斯特
title = 英国_曼彻斯特
host = 188.65.179.3

+++ruled01
menu = 圣彼得堡
title = 俄罗斯联邦_圣彼得堡
host = 188.93.20.186

+++noosl02
menu = 奥斯陆
title = 挪威_奥斯陆
host = 193.107.29.195

+++beanr02
menu = 安特卫普
title = 比利时_安特卫普
host = 193.239.211.39

+++rsbeg01
menu = 贝尔格莱德
title = 塞尔维亚_贝尔格莱德
host = 193.243.171.13

+++itpda01
menu = 帕多瓦
title = 意大利_帕多瓦
host = 195.47.199.229

+++chgva01
menu = 日内瓦
title = 瑞士_日内瓦
host = 195.70.7.234

+++robuh01
menu = 布加勒斯特
title = 罗马尼亚_布加勒斯特
host = 195.88.174.47

+++atvie01
menu = 维也纳
title = 澳大利亚_维也纳
host = 212.69.168.251

+++czprg01
menu = 布拉格
title = 捷克共和国_布拉格
host = 217.16.185.66

+++rumow02
menu = 莫斯科
title = 俄罗斯联邦_莫斯科
host = 31.131.253.230

+++frlle02
menu = 里耳
title = 法国_里耳
host = 46.29.125.10

+++iedub03
menu = 都柏林
title = 爱尔兰_都柏林
host = 52.18.211.154

+++defra03
menu = 法兰克福
title = 德国_法兰克福
host = 52.29.56.67

+++grath01
menu = 雅典
title = 希腊_雅典
host = 62.1.216.115

+++nlams05
menu = 阿姆斯特丹
title = 荷兰_阿姆斯特丹
host = 62.148.170.10

+++chzrh01
menu = 苏黎世
title = 瑞士_苏黎世
host = 62.2.86.176

+++gbglw01
menu = 格拉斯哥
title = 英国_格拉斯哥
host = 78.129.231.9

+++ltvno01
menu = 维尔纽斯
title = 立陶宛_维尔纽斯
host = 79.98.31.14

+++decgn01
menu = 科隆
title = 德国_科隆
host = 80.237.153.112

+++dkcph02
menu = 哥本哈根
title = 丹麦_哥本哈根
host = 82.103.128.238

+++fitmp02
menu = 坦佩雷
title = 芬兰_坦佩雷
host = 83.143.217.245

+++nlgrq02
menu = 格罗宁根
title = 荷兰_格罗宁根
host = 89.200.203.128

+++deber01
menu = 柏林
title = 德国_柏林
host = 91.102.10.52

+++uahrk02
menu = 哈尔科夫
title = 乌克兰_哈尔科夫
host = 91.203.146.58

+++uaiev01
menu = 基辅
title = 乌克兰_基辅
host = 91.211.117.14

+++bgsof02
menu = 索非亚
title = 保加利亚_索非亚
host = 91.230.195.119

+++frpar03
menu = 巴黎
title = 法国_巴黎
host = 92.243.23.29

+++sesto01
menu = 斯德哥尔摩
title = 瑞典_斯德哥尔摩
host = 94.254.0.224

+++ptlis01
menu = 里斯本
title = 葡萄牙_里斯本
host = 94.46.216.34

+++hubud01
menu = 布达佩斯
title = 匈牙利_布达佩斯
host = 95.140.33.161

+++itmil01
menu = 米兰
title = 意大利_米兰
host = 95.141.32.125

++australia
menu = Australia
title = 澳洲

+++aumel02
menu = 墨尔本
title = 澳大利亚_墨尔本
host = 103.12.8.33

+++nzakl03
menu = 奥克兰
title = 新西兰_奥克兰
host = 103.6.144.238

+++auper01
menu = 珀斯
title = 澳大利亚_珀斯
host = 118.88.19.195

+++ausyd03
menu = 悉尼
title = 澳大利亚_悉尼
host = 182.160.155.248

+++aubne02
menu = 布里斯班
title = 澳大利亚_布里斯班
host = 202.60.69.42

++africa
menu = Africa
title = 非洲

+++zacpt02
menu = 开普敦
title = 南非_开普敦
host = 41.223.34.194

+++egcai01
menu = 开罗
title = 埃及_开罗
host = 41.223.53.75

+++zadur01
menu = 德班
title = 南非_德班
host = 41.79.156.2

+++zajnb01
menu = 约翰尼斯堡
title = 南非_约翰尼斯堡
host = 41.79.36.222

```