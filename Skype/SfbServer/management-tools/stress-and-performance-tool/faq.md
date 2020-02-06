---
title: Skype for Business Server 2015 的常见问题应力和性能工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 应力和性能工具常见问题（FAQ），用于找出支持哪些工具配置、疑难解答工具问题，并阐明在运行压力和性能工具时可能会看到的 behaviours.
ms.openlocfilehash: 2847ecd54389f64d6961cc72ecb94d87e847b0b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816181"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 的常见问题应力和性能工具
 
Skype for Business 2015 应力和性能工具常见问题（FAQ），用于找出支持哪些工具配置、疑难解答工具问题，并阐明在运行压力和性能工具时可能会看到的 behaviours.
  
 本常见问题解答介绍了有关 Skype for Business Server 2015 应力和性能工具的一些最常见问题，并且可能会帮助你解决问题和工具配置选择。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>是否可以在生产中运行 LyncPerfTool？

建议**不要**这样做。 该工具将影响生产服务器性能、安全性和最终用户体验。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>我是首次登录我的用户。 为什么我的服务器运行的负载很高？

用户首次登录时，会在后台执行其他操作。 因此，Microsoft SQL Server 后端服务器上的性能可能会降级。 建议你先运行一个简短测试，该测试将在你的所有用户上登录，然后重新启动客户端，然后再开始使用该工具测量结果。 Skype for Business Server 不支持每秒并发用户登录会话的次数超过12个，但请注意，你的服务器可以处理的实际数字取决于你的硬件配置，并且可能低于支持的值。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的客户的内存不足！ 我该怎么办？

如果客户端内存不足，您应该减少每个 Skype for business 服务器前端池登录的用户数。 如果问题持续存在，还可以选择缩小前端池。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>是否可以在 Skype for Business 服务器上运行此工具？

不应执行此操作。 此方案不受支持，因为它可能会因二进制不匹配而失败，也可能是因为目标是测量服务器上的资源占用。 实际运行工具会影响服务器性能并使你的数据和度量无效。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>我是否可以在虚拟服务器或 Microsoft Hyper-v Server 2008/2012 上运行 LyncPerfTool？

是的，可以。
  
## <a name="what-does-mpop-mean"></a>MPOP 的含义是什么？

MPOP 是说出 "多个状态点" 的简写方式。 MPOP 旨在模拟用户从多台计算机或设备登录到 Skype for Business 2015 客户端的方案。 请注意，在 LyncPerfTool 中，每个终结点都使用默认配置文件。 换句话说，配置文件不会在两个状态点之间拆分。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我启动了 LyncPerfTool，但没有发生任何事情。 这是怎么回事？

检查服务器上的 "活动终结点总数" 计数器以查看用户是否连接。 如果用户未连接，请验证您的 Skype for business Server 2015 配置。 由于其中一个服务器名称、用户前缀或密码不正确，因此你所看到的问题通常会出现。 请注意，外部客户端应指定访问代理服务器和 TargetServer 值。 验证配置文件中的端口号。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>如何确定正在测量的内容？

有 LyncPerfTool 性能计数器可指示用户是否连接和执行操作，但确保操作的最简单方法是使用 Skype for Business 2015 客户端登录到其中一个帐户，并执行这些操作行动。 检查结果以确认已采取度量。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>我已安装 Lync Server 2010 容量规划工具和/或 Lync Server 2013 容量规划工具。 这好吗？

 这些工具具有互操作性问题！ 你必须卸载这些工具的所有早期版本才能从 Skype for Business Server 2015 应力和性能工具获取有效数据。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>压力和性能工具是否会设置 CAA 呼叫信息服务器拓扑？

否，工具不会执行此操作。 工具仅创建用户、联系人和通讯组列表，以模拟用户负载。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支持的最大用户数是多少？

在测试中，我们最多可创建80000个用户和执行的测试，这些测试将运行这些工具的30000用户总计。 我们建议最多120000用户，尽管技术限制允许使用更高的值。 请记住，这些值取决于环境中的服务器和硬件。
  

