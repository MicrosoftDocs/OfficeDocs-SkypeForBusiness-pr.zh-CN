---
title: 'Lync Server 2013: 执行和监视备份'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fffc6a8355305e11d87513ffc37626f3e386c749
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>在 Lync Server 2013 中执行和监视备份

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-05-15_

你的业务优先级应推动你的组织的备份和还原要求的规范。 对服务器和数据执行备份是规划灾难的第一防线。

运行 Lync Server 2013 服务或服务器角色的计算机必须具有当前拓扑、当前配置设置和当前策略的副本, 然后它们才能在其已设定的角色中起作用。 Lync 服务器负责确保将此信息传递给需要它的每台计算机。

**Export-CsConfiguration**和**Import CsConfiguration** Cmdlet 用于在中央管理存储升级期间备份和还原 Lync Server 拓扑、配置设置和策略。 **导出-CsConfiguration** cmdlet 使你能够将数据导出到。ZIP 文件。 然后, 你可以使用**CsConfiguration** cmdlet 进行读取。ZIP 文件, 并将拓扑、配置设置和策略还原到中央管理存储。 此后, Lync Server 的复制服务会将还原的信息复制到其他运行 Lync Server 服务的计算机。

在外围网络 (如 Edge 服务器) 中的计算机的初始配置期间还会使用导出和导入配置数据的功能。 在外围网络中配置计算机时, 必须首先使用 CsConfiguration cmdlet 执行手动复制: 必须通过使用**export-CsConfiguration**导出配置数据, 然后复制。将文件压缩到外围网络中的计算机。 之后, 你可以使用**import-CsConfiguration**和 LocalStore 参数导入数据。 您只需执行一次此操作。 之后, 将自动执行复制。

哪些人可以运行此 cmdlet: 默认情况下, 已授权以下组的成员运行本地**CsConfiguration** Cmdlet: RTCUniversalServerAdmins。 若要返回所有 RBAC 角色的列表, 请将此 cmdlet 分配给 (包括你自己创建的任何自定义 RBAC 角色), 从 Windows PowerShell 提示中运行以下命令:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

所有 SQL 2012 后端数据库应按[SQL 最佳做法](http://go.microsoft.com/fwlink/p/?linkid=290716)进行备份。

对于您的 Lync Server 2013 基础结构, 定期测试灾难恢复计划应在尽可能模拟生产环境的实验室环境中执行。 有关灾难恢复测试的详细信息, 请参阅每月任务。

请注意, 可以根据你的还原点和恢复点目标调整备份频率。 最佳做法是在一天内定期执行定期快照。 通常情况下, 每隔24小时执行完整备份。

<div>

## <a name="see-also"></a>另请参阅


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL 最佳做法](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

