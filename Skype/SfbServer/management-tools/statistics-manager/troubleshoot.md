---
title: 对 Skype for Business Server 的统计信息管理器进行故障排除
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要：阅读本主题以排查统计信息管理器Skype for Business Server部署问题。
ms.openlocfilehash: a7604b15826ee55e127cd24447b0557b24b78548
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675274"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>对 Skype for Business Server 的统计信息管理器进行故障排除

**总结：** 阅读本主题，对部署用于Skype for Business Server的 Statistics Manager 进行故障排除。

本主题介绍如何通过描述可能在应用程序事件日志中看到的事件以及纠正事件时可能采取的相应操作来排查 Statistics Manager 部署问题。 本主题包含以下各部分：

- [代理事件](troubleshoot.md#BKMK_Agent)

- [侦听器事件](troubleshoot.md#BKMK_Listener)

- [网站问题](troubleshoot.md#BKMK_Website)

## <a name="agent-events"></a>代理事件
<a name="BKMK_Agent"> </a>

- **1000** - 无法设置处理器限制 (作业对象) - 未知原因

- **1001** — 进程不允许进程限制 (可能已在作业对象内) 

    代理在Windows作业对象内部运行，以自动限制其内存占用。 如果代理不会启动，并且事件日志中存在这些事件条目，则无法在服务器上实例化作业对象。 若要解决此问题，可以通过更改配置文件中的值来删除内存上限：

  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    搜索“MaxProcessMemoryMB”并将值更改为“0”，如下所示：

  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > 如果进行此更改，代理通常仍会消耗 \< 100 MB 的内存，但不会像默认值那样强制限制为 300 MB。 如果进行了此更改，我们建议密切监视内存使用情况，以确保代理不会在其主机上使用大量内存。

- **2000** - 客户端初始化失败

- **2001** — 无法在任何源 IP 上与服务建立连接

  如果代理无法连接到侦听器计算机，请检查以下内容：

  1. 确保侦听器服务在侦听器计算机上运行。 如果没有，请确保 Redis 在该服务器上运行，然后重启侦听器服务。

     检查侦听器计算机上的 Statistics Manager 事件日志，确保统计信息管理器侦听器服务本身没有问题。

  2. 使用连接工具（如 telnet）验证从代理计算机到正确端口上的侦听器的连接。

     如果没有，请确保在侦听器计算机上为侦听器计算机连接到 (专用/公共/域) 的网络类型启用传入防火墙规则。 如果侦听器计算机未加入域，则网络可能列为公共网络，在这种情况下，使用 Statistics Manager 安装的防火墙规则默认情况下将不适用。

- **4000** — 无法从侦听器下载服务器信息 (未知原因) 

  - **4001** - 在侦听器拓扑中找不到服务器

    如果服务器成功连接到侦听器，但服务器未添加到侦听器缓存中的拓扑，则会发生此错误。 解析选项：

  - 请确保按照有关导入拓扑的说明操作。 请参阅 [“导入拓扑](deploy.md#BKMK_ImportTopology)”。

  - 例如，如果代理位于拓扑 (中未列出的服务器上，SQL AlwaysOn 群集中的节点) ，则需要按照导入[拓扑](deploy.md#BKMK_ImportTopology)中的说明手动添加代理。

  - **4002** - 侦听器密码无效

    代理尝试使用的加密密码与侦听器本身的服务密码不匹配。 卸载代理并使用正确的服务密码重新安装它。

  - **4003** - 证书指纹不匹配

    安装时给代理的证书指纹与侦听器当前使用的证书上的指纹不匹配，因此连接将被拒绝。 卸载代理并使用正确的证书指纹重新安装它。

  - **4004** - 响应无效或 HttpStatusCode

    侦听器未响应预期状态。

  - 如果代理连接，请检查代理配置。

  - 检查侦听器计算机的 StatsMan 日志，了解其配置问题。

  - **4005** - 无法取消序列化 XML

    侦听器服务器上的服务器信息已损坏，或者代理和侦听器计算机之间可能存在版本不匹配。 确保版本匹配，并检查侦听器事件日志是否存在问题。

## <a name="listener-events"></a>侦听器事件
<a name="BKMK_Listener"> </a>

- **10000** - 启动失败未知原因 (这些原因不可恢复，服务将停止/崩溃，结果) 

  - **10001** - 配置问题

    通常，当 [listener_install_location]\PerfAgentListener.exe.config文件已由手动修改并且应用程序无法读取时，会发生这种情况。

  - **10002** - HTTP 侦听器初始化错误

    在安装期间 URL ACL 未正确设置或 SSL 证书无效时，通常会记录此事件。 确保配置中的证书有效。 如果是，请根据 [部署统计](deploy.md#BKMK_Deploy)信息管理器中的说明重新安装侦听器。

  - **10003** - Redis 失败

  - **10004** - Caching基础结构故障

  - **10007** - 设置 (存储在 redis) 

    侦听器无法联系 Redis 或从缓存中检索格式正确的数据，无法启动。 确保已在服务器上正确启动和配置 Redis 服务。

  - **10005** - 服务器信息检索/分析

    Redis 缓存中的拓扑信息无效。 首先，尝试重启 Redis 和侦听器。 如果错误仍然存在，请参阅 [导入拓扑](deploy.md#BKMK_ImportTopology) 以重新创建拓扑数据。

- **10100** - Redis PING 中断

  - **10101** - Redis PING 每 60 秒持续中断 () 

  - **30100** - Redis PING 中断已还原

    当侦听器无法连接到 Redis 时，将记录这些数据。 确保 Redis 已启动，并且侦听器和 Redis 之间的网络连接可用。

- **10200** - Redis 写入中断

  - **10201** - Redis 写入中断持续 (每 60 秒) 

  - **30100** - Redis 写入中断已解决

    当侦听器无法写入 Redis 缓存时，将记录这些内容。 确保 Redis 已启动，并且侦听器和 Redis 之间的网络连接可用。

- **30000** - 成功启动

    每次启动侦听器时记录。

- **22000** - 统计信息管理器代理的初始化成功。

- **23000** - EventLogQueryManager 的初始化首次成功 (或失败后) 

- **24000** - 服务器信息初始化首次成功 (或失败后) 

- **25000** - 侦听器在未能帖子 (或首次成功帖子) 后重新联机

- **5000** - "开始"菜单用于脱机发布数据的侦听器

- **5001** - 侦听器在较长时间内仍处于脱机状态

    这些事件可用于监视/警报/清除问题。

## <a name="website-issues"></a>网站问题
<a name="BKMK_Website"> </a>

- Chrome 中的重复登录提示 - 这是已在版本 1.1 中解析的 bug。 如果在 Chrome 浏览器中看到重复登录提示，请确保已升级到最新版本的 Statistics Manager。 To verify the version of the website you are running:

  - 在文件资源管理器中，打开 (默认目录) 

  - 右键单击StatsManHubWebSite.dll并查看其属性。

  - 如果在 KHI 横向视图或“计数器详细信息”视图中找不到计算机，请确保它是站点和池的成员。 否则，它不会显示在这些视图中。 有关在拓扑中为服务器定义站点和池的信息，请参阅 [导入拓扑](deploy.md#BKMK_ImportTopology)。

  - 产品版本将显示在说明详细信息中。

## <a name="for-more-information"></a>更多详细信息
<a name="BKMK_Website"> </a>

有关详细信息，请参阅：

- [Skype for Business Server 的统计信息管理器规划](plan.md)

- [部署 Skype for Business Server 的统计信息管理器](deploy.md)

- [更新 Skype for Business Server 的统计信息管理器](upgrade.md)
