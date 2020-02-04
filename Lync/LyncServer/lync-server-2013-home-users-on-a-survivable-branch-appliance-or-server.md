---
title: Lync Server 2013：在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户
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
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>在 Lync Server 2013 中在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-12-10_

在 Survivable 分支设备或 Survivable 分支服务器上托管用户的过程与在前端池中托管用户的过程类似。 在中央站点上执行 Survivable 分支装置或 Survivable 分支服务器过程。

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>在 Survivable 分支装置或 Survivable 分支服务器上家庭用户

1.  将用户移动到 Survivable 分支服务器或 Survivable 分支服务器之前，请打开 Lync Server 命令行管理程序，然后执行以下所有操作：
    
      - 运行 cmdlet **Test-CsPstnOutboundCall**以验证 Survivable 分支服务器是否正在运行以及是否配置了公共交换电话网络（PSTN）连接。 如果需要修改 PSTN 网关属性，请使用 cmdlet **CsPstnGateway**。
    
      - 运行 cmdlet **CsVoicePolicy**以验证将托管在 Survivable 分支服务器上的用户是否具有相应的 VoIP 路由策略。 如果需要修改 VoIP 策略，请使用 cmdlet **Set-CsVoicePolicy**。
    
      - 运行 cmdlet **CsVoicemailReroutingConfiguration**以验证是否配置了语音邮件重新路由设置。 如果需要修改语音邮件重新路由设置，请使用 cmdlet **CsVoicemailReroutingConfiguration**。

2.  在 Lync Server Management Shell 中，运行 cmdlet **move-move-csuser**移动家庭用户。

<div>


> [!NOTE]  
> 您也可以使用 Lync Server 控制面板验证先决条件和家庭用户。



</div>

<div>


> [!NOTE]  
> 在 Lync Server Survivable 分支设备上托管的用户无法创建新的聊天室或查看现有聊天室的聊天室卡片。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

