---
title: Lync Server 2013：分支站点恢复能力功能
TOCTitle: 分支站点恢复能力功能
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398715(v=OCS.15)
ms:contentKeyID: 49313555
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的分支站点恢复能力功能

 

_**上一次修改主题：** 2014-02-10_

如果提供分支站点恢复能力，当分支站点到中央站点的 WAN 连接出现故障，或者当中央站点无法访问时，以下语音功能应该仍然可用：


  - 入站和出站公用电话交换网 (PSTN) 呼叫

  - 同一站点的用户间和两个不同站点的用户间的企业呼叫

  - 基本呼叫处理功能（包括呼叫保持、取回和转接）

  - 双方即时消息

  - 呼叫转接、终结点同时响铃、呼叫委派和团队呼叫服务，但前提是在同一站点配置代理程序和代理人（例如，经理和经理的管理员）或所有团队成员

  - 呼叫详细信息记录 (CDR)

  - 使用会议自动助理的 PSTN 电话拨入式会议

  - 语音邮件功能，前提是配置了语音邮件重新路由设置。（有关详细信息，请参阅 [Lync Server 2013 的分支站点恢复能力要求](lync-server-2013-branch-site-resiliency-requirements.md)。）

  - 用户身份验证和授权

仅当恢复能力解决方案是分支站点上的 Lync Server 全面部署时，以下功能才可用：

  - IM、Web 会议和 A/V 会议

  - 基于状态和请勿打扰 (DND) 的路由（其中将阻止呼叫在已激活 DND 的分机上响铃）

  - 更新呼叫转接设置

  - 响应组应用程序和呼叫寄存应用程序

  - 仅当 Active Directory 域服务 存在于分支站点上时，设置新电话和客户端。

  - 增强型 9-1-1 (E9-1-1)
    
    如果部署了 E9-1-1，且中央站点的 SIP 中继由于 WAN 连接故障而不可用， Survivable Branch Appliance 会将 E9-1-1 呼叫路由到本地分支网关。要启用该功能，分支站点用户的语音策略应在 WAN 出现故障时将呼叫路由到本地网关。

> [!NOTE]  
> XMPP 不支持 SBA（survivable branch office，自动恢复分支机构）。处于 SBA 配置的用户将无法向 XMPP 联系人发送 IM 或查看其联机状态。


