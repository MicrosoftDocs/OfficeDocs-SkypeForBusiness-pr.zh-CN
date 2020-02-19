---
title: 在共存方案中使用 Lync Server 2010 管理包
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc198abe47d76abae2ae49f426ac433c29129790
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>在共存方案中使用 Lync Server 2010 管理包

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

许多客户在其企业内采用了推出计划，在该计划中，用户从 Microsoft Lync Server 2010 逐渐迁移到 Lync Server 2013。 这些公司的管理员将负责监视两个版本的 Lync Server，以帮助确保所有最终用户都能获得最佳的通信体验。 在这种情况下，Lync Server 2013 管理包支持与 Lync Server 2010 管理包的并行迁移路径。

在 Lync Server 2010 中，通过与中央管理存储一起存储的拓扑文档发现了 Lync Server 计算机。 在此配置中，一台计算机将报告所有其他 Lync Server 计算机是否存在。

Lync Server 2013 的管理包现在使用计算机级发现，而不是在 Lync Server 2010 中使用的中央发现机制。 这意味着每个 System Center 代理实质上都会发现自己，并报告它是否存在于 System Center Operations Manager 中。 使用计算机级别发现可简化对 System Center 基础结构的管理，还会启用不同版本的 Lync Server 管理包（例如，lync server 2010 的管理包和 Lync Server 2013 的管理包）能够更轻松地共存。

若要支持此迁移，首先需要升级现有的 Lync Server 2010 监控，以避免覆盖范围的差距。 为此，请在将中央管理存储升级到 Lync Server 2013 之前，选择现有的 Lync Server 2010 计算机为 Lync Server 2010 服务的中央发现脚本。 这是四个步骤的过程：

1.  将 Lync Server 2010 管理包升级到累积更新7。

2.  指示 Lync Server 2010 计算机运行中央发现脚本。

3.  替代 Microsoft Lync Server 2010 管理包中的中央发现候选项。

4.  验证是否已发现新的中央发现候选项。

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>指示 Lync Server 2010 计算机运行中央发现脚本

若要提名非中央管理存储计算机（例如，Lync Server 前端）服务器来处理中央发现，您需要在非中心管理存储服务器上创建以下注册表项：

HKLM\\软件\\Microsoft\\实时通信\\运行状况\\CentralDiscoveryCandidate

您可以通过完成以下过程来创建此注册表项：

1.  单击“开始”****，再单击“运行”****。

2.  在“运行”**** 对话框中，键入“regedit”****，然后按 Enter 键。

3.  在注册表编辑器中，**展开\_"\_HKEY 本地计算机**"，展开 "**软件**"，再展开 " **Microsoft**"，然后展开 "**实时通信**"。

4.  右键单击 "**运行状况**"，单击 "**新建**"，然后单击 "**项**"。 如果**运行状况**项不存在，则右键单击 "**实时通信**"，指向 "**新建**"，然后单击 "**项**"。 创建新密钥时，键入 Health，然后按 ENTER。
    
    创建新密钥后，键入**CentralDiscoveryCandidate** ，然后按 enter 重命名该项。

可能需要几个小时才能获取此更改。 若要使更改立即生效，请停止运行状况代理服务，然后再重新启动它。 若要重新启动运行状况代理服务，请在 Lync Server 2010 计算机上完成以下过程：

1.  单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。

2.  在控制台窗口中键入以下命令，然后按 Enter：
    
        Net stop HealthService

3.  您将看到一条消息，指出 "System Center Management service 正在停止"，后跟第二条消息，告诉您服务已停止。 停止服务后，您可以通过键入以下命令并按 ENTER 来重新启动它：
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>替代 Lync Server 2010 管理包中的中央发现候选项

指示 Lync Server 2010 计算机在 Lync Server 2010 计算机上报告之后，您还需要通知 Lync Server 2010 管理包有关此更改。 若要执行此操作，您将需要在管理包中创建替代。 这可通过执行下列过程来完成：

1.  在 Operations Manager 控制台中，单击 "**创作**"。

2.  在 "创作" 选项卡上，展开 "**管理包对象**"，单击 "**对象发现**"，然后单击 "**范围**"。

3.  在 "**作用域管理包对象**" 对话框中，选择带有目标**LS "发现候选**项" 的项目，然后单击 **"确定"**。 请注意，只有在安装了 Lync Server 2010 管理包的情况下，才会显示 "发现候选项"。

4.  在 Operations Manager 控制台中，右键单击 " **LS 发现候选人**"，指向 "**替代**"，指向 "**替代对象发现**"，然后单击 "**类的所有对象"： LS "发现候选**"。

5.  在 "**替代属性**" 对话框中，选中参数**中心发现 watchernode.msi Fqdn**旁边的 "**替代**" 复选框。 在 "**替代值**和**有效值**" 框中键入 Lync Server 2010 计算机的完全限定域名。 选中 "**强制**" 复选框，然后单击 **"确定"**。

创建替代后，需要在根管理服务器上重新启动运行状况服务。 若要重新启动运行状况服务，请在根管理服务器上完成以下过程：

1.  单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。

2.  在控制台窗口中，键入以下命令，然后按 ENTER：
    
        Net stop HealthService

3.  你将看到一条消息，表明 "System Center Management service 正在停止"，然后再出现第二条消息，告诉你服务已停止。 停止服务后，您可以通过键入以下命令并按 ENTER 来重新启动它：
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>验证是否已发现新的中央发现候选项

升级中央管理存储之前的最后一步是确保 Lync Server 2010 管理包发现了新的中央发现候选项。 为此，请打开 Operations Manager 控制台，然后单击 "监视"。 在 "监视" 选项卡上，展开 " **Microsoft Lync Server 2010 运行状况**"，展开 "**拓扑发现**"，然后单击 "**发现状态视图**"。 验证显示的行是否有列出了中央发现候选项的完全限定域名的**路径**。 您还应验证计算机状态是否报告为**正常**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

