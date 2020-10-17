---
title: Skype for Business Online 报告 cmdlet 和 REST web 服务
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92f2be5987ad6ffc76d19e7ccad81da4115487a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514949"
---
# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Skype for Business Online 报告 cmdlet 和 REST web 服务

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-09-05_

通过与报告功能结合使用，Skype for Business Online 提供了对五个 Windows PowerShell cmdlet 的访问权限，可帮助生成这些报告，并且管理员也可以使用它们返回自定义报告数据。 Skype for Business Online 还包括 REST (代表性状态转移) ，可供开发人员用来检索自定义报告信息。

可供管理员使用的报告 cmdlet 包括：

  - Get-csactiveuserreport，它提供有关 (的活动用户数的信息，即登录到 Skype for Business Online 并参与至少一个会议或对等通信会话) 的用户。

  - Get-csavconferencetimereport，它提供有关) 用户在音频/视频会议中花费的 (时间量的信息（以分钟为单位）。

  - Get-csconferencereport，它提供有关用户参与的会议的数量和类型的信息。

  - Get-csp2pavtimereport，它提供有关) 用户在包含音频和/或视频的对等会话中花费的 (时间量（以分钟为单位）的信息。

  - Get-csp2psessionreport，它提供有关用户参与的对等会话的数量和类型的信息。

大多数管理员将使用 Microsoft 365 管理中心提供的报告：这些报告不仅是自动生成的，而且还提供了数据的图形表示形式，这些数据通常比报告 cmdlet 返回的原始号码值更容易理解。 但是，熟悉 Windows PowerShell 的管理员可以使用报告 cmdlet 从 Lync Online 报告中返回不容易提供的数据。 例如，报告 cmdlet 将返回有关会话持续时间的信息， (每个会话持续) 的时间量（以分钟为单位）。 使用 Lync Online 报告无法获取单个会话持续时间。 同样，在每日视图中，Lync Online 报告仅显示前14天的信息。 如果您想要查看不同天的每日汇总 (例如，从四个月前开始的日期) 您可以使用报告 cmdlet 执行此操作。

管理员可能还会对 [使用 Excel 检索 Office 365 报告数据](https://msdn.microsoft.com/library/dn781442.aspx)的文章感兴趣，这说明了如何使用 Microsoft Excel 中的 OData 数据查询功能创建自定义 Office 365 报告。 自定义报告使您能够规定哪些数据 (，以及从 Office 365 报告服务返回多少数据) 。 自定义报告还允许您执行以下操作：指定数据的排序和分组方式，并提供对不在管理中心中显示的信息的访问权限。

具有开发背景的管理员可以使用 REST web 服务来获取未在 Skype for Business Online 管理中心中显示的信息。 REST 服务类似于 SOAP 服务，在这种服务中，每种技术都提供了一种在客户端和服务器之间传输 XML 数据的方法。 但是，REST 服务至少具有与 SOAP 服务相比的两个优势。 对于一个，REST 使用称为 ATOM 联合联合格式的标准化格式执行 XML 数据传输。 相比之下，在传输数据时，使用非标准格式的 SOAP。 此外，REST 可以跨阻止 GET 和 POST 之外的 HTTP 谓词的网络传输数据。

<div>

## <a name="see-also"></a>另请参阅


[Lync Online 报告](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Office 365 报告 Web 服务](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[了解 Office 365 报告 Web 服务](https://msdn.microsoft.com/library/office/jj984321.aspx)  
[Exchange Online 报告 Cmdlet](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[使用 Excel 检索 Office 365 报告数据](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

