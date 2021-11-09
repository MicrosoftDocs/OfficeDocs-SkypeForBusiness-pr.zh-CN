---
title: Skype for Business Server 2015 压力和性能工具的常见问题解答
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 压力和性能工具常见问题 (FAQ) ，有助于找出受支持的工具配置、解决工具问题以及阐明在运行压力和性能工具时可能看到的行为。
ms.openlocfilehash: fb81d31711b027d58b8d5b97ecd6d14f32c0fa0f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857289"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 压力和性能工具的常见问题解答
 
Skype for Business 2015 压力和性能工具常见问题 (FAQ) ，有助于找出受支持的工具配置、解决工具问题以及阐明在运行压力和性能工具时可能看到的行为。
  
 此常见问题解答涵盖有关 Skype for Business Server 2015 压力和性能工具的一些最常见的问题，并且有助于进行故障排除和工具配置选择。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>能否在生产LyncPerfTool.exe运行应用程序？

不建议 **这样做** 。 该工具会影响生产服务器的性能、安全性和最终用户体验。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>我第一次登录我的用户。 为什么我的服务器运行高负载？

用户第一次登录时，将在后台执行其他操作。 因此，后端服务器上Microsoft SQL Server性能可能会下降。 建议您运行一个对所有用户进行登录的简短测试，然后重新启动客户端，然后再开始使用该工具测量结果。 Skype for Business Server每秒支持 12 个并发用户登录会话，但请注意服务器可以处理的实际数量取决于硬件配置，并且可能低于支持的值。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的客户端内存不足！ 我该怎么办？

如果客户端内存不足，您应该减少每个前端池Skype for Business Server用户数。 如果问题是永久性的，还可以选择扩展前端池。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>能否在服务器本身上Skype for Business此工具？

不应这样做。 不支持此方案，因为它可能由于二进制不匹配而失败，还因为目标是测量服务器上资源消耗。 实际运行该工具会影响服务器性能，并且会使数据和度量失效。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>我能否在虚拟LyncPerfTool.exe或 Microsoft Hyper-V Server 2008/2012 上运行应用程序？

可以。
  
## <a name="what-does-mpop-mean"></a>MPOP 意味着什么？

MPOP 是一种表示"多点状态"的缩短方式。 MPOP 旨在模拟用户从多台计算机或设备登录到 Skype for Business 2015 客户端的方案。 请注意，在LyncPerfTool.exe，每个终结点都使用默认配置文件。 换句话说，配置文件不会在两个状态点之间拆分。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我LyncPerfTool.exe，但没有任何变化。 What's going on?

检查服务器上总活动终结点计数器以查看用户是否正在连接。 如果用户未连接，请验证您的 Skype for Business Server 2015 配置。 您看到的问题通常是因为服务器名称、用户前缀或密码之一不正确。 请注意，外部客户端应指定 Access Proxy 和 TargetServer 值。 验证配置文件中的端口号。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>如何确保正在测量某些内容？

LyncPerfTool 性能计数器可指示用户是否正在连接和操作，但确保测量操作的最简单方法是使用 Skype for Business 2015 客户端登录到其中一个帐户，然后自己执行这些操作。 检查结果以确认已进行测量。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>我安装了 Lync Server 2010 容量规划工具和/或 Lync Server 2013 容量规划工具。 可以吗？

 这些工具有互操作性问题！ 您必须卸载这些工具的所有以前版本，才能从 Skype for Business Server 2015 Stress and Performance 工具获取有效数据。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>压力和性能工具将设置 CAA 呼叫信息服务器拓扑吗？

不，工具不会这样做。 这些工具仅创建用户、联系人和通讯组列表，以模拟用户负载。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支持的最大用户数是什么？

在测试中，我们创建了多达 80，000 个用户，并执行了总计 30，000 个用户运行这些工具的测试。 我们建议最多 120，000 个用户，尽管技术限制允许更高的值。 请记住，这些值取决于您的环境中的服务器和硬件。
  

