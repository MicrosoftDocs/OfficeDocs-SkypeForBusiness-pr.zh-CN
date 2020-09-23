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
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 对于“中介服务器”，可以指定以下内容：
ms.openlocfilehash: 9a6da594452b4675b3eed1ca734fa3b54c9117b9
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215143"
---
# <a name="mediation-service-settings-expander"></a>中介服务设置扩展器

对于“中介服务器”****，可以指定以下内容：

如果要将中介服务器并置到前端池或 Standard Edition 服务器，请选中 " **并置中介服务器已启用**" 复选框。 如果选择不并置中介服务器，则本节中没有可定义的设置。

如果已启用中介服务器并置，则需要在服务器上为传输层安全性 (TLS) 定义侦听端口范围。默认情况下，此端口为 5067。如果选择“启用 TCP 端口”****，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。这是一个可选设置，您应该参考网关要求或公用电话交换网 (PSTN) 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。

定义与并置的中介服务器关联的 PSTN 网关。如果已定义网关，则可以将这些网关与中介服务器关联。

如果有多个网关与中介服务器关联，会将第一个关联的网关作为默认网关。如果需要选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击“设为默认值”****。若要取消选择网关作为默认网关，请单击“取消设为默认值”****。

有关定义和配置 Enterprise Edition 前端池或 Standard Edition server 的设置的详细信息，请参阅 [定义和配置拓扑](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) 和 [部署中介服务器和定义对等方](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。


