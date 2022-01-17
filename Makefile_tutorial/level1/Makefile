
# 检索src目录查找cpp为后缀的文件路径， 用shell指令的find
srcs := $(shell find src -name "*.cpp")

# 将srcs的会追为c.pp的 替换为.o
objs1 := $(srcs:.cpp=.o)

# 将src/前缀替换为objs/前缀， 让o文件放到objs目录下。
objs := $(objs1:src/%=objs/%)


# 定义objs下的o文件， 依赖src下对应的cpp文件
# $@ = 左边的生成项
# @< = 右边依赖项第一个
objs/%.o : src/%.cpp
	@echo 编译$< 生成$@, 目录是:$(dir $@)
	@mkdir -p $(dir $@)
	g++ -c $< -o $@

# $^ = 右边依赖项全部
# 我们把pro放到workspace下面
workspace/pro : $(objs)
	@echo 这里的依赖项所有是[$^]
	@echo 链接$@
	g++ $^ -o $@

# 定义简介指令， make pro即可生成程序
pro : workspace/pro
	@echo 编译完成

# 定义make run， 编译好pro后，顺便执行一下
run : pro
	@cd workspace && ./pro

# 定义make clean, 清理掉编译留下的垃圾
clean :
	@rm -rf workspace/pro objs

# 定义伪符号， 这些符号不是做文件， 视作指令
# 也可以说， 视作永远都不存在的文件。
。PHONE : pro run debug clean
debug :
	@echo srcs = $(srcs)
	@echo objs1 = $(objs1)
	@echo objs = $(objs)