---
title: 使用最佳做法分析程序扫描部署以发现潜在问题
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>使用最佳做法分析程序扫描 Lync Server 2013 部署以发现潜在问题

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-21_

若要运行最佳做法分析器扫描, 必须指定以下内容:

  - **凭据**   若要运行扫描, 您必须使用作为本地管理员组成员的帐户登录到安装了最佳做法分析器的计算机。 此外, 你需要使用具有运行相应扫描所需的用户权限和权限的用户帐户进行登录, 或者你必须指定在运行最佳做法分析器时具有相应的用户权限和权限的凭据。 有关详细信息, 请参阅[Lync Server 2013 中的最佳做法分析器的组成员身份和用户权限要求](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)。

  - **扫描范围若**   要指定扫描的范围, 请选择要扫描的类别和服务器。 你可以选择 Lync Server 环境中特定类别内的所有类别、一个或多个类别, 或者一个或多个服务器。

  - **扫描类型目前**   , 运行状况检查扫描是唯一可用的扫描类型 (默认情况下处于选中状态)。 运行状况检查扫描将生成一个报表, 其中包含作用域中指定的所有服务器的错误、警告和其他信息。

  - **网络速度**   的网络速度选项包括快速 lan (100 mbps 或更高)、LAN (10 mbps)、快速 WAN (1.5 Mbps) 或 WAN (64 kbps)。 完成扫描的估计时间基于此设置。 此设置还用于设置超时时间。 在扫描期间, 最佳做法分析器会等待服务器的响应指定时间。 如果在指定的超时期限内未收到响应, 则它将移动到扫描中的下一个服务器。 在较慢的网络上, 此指定的超时周期会延长较长的网络延迟时间。 我们建议你选择此参数的拓扑中最慢的链接, 以便该工具的时间不会太快。

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>扫描 Lync Server 2013 部署

1.  使用本地管理员组成员的帐户登录到安装了最佳做法分析器的计算机, 并具有其他所需的用户权限和权限。

2.  单击 "**开始**", 指向 "**所有程序**", 单击 " **Microsoft Lync Server 2013**", 然后单击 "**最佳做法分析器**"。

3.  在 "**欢迎**" 屏幕上, 单击 "**选择新扫描的选项**"。

4.  在 "**连接到 Active directory** " 页面上, 验证**active directory Server**中指定的名称, 然后执行下列操作之一:
    
      - 若要使用用于登录计算机的凭据运行扫描, 请单击 "**连接到 Active Directory 服务器**"。
    
      - 若要指定要用于 Active Directory 域服务、边缘服务器或 Exchange Server 的其他凭据, 请单击 "**显示高级登录选项**", 选中需要单独凭据的每个复选框, 指定凭据对于每个选中的复选框, 然后单击 "**连接到 Active Directory 服务器"**。
    
    <div>
    

    > [!NOTE]
    > 在开始扫描之前, 最佳做法分析器会执行网络和权限检查, 以确保指定的帐户凭据有效, 并且最佳做法分析器可以连接到 Active Directory 域服务。 如果该工具在工作组服务器上运行, 则该工具还会验证它是否可以连接到外围网络中的边缘服务器 (即它们是否包含在扫描中)。

    
    </div>

5.  在 "**启动新的最佳做法扫描**" 页面上, 选择要包括在扫描中的选项, 指定网络速度, 然后单击 "**开始扫描**"。

6.  在 "**扫描已完成**" 页面上, 单击 "**查看此最佳做法扫描的报告**"。

7.  在 "**查看最佳做法报告**" 页面上, 执行下列操作之一:
    
      - 若要查看按服务器组件组织的列表中的报告, 请单击 "**列表报告**", 然后单击 "**所有问题**" 选项卡或 "**信息性项目**" 选项卡。
    
      - 若要将报表作为按结果类型组织的分层列表进行查看, 请单击 "**树报表**", 然后单击 "**详细视图**" 选项卡或 "**摘要视图**" 选项卡。
    
      - 若要查看其他报表, 请单击 "**其他报表**"。
    
    <div>
    

    > [!NOTE]
    > 有关最佳做法分析器报告以及它们识别的问题的详细信息, 请参阅<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">在 Lync Server 2013 中查看和使用由最佳做法分析器创建的报表</A>, 并<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">分析和解决最佳做法分析器标识的问题在 Lync Server 2013 中</A>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

