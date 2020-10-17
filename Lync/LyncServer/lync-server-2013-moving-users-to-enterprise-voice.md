---
title: Lync Server 2013：将用户移动到企业语音
description: Lync Server 2013：将用户移动到企业语音。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b075f916f4d81d8d3c24c24c7393be58e10a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542008"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>将用户移动到 Lync Server 2013 中的企业语音

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

如果要将用户从现有的 PBX 电话基础结构移动到企业语音，则部署过程包括一些步骤，这些步骤不是在 [Lync Server 2013 中规划企业语音中](lync-server-2013-planning-for-enterprise-voice.md)已介绍的规划过程的一部分。 有关从早期的企业语音部署迁移用户的信息，请参阅安装介质中包含的迁移文档。

将用户从现有的电话基础结构迁移到企业语音的过程包含以下步骤：

1.  指定主要电话号码。

2.  为用户启用企业语音。

3.  为用户准备拨号计划。

4.  规划用户语音策略。

5.  规划呼叫路由。

6.  将 PBX 或 SIP 中继配置为对启用了企业语音的用户重新路由呼叫。

7.  将用户移动到 Exchange 统一消息 (UM)  (建议的) 。

本主题介绍上述每个步骤所必需的规划。

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>步骤 1. 指定主要电话号码

企业语音将语音与其他消息传递媒体集成在一起，这样，当传入呼叫到达服务器时，服务器会将该号码映射到用户的 SIP-URI，然后将该呼叫定向到与该 SIP-URI 相关联的所有客户端终结点。此过程要求每个用户都与一个主要电话号码相关联。

主要电话号码必须满足以下条件：

  - 全局唯一，如果是内部分机，则必须在企业中保持唯一。

  - 由企业拥有且可路由。不应当使用个人号码。

企业用户可以在 Active Directory 域服务中为其列出两个或更多的电话号码。 与特定用户相关联的所有电话号码都可以在“Active Directory 用户和计算机”管理单元中该用户的属性表中进行查看或更改。

**“用户属性”** 对话框的 **“常规”** 选项卡上的 **“电话号码”** 框应当包含该用户的主要单位号码。此号码通常被指定为该用户的主要电话号码。

某些用户可能会有特殊要求（例如，主管经理希望所有的传入呼叫都通过行政助理路由），但是这样的例外应当仅限于有明确需求的关键人员。

选择了主要号码之后，必须将它：

  - 规范化为 E.164 格式（只要可能）。

  - 复制到 Active Directory **msRTCSIP-line** 属性。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>与远程呼叫控制 (RCC) 共存</STRONG><BR>RCC 是一种使用 Lync Server 监视和控制桌面 PBX 电话的功能。 远程呼叫控制是通过充当 PBX 网关的服务器路由的。 尽管无法同时为用户配置 RCC 和企业语音，但线路 URL 设置在任一情况下都会指定用户的主要电话号码。<BR>如果希望选定用户继续使用现有的 PBX 基础结构，则可在组织中逐步引入企业语音。 有关此部署方案的详细信息，请参阅规划文档中的 <A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013 中的直接 SIP 部署选项</A> 。<BR>在以前的版本中，您可以为用户启用 RCC 和企业语音，但前提是您还为用户配置了双分叉，即传入呼叫将同时拨打用户的 PBX 电话和 Communicator 的功能。 在 Lync Server 2010 中，不支持双重分叉。

    
    </div>

可通过三种方法来填充 **msRTCSIP-line** 属性：

  - Microsoft 身份集成服务器（推荐）

  - Lync Server "控制面板" 中的 " **用户** " 页

