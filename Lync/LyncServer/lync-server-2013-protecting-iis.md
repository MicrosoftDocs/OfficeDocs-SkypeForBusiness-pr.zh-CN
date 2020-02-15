---
title: Lync Server 2013：保护 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612945a8ad69cffa8401cb64367d8b860d556a19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>在 Lync Server 2013 中保护 IIS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-12-05_

在 Microsoft Office 通信服务器2007和 Microsoft Office 通信服务器 2007 R2 中，Internet 信息服务（IIS）在标准用户帐户下运行。 这有可能会导致问题：如果该密码过期，您可能会丢失 Web 服务，此问题通常难于诊断。 为了帮助避免出现密码过期问题，Microsoft Lync Server 2013 使您能够创建一个计算机帐户（对于实际不存在的计算机），该帐户可用作运行 IIS 的站点中所有计算机的身份验证主体。 由于这些帐户使用 Kerberos 身份验证协议，因此称为 Kerberos 帐户，并且新的身份验证过程称为 Kerberos Web 身份验证。 这样，您可以使用单个帐户管理所有 IIS 服务器。

要使用此身份验证主体运行服务器，必须首先使用 New-CsKerberosAccount cmdlet 创建一个计算机帐户；然后，将该帐户分配给一个或多个站点。 完成分配后，通过运行 Enable-cstopology cmdlet 可以启用帐户与 Lync Server 2013 网站之间的关联。 除其他结果之外，这样将在 Active Directory 域服务 (AD DS) 中创建所需的服务主体名称 (SPN)。 SPN 为客户端应用程序提供了一种查找特定服务的方式。 有关详细信息，请参阅操作文档中的 [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount)。

<div>

## <a name="best-practices"></a>最佳做法

为了帮助增强 IIS 的安全性，建议为 IIS 实现 Kerberos 帐户。如果不实现 Kerberos 帐户，IIS 将使用标准用户帐户运行。

</div>

</div>

<span> </span>

</div>

</div>

</div>

