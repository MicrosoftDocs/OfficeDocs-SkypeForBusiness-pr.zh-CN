---
title: Lync Server 2013：保护 IIS
TOCTitle: 在 Lync Server 2013 中保护 IIS
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn518332(v=OCS.15)
ms:contentKeyID: 60505968
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中保护 IIS

 

_**上一次修改主题：** 2013-12-05_

在 Microsoft Office Communications Server 2007 和 Microsoft Office Communications Server 2007 R2 中，Internet Information Services (IIS) 使用标准用户帐户运行。这有可能会导致问题：如果该密码过期，您可能会丢失 Web 服务，此问题通常难于诊断。为了帮助避免出现密码过期的问题，您可以通过 Microsoft Lync Server 2013 创建一个计算机帐户（用于实际上不存在的计算机），该帐户可充当站点中正运行 IIS 的所有计算机的身份验证主体。由于这些帐户使用 Kerberos 身份验证协议，因此称为 Kerberos 帐户，并且新的身份验证过程称为 Kerberos Web 身份验证。这样，您可以使用单个帐户管理所有 IIS 服务器。

要使用此身份验证主体运行服务器，必须首先使用 New-CsKerberosAccount cmdlet 创建一个计算机帐户；然后，将该帐户分配给一个或多个站点。进行分配之后，通过运行 Enable-CsTopology cmdlet 启用该帐户与 Lync Server 2013 站点之间的关联。除其他结果之外，这样将在 Active Directory 域服务 (AD DS) 中创建所需的服务主体名称 (SPN)。SPN 为客户端应用程序提供了一种查找特定服务的方式。有关详细信息，请参阅操作文档中的 [New-CsKerberosAccount](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsKerberosAccount)。

## 最佳做法

为了帮助增强 IIS 的安全性，建议为 IIS 实现 Kerberos 帐户。如果不实现 Kerberos 帐户，IIS 将使用标准用户帐户运行。

