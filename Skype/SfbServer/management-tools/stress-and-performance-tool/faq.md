---
title: 为业务服务器 2015年压力和性能工具 Skype 常见问题
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype 的业务 2015年压力和性能工具： 常见问题 (FAQ)，用于查找支持哪些工具配置、 疑难解答工具问题并阐明时运行压力和性能工具可能会看到的行为.
ms.openlocfilehash: 604644d5aecb12f94304d1c7ce271c68208e1964
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906744"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>为业务服务器 2015年压力和性能工具 Skype 常见问题
 
Skype 的业务 2015年压力和性能工具： 常见问题 (FAQ)，用于查找支持哪些工具配置、 疑难解答工具问题并阐明时运行压力和性能工具可能会看到的行为.
  
 本常见问题解答介绍一些有关 Business Server 2015 压力和性能工具 Skype 的最常见问题，可帮助具有疑难解答和工具的配置选项。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>可以在生产中运行 LyncPerfTool.exe？

这**不**建议使用。 该工具将影响您的生产服务器性能、 安全性和最终用户体验。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>我正在登录第一次的我的用户。 为什么我服务器正在运行的高负载

第一次用户登录时，在后台发生其他操作。 因此，可以降低 Microsoft SQL Server 后端服务器上的性能。 建议您的用户，所有运行小测验的日志，然后开始测量结果使用工具之前重新启动客户端。 Skype 业务服务器不支持超过 12 并发用户登录会话 / 秒，但请注意您的服务器可以处理的实际数目取决于您的硬件配置，并且可能低于受支持的值。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的客户端内存不足运行 ！ 应该怎样做？

如果客户端运行的内存不足，您应减少每 Skype 业务 Server 前端池记录的用户数。 您还可以选择扩展注销前端池，如果问题是持久。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>可以运行此工具在业务服务器 Skype 本身？

不应执行的操作。 此方案中不受支持，因为由于二进制不匹配，则可能会失败，也因为的目标是以测量的服务器上的资源消耗。 实际上那里运行该工具将影响服务器性能，并使您的数据和度量值无效。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>在虚拟服务器或 Microsoft HYPER-V Server 2008/2012 上是否可以运行 LyncPerfTool.exe？

您可以是。
  
## <a name="what-does-mpop-mean"></a>MPOP 是什么意思？

MPOP 缩短的像是说"多点状态"。 MPOP 旨在模拟其中用户登录到 Skype for Business 2015 客户端从多个计算机或设备的方案。 请注意，在 LyncPerfTool.exe，每个终结点使用的默认配置文件。 换句话说，该配置文件不是两个状态点之间拆分。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我启动 LyncPerfTool.exe 但不是会变化。 这是怎么回事？

检查以查看在用户连接的服务器上的活动终结点总数计数器。 如果用户不连接，请确认您 Skype 业务服务器 2015年配置。 问题您看到了通常发生的原因之一服务器名称、 用户前缀或密码不正确。 记下外部客户端应指定访问代理服务器和目标值。 验证配置文件中的端口号。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>如何确保内容正在衡量？

有 LyncPerfTool 性能计数器来指示用户连接和执行操作，但请确保正在度量操作的最简单方式是以登录到一个具有业务 2015年客户端 Skype 帐户并执行这些操作操作自己。 检查的结果，以确认度量做。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>我已安装的 Lync Server 2010 容量规划工具和/或 Lync Server 2013 容量规划工具。 是的正常？

 这些工具具有互操作性问题 ！ 您必须先卸载所有以前版本的这些工具从业务 Server 2015 压力 Skype 获取有效的数据和性能工具。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>压力和性能工具将设置 CAA 呼叫信息服务器拓扑结构？

否，工具不会执行此操作。 工具仅创建用户、 联系人和通讯组列表，以模拟用户负载。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支持的用户的最大号码是什么？

在测试中，我们已创建 80,000 用户总共和执行测试约 30,000 运行这些工具的用户。 我们建议最多 120,000 用户，尽管技术限制允许较高的值。 请记住这些值依赖的服务器和您的环境中的硬件。
  

