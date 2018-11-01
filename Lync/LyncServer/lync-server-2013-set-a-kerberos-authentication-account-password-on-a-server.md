---
title: Lync Server 2013：在服务器上设置 Kerberos 身份验证帐户密码
TOCTitle: 在服务器上设置 Kerberos 身份验证帐户密码
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398734(v=OCS.15)
ms:contentKeyID: 49313582
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中在服务器上设置 Kerberos 身份验证帐户密码

 

_**上一次修改主题：** 2012-01-16_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

必须为拥有前端服务器、Standard Edition Server 和控制器的每个站点设置 Kerberos 帐户密码。可通过在站点中的服务器（例如，一个 前端服务器）上运行 **Set-CsKerberosAccountPassword**Windows PowerShell cmdlet 来设置密码。对于每个站点都必须运行 **Set-CsKerberosAccountPassword** cmdlet。cmdlet 为 Web 服务 服务配置 Internet Information Services (IIS)，然后在 Active Directory 域服务 中为计算机帐户设置密码。使用已配置为 Kerberos 帐户密码源的其他服务器时，另一种基于与 cmdlet 一起使用的参数的方法会在服务器上配置 IIS。

使用 **Set-CsKerberosAccountPassword** cmdlet 设置密码时，Kerberos 会将密码设置为随机生成的字符串。此 cmdlet 会连接将该帐户分配到的所有 Lync Server 2013 中央站点中的所有 IIS 实例。

## 为 Kerberos 身份验证帐户设置密码

1.  以 RTCUniversalServerAdmins 组成员的身份登录安装了 Lync Server 命令行管理程序的任何域计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  通过命令行运行以下两个命令：
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    例如：
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    > [!NOTE]  
	> 必须使用 Domain\User 格式指定 UserAccount 参数。User@Domain.extension 格式不支持引用出于 Kerberos 身份验证目的创建的计算机对象。
    
    
    > [!IMPORTANT]
    > 对 Kerberos 身份验证进行更改（例如，添加帐户或删除帐户）之后，必须通过 Lync Server 命令行管理程序命令提示符运行 <strong>Enable-CsTopology</strong>。

