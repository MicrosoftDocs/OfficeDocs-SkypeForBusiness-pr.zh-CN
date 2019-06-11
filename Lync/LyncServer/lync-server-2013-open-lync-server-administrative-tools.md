---
title: 'Lync Server 2013: 打开 Lync Server 管理工具'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa84c132061cb599448b78cf7d4ffcc6bd7fa3d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>打开 Lync Server 2013 管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-28_

你可以使用本主题中的过程打开管理工具, 以部署、配置 Lync Server 2013 拓扑或对其进行故障排除。

  - 部署向导

  - 拓扑生成器

  - Lync Server 控制面板

  - Lync Server 命令行管理程序

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>部署向导

使用以下过程在本地启动部署向导以添加或删除 Lync Server 2013 组件文件。

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>启动 Lync Server 2013 部署向导

1.  登录到安装了 Lync Server 部署向导的计算机, 作为 "域管理员" 组和 "RTCUniversalServerAdmins" 组的成员。

2.  单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 部署向导**"。

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>拓扑生成器

使用以下过程打开拓扑生成器以定义要在 Lync Server 2013 拓扑中部署的服务器。

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>打开 Lync Server 2013 拓扑生成器以设计拓扑

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
    <div>
    

    > [!NOTE]  
    > 你可以通过使用属于本地用户组的成员的帐户定义拓扑, 但要读取、发布或启用拓扑 (需要在服务器上安装 Lync Server 2013), 必须使用域管理员组和 RTCUniv 的成员帐户。ersalServerAdmins 组, 并且具有对要用于存档文件存储的文件共享的完全控制权限 (即读取、写入和修改), 以便拓扑生成器可以配置所需的随机访问控制列表 (Dacl),或具有同等用户权限的帐户。

    
    </div>

2.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013 控制面板

使用以下过程之一打开 Lync Server 2013 控制面板以管理你环境中的服务器、用户、客户端和设备的配置。

<div>


> [!NOTE]  
> 你可以使用分配给 CsAdministrator 角色的用户帐户在 Lync Server 2013 "控制面板" 中执行任何任务。 你可以使用其他角色登录 Lync Server 2013 控制面板以执行特定的管理任务, 具体取决于你需要执行的任务。 例如, 你可以使用 CSArchivingAdministrator 在 Lync Server 2013 控制面板中管理存档。 有关角色的详细信息, 请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。 有关可用于执行特定任务的角色的详细信息, 请参阅该任务的文档。



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>从组织防火墙内的任何计算机打开 Lync Server 2013 控制面板

1.  从分配给 CsAdministrator 角色的用户帐户或具有要执行的任务的相应权限的其他角色, 使用 1024 x 768 的最低屏幕分辨率登录到内部部署中的任何计算机。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果已配置了管理简单的统一资源定位器 (URL), 则可以从组织防火墙内任何计算机上运行的 Internet 浏览器访问 Lync Server 2013 控制面板。 有关配置管理简单 URL 的详细信息, 请参阅规划文档中的 "<A href="lync-server-2013-planning-for-simple-urls.md">在 Lync server 2013 中规划简单 url</A> " 和 "在部署文档中在<A href="lync-server-2013-edit-or-configure-simple-urls.md">lync Server 2013 中编辑或配置简单 url</A> "。

    
    </div>

2.  打开一个浏览器窗口, 然后输入为你的组织配置的管理员 URL。

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>在运行 Lync Server 2013 的计算机上打开 Lync Server 2013 控制面板

1.  从属于 CsAdministrator 角色的用户帐户或其他具有要执行任务的相应权限的角色的用户帐户, 登录到已安装 Lync Server 2013 的计算机, 或者至少是 Lync Server 2013 administrat我的工具。 要配置设置, 计算机必须具有最小的屏幕分辨率 1024 x 768。

2.  启动 Lync Server 2013 控制面板: 单击 "**开始**", 单击 "**所有程序**", 指向 "**管理工具**", 指向 " **Microsoft Lync Server 2013**", 然后单击 " **Lync server 2013 控制面板**"。

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 命令行管理程序

使用以下过程打开 Lync Server 2013 管理外壳程序, 以使用命令行管理你环境中的服务器、用户、客户端和设备。

<div>


> [!NOTE]  
> 你可以使用分配给 CsAdministrator 角色的用户帐户在 Lync Server 2013 命令行管理程序中执行任何任务。 你可以使用其他角色登录, 以执行特定的管理任务, 具体取决于你需要执行的任务。 例如, 你可以使用 CSArchivingAdministrator 来运行与存档管理相关的 cmdlet。 有关角色的详细信息, 请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。 有关可用于运行特定 cmdlet 的角色的详细信息, 请参阅 cmdlet 的文档。<BR>你还可以使用 RTCUniversalServerAdmins、RTCUniversalUserAdmins 或 RTCUniversalReadOnlyAdmins 组中的用户帐户 (具体取决于 cmdlet) 运行某些 cmdlet。



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>打开 Lync Server 2013 命令行管理程序

  - 如果打开的是 Windows PowerShell 窗口, 而不是 Lync Server 2013 管理程序外壳, 则默认情况下无法运行 Lync Server 2013 cmdlet。 若要从 Windows PowerShell 中运行 Lync Server 2013 cmdlet, 请在 Windows PowerShell 命令提示符处键入以下内容:
    
    `Import-Module Lync`

  - 启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)  


[Lync Server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