在必须处理多少个电话号码的情况下，由您的组织开发的脚本自定义是更好的选择。 根据您所在组织在 Active Directory 域服务中表示电话号码的方式，脚本可能必须先将主要电话号码规范化为 E.164 格式，然后再将这些号码复制到 **msRTCSIP-line** 属性。

  - 如果您所在组织保持 Active Directory 域服务中的所有电话号码都采用一种格式，而且如果该格式为 E.164，则脚本只需要将每个主要电话号码写入 **msRTCSIP-line** 属性。

  - 如果您所在组织保持 Active Directory 域服务中的所有电话号码都采用一种格式，但该格式不是 E.164，则脚本应当定义一个相应的规范化规则，先将主要电话号码从其现有格式转换为 E.164，然后再将这些号码写入 **msRTCSIP-line** 属性。

  - 如果您所在组织不强制 Active Directory 域服务中的电话号码采用标准格式，则脚本应当定义相应的规范化规则，先将主要电话号码从其各自格式转换为符合 E.164 的格式，然后再将这些主要电话号码写入 **msRTCSIP-line** 属性。

脚本还必须先在每个主要电话号码前面插入前缀 **Tel:**，然后再将这些主要电话号码写入 **msRTCSIP-line** 属性。

在此属性中指定的号码格式应当如下所示：

  - 电话： + 14255550100; ext = 50100。

  - Tel:5550100（对于企业范围内唯一的分机）
    
    <div>
    

    > [!IMPORTANT]  
    > 即使由通讯簿服务 (ABS) 执行规范化之后，也需要对 Active Directory 域服务中每个用户的主要电话号码进行规范化，这是由于 ABS 无权访问 Active Directory 域服务，因此无法将主要号码复制到 <STRONG>msRTCSIP-line</STRONG> 属性。

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>步骤 2. 为用户启用企业语音

除了标识要启用的用户，无需进行其他特殊规划即可完成此步骤。

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>步骤 3. 为用户准备拨号计划。

已启用企业语音的用户在没有拨号计划的情况下将无法向 PSTN 发起呼叫。拨号计划是一组指定的规范化规则，可将指定位置、单个用户或联系人对象的电话号码转换为统一标准 (E.164) 格式，以进行电话授权和呼叫路由。规范化规则定义如何针对每个指定的位置、用户或联系人对象来路由以不同格式表示的电话号码。

有关准备拨号计划的信息，请参阅 [Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)。

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>步骤 4. 规划用户语音策略

随着用户的 VoIP 策略迁移到企业语音，必须重新配置旧版 PBX 上的用户服务级别设置（如从公司电话拨打长途或国际长途电话的权限）。 有关规划和创建企业语音策略的详细信息，请参阅 [Lync Server 2013 中的语音策略](lync-server-2013-voice-policies.md)。

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>步骤 5. 规划出站呼叫路由

呼叫路由指定 Lync Server 如何处理由企业语音用户发出的出站呼叫。 当用户拨打号码时，服务器在必要时将拨号串规范为 E.164 格式，并尝试将它与 SIP URI 进行匹配。 如果服务器无法进行匹配，它将基于该号码应用传出呼叫路由逻辑。 定义该逻辑的最后一步是为每个拨号计划中所列出的每组目标电话号码创建单独的命名呼叫路由。

有关规划呼叫路由的详细信息，请参阅 [Lync Server 2013 中的语音路由](lync-server-2013-voice-routes.md)。

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>步骤 6. 将 PBX 或 SIP 中继配置为重新路由企业语音用户的呼叫

迁移之后，以前在传统 PBX 或到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接上承载的用户仍保留其电话号码。 唯一要求是移动后，必须重新配置 PBX 或 SIP 中继，才能将企业语音用户的传入呼叫路由到中介服务器。

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>步骤 7. 将用户迁移到 Exchange 统一消息（推荐）

将用户迁移到 Exchange 统一消息包括以下任务：

  - 将 Exchange 统一消息和 Lync Server 配置为协同工作。

  - 为用户启用 Exchange 统一消息呼叫应答和 Outlook Voice Access。 此任务在 Exchange 统一消息服务器上执行。 有关详细信息，请参阅 Exchange Server 2010 TechNet Library （网址为） [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

