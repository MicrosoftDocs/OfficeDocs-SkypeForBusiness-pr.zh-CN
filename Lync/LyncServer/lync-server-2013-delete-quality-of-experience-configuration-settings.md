---
title: Lync Server 2013：删除体验配置设置的质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bef2a59243d065f74c09dd4bc5c3aeb6a4451bbd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a>删除 Lync Server 2013 中的体验质量配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、"抖动"量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。

安装 Microsoft Lync Server 2013 时，将为你创建一个 QoE 配置设置的单个全局集合。 管理员还可以选择可应用于各个站点的自定义设置集合。 根据设计，在站点作用域配置的设置优先于在全局作用域配置的设置。 如果您删除站点作用域设置，则将通过使用全局设置在该站点管理 QoE。

请注意，您还可以“删除”全局设置。但将不会实际删除全局设置。不过，该集合中的所有属性将重置为其默认值。例如，在 QoE 配置设置的集合中启用了默认清除功能。假定您修改了全局集合，这样就会禁用清除功能。如果稍后删除全局设置，则会将这些属性全部重置为其默认值。在这种情况下，这意味着又重新启用清除功能。

你可以使用 Lync Server 控制面板或使用[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) Cmdlet 删除 QoE 配置设置。

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 删除 QoE 配置设置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。

4.  在“**用户体验质量数据**”上，单击所需的策略，单击“**编辑**”，然后单击“**删除**”。

5.  单击“**确定**”。

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 QoE 配置设置

你可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 删除 QoE 配置设置。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>删除 QoE 配置设置的指定的集合

  - 此命令可用于删除应用于 Redmond 站点的 QoE 配置设置：
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>删除应用于该站点作用域的所有 QoE 配置设置

  - 此命令可用于删除应用于该站点作用域的所有 QoE 配置设置：
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>删除禁用 QoE 监控处的所有 QoE 配置设置

  - 此命令用于删除已禁用 QoE 监控处的所有 QoE 配置设置：
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

有关详细信息，请参阅[Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

