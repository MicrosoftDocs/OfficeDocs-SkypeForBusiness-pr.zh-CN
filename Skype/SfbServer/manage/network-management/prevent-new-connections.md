---
title: 阻止新连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817451"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>阻止新连接到 Skype for Business 服务器以进行服务器维护


Skype for Business 服务器使你能够使服务器脱机（例如，应用软件或硬件升级），而不会对用户造成任何服务损失。

当你指定用于阻止新连接或呼叫池中的服务器的选项时，一旦你执行此选项，它将停止进行任何新的连接和调用。 这些新连接和呼叫通过池中的其他服务器路由。 阻止新连接的服务器允许现有连接上的会话继续运行，直到它们自然结束。 当所有现有会话都已结束时，服务器可以脱机使用。

当您阻止与前端服务器的新连接时，某些 Skype for business 服务器功能和服务依赖于 DNS 负载平衡以确保其正常工作。 如果你未在池上使用 DNS 负载平衡，则通过这些服务的连接可能无法在服务器阻止新连接期间重新路由到其他服务器，因此当服务器脱机时，可能会中断. 依赖于 DNS 负载平衡以确保此选项正常运行的功能如下所示：

  - 助理

  - 会议通知应用程序

  - 响应组应用程序

  - 通知应用程序

  - 呼叫寄存应用程序

有关 DNS 负载平衡的详细信息，请参阅[负载平衡要求](../../plan-your-deployment/network-requirements/load-balancing.md)。

除了阻止运行 Skype for business Server 的服务器上的所有服务的新连接，您还可以阻止单个 Skype for Business 服务器服务的新连接。 例如，在需要应用不需要整个服务器关闭的 Skype for Business 服务器更新的情况下，此方法非常有用。 请注意，当你阻止一个服务的连接时，你必须选择在服务的 Windows 列表中对其进行分组和显示的服务。 例如，Skype for Business 服务器前端服务和用于监视的数据收集代理是单独的 Skype for business 服务器服务，但在 Windows 服务列表中，它们将被合并并显示为 Skype for business 服务器前端业务. 你可以阻止 Skype for business Server 前端服务的新连接，但不能单独阻止这两个单独的基础 Skype for Business 服务器服务的新连接。

> [!IMPORTANT]
> 如果将服务器设置为阻止新连接，然后重新启动服务器，则默认情况下，服务器将在启动后立即开始接受新连接。 若要防止这种情况，请将服务器设置为仅在重新启动服务器之前暂停和手动恢复。

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>阻止新连接到 Skype for Business 服务器

1.  以 Administrators 组成员的身份登录本地计算机。

2.  打开 "服务" 管理单元控制台：单击 "**开始**"，指向 "**所有程序**"，指向 "**管理工具**"，然后单击 "**服务**"。

3.  在列表中，双击要阻止新连接的 Skype for business 服务器 Windows 服务。

4.  在 "属性" 对话框中的 "**服务状态：已开始**" 下，单击 "**暂停**"。

5.  （可选，但建议在 "**启动类型**" 旁边，单击 "**手动**"。
    
    > [!IMPORTANT]
    > 如果将服务器设置为阻止新连接，然后重新启动服务器，则默认情况下，服务器将在启动后立即开始接受新连接。 若要防止这种情况，请将服务器设置为仅在重新启动服务器之前暂停和手动恢复。
