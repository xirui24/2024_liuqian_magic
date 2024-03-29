# 2024春晚刘谦魔术Python复现
本项目包含两个文件，使用堆栈方法复现刘谦2024春晚魔术              
2024_liuqian_magic_proof.py为证明版本      
2024_liuqian_magic_interaction.py为互动版本

## 证明版本
### 证明步骤如下：
1. 随机四张牌，假设为ABCD      
2. 撕开它们并且同方向放置，手里的牌目前为ABCDABCD      
3. 名字字数：随机一个数字n（2-7范围内的任意整数），将最前面的n张牌放到最后            
   例如n等于2，目前牌堆：CDABCDAB      
4. 将前三张牌取出并插入剩余牌的任意位置          
   例如第三步结束是CDABCDAB，将CDA随机插入剩下BCDAB里的任意位置，如DA之间，目前牌堆：BCDCDAAB      
5. 将最上面的牌取出，并放到一边          
   例如第四步结束为BCDCDAAB，将第一张B删除并放在一边后，目前牌堆为CDCDAAB      
6. 地域：从1-3中随机选取任意整数a，将剩余牌中的前a张插入剩余牌堆的任意位置
   例如a=3，将前3张牌，也就是CDCDAAB中的CDC随机插入剩下的DAAB中任意位置，例如DA之间，目前牌堆：DCDCAAB      
7. 性别：从1-2中随机选取任意整数b，移去牌堆中的前b张牌        
    例如b=2，从DCDCAAB中移去DC，目前牌堆：DCAAB      
8. 见证奇迹的时刻：将第一张牌移到最后，重复7次      
    例如第上一部剩余DCAAB，移动7次分别是CAABD，AABDC，ABDCA，BDCAA，DCAAB，CAABD，AABDC，最后得到AABDC      
9. 好运留下来，烦恼丢出去：对剩余的牌交替进行“将第一张牌移到最后”和“将第一张牌删除”这两个操作，直到只剩下一张牌            
    例如上一步剩下的牌是AABDC，根据指令剩余的依次是ABDCA，BDCA，DCAB，CAB，ABC，BC，CB，最后扔掉C，剩余的牌B和第五步中放到一边的B相同     
              
随机模拟一万次，正确率为100%


## 互动版本
用户可自行输入参数:      
1. 姓名字数
2. 地域：1-3之间整数，1代表南方人，2代表北方人，3代表不确定
3. 性别：1或2，1代表男性，2代表女性
