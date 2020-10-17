---
title: Lync Server 2013 电话拨入式会议要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 944aaf06ce81e5ba326841f6abe91614cdffd134
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498909"
---
# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 中的电话拨入式会议要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

在启动 Lync Server 2013 部署过程之前，您需要规划以下各项：

  - 连接到公用电话交换网 (PSTN) 时使用的配置

  - 为拨入访问号码分配电话拨入式会议区域的策略

  - 创建会议目录的策略

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>规划拨入 PSTN 连接

电话拨入式会议要求至少一个中介服务器和至少一个 PSTN 网关。

您可以在中央站点或分支站点中部署中介服务器。 在中央站点中，您可以在前端池或 Standard Edition 服务器上并置中介服务器，也可以将其部署在独立服务器或池上。 在分支站点中，可以在独立服务器上部署中介服务器，也可以将其部署为 Survivable 分支设备的组件。

您可以在中央站点或分支站点部署 PSTN 网关。 在分支站点中，PSTN 网关可以是独立的，也可以是 Survivable 分支设备的组件。

<div>


> [!NOTE]  
> 由于 A/V 会议服务器不支持媒体旁路，电话拨入式会议不会使用媒体旁路。



</div>

有关规划用于电话拨入式会议的中介服务器和 PSTN 网关的配置的详细信息，请参阅规划文档中的 " [在 Lync server 2013 中的中介服务器的组件和拓扑](lync-server-2013-components-and-topologies-for-mediation-server.md) "。

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>规划电话拨入式会议区域

在拨入配置过程中，创建拨号计划和电话拨入式会议访问号码。拨号计划是几组规范化规则，用来指定电话号码的数字和数字模式，并将电话号码转换为标准 E.164 格式以进行呼叫路由。电话拨入式会议访问号码是参与者为加入会议而呼叫的号码。

每个电话拨入式会议访问号码必须至少与一个拨号计划关联。电话拨入式会议区域会将电话拨入式会议访问号码与其拨号计划相关联。设置拨号计划时，指定应用于该拨号计划的电话拨入式会议区域。在创建拨入访问号码时，选择将该访问号码与相应拨号计划关联的区域。

创建拨号计划时，指定拨号计划的作用域：用户作用域、池作用域或站点作用域。会按照各用户适用的最小作用域为其分配拨号计划。例如，如果适用，则为用户分配用户级别的拨号计划。如果用户级别的拨号计划不适用，则为用户分配池级别的拨号计划。如果池级别的拨号计划不适用，则为用户分配站点级别的拨号计划。如果站点级别的拨号计划不适用，则为用户分配全局拨号计划。

配置拨号计划之前，规划命名和使用区域的方式非常重要。对于电话拨入式会议区域，请注意下列事项：

  - 区域通常是与某个办公室或一组办公室相关联的地理区域。

  - 语言与拨入访问号码相关联。如果支持具有多种语言的地理区域，应该决定如何定义区域以便支持多种语言。例如，可以基于地理位置和语言的组合定义多个区域，或者基于地理位置定义一个区域，且每种语言拥有不同的拨入访问号码。

  - 用户安排会议时，默认情况下会议将使用用户的拨号计划所指定的区域。

  - 默认情况下，区域的所有拨入访问号码都会包含在会议邀请中。

  - 命名区域以使其清楚识别，这一点非常重要。 用户可以使用区域名称更改会议的区域，以便在邀请中包含不同的访问号码。  (当用户使用 Outlook 安排会议时，用户使用 Lync 2013 的联机会议外接程序更改区域) 。

  - 应该对区域加以设计，以便想要拨入会议的被邀请者可以在会议邀请中看到本地访问号码。

  - 您可以配置区域中的访问号码在 "电话拨入式会议设置" 页上的显示顺序 (，因此，它们在会议邀请中的显示顺序) 通过使用 Lync Server 命令行管理程序 cmdlet。

  - 任何位置的任何用户均可拨打拨入访问号码来加入会议。

</div>

<div>

## <a name="planning-for-conference-directories"></a>规划会议目录

会议目录维护参与者在使用 Lync 2013 时用于加入会议的字母数字会议 ID 之间的映射，以及电话拨入式会议参与者用于加入会议的仅数字会议 ID。 会议 ID 的格式如下：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。通过使用此指南，通常可使会议 ID 保持较小数目。但是，一旦会议目录的数目（在池中）超过 9，则会议 ID 号将增大以支持其他会议。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)  
[Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

