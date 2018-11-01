---
title: Lync Server 2013：将 Kerberos 身份验证帐户密码同步到 IIS
TOCTitle: 将 Kerberos 身份验证帐户密码同步到 IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398107(v=OCS.15)
ms:contentKeyID: 49311871
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS

 

_**上一次修改主题：** 2010-11-08_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

在站点中，前端服务器、Standard Edition Server 和控制器可使用 Kerberos 身份验证帐户来验证对 Web 服务服务的请求。此过程在分配有 Kerberos 帐户的站点中查找运行 Web 服务的每台服务器，并更新 Internet Information Services (IIS) 配置设置以使用 Kerberos 帐户。有关详细信息，请参阅 [在 Lync Server 2013 中在服务器上设置 Kerberos 身份验证帐户密码](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)。

## 设置和配置 Kerberos 身份验证帐户密码

1.  以 RTCUniversalServerAdmins 组成员的身份登录到源计算机（例如 fe01.contoso.com）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  通过 Lync Server 命令行管理程序命令行运行以下两个命令：
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    例如：
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    > [!IMPORTANT]
    > 源计算机和目标计算机的名称必须是服务器的完全限定域名 (FQDN)。除非池名称与要用作源计算机或目标计算机的计算机名称相同，否则不能使用池 FQDN。
    
    > [!IMPORTANT]
    > 对 Kerberos 身份验证进行更改（例如，添加帐户或删除帐户）之后，必须通过 Lync Server 命令行管理程序命令提示符运行 <strong>Enable-CsTopology</strong>。

