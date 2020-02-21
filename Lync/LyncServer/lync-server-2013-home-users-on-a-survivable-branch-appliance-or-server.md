---
title: Lync Server 2013： Survivable 分支设备或服务器上的家庭用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f6fb176025dd7f075429833e48b53eb1f7a5b07
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-10_

在 Survivable 分支机构或 Survivable 分支服务器上托管用户的过程与在前端池上托管用户的过程类似。 在中央站点执行 Survivable Branch 设备或 Survivable Branch Server 过程。

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户

1.  在将用户移动到 Survivable 分支服务器或 Survivable 分支服务器之前，请打开 Lync Server 命令行管理程序，然后执行以下操作：
    
      - 运行 cmdlet **CsPstnOutboundCall**以验证 Survivable 分支服务器是否正在运行，以及是否配置了公共交换电话网络（PSTN）连接。 如果需要修改 PSTN 网关属性，请使用 cmdlet **Set-CsPstnGateway**。
    
      - 运行 cmdlet **set-csvoicepolicy**以验证将托管在 Survivable 分支服务器上的用户是否具有相应的 VoIP 路由策略。 如果需要修改 VoIP 策略，请使用 cmdlet **Set-CsVoicePolicy**。
    
      - 运行 cmdlet **Get-CsVoicemailReroutingConfiguration** 来验证是否已配置语音邮件重新路由设置。 如果需要修改语音邮件重新路由设置，请使用 cmdlet **Set-CsVoicemailReroutingConfiguration**。

2.  在 Lync Server 命令行管理程序中，运行 cmdlet **get-csuser**移动家庭用户。

<div>


> [!NOTE]  
> 您还可以使用 Lync Server 控制面板验证先决条件和家庭用户。



</div>

<div>


> [!NOTE]  
> 驻留在 Lync Server Survivable 分支设备上的用户无法创建新的聊天室或查看现有聊天室的会议室卡片。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[移动-Get-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

