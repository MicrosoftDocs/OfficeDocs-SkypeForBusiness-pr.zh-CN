---
title: Lync Server 2013：配置语音邮件转义
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c3faf28bdd85f32de1560d35aaf35392fef9746
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516949"
---
# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>在 Lync Server 2013 中配置语音邮件转义

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

如果用户为移动电话配置同时响铃，则当移动电话关机、没电或没信号时，呼叫者通常将路由到用户的个人语音邮件。 借助 Lync Server 2013，用户可以选择将与业务相关的呼叫路由到其公司语音邮件系统。 具体来说，可以配置计时器，如果运营商的语音邮件在定义的时间范围内应答呼叫，Lync Server 将断开与运营商的语音邮件系统的连接 (和用户的个人语音邮件) ，而在公司系统中，用户的其余终结点将继续振铃。 这样以来，呼叫者将自动路由到用户的企业语音邮件。

使用以下参数在语音策略级别使用 Lync Server 命令行管理程序 cmdlet （ **set-csvoicepolicy**）执行此配置。

<div>

## <a name="to-configure-voice-mail-escape"></a>配置语音邮件转义

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  指定 **Set-CsVoicePolicy** 的以下参数：
    
      - **EnableVoicemailEscapeTimer** - 启用或禁用转义计时器。
    
      - **PSTNVoicemailEscapeTimer** - 指定超时值（以毫秒为单位）。默认值为 1500 毫秒，该值的范围可介于 0 到 8000 毫秒之间。

</div>

<div>

## <a name="example"></a>示例

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>请参阅


[在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

