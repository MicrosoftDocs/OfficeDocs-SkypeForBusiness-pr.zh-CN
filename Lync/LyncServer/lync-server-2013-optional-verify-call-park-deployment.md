---
title: 'Lync Server 2013: (可选) 验证呼叫驻留部署'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110617bbd77da0efb8802c6aba401f2ea5075b01
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>可选在 Lync Server 2013 中验证呼叫寄存部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-11_

安装并配置呼叫寄存后, 您需要验证配置, 以确保停车和检索呼叫按预期工作。 至少必须验证以下内容：

  - 呼叫已启用呼叫寄存并让用户寄存呼叫的用户。
    
    <div>
    

    > [!NOTE]  
    > 如果在执行此测试之前已在语音策略中启用了呼叫寄存, 则离开呼叫的用户需要注销 Lync 服务器, 然后重新登录, 以便能够在转接呼叫列表中看到呼叫寄存选项。

    
    </div>

  - 拨打通道号码以取回此呼叫。

  - 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。

</div>

<span> </span>

</div>

</div>

</div>

