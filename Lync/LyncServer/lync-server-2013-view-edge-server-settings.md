---
title: Lync Server 2013：查看边缘服务器设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e978e28ea2c9d64a842c40237f1e5943c30d0a41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看边缘服务器设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-20_

应对照配置管理数据库中的数据检查常规边缘服务器配置，以帮助确保根据定义的更改控制过程记录所有更改。

其他检查可能包含以下各节所述的内容：

<div>

## <a name="verify-the-allow-and-block-lists"></a>验证允许和阻止名单

验证联盟域的 SIP URI "Allow" 和 "Block" 列表，以确定列出的命名空间是否仍然有效。

您可以使用 Windows PowerShell 查看允许和阻止的列表。 若要查看 "允许的域" 列表中的域，请运行以下 Windows PowerShell 命令：

`Get-CsAllowedDomain`

该命令将针对 "允许的域" 列表中的域返回类似于以下内容的信息：

标识： contoso.com

域： contoso.com

ProxyFqdn

注释

MarkForMonitoring： False

注释

若要查看阻止的域列表中的域，请使用以下命令：

`Get-CsBlockedDomain`

反过来，你将收到有关每个被阻止的域的信息，例如：

标识： tailspintoys.com

域： tailspintoys.com

Windows PowerShell 还允许您验证是否可以连接到允许的域列表中的域。 例如，以下命令将验证您的边缘服务器（TargetFqdn）与联盟域 contoso.com 之间的连接：

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

此命令将验证您的边缘服务器与您在允许的域列表中找到的所有域之间的连接：

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>验证多个边缘服务器是否相同

如果在负载平衡阵列中部署多台边缘服务器，我们建议验证是否以相同方式配置了阵列中的所有边缘服务器。

您可以在 "计算机管理" 管理单元的 Lync Server 2013 扩展的详细信息窗格中查看边缘服务器的设置。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

