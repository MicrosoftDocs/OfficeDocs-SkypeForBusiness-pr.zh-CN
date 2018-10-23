---
title: Lync Server 2013：部署企业语音
TOCTitle: 部署企业语音
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412876(v=OCS.15)
ms:contentKeyID: 49314003
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中部署企业语音

 

_**上一次修改主题：** 2012-10-03_

Lync Server 2013企业语音是 Lync Server 2013 基础结构的一部分。

部署企业语音时要求您：

1.  查看规划文档的 [在 Lync Server 2013 中规划企业语音](lync-server-2013-planning-for-enterprise-voice.md)部分。

2.  最终确定使用此工作负荷部署功能和组件的计划。

3.  运行 规划工具以设计反映部署决策的拓扑。

4.  在 拓扑生成器中打开拓扑设计，如部署文档中的 [在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)中所述。
    
    > [!NOTE]  
    > 拓扑生成器安装是内部池部署过程的一部分。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-install-lync-server-administrative-tools.md">安装 Lync Server 2013 管理工具</a>。
    


此外，必须已在与选择部署的参考拓扑对应的中央站点和分支站点中部署 Lync Server Enterprise Edition。必须至少为一个内部池定义、发布和安装文件之后，才能部署 企业语音组件，而且必须使用 拓扑生成器定义和发布内部池。

要查看带有可部署 企业语音服务器角色（及其相互间的关系，以及它们与其他 Lync Server 2013 服务器角色的关系）的示例的参考拓扑，请参阅规划文档中的 [Lync Server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)。

要查看阐明示例呼叫允许控制部署（包括网络区域、网络站点和子网）的参考拓扑，请参阅规划文档中的 [示例：在 Lync Server 2013 中收集呼叫允许控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

> [!IMPORTANT]
> 要在中央站点部署 企业语音，请继续阅读本节中的主题。要在分支站点上部署 企业语音，请跳至部署文档中的 <a href="lync-server-2013-deploying-branch-sites.md">在 Lync Server 2013 中部署分支站点</a>。


本节包含中介服务器并置到每个前端服务器或 Standard Edition Server 上的部署过程（推荐），以及独立的中介服务器池的部署过程。

如果已使用 拓扑生成器定义和发布将中介服务器并置到每个前端服务器或 Standard Edition Server 上的拓扑，则可以跳过以下内容，因为在为前端服务器池或 Standard Edition Server 安装文件时，部署向导已自动为中介服务器安装了相关文件。

  - [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)

如果已使用 拓扑生成器在独立的池中定义和发布中介服务器，则可以使用以下内容：

  - 验证拓扑是否满足软件和环境先决条件，如 [Lync Server 2013 的企业语音先决条件](lync-server-2013-enterprise-voice-prerequisites.md)中所述。

## 本节内容

  - [Lync Server 2013 的企业语音先决条件](lync-server-2013-enterprise-voice-prerequisites.md)

  - [在 Lync Server 2013 中部署中介服务器和定义对等方](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)

  - [在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)

  - [在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - [在 Lync Server 2013 中导出和导入语音路由配置](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)

  - [在 Lync Server 2013 中发布对语音路由配置所做的待处理更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [部署本地 Exchange UM 以提供 Lync Server 2013 语音邮件](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - [在托管 Exchange UM 上提供 Lync Server 2013 用户语音邮件](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - [配置本地 Lync Server 2013 与 Exchange Online 的集成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - [在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [关于 Lync Server 2013 中的网络区域、站点和子网](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)
    
      - [在 Lync Server 2013 中配置增强型 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [在 Lync Server 2013 中配置媒体绕过](lync-server-2013-configure-media-bypass.md)

  - [在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中部署分支站点](lync-server-2013-deploying-branch-sites.md)  
[在 Lync Server 2013 中配置拨入式会议](lync-server-2013-configuring-dial-in-conferencing.md)  
[在 Lync Server 2013 中配置呼叫寄存](lync-server-2013-configuring-call-park.md)  
[在 Lync Server 2013 中配置未分配号码的通知](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[部署监控](lync-server-2013-deploying-monitoring.md)

