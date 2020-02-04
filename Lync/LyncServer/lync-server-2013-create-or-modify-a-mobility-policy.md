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
ms.openlocfilehash: 3f64e74b389b268027e06b2f4103b0c828c5be6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改移动策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

你可以创建或修改移动策略，以允许移动用户为 Lync 功能使用支持的移动设备，例如即时消息（IM）、状态和联系人。 可以从 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳程序创建或修改移动策略

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server "控制面板" 创建移动策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**移动策略**导航" 按钮。

4.  在 "**移动策略**" 页面上，单击 "**新建**"，然后执行下列操作之一：
    
    1.  若要创建网站移动策略，请单击 "**网站策略**"，单击网站，单击 **"确定**"，查看默认设置，如果需要，可进行任何更改。
    
    2.  若要创建用户移动策略，请单击 "**用户策略**"，键入名称，查看默认设置，如果需要，请进行任何更改。

5.  单击“**提交**”。

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server "控制面板" 修改移动策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**移动策略**导航" 按钮。

4.  在 "**移动策略**" 页面上，单击现有移动策略之一。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  编辑任何设置。

7.  单击“**提交**”。

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建外部访问策略

你可以使用 Windows PowerShell 和**CsMobilityPolicy** cmdlet 创建移动策略（在网站范围或每用户范围内）。 此外，你可以使用**CsMobilityPolicy** cmdlet 修改你的任何现有策略，包括全局策略。 这些 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>在网站范围内创建移动策略

  - 此命令为 Redmond 网站创建新的移动策略：
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    由于前面的命令中未指定任何参数（强制标识参数除外），因此策略将对其所有属性使用默认值。

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>在每用户范围内创建移动策略

  - 若要在每用户范围内创建移动策略，请为策略指定唯一标识：
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>创建移动策略时更改单个属性值

  - 若要创建使用不同属性值的策略，请包含相应的参数和参数值。 例如，此命令将创建通过工作禁用呼叫的移动策略：
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>创建移动策略时更改多个属性值

  - 可以通过包含多个参数来修改多个属性值。 例如，此命令将创建一个策略，该策略通过工作禁用移动和呼叫：
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

有关详细信息，请参阅[新的-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)和[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 的帮助主题。

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

