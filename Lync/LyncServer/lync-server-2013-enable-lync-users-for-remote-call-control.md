---
title: Lync Server 2013：为 Lync 用户启用远程呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

你可以使用基于服务器的带内配置策略为远程呼叫控制配置 Lync 用户。 你可以使用 Lync Server 控制面板或 Lync Server Management Shell 命令行界面管理带内配置设置。 这些工具将替换用于在早期版本中管理组策略设置的 Windows Management Instrumentation (WMI) 管理单元。

如果你希望让用户在 Lync 中配置其自己的远程呼叫控制设置, 则可以为服务器上的用户配置远程呼叫控制设置, 而无需指定**行服务器 URI**和**行 URI**值。 请确保将相应的**Line 服务器 URI**和**行 URI**值与你的用户通信, 并向你的用户提供配置这些设置的说明。 有关在 Lync Server 中手动配置远程呼叫控制的过程, 请参阅 Microsoft Office 网站上 Lync 客户端<http://go.microsoft.com/fwlink/p/?linkid=210132>文档中的 "设置手机选项和号码"。

如果你有现有的通信服务器 2007 R2 或通信服务器2007部署, 则 Communicator 2007 R2 和 Communicator 2007 客户端将在并行迁移期间继续使用组策略。 但是, 如果你希望将策略设置传送到 Lync 客户端, 你需要配置等效的 Lync Server 带内预配设置。

<div>


> [!NOTE]  
> 若要为用户启用远程呼叫控制, 你需要为用户提供行 URI 和行服务器 URI。 如<A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 中的 "远程呼叫控制部署任务</A>" 中所述, 你需要确保使用网关为这些设置所需的语法。<BR>请确保在将静态路由配置到网关时, 行服务器 URI 中的域与在 MatchUri 参数中指定的目标域相同。<BR>行 URI 以 E-164 格式指定分配给用户的电话号码, 使用 "电话:" 前缀 (例如电话: + 14255550150)。 如果您想要配置分机号码, 则该格式为电话: + 14255550150; ext = 111。 如果你以前配置了用户的行 URI 且值未更改, 则在启用远程呼叫控制的用户时无需指定行 URI。



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>使用命令行管理程序为启用了 Lync 的用户启用远程呼叫控制

1.  登录到安装了 Lync Server Management Shell 的计算机作为 RTCUniversalServerAdmins 组的成员, 或者作为你为其分配了**move-csuser** cmdlet 的基于角色的访问控制角色。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  若要使用**move-csuser** cmdlet 为已启用 Lync 的现有用户配置远程呼叫控制, 请执行下列操作:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    例如：
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板为 "远程呼叫控制" 配置用户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在 "**搜索用户**" 框中, 键入所需用户帐户的 "显示名称"、"名字"、"姓氏"、"安全帐户管理器" (SAM) 帐户名称、SIP 地址或行统一资源标识符 (URI) 的所有 (或第一部分), 然后单击**查找**。

5.  在表中, 单击要修改的用户帐户。

6.  在 "**编辑**" 菜单上, 单击 "**修改**"。

7.  在**电话服务**中, 执行下列操作之一:
    
      - 若要启用远程呼叫控制以使用户能够从 Lync 2013 控制其专用分支机构 (PBX) 电话, 以进行 PC 到 PC 的音频呼叫和 PC 至电话呼叫, 请单击 "**远程呼叫控制**"。 在 "**行 URI**" 中, 指定用户的电话号码。 在 "**行服务器 URI**" 中, 指定 SIP/CSTA 网关的 sip URI。
    
      - 若要启用远程呼叫控制, 但禁用 PC 到 PC 音频呼叫, 并仅允许用户从 Lync 2013 控制其 PBX 电话, 以便进行 PC 至电话呼叫, 请单击 "**仅远程呼叫控制**"。 在 "**行 URI**" 中, 指定用户的电话号码。 在 "**行服务器 URI**" 中, 指定 SIP/CSTA 网关的 sip URI。

8.  完成后, 单击 "**提交**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

