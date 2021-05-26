# 指令与程序在主机上执行过程

### 主机模型图

![CPU&#x548C;&#x5B58;&#x50A8;&#x4F53;&#x4EA4;&#x4E92;&#x53D6;&#x6307;&#x4EE4;&#xFF0C;MAR&#xFF0C;MDR&#x4F4D;&#x7F6E;&#x8BE6;&#x89C1;&#x8BF4;&#x660E;](../.gitbook/assets/image%20%281%29.png)



> 1. 取指令（PC:存放当前预执行指令的地址，具有计数功能（PC）+1 -&gt;PC）
> 2. 分析指令（IR：存放当前预执行的指令）
> 3. 执行指令（CU）

### 主机完成一条指令的过程

![&#x53D6;&#x6570;](../.gitbook/assets/image%20%2813%29.png)

#### 取数指令步骤 

1. 取指令
   1. PC将指令地址给MAR 
   2. MAR将指令地址给存储体 
   3. 在控制器控制下，将存储体中的取数指令取出并保存到MDR 
   4. 取出的MDR中的指令存储到IR中 
2. 分析指令 
   1. 把IR中操作码部分送给CU
3. 执行指令 
   1. IR中存放了这条指令的地址，也保存了当前这条指令操作数的地址
   2. 所以从IR中将地址送给MAR，来取操作数
   3. MAR将指令地址给存储体 
   4. 在控制器控制下，将存储体中的数据取出并保存到MDR 
   5. 在控制器的作用下，将MDR中的数据存放在ACC中

![&#x53D6;&#x6570;&#x6307;&#x4EE4;&#x5B8C;&#x6210;](../.gitbook/assets/image%20%287%29.png)

#### 存数指令步骤

![](../.gitbook/assets/image%20%2812%29.png)

### 说明

{% hint style="danger" %}
 主存的工作方式是按照存储单元的地址进行存取，这种存取方式称为按地址存取方式（相联存储器是按内容访问的）。

存储体存放二进制信息

MAR存放访存地址，经过地址译码后找到所选的存储单元。

MDR用于暂存要从存储器中读或写的信息，时序控制逻辑用于产生存储器操作所需的各种时序信号。  
  
**注意MAR和MDR虽然是存储器的一部分，但是在现代CPU中却是存在于CPU中的；另外高速缓存Cache也存在于CPU中。**
{% endhint %}

### 例题

![](../.gitbook/assets/image%20%283%29.png)

### 引用

> [https://bbs.csdn.net/topics/394965144](https://bbs.csdn.net/topics/394965144)
>
> [https://blog.csdn.net/ChenfengZhang/article/details/108069525?spm=1001.2014.3001.5501](https://blog.csdn.net/ChenfengZhang/article/details/108069525?spm=1001.2014.3001.5501)

