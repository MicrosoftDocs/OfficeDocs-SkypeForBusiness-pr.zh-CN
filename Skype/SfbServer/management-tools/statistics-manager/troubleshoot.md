---
title: 对 Skype for Business Server 的统计信息管理器进行故障排除
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要：阅读本主题，解决统计信息管理器部署问题Skype for Business Server。
ms.openlocfilehash: 6e6edefe8d6070a917f817b3b6d79bf35ff36599
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857339"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>对 Skype for Business Server 的统计信息管理器进行故障排除
 
**摘要：** 阅读本主题，了解统计信息管理器部署疑难解答Skype for Business Server。
  
本主题介绍如何通过描述你可能在应用程序事件日志中看到的事件以及你为纠正事件可能采取的适当操作，来对统计信息管理器部署进行疑难解答。 本主题包含以下各部分：
  
- [代理事件](troubleshoot.md#BKMK_Agent)
    
- [侦听器事件](troubleshoot.md#BKMK_Listener)
    
- [网站问题](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>代理事件
<a name="BKMK_Agent"> </a>

- **1000** — 无法为作业对象设置 (限制) — 未知原因
    
- **1001** — 在作业对象模型内 (进程上不允许进程) 
    
    代理在作业对象Windows自动限制其内存占用。 如果代理不会启动，并且这些事件条目存在于事件日志中，则不能在服务器上实例化作业对象。 若要处理此情况，可以通过更改以下项中的值来配置文件：
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    搜索"MaxProcessMemoryMB"，将值更改为"0"，如下所示：
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > 如果进行了此更改，代理通常仍将占用 100 MB 的内存，但是不会强制限制为 \< 默认为 300 MB。 如果进行了此更改，我们建议密切监视内存使用率，以确保代理不会在其主机上占用大量内存。 
  
- **2000** — 客户端初始化失败
    
- **2001**- 无法连接到任何源 IP 上的服务
    
    如果代理无法连接到侦听器计算机，请检查以下内容：
    
    1. 确保侦听器服务在侦听器计算机上运行。 如果不是，请确保 Redis 正在该服务器上运行，然后重新启动侦听器服务。
        
        检查侦听器计算机上统计信息管理器事件日志以确保统计信息管理器侦听器服务本身没有问题。
        
    2. 使用 telnet 等连接工具验证从代理计算机到正确端口上的侦听器的连接。
        
        如果未启用，请确保在侦听器计算机上为侦听器计算机连接到专用/公共/域 (类型的网络类型启用传入防火墙) 。 如果侦听器计算机未加入域，则网络可能列为公共网络，在这种情况下，随统计信息管理器一起安装的防火墙规则在默认情况下不适用。
    
- **4000** - 无法从侦听器下载服务器信息 (未知原因) 
    
  - **4001** — 侦听器拓扑中找不到服务器
    
    如果服务器成功连接到侦听器，但服务器未添加到侦听器缓存中的拓扑，则会发生此错误。 解决方案选项：
    
  - 确保按照导入拓扑的说明进行操作。 请参阅 [导入拓扑](deploy.md#BKMK_ImportTopology)。 
    
  - 如果代理位于拓扑中未列出的服务器上 (例如 SQL AlwaysOn 群集) 中的节点，则需要按照导入拓扑中的说明手动添加[代理](deploy.md#BKMK_ImportTopology)。
    
  - **4002** — 侦听器密码无效
    
    代理尝试使用的加密密码与侦听器本身上的服务密码不匹配。 卸载代理，然后使用正确的服务密码重新安装它。
    
  - **4003** — 证书指纹不匹配
    
    安装时为代理给定的证书指纹与侦听器当前使用的证书上的指纹不匹配，因此连接将被拒绝。 卸载代理，然后使用正确的证书指纹重新安装它。
    
  - **4004** — 无效响应或 HttpStatusCode
    
    侦听器没有响应预期状态。 
    
  - 如果连接是代理连接，请检查代理配置。
    
  - 检查侦听器计算机的 StatsMan 日志，了解其配置问题。
    
  - **4005** — 无法对 XML 进行反序列化
    
    侦听器服务器上服务器信息已损坏，或者代理计算机和侦听器计算机之间可能有版本不匹配。 确保版本匹配，并检查侦听器事件日志中的问题。
    
## <a name="listener-events"></a>侦听器事件
<a name="BKMK_Listener"> </a>

- **10000** - 启动失败 未知 (无法恢复，服务将停止/崩溃，) 
    
  - **10001** — 配置问题
    
    通常，当 [listener_install_location]\PerfAgentListener.exe.config文件已手动修改并且无法由应用程序读取时，将会发生这种情况。
    
  - **10002** — HTTP 侦听器初始化错误
    
    在安装期间未正确设置 URL ACL 或 SSL 证书无效时，通常会记录此事件。 确保配置中的证书有效。 如果是，请按照部署统计信息管理器 中的说明 [重新安装侦听器](deploy.md#BKMK_Deploy)。
    
  - **10003** — Redis 失败
    
  - **10004** - Caching基础结构故障
    
  - **10007** - 设置 (redis) 
    
    侦听器无法联系 Redis 或从缓存检索格式良好的数据，并且无法启动。 确保在服务器上正确启动和配置 Redis 服务。
    
  - **10005** - 服务器信息检索/分析
    
    Redis 缓存中的拓扑信息无效。 首先，尝试重新启动 Redis 和侦听器。 如果错误仍然存在，请参阅 [导入拓扑以](deploy.md#BKMK_ImportTopology) 重新创建拓扑数据。
    
- **10100** — Redis PING 中断
    
  - **10101** — Redis PING 每隔 60 (60 秒持续中断) 
    
  - **30100** — Redis PING 中断还原
    
    当侦听器无法连接到 Redis 时，将记录这些记录。 确保 Redis 已启动，并且侦听器和 Redis 之间的网络连接可用。
    
- **10200** — Redis 写入中断
    
  - **10201** - Redis 写入中断 (每隔 60 秒) 
    
  - **30100** — Redis 写入中断已解决
    
    当侦听器无法写入 Redis 缓存时，将记录这些记录。 确保 Redis 已启动，并且侦听器和 Redis 之间的网络连接可用。
    
- **30000** - 已成功启动
    
    每次启动侦听器时记录。
    
- **22000** — 统计信息管理器代理初始化成功。
    
- **23000** - EventLogQueryManager 的初始化在首次 (或失败后成功) 
    
- **24000** - 第一次 (或失败后，serverinfo 的初始化) 
    
- **25000** - 侦听器在未能发布或首次成功发布 (后重新联机) 
    
- **5000** — 启动脱机侦听器以发布数据
    
- **5001** - 侦听器在长时间内仍处于脱机状态
    
    这些事件可用于监视/警报/清除问题。
    
## <a name="website-issues"></a>网站问题
<a name="BKMK_Website"> </a>

- Chrome 中的重复登录提示 - 这是一个已在版本 1.1 中解决的 Bug。 如果你在 Chrome 浏览器中看到重复的登录提示，请确保你已升级到最新版本的统计信息管理器。 若要验证您正在运行的网站版本，请运行以下代码：
    
  - 在文件资源管理器中， (默认目录) 
    
  - 右键单击StatsManHubWebSite.dll并查看其属性。
    
  - 如果在 KHI 横向视图或计数器详细信息视图中找不到计算机，请确保它是站点和池的成员。 如果不是，将不会显示在这些视图中。 有关为拓扑中的服务器定义站点和池的信息，请参阅导入 [拓扑](deploy.md#BKMK_ImportTopology)。
    
  - 产品版本将显示在"说明详细信息"中。
    
## <a name="for-more-information"></a>更多详细信息
<a name="BKMK_Website"> </a>

有关详细信息，请参阅：
  
- [Skype for Business Server 的统计信息管理器规划](plan.md)
    
- [部署 Skype for Business Server 的统计信息管理器](deploy.md)
    
- [更新 Skype for Business Server 的统计信息管理器](upgrade.md)
