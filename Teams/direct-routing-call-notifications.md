---
title: 管理直接路由的呼叫通知
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由呼叫通知
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268427"
---
# <a name="manage-call-notifications"></a>管理呼叫通知

本文介绍如何管理直接路由用户的呼叫通知。 可以将呼叫终结点配置为 Teams 和第三方专用分支交换 (PBX) 或会话边界控制器 (SBC) 。 例如，如果要同时向用户的移动电话和桌面电话发送呼叫，此设置非常有用。   

在下图中，用户 Irena 有两个终结点：

- Teams 终结点
- 连接到第三方 SBC 的 SIP 电话

呼叫到达时，SBC 会分叉直接路由和第三方 SBC 之间的呼叫。


![显示分叉 Teams 终结点的图示。](media/direct-routing-call-notification-1.png)

如果第三方 SBC) 在分叉 2 (接受呼叫，Teams 将生成“错过呼叫”通知。  

可通过将 SBC 配置为在 Fork 1 上发送“取消”通知来阻止“错过呼叫”通知，如下所示：

原因：SIP;cause=200;text“Call completed elsewhere” 

呼叫不会在 Teams 电话系统的通话详细信息记录中注册为成功呼叫。 调用将注册为具有最终 SIP 代码“487”、最终 Microsoft 子代码“540200”和最终 SIP 代码短语“调用在其他位置完成”的“尝试”。   (若要查看呼叫详细信息记录，请转到 Teams 管理员中心 ->**分析和报** -> 表 **使用情况报告**，然后选择 **PSTN 使用** 情况.) 


下图演示了 Fork 1 的 SIP 阶梯、调用流以及取消消息中的预期原因。 

![图中显示了分叉的 Teams 终结点。](media/direct-routing-call-notification-2.png)
