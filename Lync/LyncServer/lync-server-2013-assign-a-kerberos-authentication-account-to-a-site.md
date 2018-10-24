---
title: Lync Server 2013：将 Kerberos 身份验证帐户分配给站点
TOCTitle: 将 Kerberos 身份验证帐户分配给站点
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425901(v=OCS.15)
ms:contentKeyID: 49312592
ms.date: 04/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将 Kerberos 身份验证帐户分配给站点

 

_**上一次修改主题：** 2017-04-18_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

创建 Kerberos 帐户后，必须将其分配给站点。此处指的是 Lync Server 2013 站点，而非 Active Directory 站点。每个部署可以创建多个 Kerberos 身份验证帐户，但只能将一个帐户分配给站点。使用以下过程将之前创建的 Kerberos 身份验证帐户分配给站点。有关创建 Kerberos 帐户的详细信息，请参阅 [在 Lync Server 2013 中创建 Kerberos 身份验证帐户](lync-server-2013-create-a-kerberos-authentication-account.md)。

## 将 Kerberos 身份验证帐户分配给站点

1.  以 RtcUniversalServerAdmins 组成员的身份，登录到域中运行 Lync Server 2013 的计算机，或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  通过命令行运行以下两个命令：
    
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount" -Identity "site:SiteName"
        
       &nbsp;
    
        Enable-CsTopology
    
    例如：
    
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth" -Identity "site:redmond"

       &nbsp;
    
        Enable-CsTopology
    
    > [!NOTE]  
    > 必须使用 Domain\User 格式指定 UserAccount 参数。User@Domain.extension 格式不支持引用出于 Kerberos 身份验证目的创建的计算机对象。
    
    
    > [!IMPORTANT]  
    > 对 Kerberos 身份验证进行更改（例如，添加帐户或删除帐户）之后，必须通过 Lync Server 命令行管理程序命令提示符运行 <strong>Enable-CsTopology</strong>。

