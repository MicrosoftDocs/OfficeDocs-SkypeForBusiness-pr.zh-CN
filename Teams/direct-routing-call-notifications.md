---
title: 电话系统直接路由
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
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341806"
---
# <a name="manage-call-notifications"></a>管理呼叫通知

本文介绍如何管理用户的呼叫通知。 你可以将呼叫终结点配置到两个团队和第三方专用分支交换（PBX）或会话边界控制器（SBC）。  例如，如果您想要同时向用户的手机和桌面电话发送呼叫，这很有用。   

在下图中，用户 Irena 有两个终结点：

- 团队终结点
- 连接到第三方 SBC 的 SIP 电话

当呼叫到达时，SBC 将电话系统直接路由和第三方 SBC 之间的通话派生在一起。


![显示分叉团队终结点的图表](media/direct-routing-call-notification-1.png)

如果在分叉2上接受呼叫（由第三方 SBC），团队将生成 "未接来电" 通知。  

你可以通过将 SBC 配置为在分叉1上发送取消，从而阻止 "未接来电" 通知，如下所示：

原因： SIP;原因 = 200; 文本 "通话在别处完成" 

请注意，呼叫将不会在 Microsoft Phone 系统的呼叫详细记录中注册为成功通话。 该呼叫将注册为 "尝试"，最终 SIP 代码为 "487"、最终 Microsoft 子代码 "540200" 和最终 SIP 代码短语 "在别处完成通话"。  （若要查看呼叫详细记录，请转到团队管理员门户、分析和报表、使用情况报告，并选择 PSTN 使用。）


下图显示了分叉1的 SIP 阶梯、解释调用流以及取消消息中的预期原因。 

![显示分叉团队终结点的图表](media/direct-routing-call-notification-2.png)
