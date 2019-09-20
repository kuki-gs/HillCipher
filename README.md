# HillCipher
## 数学原理说明：
K为n*n维矩阵，要求满秩，且det(K)与26互质。
*  加密：
c=m*K mod 26
*  解密：
m=c*K1 mod 26
*  解密矩阵推导
K1= Kw*INV mod 26 其中Kw为K的伴随矩阵，INV为det(K)关于26的模反，可用模反算法求得。

推导过程：


 c   * (Kw*INV mod 26) mod 26
                 
 = (m*K mod 26) * (Kw*INV mod 26) mod 26
 
=  (m*K+26*P1) * (Kw*INV+26*P2) mod 26   #P1，P2为整数矩阵

=   m*K*Kw*INV mod 26 + 0

=   m*K*K_1*det(K)*INV mod 26       #逆矩K_1 = Kw/det(K)

=   m*det(K)*INV mod 26 

又因：det(K)*INV = 1 mod 26 = 1 + 26*P4，代入

=   m*(1+26*P4) mod 26 

=   m + 0
