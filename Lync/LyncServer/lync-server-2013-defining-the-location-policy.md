---
title: Lync Server 2013：定义位置策略
description: Lync Server 2013：定义位置策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fddd5b2ce34e44240162e886672a236789857e7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567534"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a>定义 Lync Server 2013 的位置策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

每个位置策略包含以下信息：

  - **已启用紧急服务**  
    如果此值为 **"是"**，则为 E9-1-1 启用客户端。 当客户端注册时，它会尝试从 Location 信息服务获取位置，并将位置信息作为紧急呼叫的一部分包括在内。

<!-- end list -->

  - **必需的位置**  
    此设置仅在 "**启用了激活服务**   " 设置为 **"是"** 时使用。
    
    您可以配置 " **需要的位置** " 设置以定义客户端行为。 如果将值设置为 " **否** "，则意味着将不会提示用户输入位置。 将值设置为 **"是"** 表示将提示用户输入位置，但可以消除提示。 将此值设置为 **免责声明** 意味着将提示用户输入位置，如果用户尝试消除提示，还会显示免责声明。 在所有情况下，用户都可以继续使用客户端。
    
    <div>
    

    > [!NOTE]  
    > 如果用户在启用 E9-1-1 前手动输入了一个位置，则不会显示免责声明文本。 已查看免责声明的用户将不会查看对免责声明文本的更新。

    
    </div>

<!-- end list -->

  - **增强的紧急服务免责声明**  
    此设置指定用户在消除对某个位置的提示时所看到的免责声明。 在 Lync Server 2013 中，可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明。
    
    <div>
    

    > [!NOTE]  
    > 此位置策略设置与 Lync Server 2010 不同，您使用 <STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet 为整个组织设置全局免责声明。 如果已存在全局免责声明，则需要在位置策略中指定该免责声明。 也就是说，Lync Server 2013 仅使用在位置策略中指定的免责声明。

    
    </div>

<!-- end list -->

  - **紧急拨号字符串**  
    此拨号字符串 (较小的行距 "+"，但包括 Lync 用户的拨号计划所做的任何规范化) 表示呼叫是紧急呼叫。 **紧急拨号字符串**使客户端将位置和回叫信息包含在呼叫中。
    
    <div>
    

    > [!NOTE]  
    > 如果您的组织不使用外部线路访问前缀，则在将呼叫发送到 Lync 池服务器上的出站路由之前，无需创建相应的拨号计划规范化规则，将 "+" 添加到911字符串中;由于位置策略，Lync 客户端将自动预置 "+"。 但是，如果您的网站使用外部访问前缀，则需要向适用的拨号计划策略中添加规范化规则，以去除外部访问前缀并添加 "+"。 例如，如果您的位置使用外部访问前缀9，并且用户拨打 9 &nbsp; 911 以发出紧急呼叫，则在呼叫者的位置配置文件中的路由评估拨号号码之前，客户端将使用其拨号计划策略将其与 + 911 进行规范化。

    
    </div>

<!-- end list -->

  - **紧急拨号字符串掩码**  
    将以分号分隔的拨号字符串列表转换为指定的 **紧急拨号字符串**。 例如，您可能希望添加112，这是欧洲大多数欧洲的紧急服务号码。 来自欧洲的来访 Lync 用户可能不知道911是美国的紧急号码，但可以拨打112并获得相同的结果。 与紧急拨号字符串一样，在每个号码前不包含 "+"，如果您使用外部线路访问代码，请确保用户的拨号计划策略中有规范化规则，以去除访问代码位。

<!-- end list -->

  - **PSTN 用法**  
    包含用于确定哪些 SIP 中继、PSTN 网关或 ELIN 网关紧急呼叫将转到的路由路径的 PSTN 用法的名称。
    
    <div>
    

    > [!NOTE]  
    > 一个位置策略只能分配一个用法。 此 PSTN 用法覆盖分配给用户语音策略的 PSTN 用法，但仅适用于进入紧急拨号字符串或某个紧急拨号字符串掩码的呼叫。

    
    </div>

<!-- end list -->

  - **通知 URI**  
    指定在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP Uri。 支持通讯组。

<!-- end list -->

  - **会议 URI**  
    指定直接向内拨号 (已) 号码 (通常是在发出紧急呼叫时应 conferenced 的安全桌面号码) 。

<!-- end list -->

  - **会议模式**  
    指定是使用单向通信还是双向通信将会议 URI conferenced 为紧急呼叫。

<!-- end list -->

  - **位置刷新间隔**  
    指定从 Location 信息服务进行位置更新的客户端请求之间的时间间隔（以小时为) 单位） (的时间量。 值可以设置为1到12之间的任意值。 默认值为 4。

</div>

<span> </span>

</div>

</div>

</div>

