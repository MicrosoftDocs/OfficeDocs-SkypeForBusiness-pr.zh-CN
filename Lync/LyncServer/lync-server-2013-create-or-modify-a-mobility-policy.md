---
title: Lync Server 2013：创建或修改移动策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4246569ad7d66788cef507488b78567b6b892f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改移动策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

您可以创建可修改移动策略以允许移动用户使用受支持的移动设备来实现 Lync 功能，例如，即时消息 (IM)、状态和联系人。 您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序创建或修改移动策略

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server 控制面板创建移动策略

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“移动策略”**** 导航按钮。

4.  在 "**移动策略**" 页上，单击 "**新建**"，然后执行下列操作之一：
    
    1.  要创建站点移动策略，请依次单击“站点策略”****、“站点”和“确定”****，查看默认设置，且如果需要，可做任何更改。
    
    2.  要创建用户移动策略，请单击“用户策略”****，键入名称，查看默认设置，且如果需要，可做任何更改。

5.  单击“提交”****。

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server 控制面板修改移动策略

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“移动策略”**** 导航按钮。

4.  在 "**移动策略**" 页上，单击某个现有移动策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  编辑任何设置。

7.  单击“提交”****。

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建外部访问策略

您可以使用 Windows PowerShell 和**set-csmobilitypolicy** cmdlet 创建移动策略（在站点范围或每用户范围内）。 另外，可以使用 **Set-CsMobilityPolicy** cmdlet 修改任何现有策略，包括全局策略。 这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>在站点范围创建移动策略

  - 此命令可用于为 Redmond 站点创建新的移动策略：
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    因为在上述命令中没有指定任何参数（不是必需的 Identity 参数），所以这些策略会为其所有属性使用默认值。

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>在每用户范围创建移动策略

  - 要在每用户作用域创建移动策略，请为该策略指定唯一身份：
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>创建移动策略时更改单个属性值

  - 要创建使用不同属性值的策略，请包括属性参数和属性值。例如，此命令可创建禁用单位电话的移动策略：
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>创建移动策略时更改多个属性值

  - 通过包括多个参数可修改多个属性值。例如，此命令可用于创建禁用移动和单位电话的策略：
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

有关详细信息，请参阅 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) 和 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置移动策略](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

