#### 面向车载CAN网络的模拟攻击数据集

##### 文件格式说明
1. 文件命名格式：包含三个文件夹：训练、验证、测试数据集，文件名称格式为：攻击类型+异常CAN ID，对应不同的攻击数据类型。

2. 文件内容格式：所有数据保存为二进制文件，压缩了存储所需的内存大小，能够提高读取效率。定义如下：

    | 偏移量 | 大小  | 描述             |
    | ------ | ----- | ---------------- |
    | 0000   | 4字节 | 包含的CAN ID总数 |
    | 0004   | 1字节 | 状态标记值       |
    | 0005   | 2字节 | CAN ID           |
    | 0007   | 1字节 | 状态标记值       |
    | 0008   | 2字节 | CAN ID           |
    | ...    | ...   | ...              |
    
    
    
    - 文件前4个字节保存该文件的CAN ID个数。
    - 其次，第5个字节保存该CAN消息是否为异常消息的标记值，0、1、2、3、4、5分别代表正常、DoS攻击、模糊攻击、欺骗攻击、重放攻击、删除攻击。第6、7个字节表示CAN ID大小。
    - 后续字节按照一个字节表示标记值两个字节表示CAN ID的规律依次保存。
    
3. 数据集大小：如下表所示：

   | 消息类型 | 数据大小 | 占比（%） |
   | :------: | :------: | :-------: |
   | 正常状态 | 1850431  |   65.77   |
   | DoS攻击  |  283381  |   10.07   |
   | 模糊攻击 |  283381  |   10.07   |
   | 欺骗攻击 |  283380  |   10.07   |
   | 重放攻击 |  65092   |   2.31    |
   | 删除攻击 |  47749   |   1.70    |

   ​      

