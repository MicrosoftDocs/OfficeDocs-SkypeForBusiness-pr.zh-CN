---
title: 在共存方案中使用 Lync Server 2010 管理包
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>在共存方案中使用 Lync Server 2010 管理包

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

许多客户在其企业内采用推出计划, 用户从 Microsoft Lync Server 2010 逐渐迁移到 Lync Server 2013。 这些公司的管理员将注意监视这两个版本的 Lync Server, 以帮助确保其所有最终用户获得最佳通信体验。 对于此方案, Lync Server 2013 管理包支持使用 Lync Server 2010 管理包的并行迁移路径。

在 Lync Server 2010 中, 通过中央管理存储中存储的拓扑文档发现了 Lync Server 计算机。 在此配置中, 单个计算机将报告所有其他 Lync 服务器计算机的存在。

Lync Server 2013 的管理包现在使用计算机级发现, 而不是在 Lync Server 2010 中使用的集中发现机制。 这意味着每个 System Center 代理实质上都会发现自己并向 System Center Operations Manager 报告它的存在。 使用计算机级发现可简化 System Center 基础结构的管理, 还支持不同版本的 Lync Server 管理包 (例如 lync server 2010 的管理包和 Lync Server 2013 的管理包)更加轻松地共存。

若要支持此迁移, 首先需要升级现有 Lync Server 2010 监视, 以避免覆盖范围中的差距。 若要执行此操作, 请在将中央管理存储升级到 Lync Server 2013 之前, 选择现有 Lync Server 2010 计算机为 Lync Server 2010 服务 "中央发现脚本"。 这是一个包含四个步骤的过程:

1.  将 Lync Server 2010 管理包升级到累积更新7。

2.  指示 Lync Server 2010 计算机运行中央发现脚本。

3.  替代 Microsoft Lync Server 2010 管理包中的中央发现候选人。

4.  验证是否已发现新的中心发现候选项。

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>指示 Lync Server 2010 计算机运行中央发现脚本

若要提名非中央管理存储计算机 (例如, Lync Server 前端) 服务器处理中央发现, 需要在非中心管理存储服务器上创建以下注册表项:

HKLM\\软件\\Microsoft\\实时通信\\运行状况\\CentralDiscoveryCandidate

你可以通过完成以下过程来创建此注册表项:

1.  单击 "**开始**", 然后单击 "**运行**"。

2.  在 "**运行**" 对话框中, 键入**regedit** , 然后按 enter。

3.  在注册表编辑器中,**展开\_"\_HKEY 本地计算机**", 展开 "**软件**", 展开 " **Microsoft**", 然后展开 "**实时通信**"。

4.  右键单击 "**运行状况**", 单击 "**新建**", 然后单击 "**项**"。 如果**运行状况**键不存在, 则右键单击 "**实时通信**", 指向 "**新建**", 然后单击 "**项**"。 创建新密钥时, 键入 "运行状况", 然后按 ENTER。
    
    创建新密钥后, 键入**CentralDiscoveryCandidate** , 然后按 enter 重命名该键。

该计算机可能需要几个小时才能获取此更改。 若要使更改立即生效, 请停止运行状况代理服务, 然后重新启动它。 若要重新启动运行状况代理服务, 请在 Lync Server 2010 计算机上完成以下过程:

1.  单击 "**开始**", 单击 "**所有程序**", 单击 "**附件**", 右键单击 "**命令提示符**", 然后单击 "以**管理员身份运行**"。

2.  在控制台窗口中, 键入以下命令, 然后按 ENTER:
    
        Net stop HealthService

3.  你将看到一条消息, 指出 "System Center Management service 正在停止", 然后再次出现一条消息, 告知你服务已停止。 服务停止后, 您可以通过键入以下命令并按 ENTER 来重新启动它:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>覆盖 Lync Server 2010 管理包中的中央发现候选人

指示 Lync Server 2010 计算机在 Lync Server 2010 计算机上进行报告后, 您还需要通知 Lync Server 2010 管理包此更改。 若要执行此操作, 你需要在管理包中创建替代。 可通过完成以下过程来执行此操作:

1.  在 Operations Manager 控制台中, 单击 "**创作**"。

2.  在 "创作" 选项卡上, 展开 "**管理包对象**", 单击 "**对象发现**", 然后单击 "**范围**"。

3.  在 "**作用域管理包对象**" 对话框中, 选择带有目标**LS "发现候选**项" 的项目, 然后单击 **"确定"**。 请注意, 只有在安装了 Lync Server 2010 管理包后, 才会显示 LS "发现候选项"。

4.  在 Operations Manager 控制台中, 右键单击**LS "发现候选**项", 指向 "**替代**", 指向 "**替代对象发现**", 然后单击 "**用于类的所有对象: LS 发现候选项**"。

5.  在 "**替代属性**" 对话框中, 选中参数 "**中央发现 WatcherNode Fqdn**" 旁边的 "**覆盖**" 复选框。 在 "**替代值**" 和 "**有效值**" 框中键入 Lync Server 2010 计算机的完全限定的域名。 选中 "**强制执行**" 复选框, 然后单击 **"确定"**。

创建替代后, 需要重启根管理服务器上的运行状况服务。 若要重新启动运行状况服务, 请在根管理服务器上完成以下过程:

1.  单击 "**开始**", 单击 "**所有程序**", 单击 "**附件**", 右键单击 "**命令提示符**", 然后单击 "以**管理员身份运行**"。

2.  在控制台窗口中, 键入以下命令, 然后按 ENTER:
    
        Net stop HealthService

3.  你将看到一条消息, 指出 "System Center Management service 即将停止", 然后是另一条消息, 告诉你服务已停止。 服务停止后, 您可以通过键入以下命令并按 ENTER 来重新启动它:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>验证是否发现新的中央发现候选项

升级中央管理存储之前的最后一步是确保 Lync Server 2010 管理包发现新的中心发现候选项。 若要执行此操作, 请打开 Operations Manager 控制台, 然后单击 "监视"。 在 "监视" 选项卡上, 展开 " **Microsoft Lync Server 2010 运行状况**", 展开 "**拓扑发现**", 然后单击 "**发现状态视图**"。 验证显示中的行是否具有列出中央发现候选项的完全限定的域名的**路径**。 你还应验证计算机状态是否报告为 "**正常**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

