---
title: Lync Server 2013：为 Lync 用户启用远程呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a400b5a071a3540f65c38d606724df10883931e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

您可以使用基于服务器的带内设置策略为 Lync 用户配置远程呼叫控制。 您可以通过使用 Lync Server 控制面板或 Lync Server Management Shell 命令行界面来管理带内配置设置。 这些工具将替换用于在早期版本中管理组策略设置的 Windows Management Instrumentation （WMI）管理单元。

如果你想让用户在 Lync 中配置其自己的远程呼叫控制设置，可以在不指定**行服务器 URI**和**线路 URI**值的情况下为服务器上的用户配置远程呼叫控制设置。 确保将适当的**行服务器 URI**和**行 URI**值传递给用户，并向用户提供有关配置这些设置的说明。 有关在 Lync Server 中手动配置远程呼叫控制的过程，请参阅 Microsoft Office 网站上的 Lync 客户<https://go.microsoft.com/fwlink/p/?linkid=210132>端文档中的 "设置电话选项和号码"。

如果您有一个现有的通信服务器 2007 R2 或通信服务器2007部署，Communicator 2007 R2 和 Communicator 2007 客户端将继续在并行迁移过程中使用组策略。 但是，如果您希望将策略设置传输到 Lync 客户端，则需要配置等效的 Lync Server 带内设置设置。

<div>


> [!NOTE]  
> 若要为用户启用远程呼叫控制，您需要为用户提供线路 URI 和行服务器 URI。 如<A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 中的远程呼叫控制的部署任务</A>中所述，您需要确保使用网关对这些设置所需的语法。<BR>在将静态路由配置为网关时，请确保行服务器 URI 中的域与您在 MatchUri 参数中指定的目标域相同。<BR>线路 URI 以 e.164 格式指定分配给用户的电话号码，带有 "电话：" 前缀（例如电话： + 14255550150）。 如果要配置分机号，则格式为 tel:+14255550150;ext=111。 如果您之前已配置用户的“线路 URI”，且未更改其值，则在为用户启用远程呼叫控制时，不需要指定“线路 URI”。



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>使用命令行管理程序为启用了 Lync 的用户启用远程呼叫控制

1.  登录到安装了 Lync Server 命令行管理程序的计算机上作为 RTCUniversalServerAdmins 组的成员，或者作为已为其分配**get-csuser** cmdlet 的基于角色的访问控制角色。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  要使用 **Set-CsUser** cmdlet 为已启用 Lync 的现有用户配置远程呼叫控制，请执行以下操作：
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    例如：
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板为用户配置远程呼叫控制

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  在 "**搜索用户**" 框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名、SIP 地址或线路统一资源标识符（URI）的全部（或第一部分），然后单击 "**查找**"。

5.  在表中，单击要修改的用户帐户。

6.  在 **“编辑”** 菜单上，单击 **“修改”**。

7.  在 **“电话”** 中，执行下列操作之一：
    
      - 若要启用远程呼叫控制以使用户能够通过 Lync 2013 控制其专用交换机（PBX）电话，以进行 PC 到 PC 的音频呼叫和 PC 到电话呼叫，请单击 "**远程呼叫控制**"。 在 **“线路 URI”** 中，指定用户的电话号码。 在 **“线路服务器 URI”** 中，指定 SIP/CSTA 网关的 SIP URI。
    
      - 若要启用远程呼叫控制，但禁用 PC 到 PC 音频呼叫，并且仅允许用户从 Lync 2013 控制其 PBX 电话以进行 PC 到电话呼叫，请单击 "**仅远程呼叫控制**"。 在 **“线路 URI”** 中，指定用户的电话号码。 在 **“线路服务器 URI”** 中，指定 SIP/CSTA 网关的 SIP URI。

8.  完成后，单击 **“提交”**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

