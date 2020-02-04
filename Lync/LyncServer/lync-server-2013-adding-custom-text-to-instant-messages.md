---
title: Lync Server 2013：向即时消息添加自定义文本
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b54b4724568a4f57bebc7ef6162a553cfdd9a091
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>在 Lync Server 2013 中向即时消息添加自定义文本

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-20_

通过使用**set-csclientpolicy**或**Set-csclientpolicy** Lync Server Management Shell cmdlet 和 IMWarning 参数，将免责声明或警告添加到每个 Lync 2013 即时消息（IM）对话的开头。

以下示例中的命令在新的 IM 对话开始时在对话窗口的顶部添加安全提醒：

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

使用**Grant-set-csclientpolicy**将此新策略分配给用户。 有关详细信息，请参阅 Lync Server Management Shell 文档中的 "**新建-set-csclientpolicy** " 和 "**授予" set-csclientpolicy** 。

</div>

<span> </span>

</div>

</div>

</div>

