---
title: 中介服务设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 对于“中介服务器”，可以指定以下内容：
ms.openlocfilehash: e6b89c61e84577af86576850f5c675861cfa3a80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819554"
---
# <a name="mediation-service-settings-expander"></a>中介服务设置扩展器

对于“**中介服务器**”，可以指定以下内容：

如果你要将中介服务器 collocating 到前端池或标准版服务器，请选中 "**启用中介服务器" Collocated**的复选框。 如果您选择不 collocate 中介服务器，此部分中没有可定义的设置。

如果已启用中介服务器的 collocation，则需要在服务器上定义用于传输层安全（TLS）的侦听端口范围。 默认情况下，此端口为 5067。 如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。 这是一个可选设置，您应该参考网关要求或公用电话交换网 (PSTN) 要求以确定是否需要此设置。 默认情况下，TCP 端口值为 5068。

定义与 collocated 中介服务器相关联的 PSTN 网关。 如果您已定义网关，则它们将可与中介服务器相关联。

如果您有多个与中介服务器关联的网关，则第一个关联的网关将是默认网关。 如果需要选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击“**设为默认值**”。 若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。

有关为企业版前端池或标准版服务器定义和配置设置的详细信息，请参阅[定义和配置拓扑](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)和[部署中介服务器以及定义对等](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。


