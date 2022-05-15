[> Back](../README.md#网络安全)

# 一次性口令

Created: November 8, 2021
Sort: Security

> OTP（One-Time Password）：动态口令又叫作一次性口令。

## 1. OTP的好处

通常情况下，一次性密码有两个好处：

- 避免密码安全性的常见陷阱：组合规则，已知的错误和弱密码，共享凭据或在多个帐户和系统上重复使用相同的密码；

- 避免二次使用：它们会在几分钟内失效，这可以防止攻击者获取密码并再次使用它们。

## 2. 挑战/应答是否需要时间同步机制？

不需要。

OTP按技术分为三种形式，时间同步、事件同步、挑战/应答：

- 时间同步
    
    **原理**：基于动态令牌和动态口令验证服务器的时间比对，基于时间同步的令牌，一般每60秒产生一个新口令。
    
    **要求**：服务器能够十分精确的保持正确的时钟，同时对其令牌的晶振频率有严格的要求，这种技术对应的终端是硬件令牌。
    
- 事件同步
    
    **原理**：基于事件同步的令牌，通过某一特定的事件次序及相同的种子值作为输入。
    
    **应用**：通过HASH算法中运算出一致的密码。
    
- 挑战/应答
    
    **原理**： 动态令牌输入该挑战码，通过内置的算法上生成一个6/8位的随机数字，口令一次有效。

    **应用**：在网站/应答上输入服务端下发的挑战码，包括刮刮卡、短信密码、动态令牌也有挑战/应答形式。