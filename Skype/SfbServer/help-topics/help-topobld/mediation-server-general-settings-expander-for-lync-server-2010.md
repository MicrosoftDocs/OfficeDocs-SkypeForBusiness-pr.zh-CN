---
title: 适合于 Lync Server 2010 的中介服务器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 在此对话框中编辑中介服务器的属性。 沿左侧是一组快速链接，可转到 "常规设置"、"下一跃点设置" 和 "PSTN 网关设置" 的设置。 每个部分都有以下设置：
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684545"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的中介服务器常规设置扩展器

在此对话框中编辑中介服务器的属性。 沿左侧是一组快速链接，可转到 "常规设置"、"下一跃点设置" 和 "PSTN 网关设置" 的设置。 每个部分都有以下设置：

 **常规**：

- **FQDN**：编辑中介服务器的完全限定的域名

- **关联**：选择 "**关联边缘池" （对于 "媒体组件"）** 复选框，然后选择要用作外部访问媒体路径的中介服务器的边缘服务器或边缘池。

  **下一跃点**：

- **下一跃点选择**：从列表中选择前端服务器或前端池作为用于与部署进行通信的中介服务器的路径。

  **PSTN 网关**：

  **中介服务器 PSTN 网关**：

- **侦听端口**：定义中介服务器将侦听的端口。 你可以为**TLS**或传输层安全性、 **TCP**或传输控制协议定义端口。 若要使 TCP 的端口项可用，必须选中 "**启用 tcp 端口**" 复选框。

    > [!IMPORTANT]
    > 请参阅公共交换电话网络（PSTN）网关的文档和配置设置，确定是否需要启用和定义 TLS、TCP 或两者的端口值。 TLS 是一种更安全的协议，使用证书加密中介服务器和 PSTN 网关之间的流量。 并非所有 PSTN 网关都支持 TLS。

- 将列出 SIP 中继和为你的部署定义和配置的网关的列表。 如果不存在任何条目，则表示你的部署没有配置 SIP 中继或 PSTN 网关。 在拓扑生成器中的 "**共享组件**" 下定义和配置中继和网关。

## <a name="see-also"></a>另请参阅

[SIP 中继概述](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[PSTN 网关部署选项](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
