---
layout: post
title: "加密货币如何泄露隐私；门罗币(Monero, XMR)是如何保护隐私的"
date:   2023-01-14
tags: [加密货币，Monero，区块链]
comments: true
author: Arnold
toc: true
---

比特币、以太币等货币的转账记录在其区块链上，由于区块链所有人可见，因此转账记录也是所有人可见

如果你的朋友向由你实际控制的账户（别人能看到地址，也就是公钥，而只有你有私钥）支付1比特币，事后他因贩毒被抓，那么执法机构就知道这个账户里有涉毒资金)

下次你用同一账户在小卖部购买饮料（转账给店主），执法机构便知道，买饮料的你就是当初涉毒的你（因为使用的账户地址相同），于是你就进去了
***
你可以将这些钱转到你拥有的其他账户，但无论转多少次，记录都是公开的，所以这笔钱怎么也洗不干净
***
Monero的解决方案：转账的时候，转账记录不是一对一（发送者和接收者），而是多对一的。

一笔转账记录看上去类似这样：
```
小明    
小刚    
小李 --> 阿强
小赵    
小米    
```
其中只有一个发送者是真实的，其他发送者都是凑数的。

该转账记录通过非常复杂的公钥密码学算法加密、签名，参见https://eprint.iacr.org/2017/1066.pdf。

在第三方看来：
* 确定该转账行为是合法的（发起人是账户持有人）
* 确定转账的数目是合法的（转账完成后，被转出账户的余额大于等于零）
* 无法确定收款人是谁
* 无法确定五个转账人是谁
* 转账人可能是五个人中的任意一个，无法确定是哪个
* 无法确定转账金额
* 无法确定账户余额

在阿强（收款账户的实际持有者，拥有对应的私钥）看来：
* 确定收到了一笔钱
* 可以将这笔钱转作他用
* 知道这笔钱的数目
* 无法确定转账人是谁
* 转账人可能是五个人中的任意一个，无法确定是哪个
***
当你的朋友向你支付1门罗币，事后他因贩毒被抓，由于上面介绍的原因，执法部门知道他把门罗币转给了一个地址，但执法部门并不知道这个地址的实际控制人是你。（别人只能看到地址，也就是公钥，而对应的私钥在你手中）

你去小卖部购买饮料，并转账给店主。由于上面介绍的原因，执法部门在区块链上看不到你之前接收毒资时使用的收款地址。他们只能看到五个被加密的地址共同购买了饮料，即便他们确定其中一个地址包含毒资，也无法确定那个地址到底是真的被用于本次交易，还是被随机拉来凑数的。

除此之外，其他人使用Monero进行交易时，也会不断地拉各种无关账户（包括你的涉毒账户）进来凑数。经过一段时间的“混合”，执法部门已经无法确定这些钱到底在哪一笔交易中真正被使用、最终去到了哪些账户中。

这种“混合”(mixing)帮助Monero掩盖账户的交易历史，每次交易的混合比例是可选的，用于混合的账户数越多，匿名性就越好，手续费也越高。

总之，用于混合的账户数越多，以及混合的次数越多，资金的来源越难追踪。这就是为什么有些monero用户建议收款人将资金在自己的账户之间多转几次，以最大限度降低被执法机构盯上的风险。
***
私钥必须保管好，绝对不能落入执法部门手中，只要有私钥，一个账户的所有收款记录都能看到。
***
换言之，XMR最大的用途是洗钱。

随着中国对资金出入境监管越来越严，国内维稳越来越强力，洗钱需求必然越来越旺盛，预计XMR价格将大幅上涨。

此文就到此结束啦！欢迎大家在评论区留言哦ヾ(^▽^*)))  
Ciallo～(∠・ω< )⌒☆​  
写文不易，如果你觉得我的文章对你有帮助，欢迎[打赏](https://dotponder.github.io/likes/)！