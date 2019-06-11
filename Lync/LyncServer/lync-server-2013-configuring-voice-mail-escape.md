---
title: 'Lync Server 2013: 配置语音邮件转义'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f08e12b97c51d68b4b08d10692802cb035ce8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>在 Lync Server 2013 中配置语音邮件转义

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-22_

如果用户为移动电话配置同时响铃，则当移动电话关机、没电或没信号时，呼叫者通常将路由到用户的个人语音邮件。 使用 Lync Server 2013, 用户可以选择将与业务相关的呼叫路由到其企业语音邮件系统。 具体说来, 可以配置计时器, 并且如果运营商的语音邮件在定义的时间范围内接听呼叫, 则 Lync Server 将断开与运营商的语音邮件系统 (和用户的个人语音邮件) 的连接, 同时用户的剩余公司系统中的终结点继续拨打。 这样以来，呼叫者将自动路由到用户的企业语音邮件。

使用以下参数在语音策略级别上使用 Lync Server Management Shell cmdlet ( **CsVoicePolicy**) 执行此配置。

<div>

## <a name="to-configure-voice-mail-escape"></a>配置语音邮件转义

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

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

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

