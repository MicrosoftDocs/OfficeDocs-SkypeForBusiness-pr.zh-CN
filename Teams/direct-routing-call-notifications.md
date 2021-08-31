---
title: Teams：管理呼叫通知
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由呼叫通知
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 80c7c5487d61447a38852ca30328126b19c0499b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725921"
---
# <a name="manage-call-notifications"></a>管理呼叫通知

本文介绍如何管理用户的呼叫通知。 可以将呼叫终结点配置为同时Teams第三方专用分支 Exchange (PBX) 或会话边界控制器 (SBC) 。  此设置非常有用，例如，如果要同时向用户的移动电话和桌面电话发送呼叫。   

下图中，用户 Irena 有两个终结点：

- Teams终结点
- 连接到第三方 SBC 的 SIP 电话

当呼叫到达时，SBC 将分叉电话系统直接路由和第三方 SBC 之间的呼叫。


![显示分叉终结点的Teams图。](media/direct-routing-call-notification-1.png)

如果第三方 SBC (在分叉 2 上接受) ，Teams将生成"未接呼叫"通知。  

可以通过将 SBC 配置为在分叉 1 上发送取消来阻止"错过的呼叫"通知，如下所示：

原因：SIP;cause=200;text"Callcompleted else" 

呼叫不会作为成功的调用注册到 Microsoft 电话 System 的呼叫详细信息记录中。 该调用将注册为最终 SIP 代码"487"、最终 Microsoft 子代码"540200"和最终 SIP 代码短语"呼叫已在其他位置完成"的"尝试"。   (要查看呼叫详细信息记录，请转到 Teams 管理门户、分析和报告、使用情况报告，然后选择"PSTN 使用情况.) 


下图演示了分叉 1 的 SIP 阶梯，解释了呼叫流以及"取消"消息中的预期原因。 

![关系图显示分叉Teams终结点。](media/direct-routing-call-notification-2.png)
