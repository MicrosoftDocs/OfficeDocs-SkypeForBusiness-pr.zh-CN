---
title: Lync Server 2013：查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序
TOCTitle: 查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182575(v=OCS.15)
ms:contentKeyID: 49314029
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序

 

_**上一次修改主题：** 2014-09-26_

Microsoft SIP 处理语言 (MSPL) 服务器应用程序是一种只包含脚本的应用程序，它使用脚本语言而不是 Microsoft Lync 2010 API。除提供将特定消息分派到基于事务的 SIP 应用程序的工具之外，MSPL 还提供了对筛选和代理行为的更精细控制。MSPL 专门用于筛选和路由 SIP 消息。MSPL 应用程序与 UserServices 模块在相同的进程中运行，而基于 Lync 2010 API 的程序则在另外的进程中运行。

可以使用 Lync Server 控制面板的“拓扑”组中的“服务器应用程序”页查看在 Lync Server 2013 环境中的前端服务器上运行的 MSPL 服务器应用程序列表。列表显示了可供每个池使用的脚本，以及它们是否处于已启用或关键状态。脚本按照所列的顺序运行。

这些脚本包括：

  - ClientVersionFilter，可供管理员用来指定某个池所支持的客户端版本。客户端版本筛选器检查客户端版本，并可以阻止客户端登录或向用户显示一个消息，指出他（或她）所使用的客户端不受支持。还可以对客户端版本筛选器进行配置，向用户显示包含客户端的最新可下载版本的 URL 的消息。

  - TranslationService，根据管理员定义的规范化规则将用户拨打的号码转换为一个 E.164 号码。有关详细信息，请参阅 [Lync Server 2013 中的转换规则](lync-server-2013-translation-rules.md)。

  - IncomingFederation 用于对从外部部署传入的租户间的消息强制执行租户级别的联盟验证。

  - UserServices 是前端服务器的 SIP 注册器、状态指示和会议组件。它提供构建于 SIP 代理之上、紧密集成的 IM、状态指示和会议功能。

  - InterClusterRouting 负责将呼叫路由至被叫方的主注册器池。有关详细信息，请参阅 [Lync Server 2013 的前端服务器 VoIP 组件](lync-server-2013-front-end-server-voip-components.md)。

  - IIMFilter（智能 IM 筛选器）阻止包含可单击的 URL 的消息，或阻止尝试启动文件传输的消息。IIMFilter 还代表服务器检查客户端版本。IIMFilter 可影响使用 Lync Server 或 Communicator 启动的文件传输。默认情况下，在可单击链接的第一个字符之前添加一个下划线可以禁用该链接。管理员可以更改此行为以阻止该链接，此时，包含可单击的 URL 的消息或尝试启动文件传输的消息将被服务器阻止，无法到达预定的目的地。IIMFilter 安装在除代理服务器和存档服务器以外运行 Lync Server 的所有服务器上。

  - UserPinService 用于验证电话拨入式会议的用户个人标识号 (PIN)。

  - DefaultRouting 是运行 Lync Server 的服务器的默认路由应用程序。默认情况下处于启用状态。该路由应用程序安装在所有 Standard Edition Server 和 Enterprise Edition Server 上。

  - ExumRouting 将呼叫路由到 Exchange Server 统一消息 (UM)。当有新的语音邮件需要处理时，ExumRouting 会确定要将呼叫路由到的相应 Exchange UM 服务器。ExumRouting 还会处理 Exchange UM 集成的其他一些方面，包括路由到自动助理和订阅者访问。

  - OutboundRouting 根据拨打的电话号码和用户的拨号权限来确定路由对该号码的呼叫的网关。如果网关无法处理呼叫，OutboundRouting 还会处理呼叫的重新路由。

  - QoEAgent 通过 SIP SERVICE 请求接收来自终结点的用户体验质量 (QoE) 数据报告，并通过 HTTP POST 将数据发送至监控服务器上的目标队列或第三方使用者。有关详细信息，请参阅 [部署监控](lync-server-2013-deploying-monitoring.md)。

  - OutgoingFederation 可对发送外部目标部署的消息强制执行租户级别的联盟验证。

  - AcpRouting 可将发往音频会议提供商的 INVITE 请求代理到音频会议提供商网关。

在边缘服务器上运行的脚本包括：

  - IIMFilter

  - OptionsHandler 可在包含 **200 OK** 的传入 OPTIONS 请求发往当前服务器时对其进行响应。这可以用于验证拓扑。

## 另请参阅

#### 任务

[启用或禁用 Microsoft SIP 处理语言 (MSPL) 服务器应用程序](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[将 Microsoft SIP 处理语言 (MSPL) 应用程序标记为关键或非关键](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)

