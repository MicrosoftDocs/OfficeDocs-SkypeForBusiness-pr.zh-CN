---
title: 为业务服务器 2015年的压力和性能工具 Skype 的常见问题解答
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype 业务 2015年压力和性能工具的常见问题 (FAQ)，用于找出支持哪些工具配置、 故障排除工具的问题，以及澄清运行压力和性能工具时可能看到的行为.
ms.openlocfilehash: 730f9620e4aa498df26cc24f3c17ea1bd2ad7d5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>为业务服务器 2015年的压力和性能工具 Skype 的常见问题解答
 
Skype 业务 2015年压力和性能工具的常见问题 (FAQ)，用于找出支持哪些工具配置、 故障排除工具的问题，以及澄清运行压力和性能工具时可能看到的行为.
  
 本常见问题解答介绍的一些有关业务服务器 2015年压力和性能工具 Skype 最常问的问题，并可能帮助进行故障排除和工具配置选择。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>我可以在生产环境中运行 LyncPerfTool.exe 吗？

这**不**推荐。 该工具会影响生产服务器的性能、 安全性和最终用户体验。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>我第一次在登录我的用户。 为什么我的服务器运行的较高负载？

第一次用户登录时，在后台发生的附加操作。 因此，Microsoft SQL Server 后端服务器上的性能可能会下降。 建议您的用户的所有运行记录一个简短的测试，然后重新启动客户端之前就开始衡量工具的结果。 Skype 业务服务器不支持每秒，超过 12 并发用户的登录会话，但请注意您的服务器可以处理的实际数目取决于您的硬件配置，并且可能低于受支持的值。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的客户正在运行内存不足 ！ 我应该做什么？

如果客户端运行内存不足的应减少每 Skype 业务服务器前端池在登录的用户数。 您还可以选择扩展出前结束池，如果是持久性的问题。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>可以运行此工具 Skype 业务服务器上本身？

您不应该这样做。 由于二进制不匹配，则可能会失败，因为不支持这种情况下，还因为目标是测量服务器上的资源消耗。 实际上那里运行该工具会影响服务器的性能，使您的数据和测量结果。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>在虚拟服务器上或在 Microsoft Hyper-V 服务器 2008年/2012年是否可以运行 LyncPerfTool.exe？

是的您可以。
  
## <a name="what-does-mpop-mean"></a>MPOP 是什么意思？

MPOP 是存在的缩短的种说法"多个点"。 MPOP 旨在模拟其中用户登录到 Skype 业务 2015年客户端的多个机器或设备的方案。 请注意，LyncPerfTool.exe，在每个终结点使用的默认配置文件。 换句话说，该配置文件不存在的两个点之间拆分。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我开始 LyncPerfTool.exe，但什么都没有发生。 这是怎么回事？

检查总有效终结点计数器，以查看用户连接的服务器上。 如果用户不能连接，请验证您 Skype 业务服务器 2015年配置。 因为一个服务器名称、 用户前缀，或密码不正确，通常可以看到的问题出现。 请注意，外部客户端应指定访问代理服务器和目标服务器的值。 验证配置文件中的端口号。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>如何能够确保内容正在衡量？

有 LyncPerfTool 性能计数器指示用户连接并执行操作，但确保正在测量操作的最简单方法就是登录到其中一个与 Skype 业务 2015年客户端的帐户并执行那些操作您自己。 检查结果确认测量拍摄。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>我有安装 Lync Server 2010 容量规划工具和/或 Lync 服务器 2013年容量规划工具。 是这样可以吗？

 这些工具具有互操作性问题 ！ 您必须卸载这些工具来获得有效的数据从 Skype 业务服务器 2015年压力和性能工具的所有以前版本。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>将压力和性能工具，设置 CAA 调用信息服务器拓扑结构？

否，这些工具将不会执行此操作。 工具只能创建用户、 联系人和通讯组列表、 要模拟的用户负载。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>最大的工具支持的用户数是什么？

在测试中，我们总共可以有 80000 用户，创建并执行总额为 3 万名用户运行这些工具的测试。 建议最多的 120000 个用户，尽管技术限制允许较高的值。 请记住，这些值取决于服务器和硬件在您的环境中。
  

