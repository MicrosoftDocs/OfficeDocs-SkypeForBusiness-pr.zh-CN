---
title: 阻止新连接
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: c776c915247533641bc92d1a5458daf671bf6a04
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759724"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>阻止与服务器Skype for Business Server新连接


Skype for Business Server使您可以使服务器脱机 (例如，将软件或硬件升级) 用户不会丢失任何服务。

如果指定阻止对池中服务器的新连接或新呼叫的选项，则一旦实现此选项，服务器将停止接收任何新连接和呼叫。这些新的连接和呼叫将通过池中的其他服务器进行路由。阻止新连接的服务器允许其现有连接上的会话继续进行，直至会话自然结束。所有现有会话都结束后，即可将服务器置于脱机状态。

当您阻止与前端服务器建立新连接时，Skype for Business Server功能和服务依赖于 DNS 负载平衡以确保其正常工作。 如果在池中没有使用 DNS 负载平衡，则服务器阻止新连接期间，通过这些服务的连接可能不会重新路由到其他服务器，因此将服务器置于脱机状态时，某些会话和呼叫可能会中断。 依赖 DNS 负载平衡以确保此选项正常运行的功能如下所示：

  - 助理版

  - 会议通知应用程序

  - 响应组应用程序

  - Announcement application － 通知应用程序

  - Call Park 应用程序

有关 DNS 负载平衡的详细信息，请参阅 [负载平衡要求](../../plan-your-deployment/network-requirements/load-balancing.md)。

除了阻止运行 Skype for Business Server 服务器上所有服务的新连接，您还可以阻止单个服务的新Skype for Business Server连接。 例如，在需要应用不需要关闭整个服务器的 Skype for Business Server 更新时，此方法非常有用。 请注意，阻止一项服务的连时，必须选择 Windows 服务列表中所属和显示的服务。 例如，监控的 Skype for Business Server Front-End 服务和数据收集代理是单独的 Skype for Business Server 服务，但在 Windows 服务列表中，它们合并显示为Skype for Business Server前端服务。 您可以阻止前端服务的新Skype for Business Server，但不能分别阻止这两个单独的基础 Skype for Business Server连接。

> [!IMPORTANT]
> 如果将某台服务器设置为阻止新连接，然后重新启动该服务器，则默认情况下，该服务器启动后将立即开始接受新连接。要防止此情况发生，请在重新启动服务器之前，将其设置为仅手动暂停和恢复。

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>阻止新连接Skype for Business Server

1.  以以下组的成员登录到本地管理员组。

2.  打开服务管理单元控制台：单击"开始"，指向"**所有** 程序"，指向"**管理工具**"，然后单击"服务 **"。**

3.  在列表中，双击Skype for Business Server Windows阻止新连接的服务。

4.  在“属性”对话框的“服务状态: 已启动”下，单击“暂停”。

5.  或者，作为推荐选项，单击“启动类型”旁边的“手动”。
    
    > [!IMPORTANT]
    > 如果将某台服务器设置为阻止新连接，然后重新启动该服务器，则默认情况下，该服务器启动后将立即开始接受新连接。要防止此情况发生，请在重新启动服务器之前，将其设置为仅手动暂停和恢复。
