---
title: 配置 AD FS 2.0 以支持客户端身份验证
TOCTitle: 配置 AD FS 2.0 以支持客户端身份验证
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn308565(v=OCS.15)
ms:contentKeyID: 56271144
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 AD FS 2.0 以支持客户端身份验证

 

_**上一次修改主题：** 2016-12-08_

有两种可能的身份验证类型可配置为允许 AD FS 2.0 支持使用智能卡进行身份验证：

  - 基于表单的身份验证 (FBA)

  - 传输层安全性客户端身份验证

使用基于表单的身份验证，您可以部署一个网页以允许用户使用其用户名/密码或使用其智能卡和 PIN 进行身份验证。本主题着重介绍如何实施传输层安全性客户端身份验证与 AD FS 2.0。有关 AD FS 2.0 身份验证类型的详细信息，请参阅“AD FS 2.0：如何更改本地身份验证类型”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)。


**配置 AD FS 2.0 以支持客户端身份验证**

1.  使用域管理员帐户登录到 AD FS 2.0 计算机。

2.  启动 Windows 资源管理器。

3.  浏览到 C:\\inetpub\\adfs\\ls

4.  创建现有 web.config 文件的备份副本。

5.  使用记事本打开现有 web.config 文件。

6.  从菜单栏中，选择“编辑”，然后选择“查找”。

7.  搜索 **\<localAuthenticationTypes\>**。
    
    请注意，列出了四种身份验证类型，每行一个。

8.  将包含 TLSClient 身份验证类型的行移动到列表顶部。

9.  保存并关闭 web.config 文件。

10. 使用提升的特权启动命令提示符。

11. 通过运行以下命令来重新启动 IIS：
    
        IISReset /Restart /NoForce

