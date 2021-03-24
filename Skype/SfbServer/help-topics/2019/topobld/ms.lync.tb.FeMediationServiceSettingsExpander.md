---
title: 中介服务设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 对于“中介服务器”，可以指定以下内容：
ms.openlocfilehash: e3593fd98c9207b6dd7033e5aac26170988ae956
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096898"
---
# <a name="mediation-service-settings-expander"></a>中介服务设置扩展器

对于“中介服务器”，可以指定以下内容：

如果要将中介服务器并并到前端池或 Standard Edition Server，请选中"并 **排中介服务器已启用"复选框**。 如果选择不并置中介服务器，则本节中没有可定义的设置。

如果已启用中介服务器并置，则需要在服务器上为传输层安全性 (TLS) 定义侦听端口范围。默认情况下，此端口为 5067。如果选择“启用 TCP 端口”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。这是一个可选设置，您应该参考网关要求或公用电话交换网 (PSTN) 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。

定义与并置的中介服务器关联的 PSTN 网关。如果已定义网关，则可以将这些网关与中介服务器关联。

如果有多个网关与中介服务器关联，会将第一个关联的网关作为默认网关。如果需要选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击“设为默认值”。若要取消选择网关作为默认网关，请单击“取消设为默认值”。

有关定义和配置 Enterprise Edition 前端池或 Standard Edition Server 的设置的详细信息，请参阅 Defining [and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) 和 [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)。