Marktodo： A syntax for TODO lists
	
	#any.do#
	=project name
		-todo list
			[-] todo item A
			[=] doing item B
			[+] done item C
		+done list
			[+] done item a
			[+] done item b
			[+] done item c
	

# 系统标识 #

使用2个#号包含起来，放在第一行。系统标识用来标识该文档由什么系统生成，可选。

例如 
	
	#any.do#

# 标记符号 #

	= 等于号标识项目名称

	- 减号标识未完成的TODO任务列表

	+ 加号标识已经完成的TODO任务列表

	[-] 中括号中包含减号，标识未完成的TODO任务

	[=] 中括号中包含等于号，标识正在做的TODO任务

	[+] 中括号中包含加号，标识已经完成的TODO任务

标记符号前后都可以有空格/Tab键，也可以没有

# 附加信息 #

格式：

	[xxx1=yyy1 xxx2=yyy2] 

附加信息是对Project，TODO list，TODO item信息的补充，位置放在信息的最后。

支持的附加字段：

	- id 			全局唯一标识
 	
	- user 			TODO任务的创建者/完成者
	
	- complete-date TODO任务的完成时间(格式： YYYY-MM-DD)
	
	- creation-date TODO任务的创建时间(格式： YYYY-MM-DD)
	
	- due-date 		TODO任务预计完成时间(格式： YYYY-MM-DD)

Project，TODO list只支持id、user字段

任何附加字段都是可选的，附加字段的值可以使用双引号""包含起来,也可以不用，字段之间使用空格分割。

# 例子 #

	#any.do#

	=project1 [id=1 user=test1]
		-todo list1 [id=1]
			[-] todo item A [user=test1 due-date=2013-01-20]
			[=] doing item B [user=test2]
			[+] done item C [user=test1 complete-date=2013-01-15]
		+done list2 [id=2]
			[+] done item a [id=1 user=test1 due-date=2013-01-20 complete-date=2013-01-15]
			[+] done item b [id=2 user=test1 complete-date=2013-01-15]
			[+] done item c [id=3 user=test2 complete-date=2013-01-15]
	
	=project2 [id=2 user=test2]
		-todo list1 [id=3]
			[-] todo item A [user=test1]
			[=] doing item B [user=test1]
			[+] done item C [user="test username1" complete-date=2013-01-15]

	=project3
		-todo list1
			[-] todo item A
			[=] doing item B
			[+] done item C
		+done list2
			[+] done item a
			[+] done item b
			[+] done item c



# 用途 #

1、方便存储

2、方便交互(导入/导出，数据迁移)



