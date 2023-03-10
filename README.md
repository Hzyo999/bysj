##<font size=8>毕业设计进度

###<font size=6>20230309
<font size=5 face="黑体">本周阅读了FEMU中写入操作部分和部分代码需改。对于FEMU写操作部分，FEMU中采用NVME协议结合QEMU中的内存管理方式来实现I/O操作。我结合NVME 1.3协议和QEMU的相关文档进行项目中相关代码的阅读。然后简单构思了一下需要实现的部分和需要注意的点：写入缓冲区需要设置在NVME写操作从内存中获取数据并进行分页之后，同时写入缓冲区的设置是页对齐且分配了页号（即把写入缓冲区当成NAND Flash），这样从缓冲区进行读取就只需要先遍历写缓冲区，若未命中再从Flash中读取。实现上，本周只进行小部分的代码修改，准备下一周完成关于设置写缓冲区相关的代码修改。