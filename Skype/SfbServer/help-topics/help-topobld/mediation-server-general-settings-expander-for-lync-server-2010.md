---
title: 适合于 Lync Server 2010 的中介服务器常规设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 编辑此对话框中的中介服务器的属性。 左侧为快速链接使您转到设置常规设置、 下一个跃点设置和 PSTN 网关设置一组。 在每个部分包括以下设置：
ms.openlocfilehash: a5af8e844c82d1af194e0c59fde67725c019ec99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892425"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的中介服务器常规设置扩展器

编辑此对话框中的中介服务器的属性。 左侧为快速链接使您转到设置常规设置、 下一个跃点设置和 PSTN 网关设置一组。 在每个部分包括以下设置：

 **常规**：

- **FQDN**： 编辑中介服务器的完全限定的域名

- **关联**： 选择**关联边缘池 （用于媒体组件）** 复选框，然后选择要用作外部访问的媒体路径的边缘服务器或边缘池用于中介服务器。

  **下一个跃点**：

- **下一个跃点选择**： 从列表中选择要用作中介服务器的路径，用于与部署的通信的前端服务器或前端池。

  **PSTN 网关**：

  **中介服务器 PSTN 网关**：

- **侦听端口**： 定义中介服务器将侦听的端口。 您可以定义用于**TLS**或传输层安全性或**TCP**的端口或传输控制协议。 可用的 tcp 端口条目，您必须为**启用 TCP 端口**选择复选框。

    > [!IMPORTANT]
    > 请参阅确定如果您需要启用并定义端口值 TLS、 TCP 或同时公用电话交换网 (pstn) 网关的文档和配置设置。 TLS 是一种更安全协议证书用于对中介服务器和 PSTN 网关之间的通信进行加密。 并非所有 PSTN 网关都支持 TLS。

- 列出的 SIP 中继和网关定义和部署配置的列表。 是否存在任何条目，SIP 中继或 PSTN 网关配置为您的部署。 定义和配置中继和网关，在**共享组件**下的，在拓扑生成器。

## <a name="see-also"></a>另请参阅

[SIP 中继的概述](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[PSTN 网关部署选项](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
