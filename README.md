# Bamboo-green-everywhere

Bamboo green everywhere

Problem Description

"临流揽镜曳双魂 落红逐青裙 依稀往梦幻如真 泪湿千里云"

在MCA山上,除了住着众多武林豪侠之外,还生活着一个低调的世外高人,他本名逐青裙,因为经常被人叫做"竹蜻蜓",终改名逐青,常年隐居于山中,不再见外人.根据山上附近居民所流传的说法,逐青有一个很奇怪的癖好,从他住进来那天开始,他就开始在他的院子周围种竹子,第1个月种1根竹子,第2个月种8根竹子,第3个月种27根竹子...第N个月就种(N^3)根竹子.他说当他种下第X根竹子那一刻,就是他重出江湖之时!告诉你X的值,你能算出逐青的复出会是在第几个月吗?

Input

首先输入一个t,表示有t组数据，跟着t行.每行是一个整数X,X < 1000000000


Output

输出一个整数n,表示在第n个月复出

Sample Input

3 1 2 10

Sample Output

1 2 3

代码：

#include<stdio.h>

int num[1001]={0};

int main()

{

    int n,i,m;
    
    for(i=1;i<1001;i++)              //这里先把每个月逐青种的竹子总数计算出来
    
        num[i]=num[i-1]+i*i*i;    //以后的数据处理就可以直接找这的计算结果
        
    scanf("%d",&n);
    
    while(n--)
    
    {
    
        scanf("%d",&m);
        
        for(i=0;;i++)
        
            if(m>num[i]&&m<=num[i+1])    //i遍历找到符合条件的数
            
                break;
                
        printf("%d\n",i+1);
        
    }
    
}

