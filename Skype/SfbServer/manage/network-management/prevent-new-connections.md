---
title: 防止新连接
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: ec4bc6f9928d709a16eea11250403e5097596c36
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222735"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>阻止新的连接到 Skype 业务服务器以进行服务器维护


Skype 业务服务器，您可以向用户不会丢失任何服务使服务器脱机 （例如，若要应用软件或硬件升级）。

当指定的选项，以防止新连接或池中的服务器调用时，停止采取任何新连接和呼叫，只要您实现此选项。 这些新连接和呼叫路由到其他池中的服务器。 阻止了新连接的服务器上以继续，直到其自然结束的现有连接允许其会话。 当所有现有会话已结束时，服务器已准备好脱机。

当您阻止建立新连接到前端服务器时，业务服务器功能和服务的一些 Skype 依赖于 DNS 负载平衡，以确保其正确运行。 如果您不使用 DNS 负载平衡池上，通过这些服务的连接可能无法重新路由到其他服务器期服务器阻止了新的连接，因此当服务器处于脱机状态和一些会话和呼叫可能中断。 DNS 负载平衡来确保此选项可以正常运行所依赖的功能如下所示：

  - 助理

  - 会议通知应用程序

  - 响应组应用程序

  - 通知应用程序

  - 呼叫寄存应用程序

有关 DNS 负载平衡的详细信息，请参阅[负载平衡的要求](../../plan-your-deployment/network-requirements/load-balancing.md)。

除了防止新业务服务器运行 Skype 的服务器上的所有服务的连接，还可以防止对业务 Server 服务的单个 Skype 的新连接。 例如，此方法可在需要应用不需要要关闭的整个服务器的企业服务器更新 Skype 的情况下。 请注意，当您阻止的一个服务连接，您必须选择服务，因为它分组，Windows 服务列表中显示。 例如，业务 Server 前端服务 Skype 和监控的数据集代理是单独 Skype 业务 Server 服务，但是在 Windows 服务列表中合并而且显示为 Skype 的业务 Server 前端服务。 您可以防止新连接以进行业务 Server 前端服务 Skype，但无法单独阻止业务 Server 服务的以下两个单独基础 Skype 的新连接。

> [!IMPORTANT]
> 设置将阻止建立新连接，然后重新启动服务器的服务器时，默认情况下服务器将立即启动后对其接受新连接。 若要防止这一点，设置要仅暂停和继续手动之前重新启动服务器, 的服务器。

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>若要防止新连接到 Skype 业务服务器

1.  以 Administrators 组成员的身份登录本地计算机。

2.  打开服务管理单元控制台： 单击**开始**和指向**所有程序**、 都**管理工具**，然后单击**服务**。

3.  在列表中，双击您要阻止建立新连接的业务 Windows 服务器服务 Skype。

4.  在属性对话框中，在**服务状态： 启动**，单击**暂停**。

5.  （可选)，但建议，旁边**启动类型**，单击**手动**。
    
    > [!IMPORTANT]
    > 设置将阻止建立新连接，然后重新启动服务器的服务器时，默认情况下服务器将立即启动后对其接受新连接。 若要防止这一点，设置要仅暂停和继续手动之前重新启动服务器, 的服务器。
