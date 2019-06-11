---
title: 'Lync Server 2013: 修改体验质量设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce6041e6512714f10785cf2976727788e105f70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a>在 Lync Server 2013 中修改体验质量设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

默认情况下，用户体验质量 (QoE) 数据会在 60 天后清除。可以使用“**用户体验质量数据**”页上的设置将该数据保留更长或更短的时间。如果禁用 QoE，则在启用 QoE 之前捕获的数据也将清除。

<div>


> [!NOTE]  
> 应该对呼叫详细信息记录 (CDR) 和 QoE 进行配置，使二者保留数据的天数相同。监控报告主页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。



</div>

以下过程介绍如何配置 QoE 数据的清除设置。

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 指定 QoE 数据的保留

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。

4.  在“**用户体验质量数据**”页上，单击表中的相应站点，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  要打开清除，请选择“**启用 QoE 清除**”。

6.  在“**QoE 最长保留期限（天）**”中选择 QoE 数据的最长保留天数。

7.  单击“**提交**”。

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 QoE 保留

你可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 创建 QoE 保留设置。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a>为特定位置指定 QoE 保留

  - 此命令会为 Redmond 站点启用 QoE 数据的清除，并将该站点配置为保留 QoE 数据 20 天。
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a>为多个位置指定 QoE 保留

  - 此命令会为组织中使用的所有 QoE 配置设置配置 QoE 保留。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

有关详细信息, 请参阅[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

