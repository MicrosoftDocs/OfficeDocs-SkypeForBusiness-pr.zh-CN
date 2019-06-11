---
title: Lync Server 2013：将用户迁移至企业语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1127bd0c767da7f02df8aefb30fda41a64bd353a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中将用户迁移至企业语音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-18_

如果您要将用户从现有 PBX 电话基础结构移动到企业语音, 则部署过程包括某些步骤, 这些步骤不属于[Lync Server 2013 中的 "规划企业语音](lync-server-2013-planning-for-enterprise-voice.md)" 中已描述的规划过程。 有关从早期的企业语音部署迁移用户的信息, 请参阅安装媒体附带的迁移文档。

将用户从现有的电话基础结构移动到企业语音的过程包括以下步骤:

1.  指定主要电话号码。

2.  为用户启用企业语音。

3.  为用户准备拨号计划。

4.  规划用户语音策略。

5.  计划呼叫流程。

6.  将 PBX 或 SIP 干线配置为对启用企业语音的用户重新路由呼叫。

7.  将用户移动到 Exchange 统一消息 (UM) (推荐)。

本主题介绍每个步骤所需的规划。

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>第 1 步 指定主要电话号码

企业语音与其他邮件媒体集成语音, 这样, 当传入呼叫到达服务器时, 服务器会将该号码映射到用户的 SIP URI, 然后将该呼叫派生到与该 SIP URI 关联的所有客户终结点。 此过程要求每个用户都与一个主要电话号码相关联。

主要电话号码必须:

  - 全球唯一的或在内部扩展的情况下, 企业中的独特之处。

  - 企业中拥有和可路由的。 不应使用个人号码。

企业用户可以在 Active Directory 域服务中为其列出两个或多个电话号码。 在 Active Directory 用户和计算机管理单元中, 可以在该用户的属性表上查看或更改与特定用户相关联的所有电话号码。

"**用户属性**" 对话框的 "**常规**" 选项卡上的 "**电话号码**" 框应包含用户的主工作电话号码。 此号码通常指定为用户的主要电话号码。

某些用户可能有特殊要求 (例如, 希望所有传入呼叫通过行政助理进行路由的管理者), 但此类例外仅限于需要明确且关键的用户。

选择主号码后, 它必须:

  - 尽可能规范化为. 164 格式。

  - 已复制到 Active Directory **msRTCSIP line**属性。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>与远程呼叫控制 (RCC) 共存</STRONG><BR>RCC 是使用 Lync Server 监控和控制桌面 PBX 电话的功能。 控制通过服务器路由, 它充当 PBX 的网关。 尽管不能同时为 RCC 和企业语音配置用户, 但行 URI 设置会在任何一种情况下都指定用户的主要电话号码。<BR>如果你有一个现有的 PBX 基础结构, 而你希望选择用户继续使用, 则可以在你的组织中以增量方式引入企业语音。 有关此部署方案的详细信息, 请参阅规划文档中<A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013 中的直接 SIP 部署选项</A>。<BR>在以前的版本中, 你可以为用户启用 RCC 和企业语音, 但仅当你还为双重呼叫配置了用户时, 传入呼叫将同时拨打用户的 PBX 手机和 Communicator。 在 Lync Server 2010 中, 不支持双分叉。

    
    </div>

填充**msRTCSIP**属性有三种方法:

  - Microsoft 身份集成服务器 (推荐)

  - Lync Server "控制面板" 中的 "**用户**" 页面

必须处理多个电话号码时, 由您的组织制定的脚本自定义是更好的选择。 根据您的组织如何表示 Active Directory 域服务中的电话号码, 该脚本可能必须先将主要电话号码正常化为164个格式, 然后才能将其复制到**msRTCSIP**属性。

  - 如果你的组织以单个格式维护 Active Directory 域服务中的所有电话号码, 并且如果该格式为 E.i, 则你的脚本只需要将每个主要电话号码写入**msRTCSIP**属性。

  - 如果你的组织以单个格式维护 Active Directory 域服务中的所有电话号码, 但该格式不是 E.i, 则你的脚本应定义适当的规范化规则以将主要电话号码转换为其现有格式先发送到 164, 然后再将其写入**msRTCSIP**属性。

  - 如果你的组织未对 Active Directory 域服务中的电话号码强制使用标准格式, 你的脚本应定义适当的规范化规则, 以便将主要电话号码从其各种格式转换为 E。先遵守164将主要电话号码写入**msRTCSIP**属性。

你的脚本还必须插入前缀**电话:** 在每个主号码之前, 将其写入**msRTCSIP**属性。

此属性中指定的数字的预期格式为:

  - 电话: + 14255550100; ext = 50100。

  - 电话: 5550100 (适用于唯一的企业级扩展)
    
    <div>
    

    > [!IMPORTANT]  
    > 由通讯簿服务 (ABS) 执行的规范化不替换或消除了在 Active Directory 域服务中对每个用户的主要电话号码进行规范化的需要, 因为 ABS 无权访问 Active Directory 域服务和因此, 不能将主号码复制到<STRONG>msRTCSIP</STRONG>属性。

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>第 2 步 为用户启用企业语音

除了确定要启用哪些用户之外, 不需要特殊计划来完成此步骤。

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>第 3 步 为用户准备拨号计划。

已启用企业语音的用户将无法在没有拨号计划的情况下拨打 PSTN。 拨号计划是一组指定的规范化规则，可将指定位置、单个用户或联系人对象的电话号码转换为统一标准 (E.164) 格式，以进行电话授权和呼叫路由。 规范化规则定义如何针对每个指定的位置、用户或联系人对象来路由以不同格式表示的电话号码。

有关准备拨号计划的信息, 请参阅[Lync Server 2013 中的 "拨号计划和规范规则](lync-server-2013-dial-plans-and-normalization-rules.md)"。

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>第 4 步 规划用户语音策略

在旧式 PBX (如从公司电话进行长途或国际长途) 的用户级服务设置必须重新配置为将用户移动到企业语音的 VoIP 策略。 有关为企业语音规划和创建策略的详细信息, 请参阅[Lync Server 2013 中的语音策略](lync-server-2013-voice-policies.md)。

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>第 5 步 规划出站呼叫流程

呼叫路线指定 Lync 服务器如何处理由企业语音用户发出的出站呼叫。 当用户拨号码时, 服务器 (如有必要) 会将拨号字符串标准化为164格式, 并尝试将其与 SIP URI 匹配。 如果服务器无法进行匹配, 它将基于该号码应用传出呼叫路由逻辑。 定义该逻辑的最后一步是为每个拨号计划中列出的每组目标电话号码创建单独的命名呼叫路由。

有关规划呼叫路由的详细信息, 请参阅[Lync Server 2013 中的语音路由](lync-server-2013-voice-routes.md)。

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>第 6 步 配置 PBX 或 SIP 干线以重排企业语音用户的呼叫

以前托管于传统 PBX 或在与 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接上的用户在移动后保留其电话号码。 唯一的要求是在移动后, 必须重新配置 PBX 或 SIP 干线, 才能将企业语音用户的传入呼叫路由到中介服务器。

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>第 7 步 将用户移动到 Exchange 统一消息 (推荐)

将用户移动到 Exchange 统一消息包含以下任务:

  - 将 Exchange 统一消息和 Lync 服务器配置为协同工作。

  - 为用户启用 Exchange 统一消息呼叫应答和 Outlook Voice Access。 此任务在 Exchange 统一消息服务器上执行。 有关详细信息, 请参阅 Exchange Server 2010 中的[http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)"TechNet 库"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

