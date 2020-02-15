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
ms.openlocfilehash: f8d739c9987c0a17c29997fad8ac47b2d886fbea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中为用户启用呼叫寄存

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-11_

用户在为语音策略中的呼叫寄存启用之前，不能寄存呼叫或检索寄存的呼叫。

<div>


> [!NOTE]  
> 默认情况下，对所有用户禁用呼叫寄存。



</div>

您可以在全局作用域、站点作用域或用户作用域上启用呼叫寄存。 用户作用域优先于站点范围，而站点范围优先于全局作用域。 如果您有多个语音策略，请查看所有策略以启用呼叫寄存，而不仅仅是全局策略。

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>使用 Lync Server 控制面板为用户启用呼叫寄存

1.  以**RTCUniversalServerAdmins**组成员或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**管理角色的成员身份登录到计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“语音路由”**。

4.  单击 "**语音策略**" 选项卡。

5.  双击现有的语音策略以打开 "**编辑语音策略**" 对话框。

6.  在 "**呼叫功能**" 下，选择 "**启用呼叫寄存**"。

7.  单击 **"确定"** 以保存语音策略

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>使用 Cmdlet 为用户启用呼叫寄存

1.  以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    例如，要为默认全局语音策略启用呼叫寄存，请执行以下操作：
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

