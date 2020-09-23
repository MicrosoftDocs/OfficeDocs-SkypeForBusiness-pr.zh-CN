---
title: Lync Server 2010 的中介服务器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 在此对话框中编辑中介服务器的属性。 左侧是一组快速链接，带您设置常规设置、下一个跃点设置和 PSTN 网关设置。 每个部分的设置如下：
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215153"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的中介服务器常规设置扩展器

在此对话框中编辑中介服务器的属性。 左侧是一组快速链接，带您设置常规设置、下一个跃点设置和 PSTN 网关设置。 每个部分的设置如下：

 **常规**：

- **FQDN**：编辑中介服务器的完全限定的域名称

- **关联**：选中 " **关联) 媒体组件的边缘池 (** " 复选框，然后选择要用作外部访问的媒体路径的中介服务器的边缘服务器或边缘池。

  **下一个跃点**：

- **下一跃点选择**：从列表中选择前端服务器或前端池用作中介服务器的路径，以用于与您的部署进行通信。

  **PSTN 网关**：

  **中介服务器 PSTN 网关**：

- **侦听端口**：定义中介服务器将侦听的端口。 可以为 **TLS**（即传输层安全性）或 **TCP**（即传输控制协议）定义端口。 要让 TCP 端口输入可用，必须选中“启用 TCP 端口”**** 复选框。

    > [!IMPORTANT]
    > 请参阅公用电话交换网 (PSTN) 网关的文档和配置设置，以确定是需要启用并定义端口值 TLS 和/或 TCP。 TLS 是一种更安全的协议，它使用证书来加密中介服务器和 PSTN 网关之间的通信。 并非所有的 PSTN 网关都支持 TLS。

- 列出针对部署定义和配置的 SIP 中继和网关列表。 如果未提供任何项目，则未针对部署配置任何 SIP 中继或 PSTN 网关。 您可以在拓扑生成器中的 " **共享组件** " 下定义和配置中继和网关。

## <a name="see-also"></a>另请参阅

[SIP 中继的概述](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[PSTN 网关部署选项](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
