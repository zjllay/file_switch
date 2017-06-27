import tablib
# 返回一个文件对象
f1 = open("/Users/jiangli/Documents/学习内容/github作业/work/file_switch/courses.json")
# 调用文件的readline()方法
line = f1.readline()
while line:
    print(line)
    line = f1.readline()
f1.close()
print("----json switch excel----")
# 写入到外部文件中
output = open('file_switch.xls','wb')
with open('file_switch','w') as switch:
    data = tablib.Dataset().load(open('/Users/jiangli/Documents/学习内容/github作业/work/file_switch/courses.json').read())
    # # .xls为二进制文件，所以直接print会出现乱码写的是二进制文件
    switch = data.xls
    output.write(switch)
    output.close()
