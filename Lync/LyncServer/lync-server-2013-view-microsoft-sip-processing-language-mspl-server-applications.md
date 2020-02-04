---
title: 查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-09-26_

Microsoft SIP 处理语言（MSPL）服务器应用程序是一个仅脚本的应用程序，该应用程序使用脚本语言而不是 Microsoft Lync 2010 API。 MSPL 提供对筛选和代理行为的更精细的控制，以及用于向基于事务的 SIP 应用程序调度特定消息的功能。 MSPL 专门用于筛选和路由 SIP 消息。 MSPL 应用程序在与 UserServices 模块相同的进程中运行，而基于 Lync 2010 API 的程序在单独的进程中运行。

你可以使用 Lync Server 控制面板的 "**拓扑**" 组中的 "**服务器应用程序**" 页面查看在 Lync server 2013 环境中的前端服务器上运行的 MSPL 服务器应用程序的列表。 该列表显示了每个池可用的脚本以及它们是否已启用或关键。 脚本将按照它们列出的顺序运行。

这些脚本包括以下内容：

  - ClientVersionFilter 向管理员提供一种方法来指定池支持的客户端版本。 客户端版本筛选器检查客户端版本，并可阻止客户端登录或向用户显示一条消息，指示用户正在使用不受支持的客户端。 客户端版本筛选器还可以配置为向用户显示一条消息，其中包含最新可下载版本的客户端的 URL。

  - TranslationService 将根据管理员定义的规范化规则转换用户拨打的电子号码为164的数字。 有关详细信息，请参阅[Lync Server 2013 中的翻译规则](lync-server-2013-translation-rules.md)。

  - IncomingFederation 强制实施租户级联合身份验证，用于租户内部部署和来自外部部署的传入消息。

  - UserServices 是前端服务器的 SIP 注册机构、状态和会议组件。 它提供了在 SIP 代理的基础上构建的紧密集成的 IM、状态和会议功能。

  - InterClusterRouting 负责将呼叫路由到被调用方的主注册池。 有关详细信息，请参阅[Lync server 2013 的前端服务器 VoIP 组件](lync-server-2013-front-end-server-voip-components.md)。

  - IIMFilter （智能 IM 筛选器）阻止包含可单击的 Url 或尝试启动文件传输的邮件。 IIMFilter 还会代表服务器检查客户端版本。 IIMFilter 影响通过使用 Lync Server 或 Communicator 启动的文件传输。 默认情况下，通过在链接的第一个字符前面添加一个下划线字符来禁用可点击的链接。 管理员可以更改此行为，以便阻止链接，在这种情况下，包含可单击的 Url 的邮件或尝试启动文件传输的邮件将被服务器阻止到达其预定目的地。 IIMFilter 安装在代理服务器和存档服务器以外的所有运行 Lync Server 的服务器上。

  - UserPinService 用于验证电话拨入式会议的用户个人识别码（Pin）。

  - DefaultRouting 是运行 Lync Server 的服务器的默认路由应用程序。 默认情况下，它处于启用状态。 路由应用程序安装在所有标准版和企业版服务器上。

  - ExumRouting 路由到 Exchange Server 统一消息（UM）的呼叫。 ExumRouting 确定要放入新的语音邮件时将呼叫路由到的相应 Exchange UM 服务器。 ExumRouting 还处理其他一些 Exchange UM 集成方面，包括路由到自动助理和订阅者访问。

  - OutboundRouting 确定根据所拨号码和用户的拨号授权将呼叫路由到电话号码的网关。 如果网关无法处理呼叫，OutboundRouting 还会处理呼叫的重新路由。

  - QoEAgent 通过 SIP 服务请求从终结点接收数据报表质量（QoE），并使用 HTTP POST 将数据发送到监视服务器或第三方使用者的目标队列。 有关详细信息，请参阅[在 Lync Server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)。

  - OutgoingFederation 将为转到目标外部部署的邮件强制执行租户级别的联合身份验证验证。

  - AcpRouting 代理将邀请音频会议提供商的请求发送到音频会议提供商网关。

在边缘服务器上运行的脚本包括以下内容：

  - IIMFilter

  - OptionsHandler 响应传入选项请求200如果请求是当前服务器的目标，则为**OK** 。 这用于拓扑验证。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[在 Lync Server 2013 中将 Microsoft SIP 处理语言（MSPL）应用程序标记为关键或非关键应用程序](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

