---
title: Lync Server 2013：创建 Kerberos 身份验证帐户
TOCTitle: 创建 Kerberos 身份验证帐户
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398449(v=OCS.15)
ms:contentKeyID: 49313063
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建 Kerberos 身份验证帐户

 

_**上一次修改主题：** 2012-01-02_

要成功完成此过程，至少应以 Domain Admins 组成员身份登录到服务器或域。

可以为每个站点创建多个 Kerberos 身份验证帐户，或者创建一个 Kerberos 身份验证帐户，然后将其用于所有站点。使用 Windows PowerShell cmdlets 创建并管理帐户，包括确认分配给每个站点的帐户。 拓扑生成器和 Lync Server 2013 控制面板不显示 Kerberos 身份验证帐户。使用以下过程创建一个或多个要用于 Kerberos 身份验证的用户帐户。

## 创建 Kerberos 帐户

1.  以 Domain Admins 组成员的身份登录到运行 Lync Server 2013 的域中的计算机，或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中运行以下命令：
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    例如：
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  通过打开“Active Directory 用户和计算机”确认是否已创建计算机对象，展开“用户”容器，然后确认容器中存在此用户帐户的计算机对象。

