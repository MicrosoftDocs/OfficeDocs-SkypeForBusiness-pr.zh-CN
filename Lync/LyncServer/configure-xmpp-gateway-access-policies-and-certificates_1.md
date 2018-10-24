---
title: 配置 XMPP 网关访问策略和证书
TOCTitle: 配置 XMPP 网关访问策略和证书
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49888615
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 XMPP 网关访问策略和证书

 

_**上一次修改主题：** 2012-10-15_

XMPP 联盟可根据可扩展消息传递和状态协议 (XMPP) 定义外部部署。XMPP 配置允许 Lync 用户通过以下方式访问 XMPP 域用户：

  - IM 和状态 – 仅限于面对面

  - Lync 客户端中 XMPP 联盟联系人的创建

当您将策略配置为支持可扩展消息传递和状态协议 (XMPP) 联盟伙伴时，这些策略适用于 XMPP 联盟域的用户，但不适用于会话初始协议 (SIP) 即时消息 (IM) 服务提供者（例如，Windows Live）或 SIP 联盟域的用户。您可以针对要允许您的用户添加联系人并与之进行通信的每个 XMPP 联盟域配置 XMPP 联盟伙伴。在制定好这些策略之后，您需要配置 XMPP 网关证书。

> [!NOTE]  
> 要开始 XMPP 网关迁移，您需要部署 Lync Server 2013 XMPP 网关，并配置访问策略以启用 Lync Server 2013 XMPP 网关的用户。在执行这些步骤之前，必须将所有用户都移至 Lync Server 2013 部署。有关详细信息，请参阅 <a href="configure-xmpp-gateway-on-lync-server-2013_1.md">在 Lync Server 2013 上配置 XMPP 网关</a>。



## 配置外部访问策略以启用 Lync Server 2013 XMPP 网关的用户

1.  打开 Lync Server 控制面板。

2.  在左侧导航栏中，单击“联盟和外部访问”，然后单击“外部访问策略”。

3.  单击“新建”，然后单击“用户策略”。

4.  输入外部访问用户策略的名称。

5.  提供外部访问用户策略的说明。

6.  选择“启用与联盟用户的通信”。

7.  选择“启用与 XMPP 联盟用户的通信”。

8.  单击“提交”保存对站点或用户策略的更改。

