---
title: 添加前端计算机
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 指定在该池中要添加为前端服务器的每台计算机的完全限定域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。 有关向拓扑中添加前端池的详细信息，请参阅部署文档中的定义和配置前端池。
ms.openlocfilehash: 4582aa09527dbc2e663dd6986772b5e88f980a0f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800143"
---
# <a name="add-front-end-machine"></a>添加前端计算机

指定在该池中要添加为前端服务器的每台计算机的完全限定域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。 有关向拓扑中添加前端池的详细信息，请参阅部署文档中的[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。

> [!IMPORTANT]
> 请注意，拓扑生成器指示池中可以有最多 20 台前端服务器。 支持的最大服务器数为 12。 您可以在结构中定义最多 20 个状态服务器，其中 12 个服务器可同时处于活动状态和联机。


