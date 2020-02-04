---
title: Lync Server 2013：为用户启用呼叫寄存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd89ba10f5cae16e88c65e6e56178fc517c71213
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中为用户启用呼叫寄存

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-11_

用户不能寄存通话或检索寄存的呼叫，直到它们在语音策略中被启用呼叫寄存。

<div>


> [!NOTE]  
> 默认情况下，将对所有用户禁用 "呼叫寄存"。



</div>

你可以在全局范围内或在网站范围或用户范围内启用呼叫寄存。 用户作用域优先于站点作用域，而站点作用域又优先于全局作用域。 如果你有多个语音策略，请查看所有策略以启用呼叫寄存，而不仅仅是全局策略。

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>使用 Lync Server "控制面板" 为用户启用呼叫寄存

1.  以 **RTCUniversalServerAdmins** 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”****。

4.  单击“语音策略”**** 选项卡。

5.  双击现有语音策略以打开“编辑语音策略”**** 对话框。

6.  在“呼叫功能”**** 下，选择“启用呼叫寄存”****。

7.  单击“确定”**** 保存语音策略。

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>使用 Cmdlet 为用户启用呼叫寄存

1.  以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    例如，若要为默认全局语音策略启用呼叫寄存，请执行以下操作：
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

