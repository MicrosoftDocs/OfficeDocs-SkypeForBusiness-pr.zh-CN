---
title: Lync Server 2013：打开 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1019a763647ff2bf1ec2333e3a88315c987e85ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>打开 Lync Server 2013 管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-28_

您可以使用本主题中的过程打开管理工具，以部署、配置或排除 Lync Server 2013 拓扑。

  - 部署向导

  - 拓扑生成器

  - Lync Server 控制面板

  - Lync Server 命令行管理程序

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>部署向导

使用以下过程可在本地启动部署向导，以添加或删除 Lync Server 2013 组件文件。

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>启动 Lync Server 2013 部署向导

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录到安装了 Lync Server 部署向导的计算机。

2.  依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 部署向导**"。

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
    > 您可以通过使用属于本地用户组成员的帐户来定义拓扑，但要读取、发布或启用拓扑（在服务器上安装 Lync Server 2013 所必需的拓扑），必须使用属于 Domain Admins 组和 RTCUniv 的帐户。ersalServerAdmins 组，并且具有对要用于存档文件存储的文件共享的完全控制权限（即读取、写入和修改），以便拓扑生成器可以配置所需的任意自由访问控制列表（Dacl）。或具有等效用户权限的帐户。

    
    </div>

2.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013 控制面板

使用以下过程之一打开 Lync Server 2013 控制面板，以管理环境中的服务器、用户、客户端和设备的配置。

<div>


> [!NOTE]  
> 您可以使用分配给 CsAdministrator 角色的用户帐户在 Lync Server 2013 控制面板中执行任何任务。 您可以使用其他角色登录到 Lync Server 2013 控制面板来执行特定的管理任务，具体取决于您需要执行的任务。 例如，可以使用 CSArchivingAdministrator 在 Lync Server 2013 控制面板中管理存档。 有关角色的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。 有关可用于执行某项特定任务的角色的详细信息，请参阅该任务的文档。



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>从组织的防火墙内的任何计算机中打开 Lync Server 2013 控制面板

1.  从分配给 CsAdministrator 角色或其他角色且具有要执行的任务的相应用户权限的用户帐户，以最小屏幕分辨率为 1024 x 768 登录到内部部署中的任何计算机。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果已配置了管理简单的统一资源定位器（URL），则可以从组织的防火墙内的任何计算机上运行的 Internet 浏览器访问 Lync Server 2013 控制面板。 有关配置管理简单 URL 的详细信息，请参阅部署文档中的规划文档中的规划简单 Url 和在<A href="lync-server-2013-edit-or-configure-simple-urls.md">Lync server 2013 中编辑或配置简单</A>url 中的 "在 lync server <A href="lync-server-2013-planning-for-simple-urls.md">2013 中规划简单 url</A> "。

    
    </div>

2.  打开浏览器窗口，然后输入为组织配置的管理 URL。

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>在运行 Lync Server 2013 的计算机上打开 Lync Server 2013 控制面板

1.  从属于 CsAdministrator 角色的成员或其他角色且具有要执行的任务的相应用户权限和权限的用户帐户，登录到已安装 Lync Server 2013 的计算机，或者至少在 Lync Server 2013 administrat。我的工具。 若要配置设置，计算机的最小屏幕分辨率必须为 1024 x 768。

2.  启动 Lync Server 2013 控制面板：单击 "**开始**"，单击 "**所有程序**"，指向 "**管理工具**"，指向 " **Microsoft Lync Server 2013**"，然后单击 " **Lync server 2013 控制面板"**。

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 命令行管理程序

使用以下过程打开 Lync Server 2013 命令行管理程序，以使用命令行管理环境中的服务器、用户、客户端和设备。

<div>


> [!NOTE]  
> 您可以使用分配给 CsAdministrator 角色的用户帐户在 Lync Server 2013 命令行管理程序中执行任何任务。 可使用其他角色登录以执行特定的管理任务，具体取决于需执行的任务。 例如，可以使用 CSArchivingAdministrator 运行与存档管理相关的 cmdlet。 有关角色的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。 有关可用于运行某个特定 cmdlet 的角色的详细信息，请参阅该 cmdlet 的文档。<BR>还可以使用 RTCUniversalServerAdmins 组、RTCUniversalUserAdmins 组或 RTCUniversalReadOnlyAdmins 组中的用户帐户来运行某些 cmdlet，具体取决于该 cmdlet。



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>打开 Lync Server 2013 命令行管理程序

  - 如果打开的是 Windows PowerShell 窗口而不是 Lync Server 2013 命令行管理程序，则默认情况下无法运行 Lync Server 2013 cmdlet。 若要从 Windows PowerShell 中运行 Lync Server 2013 cmdlet，请在 Windows PowerShell 命令提示符处键入以下内容：
    
    `Import-Module Lync`

  - 启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

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

