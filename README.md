# Hash算法

一个优秀的 Hash 算法，将能满足：

- 正向快速：给定原文和 Hash 算法，在有限时间和有限资源内能计算得到 Hash 值；
- 逆向困难：给定（若干）Hash 值，在有限时间内无法（基本不可能）逆推出原文；
- 输入敏感：原始输入信息发生任何改变，新产生的 Hash 值都应该发生很大变化；
- 碰撞避免：很难找到两段内容不同的明文，使得它们的 Hash 值一致（即发生碰撞）。

哈希函数主要有三个特性：

1、碰撞特性（collision resistance）；假设输入x1，哈希值为H(x1)，此时很难找到一个x2，使得H(x1)=H(x2)。

2、隐秘性（Hiding）；哈希函数的计算过程是单向的，不可逆的。给定一个输入值X，可以算出哈希值H(x)，但是不能从H(x)推出X。

3、谜题友好（puzzle friendly）。求解一个长随机数n，这个n和区块链中的区块的块头组成输入信息x，使x的hash值h(x)落在某个指定的范围内。

## Message Digest（MD）

MD5 已于 2004 年被成功碰撞

## Secure Hash Algorithm（SHA）

```jsx
echo "hello world"  | shasum -a 256
a948904f2f0f479b8f8197694b30184b0d2ed1c1cd2a1ec0fb85d299a192a447  -
```

# **非对称加密**

RSA

```go
ssh-keygen -t rsa -C "My-SSH"
```

ED25519

```go
ssh-keygen -t ed25519 -C "My-SSH"
```

## **数字证书**

使用 PEM（Privacy Enhanced Mail）格式来存储证书相关的文件。证书文件的文件名后缀一般为 `.crt` 或 `.cer`

数字证书内容可能包括证书域（证书的版本、序列号、签名算法类型、签发者信息、有效期、被签发主体、**签发的公开密钥**）、CA 对证书的签名算法和签名值等。

## TLS握手

- 指定将要使用的 TLS 版本（TLS 1.0、1.2、1.3 等）
- 决定将要使用哪些密码套件
- 通过服务器的公钥和 SSL 证书颁发机构的数字签名来验证服务器的身份
- 生成会话密钥，以在握手完成后使用对称加密

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8a343b86-3c21-4ea2-a85c-1468f2d5b98d/b42f195f-e0cf-4daa-855c-24c8953c8505/image.png)
