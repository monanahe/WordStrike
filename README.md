# 轻松背单词
本科期间为了（逃避）背单词写的一个小程序。
只需要一个python shell，方便边写代码边写
有一个一运行就崩溃的安卓版本，没有发布。
附赠GRE佛教单词 20List

##Background
###适合人群：
喜欢在电脑上背单词的人群
大规模单词（如GRE/GMAT）背诵者
计算机从业者边写代码边背单词
适用看英文想中文的背单词模式
不喜欢app自带的词库，想背自己自定义的词库
亲测：GRE 2500词的佛脚词，100单词/List，每天背一个新List，复习3-5个list的单词。快速过3遍错词。20天左右可背完一轮，熟悉度70%。

## GetStarted
### 单词list文件
你自己的单词文件放入words/
输入文件只需要一个中文+英文的文件即可，.txt/.csv/.tsv/.whatever 等任何python可读写的格式都可以。
也完美支持excel xlsx格式。
[pic/input_file_excel.png]
[pic/input_file_txt.png]

### 支持功能
可一次背10个、100个、1000等任意数量个单词。
可以一次背一个list文件的单词，顺序或者打乱。
也可以将几个单词list文件的单词放在一起打乱顺序背诵。
支持自动发音，调用有道API。
正确/错误的音效提示。
支持输出准确率、查背错的单词。
背错单词自动输出到wrong.csv文件。
其他可选的参数还很多。

###使用说明
实例化WordTest的参数说明：
背诵单个单词文件F17.xlsx，从单词文件的第1个单词，到第90个单词，背诵模式为“随机”，计分模式，会打印你背错的单词和正确率，会存储本次背单词的相关记录到/record的pickle文件中（这项功能其实没啥用，可以忽略）
'''
test1=WordTest(filename='F17.xlsx',start=0,end=90,mode='random',score=True,save=1)
test1.go()
'''
屏幕会输出单词序号和英文单词
'''
out[1]:2/.immerse
'''
然后你需要回想这个单词的中文释义，想起来按“回车”，想不起来放弃按“任意键”，不想背了按“q”。
之后屏幕会输出正确的中文含义。
'''
out[1]:2/.immerse

浸润
'''
如果跟你想的一样，按“回车”，记录一次正确，如果和你想的不一样，按“任意键”，系统会记录下这个错误的单词，之后在一次单词测试结束后，统计你的正确率，并输出所有错误的单词到wrong.csv。
然后继续下一个单词。
非常机械的操作，很适合背GRE单词。背的好的话，一个单词大概3秒，一分钟可以过20个单词，五分钟过完100个单词。

##Contributing
整个代码还是比较好看懂的，只要你能大概看懂，用起来会非常方便的。
可以自己增添接口、修改函数，满足自己的更多需求。
大三写的程序，总的来说写的挺烂，但是完全能满足自己背单词的各种需求，用起来很顺手。