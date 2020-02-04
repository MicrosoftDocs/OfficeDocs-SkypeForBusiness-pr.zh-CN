---
title: Lync Server 2013：定义位置策略
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
ms.openlocfilehash: feb7550412fa6cdcda3a8fc4dd9b7913912c34e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>定义 Lync Server 2013 的位置策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-29_

每个位置策略包含以下信息：

  - **已启用紧急服务**  
    如果此值为 **"是"**，则为 E9 启用客户端-1-1。 客户端注册时，它会尝试从位置信息服务获取位置，并将位置信息包含在紧急呼叫的一部分中。

<!-- end list -->

  - **需要位置**  
    此设置仅在 "**已启用** 的兴起服务" 设置为 **"是"** 时使用。
    
    你可以配置 "**需要位置**" 设置以定义客户端行为。 将该值设为**否**表示不会提示用户输入位置。 设为**是**表示将提示用户输入位置，但可以消除提示。 设为**免责声明**表示将会提示用户输入位置，并且当用户尝试消除提示时将显示免责声明。 在所有情况下，用户都可以继续使用该客户端。
    
    <div>
    

    > [!NOTE]  
    > 如果在启用 E9-1-1 之前用户手动输入位置，则不会显示免责声明文本。已查看免责声明的用户将不能查看免责声明文本的更新。

    
    </div>

<!-- end list -->

  - **增强型紧急服务免责声明**  
    该设置指定当用户消除输入位置提示时显示的免责声明。 在 Lync Server 2013 中，你可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明。
    
    <div>
    

    > [!NOTE]  
    > 此位置策略设置与 Lync Server 2010 不同，您使用<STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet 为整个组织设置全局免责声明。 如果全局免责声明已存在，则需要在位置策略中指定该免责声明。 也就是说，Lync Server 2013 仅使用位置策略中指定的免责声明。

    
    </div>

<!-- end list -->

  - **紧急拨号字符串**  
    此拨号字符串（较少前导 "+"，但包括 Lync 用户的拨号计划完成的任何规范化）表示呼叫是紧急呼叫。 **紧急拨号串**使客户端包括有关呼叫的位置和回拨信息。
    
    <div>
    

    > [!NOTE]  
    > 如果您的组织不使用外部线路访问前缀，则无需创建相应的拨号计划规范化规则，在将呼叫发送到 Lync 池服务器上的出站路由之前将 "+" 添加到911字符串;由于位置策略，Lync 客户端将自动预置 "+"。 但是，如果你的站点使用外部访问前缀，则需要向适用的拨号计划策略添加规范化规则，以去掉外部访问前缀并添加“+”。 例如，如果你的位置使用了外部访问前缀9，并且用户拨了 9&nbsp;911 以进行紧急呼叫，则客户端将使用其拨号计划策略将此号码与 + 911 进行规范化，然后由呼叫者的位置配置文件中的路由评估该拨出的号码。

    
    </div>

<!-- end list -->

  - **紧急拨号字符串掩码**  
    一个分号分隔的拨号字符串列表，将转换为指定的**紧急拨号字符串**。 例如，你可能想要添加 112（欧洲大部分地区的紧急服务号码）。 从欧洲访问 Lync 用户可能不知道911是美国的紧急电话号码，但他们可以拨打112并获得相同的结果。 使用紧急拨号字符串，每个号码前都没有“+”，如果你使用外线访问代码，请确保用户的拨号计划策略中存在规范化规则以去掉访问代码数字。

<!-- end list -->

  - **PSTN 用法**  
    包含确定紧急呼叫将转至哪一 SIP 中继、PSTN 网关或 ELIN 网关的路由路径的 PSTN 用法名称。
    
    <div>
    

    > [!NOTE]  
    > 一个用法只能分配给一个位置策略。此 PSTN 用法覆盖分配给用户语音策略的 PSTN 用法，但仅适用于紧急拨号字符串或紧急拨号字符串掩码之一发出的呼叫。

    
    </div>

<!-- end list -->

  - **通知 URI**  
    指定要在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP URI。支持通讯组。

<!-- end list -->

  - **会议 URI**  
    指定在发出紧急呼叫时应加入会议的外线直拨分机 (DID) 号码（通常是安全服务台号码）。

<!-- end list -->

  - **会议模式**  
    指定会议 URI 将使用单向还是双向通信加入紧急呼叫。

<!-- end list -->

  - **位置刷新间隔**  
    指定从位置信息服务的位置更新的客户端请求之间的时间量（以小时为单位）。 该值可以设置为 1 和 12 之间的任意值。 默认值为 4。

</div>

<span> </span>

</div>

</div>

</div>

