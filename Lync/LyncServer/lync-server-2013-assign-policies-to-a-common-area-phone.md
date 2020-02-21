---
title: Lync Server 2013：将策略分配给公用区域电话
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67ac175ea9aae83a56bd2706bee3c80418b99ea8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a>在 Lync Server 2013 中将策略分配给公用区域电话

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

为公用区域电话创建策略后（有关详细信息，请参阅[create a voice policy and CONFIGURE PSTN usage usage In Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)）中，可以使用 Windows PowerShell 和相应的**Grant-Cs** cmdlet 将策略分配给公用区域电话。 这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a>将策略分配给单个公共区域电话

  - 以下命令将每用户语音策略 RedmondVoice 分配给具有标识生成14前厅浏览的公共区域电话。
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a>将策略分配给多个公用区域电话

  - 在此示例中，将每用户语音策略 RedmondVoice 分配给配置为在组织中使用的所有公用区域电话。
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

有关详细信息，请参阅[set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

