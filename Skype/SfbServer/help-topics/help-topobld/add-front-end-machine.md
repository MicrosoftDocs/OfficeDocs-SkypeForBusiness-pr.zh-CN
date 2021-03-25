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
ms.openlocfilehash: b100cfd933f19c87213fa48d4d030eda52e90dc8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119761"
---
# <a name="add-front-end-machine"></a>添加前端计算机

指定在该池中要添加为前端服务器的每台计算机的完全限定域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。 有关向拓扑中添加前端池的详细信息，请参阅部署文档中的[定义和配置前端池](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)。

> [!IMPORTANT]
> 请注意，拓扑生成器指示池中最多可以有 20 台前端服务器。 支持的最大服务器数为 12 台。 构造中可定义最多 20 个状态服务器，其中 12 个服务器可以处于活动状态且随时联机。