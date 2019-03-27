---
title: 对 Skype for Business Server 的统计信息管理器进行故障排除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要： 阅读本主题解决 Skype 您部署的统计信息管理器中的业务服务器。
ms.openlocfilehash: 33635c39086211e7e3e99b33268870c56704a367
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883804"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>对 Skype for Business Server 的统计信息管理器进行故障排除
 
**摘要：** 阅读本主题解决 Skype 您部署的统计信息管理器中的业务服务器。
  
本主题介绍如何通过在应用程序事件日志中，您可能会看到的事件和相应的操作，您可能采取纠正事件描述中解决统计信息管理器部署。 本主题包含以下部分：
  
- [代理事件](troubleshoot.md#BKMK_Agent)
    
- [侦听器事件](troubleshoot.md#BKMK_Listener)
    
- [网站问题](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>代理事件
<a name="BKMK_Agent"> </a>

- **1000** - 无法设置处理器限制器（作业对象） - 未知原因
    
- **1001** — 过程限制不允许的进程 (可能已在作业对象)
    
    代理在 Windows 作业对象内以运行以自动限制其内存使用量。 如果代理无法启动，并且这些事件条目在事件日志中存在，则作业对象无法在在服务器上实例化。 要解决此问题，可以通过更改配置文件中的值来取消内存上限：
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    搜索"MaxProcessMemoryMB"，并将值更改为"0"，如下所示：
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > 如果进行此更改，代理通常仍将使用\<100 MB 的内存，但是它不会关闭限于 300 MB 原样默认值。 如果进行更改后，我们建议密切监视内存使用情况，以确保代理不会占用大量内存其主机计算机上。 
  
- **2000** - 客户端初始化失败
    
- **2001** - 无法在任何源 IP 上建立与该服务的连接
    
    如果代理无法连接到侦听器计算机，请检查以下各项：
    
1. 确保侦听器服务正在侦听器计算机上运行。 否则，请确保 Redis 正在服务器上运行，然后重新启动侦听器服务。
    
    检查以确保不存在与统计信息管理器侦听器服务本身问题的侦听器计算机上的统计信息管理器事件日志。
    
2. 使用连接工具（例如 telnet）验证正确端口上从代理计算机到侦听器的连接。
    
    否则，请确保根据侦听器计算机连接到的网络类型（专用/公共/域）在侦听器计算机上启用传入防火墙规则。 如果侦听器计算机未加入到域中，可能为公共列出网络并在此情况下使用统计信息管理器安装的防火墙规则不会应用默认情况下。
    
- **4000** - 无法从侦听器下载服务器信息（未知原因）
    
  - **4001** - 在侦听器拓扑未找到服务器
    
    如果服务器成功连接到该侦听器，但服务器未添加到的侦听器缓存中的拓扑，则会发生此错误。 解决办法选项：
    
  - 	确保遵循导入拓扑的说明。请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)。   
    
  - 如果代理位于拓扑中未列出的服务器上（例如，SQL AlwaysOn 群集内的节点），你将需要按照[导入拓扑](deploy.md#BKMK_ImportTopology)中的说明手动添加代理。
    
  - **4002** - 无效侦听器密码
    
    代理尝试使用的加密密码与侦听器上的服务密码不匹配。 请卸载代理，然后使用正确的服务密码重新安装。
    
  - **4003** - 证书指纹不匹配
    
    在安装时为代理提供的证书指纹与侦听器当前使用的证书上的指纹不匹配，因此该连接将被拒绝。 请卸载代理，然后使用正确的证书指纹重新安装。
    
  - **4004** - 无效响应或 HttpStatusCode
    
    侦听器未以预期的状态响应。   
    
  - 如果连接使用代理，请检查代理配置。
    
  - 检查其配置问题的侦听器计算机 StatsMan 日志。
    
  - **4005** - 无法将 XML 反序列化
    
    侦听器服务器上的服务器信息已损坏，或者代理与侦听器计算机之间可能存在版本不匹配的情况。 请确保版本匹配，并检查侦听器事件日志了解相关问题。
    
## <a name="listener-events"></a>侦听器事件
<a name="BKMK_Listener"> </a>

- **10000** - 启动失败未知原因（这些错误无法恢复，因此服务将停止/失败）
    
  - **10001** - 配置问题
    
    通常，当 [listener_install_location]\PerfAgentListener.exe.config 文件被手动修改而无法由应用程序读取时，会发生此错误。
    
  - **10002** - HTTP 侦听器初始化错误
    
    当 URL ACL 在安装期间未正确设置或 SSL 证书无效时，通常会记录此事件。 请确保配置中的证书有效。 如果证书有效，请根据[部署统计信息管理器](deploy.md#BKMK_Deploy)中的说明重新安装侦听器。
    
  - **10003** - Redis 故障
    
  - **10004** - 缓存基础结构故障
    
  - **10007** - 设置（存储在 redis 中）
    
    侦听器无法联系 Redis，或者无法从缓存中检索到格式正确的数据，因此无法启动。 请确保 Redis 服务已启动并且在服务器上正确配置。
    
  - **10005** - 服务器信息检索/解析
    
    Redis 缓存中的拓扑信息无效。 首先，尝试重新启动 Redis 和侦听器。 如果错误仍然存在，请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)重新创建拓扑数据。
    
- **10100** - Redis PING 中断
    
  - **10101** - Redis PING 连续中断（每隔 60 秒）
    
  - **30100** - Redis PING 中断已恢复
    
    当侦听器无法连接到 Redis 时，将记录这些数据。 请确保 Redis 已启动并且侦听器与 Redis 网络之间的连接可用。
    
- **10200** - Redis 写入中断
    
  - **10201** - Redis 写入中断连续发生（每隔 60 秒）
    
  - **30100** - Redis 写入中断已解决
    
    当侦听器无法写入 Redis 缓存时，将记录这些数据。 请确保 Redis 已启动并且侦听器与 Redis 网络之间的连接可用。
    
- **30000** - 已成功启动
    
    侦听器每次启动时记录。
    
- **22000** — 初始化的统计信息管理器代理成功。
    
- **23000** - EventLogQueryManager 的初始化成功（首次或失败之后）
    
- **24000** - serverinfo 的初始化成功（首次或失败之后）
    
- **25000** - 侦听器在无法开机自检（或首先成功开机自检）之后恢复联机
    
- **5000** - 侦听器启动脱机对数据进行开机自检
    
- **5001** - 侦听器在长时间内仍脱机
    
    这些事件可用于监控/警示/清除问题。
    
## <a name="website-issues"></a>网站问题
<a name="BKMK_Website"> </a>

- 重复性的登录提示在部件版式-这是 1.1 版中已解决错误。 确保您已升级到最新版本的统计信息管理器中，如果您看到的 Chrome 浏览器中的重复的登录提示。 要验证你正在运行的网站的版本，请执行以下操作：
    
  - 	在文件资源管理器中，打开默认目录
    
  - 右键单击 StatsManHubWebSite.dll 并查看其属性。
    
  - 如果在 KHI 的“横向”视图或“计数器详细信息”视图中找不到某台计算机，确保它是某个站点和池的成员。 否则，它将不会出现在这些视图中。 有关为拓扑中的服务器定义站点和池的信息，请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)。
    
  - 产品版本将在“说明”详细信息中显示。
    
## <a name="for-more-information"></a>有关详细信息
<a name="BKMK_Website"> </a>

有关详细信息，请参阅以下文章：
  
- [Skype for Business Server 的统计信息管理器规划](plan.md)
    
- [部署 Skype for Business Server 的统计信息管理器](deploy.md)
    
- [更新 Skype for Business Server 的统计信息管理器](upgrade.md)
