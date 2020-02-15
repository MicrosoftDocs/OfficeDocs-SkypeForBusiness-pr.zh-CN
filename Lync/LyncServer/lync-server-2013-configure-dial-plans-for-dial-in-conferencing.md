---
title: Lync Server 2013：配置电话拨入式会议的拨号计划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28dd2ddb0633a45d19f1a7bb7638d86e042658b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中配置电话拨入式会议的拨号计划

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-25_

部署电话拨入式会议时，需要创建或修改一个或多个用于路由拨入访问电话号码的拨号计划。确保每个拨号计划中至少有一个规范化规则可以将电话分机号转换为 E.164 格式的完整电话号码。电话拨入式会议的用户通过输入其个人标识号 (PIN) 及其电话号码，可以作为经过身份验证的企业用户加入会议。需要使用规范化规则将分机号转换为完整的电话号码，以便在用户只输入电话分机号时可以对其进行身份验证。

要设置电话拨入式会议的拨号计划，请执行下列操作：

  - 无论是否部署企业语音，都要修改全局拨号计划以添加电话拨入式会议区域，并确保规范化规则准确地转换拨入访问号码。 有关详细说明，请参阅[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。

  - 如果未部署企业语音，请创建电话拨入式会议访问号码的拨号计划。 确保其中包含电话拨入式会议区域。 有关详细说明，请参阅[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。

  - 如果已部署企业语音，请根据需要修改企业语音拨号计划以包含区域，并对拨入访问号码使用适当的规范化规则。 有关详细说明，请参阅[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。 还可以创建仅用于拨入访问号码的专用拨号计划。 有关详细说明，请参阅[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。

有关规划区域的详细信息，请参阅规划文档中的[Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中查看拨号计划信息](lync-server-2013-view-dial-plan-information.md)

  - [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)

  - [在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)

  - [在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

