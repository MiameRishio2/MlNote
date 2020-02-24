生成对抗网络GAN是一类生成模型。是一种无监督的深度学习。神经网络的主要擅长的是判别模型。2014年Goodfellow提出神之一手的GAN模型，GAN的经典模型包含Generator和Discriminator，Generator用来生成数据，Discriminator用来做数据的判定。通过反复的迭代生成和判定，让生成的结果让判定器无法识别来达到生成的目的。以下是具体原理：

Generator是一个数据的生成器，首先随机一个噪音z，通过噪音生成一个数据G(z)。所以定义损失函数：
max{-1 * (1 - y) * log(1 - D(G(z)))} = max{-log(1 - D(G(z)))}
可以直观的理解成要让D(G(z))尽可能的接近1，来骗过Discriminator

Discriminator是一个数据判别器，判别这个数据是否Real。如果一个真实的数据，Discriminator就会给出概率1，相反的如果是给出概率0，就代表这个不是真的数据。所以定义损失函数：
min{-y * log(D(x)) - (1 - y)log(1 - D(x))}
可以直观理解成让图像尽量拟合真实的数据接近1和虚假的数据接近0

交替训练Discriminator和Generator，最终让Discriminator难以分辨数据是否真实。

GAN的基本原理比较简单，大大推进了AI无监督学习的进程。现在已经有很多种不同的GAN的进化算法，可以在https://github.com/hindupuravinash/the-gan-zoo上找到。