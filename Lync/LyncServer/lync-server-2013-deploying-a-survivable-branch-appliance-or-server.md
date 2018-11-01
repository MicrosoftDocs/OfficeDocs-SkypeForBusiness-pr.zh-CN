---
title: Lync Server 2013：部署 Survivable Branch Appliance 或 Survivable Branch Server
TOCTitle: 部署 Survivable Branch Appliance 或 Survivable Branch Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398849(v=OCS.15)
ms:contentKeyID: 49314268
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server

 

_**上一次修改主题：** 2014-12-10_

可恢复 企业语音指的是分支站点恢复能力，即，在指向中央站点的链接不可用时为分支站点用户提供连续 企业语音服务的能力。

对于中小型分支站点（具有 25 到 1,000 个用户的分支站点），建议部署 Survivable Branch Appliance，它将通过使用其内置 PSTN 网关或指向电话服务提供商的 SIP 中继终止公用电话交换网 (PSTN) 呼叫。 Survivable Branch Appliance 是一种包含刀片式服务器的第三方设备，该刀片式服务器运行 Windows Server 2008 R2 操作系统、 Lync Server 2013 注册器、 中介服务器软件以及 PSTN 网关，所有这些组件均位于单个设备机架中。

对于具有 1,000 到 5,000 个用户且没有可恢复 WAN 的分支站点，建议将 Survivable Branch Server 连接到 PSTN 网关或指向电话服务提供商的 SIP 中继。 Survivable Branch Server 是基于 Windows Server 的计算机，其上安装有注册器和 中介服务器软件。

> [!NOTE]  
> 对于具有 5,000 多个用户和专门 Lync Server 管理员的分支站点，建议进行独立于中央站点部署的完整 Lync Server 2013 部署。<br />
有关为组织中的分支站点选择最佳恢复能力解决方案的详细信息（包括先决条件和规划注意事项），请参阅规划文档中的 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复能力要求</a>。



## 本部分内容

  - [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央站点任务](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [在 Lync Server 2013 中为用户配置分支站点恢复能力](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [在 Lync Server 2013 中在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [附录：Lync Server 2013 中的 Survivable Branch Appliance 和 Survivable Branch Server](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

## 另请参阅

#### 其他资源

[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)

