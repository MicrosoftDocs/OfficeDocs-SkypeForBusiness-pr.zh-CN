---
title: 旧版合并
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: “Web 会议外部 FQDN”允许外部用户加入内部会议。输入旧版边缘服务器的 Web 会议外部接口的完全限定的域名 (FQDN)。
ms.openlocfilehash: 2541de3efa0a1585699edcb11ae5187dbe9c425b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395464"
---
# <a name="legacy-merge"></a>旧版合并

“Web 会议外部 FQDN”允许外部用户加入内部会议。输入旧版边缘服务器的 Web 会议外部接口的完全限定的域名 (FQDN)。

**“外部 Web 会议外部端口”** 值 **“443”** 是为会议客户端配置的默认传输控制协议 (TCP) 会话初始协议 (SIP) 端口。如果未使用默认值，请更新 **“外部 Web 会议外部端口”** 值。

如果计划将此边缘服务器用于联盟，请选中“此边缘池用于联盟和公共 IM 连接”复选框。如果部署了多台边缘服务器，则只会为其中一台边缘服务器启用联盟。如果未选中此复选框，但之后决定要启用联盟，则必须再次运行拓扑生成器合并向导并发布拓扑。有关详细信息，请参阅[Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)。