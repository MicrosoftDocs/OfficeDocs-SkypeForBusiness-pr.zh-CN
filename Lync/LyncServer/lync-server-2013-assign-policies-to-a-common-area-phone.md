---
title: 'Lync Server 2013: 为公共区域电话分配策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b792d6ae14ee13fd1d95761d2a0d6b0af7bbdfae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a>在 Lync Server 2013 中将策略分配到常见的区域电话

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-20_

为常用的区域电话创建策略后 (有关详细信息, 请参阅[在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), 您可以使用 Windows PowerShell 和相应的**Grant-Cs 将策略分配给公共区域电话。** cmdlet。 这些 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a>向单个公共区域电话分配策略

  - 以下命令将每用户语音策略 RedmondVoice 分配给具有标识建筑物14会议厅的通用区域电话。
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a>向多个公共区域电话分配策略

  - 在此示例中, 每用户语音策略 RedmondVoice 分配给所有配置为在组织中使用的常用区域电话。
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

有关详细信息, 请参阅[授权 CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

