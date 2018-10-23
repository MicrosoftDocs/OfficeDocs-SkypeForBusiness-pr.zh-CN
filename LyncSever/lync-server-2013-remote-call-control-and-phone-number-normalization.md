---
title: Lync Server 2013：远程呼叫控制和电话号码规范化
TOCTitle: 远程呼叫控制和电话号码规范化
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558630(v=OCS.15)
ms:contentKeyID: 49312321
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的远程呼叫控制和电话号码规范化

 

_**上一次修改主题：** 2012-09-22_

Lync 客户端会在通讯簿服务 (ABS) 文件下载过程中下载电话号码规范化规则。在远程呼叫控制方案中，通讯簿服务电话号码规范化规则同时适用于传入和传出远程呼叫控制呼叫。对于对启用了远程呼叫控制的用户的传入呼叫，呼叫者的电话号码首先通过 SIP/CSTA 网关或专用交换机 (PBX) 规范化为 E.164 格式。 Lync Server 2013 从网关接收呼叫时，将针对被叫方的 Microsoft Office Outlook 联系人列表或存储在通讯簿服务中的全局地址列表 (GAL) 中的规范化号码对呼叫者的电话号码执行反向号码查找 (RNL)。如果反向号码查找成功找到了匹配项，则通过传入呼叫通知中的名称来识别呼叫者。

对于传出远程呼叫控制呼叫， Lync 在将呼叫路由至 SIP/CSTA 网关之前，会对拨打号码应用通讯簿服务电话号码规范化规则。

有关为远程呼叫控制创建电话号码规范化规则的详细信息，请参阅规划文档中的 [Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)。

## 迁移电话号码规范化规则

如果要迁移以前启用了远程呼叫控制的用户，请参阅迁移文档中的以下主题：

  - 若要了解 Lync Server 2010，请参阅迁移文档中的 [迁移通讯簿](migrate-address-book.md)。

  - 若要了解 Communications Server 2007 R2，请参阅迁移文档中的 [迁移通讯簿](migrate-address-book_1.md)。

