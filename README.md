# post-quantum-cryptography
摘自：
https://zhuanlan.zhihu.com/p/45393166 

后量子密码，是[能够抵抗量子计算机对现有密码算法攻击的]新一代密码算法。

量子算法可以完全攻破一系列基于数学问题的公钥算法，如离散对数（椭圆曲线），大整数分解等。对于私钥算法，如AES，SHA1（2），量子算法影响不如公钥算法大。

4种后量子密码算法：
1. 基于哈希，主要用于构造数字签名。如Merkle 哈希树签名、XMSS、Lamport 签名等
2. 基于编码， 主要用于构造加密算法。如McEliece
3. 基于多变量，主要用于构造数字签名、加密、密钥交换等。代表方法/算法：HFE (Hidden Field Equations)、Rainbow (Unbalanced Oil and Vinegar (UOV) 方法)、HFEv- 等
4 基于格，主要用于构造加密、数字签名、密钥交换，以及众多高级密码学应用，如：属性加密 (Attribute-based encryption)、陷门函数 (Trapdoor functions)、伪随机函数 (Pseudorandom functions)、同态加密 (Homomorphic Encryption) 等。代表算法：NTRU 系列、NewHope (Google 测试过的)、一系列同态加密算法 (BGV、GSW、FV 等)。由于其计算速度快、通信开销较小，且能被用于构造各类密码学算法和应用，因此被认为是最有希望的后量子密码技术

