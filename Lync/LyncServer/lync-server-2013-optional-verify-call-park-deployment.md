---
title: Lync Server 2013：（可选）验证呼叫寄存部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0389e729f91da7cb91dff9426e38c1dcf20024
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Optional在 Lync Server 2013 中验证呼叫寄存部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-11_

在安装和配置呼叫寄存之后，需要验证配置，以确保停车和检索呼叫按预期方式工作。 至少必须验证以下内容：

  - 呼叫已启用呼叫寄存且用户寄存呼叫的用户。
    
    <div>
    

    > [!NOTE]  
    > 如果您在执行此测试之前在语音策略中启用了呼叫寄存，则寄存呼叫的用户需要注销 Lync Server，然后重新登录，才能在转移呼叫列表中查看呼叫寄存选项。

    
    </div>

  - 拨打通道号码以取回此呼叫。

  - 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。

</div>

<span> </span>

</div>

</div>

</div>

