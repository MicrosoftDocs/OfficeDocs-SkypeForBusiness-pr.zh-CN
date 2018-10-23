---
title: Lync Server 2013：设置 Kerberos 身份验证帐户密码
TOCTitle: 设置 Kerberos 身份验证帐户密码
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412870(v=OCS.15)
ms:contentKeyID: 49313979
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中设置 Kerberos 身份验证帐户密码

 

_**上一次修改主题：** 2010-11-03_

为 Kerberos 身份验证帐户创建计算机对象后，即可设置该帐户的密码。在一台服务器上运行 Windows PowerShell cmdlet 可设置 Kerberos 帐户密码。可以在为 Kerberos 身份验证所创建的对象上设置密码。可将密码设置为已知值，但默认情况下为随机密码。该密码可用于所有使用该帐户的 Kerberos 身份验证源。使用 Windows PowerShell cmdlet 可设置和管理 Kerberos 帐户密码。

> [!NOTE]  
> Kerberos 帐户对象是计算机对象，但使用 UserAccount 参数通过引用的 Windows PowerShell cmdlet 进行操作。请注意，这并非错误，而是 cmdlet 在与 Kerberos 帐户创建和维护结合使用时的预期行为。



## 本部分内容

  - [在 Lync Server 2013 中在服务器上设置 Kerberos 身份验证帐户密码](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

