---
title: Lync Server 2013：执行和监视备份
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf3ba3dc27bf3849ad6c3434f4baf1fa28c07780
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>在 Lync Server 2013 中执行和监视备份

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-15_

您的业务优先级应推动组织的备份和还原要求的规范。 在规划灾难时，执行服务器和数据的备份是第一条防御措施。

运行 Lync Server 2013 服务或服务器角色的计算机必须具有当前拓扑的副本、当前配置设置和当前策略，然后它们才能在其可配置的角色中运行。 Lync Server 负责确保将此信息传递给需要它的每台计算机。

**CsConfiguration**和**CsConfiguration** Cmdlet 用于在中央管理存储升级期间备份和还原 Lync Server 拓扑、配置设置和策略。 **CsConfiguration** cmdlet 使您能够将数据导出到。ZIP 文件。 然后，您可以使用**CsConfiguration** cmdlet 读取该。ZIP 文件，并将拓扑、配置设置和策略还原到中央管理存储。 之后，Lync Server 的复制服务会将还原的信息复制到其他运行 Lync Server 服务的计算机。

在位于外围网络（例如，边缘服务器）中的计算机的初始配置过程中，还将使用导出和导入配置数据的功能。 在外围网络中配置计算机时，必须首先使用 CsConfiguration cmdlet 执行手动复制：必须使用**export-CsConfiguration**导出配置数据，然后复制。ZIP 文件到外围网络中的计算机。 此后，您就可以使用 **Import-CsConfiguration** 和 LocalStore 参数导入该数据。 您只需执行一次此操作。 之后，将自动执行复制。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Export-CsConfiguration** cmdlet：RTCUniversalServerAdmins。 若要返回所有 RBAC 角色的列表，请将此 cmdlet 分配给（包括您自己创建的任何自定义 RBAC 角色），从 Windows PowerShell 提示符处运行以下命令：

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

应按照[sql 最佳实践](https://go.microsoft.com/fwlink/p/?linkid=290716)来备份所有 SQL 2012 后端数据库。

应在尽可能模拟生产环境的实验室环境中执行对 Lync Server 2013 基础结构的灾难恢复计划的定期测试。 有关灾难恢复测试的详细信息，请参阅每月任务。

请注意，可以根据还原点和恢复点目标调整备份频率。 作为最佳实践，请在全天中定期拍摄定期快照。 通常情况下，每隔24小时执行一次完整备份。

<div>

## <a name="see-also"></a>另请参阅


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL 最佳实践](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

