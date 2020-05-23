# post-quantum-cryptography
摘自：
https://zhuanlan.zhihu.com/p/45393166
https://zhuanlan.zhihu.com/p/45662344

后量子密码，是[能够抵抗量子计算机对现有密码算法攻击的]新一代密码算法。

量子算法可以完全攻破一系列基于数学问题的公钥算法，如离散对数（椭圆曲线），大整数分解等。对于私钥算法，如AES，SHA1（2），量子算法影响不如公钥算法大。

4种后量子密码算法：
1. 基于哈希，主要用于构造数字签名。如Merkle 哈希树签名、XMSS、Lamport 签名等
2. 基于编码， 主要用于构造加密算法。如McEliece
3. 基于多变量，主要用于构造数字签名、加密、密钥交换等。代表方法/算法：HFE (Hidden Field Equations)、Rainbow (Unbalanced Oil and Vinegar (UOV) 方法)、HFEv- 等
4 基于格，主要用于构造加密、数字签名、密钥交换，以及众多高级密码学应用，如：属性加密 (Attribute-based encryption)、陷门函数 (Trapdoor functions)、伪随机函数 (Pseudorandom functions)、同态加密 (Homomorphic Encryption) 等。代表算法：NTRU 系列、NewHope (Google 测试过的)、一系列同态加密算法 (BGV、GSW、FV 等)。由于其计算速度快、通信开销较小，且能被用于构造各类密码学算法和应用，因此被认为是最有希望的后量子密码技术

# 基于格的算法
在
  1 安全性
  2 公私钥尺寸
  3 计算速度
三个维度达到了平衡

近年来，基于 LWE (Learning with Errors) 问题 [9] 和 RLWE (Ring-LWE) 问题 [10] 的格密码学构造发展迅速，被认为是最有希望被标准化的技术路线之一。

# 格
在m维线性空间中，一组互相线性无关的向量的整数线性组合。

密码学中的格维度一般在1000左右。

# 格中的困难问题
例如：TU Darmstadt 给出了一系列格问题挑战：SVP Challenge、LWE Challenge、Lattice Challenge、Ideal Lattice Challenge 等

1. Shortest Vector Problem. 给定格L，找到一个非零向量v，使之对于格中的任意的非零向量u，||v||小于等于||u||
2. approximate SVP. 给定格L，找到一个非零向量v，使之对于格中的任意的非零向量u，||v||小于等于lambda*||u||,lambda 大于等于1
3. Unique Shortest Vector Problem, uSVP
4. 近似最短向量问题判定版本 (GapSVP)
5. Closest Vector Problem, CVP
6. pproximate Closest Vector Problem, aCVP
7. Bounded Distance Decoding, BDD
8. Shortest Independent Vector Problem, SIVP

# 新的格问题
新的格困难问题中，有几种重要的平均情况困难的问题：SIS、LWE、RLWE 及变种。在一定的参数设定下，这些问题可以归约到 GapSVP、SIVP 等格上的困难问题（即求解这些问题并不比求解格上困难问题容易）。

1. Small Integer Solutions Problem, SIS
找一个对自身膜有约束的m维向量v，使Av = 0 mod q，A 为 n\*m的矩阵，q为矩阵
2. Learning with Errors Problem, LWE
给定均匀生成的矩阵，A，向量s，e，满足b = As+e。搜索版本，给定多组A，b，找s。判定版本，将b和均匀生成的向量区分。
