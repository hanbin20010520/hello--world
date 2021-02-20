# hello--world
import random
import numpy as np

six=['年','年','年','年','年','能天使','推进之王','伊芙利特','艾雅法拉','安洁莉娜',\
    '闪灵','夜莺','星熊','塞雷娅','银灰','斯卡蒂','陈','黑','赫拉格','麦哲伦','莫斯提马',\
    '煌','阿','刻俄柏','风笛','傀影','温蒂','早露','铃兰','棘刺','森蚺','史尔特尔','瑕光',\
    '泥岩','山','空弦']
five=[['白面鸮','凛冬','德克萨斯','芙兰卡','拉普兰德','蓝毒','白金','陨星','天火','梅尔','赫默','华法琳','临光'],\
    ['红','雷蛇','可颂','普罗旺斯','守林人','崖心','初雪','真理','空','狮蝎','食铁兽','夜魔','诗怀雅'],\
    ['格劳克斯','星极','送葬人','槐琥','苇草','布洛卡','灰喉','吽','惊蛰','慑砂','巫恋','极境','石棉'],\
    ['月禾','莱恩哈特','断崖','蜜蜡','贾维','安哲拉','燧石','四月','奥斯塔','絮雨','卡夫卡','爱丽丝','幽灵鲨']]
four=[['夜烟','远山','杰西卡','流星','白雪','清道夫','红豆','杜宾','缠丸','霜叶','慕斯','砾','暗索'],\
    ['末药','调香师','角峰','蛇屠箱','古米','深海色','地灵','阿消','猎蜂','格雷伊','苏苏洛','桃金娘','红云'],\
    ['梅','安比尔','宴','刻刀','波登可','卡达','孑','酸糖','芳汀','泡泡','杰克','松果','豆苗']]
three=[['芬','香草','翎羽','玫兰莎','卡提','米格鲁','克罗丝','炎熔'],\
    ['芙蓉','安塞尔','史都华德','梓兰','空爆','月见夜','斑点','泡普卡']]
Sum = num = xi = liu_xing = wu_xing = si_xing = san_xing = cuo_e =0

while num == 0:
    num_1 = eval(input('请选择抽卡次数：单抽 十连\n'))
    num_2 = np.random.random(num_1)
    for i in range(0,num_1):
        if Sum >= 50:
            luck = 0.02 + 0.02 * (Sum - 49)
        else:
            luck = 0.02
        if num_2[i] <= luck:
            xing_ji = '六星'
            Sum = 0
            liu_xing += 1
            num_3 = random.random()
            if num_3 <= 0.35:
                guan_yuan = '夕'
                xi += 1
            elif num_3 >= 0.7:
                num_4 = random.randint(0,35)
                guan_yuan = six[num_4]
            else:
                guan_yuan = '嵯娥'
                cuo_e += 1
        elif num_2[i] <= (1 - luck) * (8/98) and num_2[i] > luck:
            xing_ji = '五星'
            Sum += 1
            wu_xing += 1
            num_3 =random.random()
            if num_3 > 0.5:
                guan_yuan = '乌有'
            else:
                num_4 = random.randint(0,3)
                num_5 = random.randint(0,12)
                guan_yuan = five[num_4][num_5]
        elif num_2[i] > (1 - luck) * (8/98) + luck and num_2[i] < (1 - luck) * (50/98):
            xing_ji = '三星'
            Sum += 1
            san_xing += 1
            num_3 = random.randint(0,1)
            num_4 = random.randint(0,7)
            guan_yuan = three[num_3][num_4]
        else:
            xing_ji = '四星'
            Sum += 1
            si_xing += 1
            num_3 = random.randint(0,2)
            num_4 = random.randint(0,12)
            guan_yuan = four[num_3][num_4]
        print(xing_ji+' '+guan_yuan)


