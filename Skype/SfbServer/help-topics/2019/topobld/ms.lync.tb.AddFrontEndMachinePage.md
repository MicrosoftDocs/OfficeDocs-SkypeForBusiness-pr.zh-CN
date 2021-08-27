---
title: 添加前端计算机
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: 指定要添加为此池中的前端服务器的每台计算机的完全限定域名 (FQDN)。将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。有关向拓扑中添加前端池的详细信息，请参阅部署文档中的定义和配置前端池。
ms.openlocfilehash: f1624a2e8abbba455abf0982c33730d95235e1f4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625404"
---
# <a name="add-front-end-machine"></a>添加前端计算机

指定要添加为此池中的前端服务器的每台计算机的完全限定域名 (FQDN)。将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。有关向拓扑中添加前端池的详细信息，请参阅部署文档中的[定义和配置前端池](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)。

> [!IMPORTANT]
> 请注意，拓扑生成器指示池中最多可以有 20 台前端服务器。 支持的最大服务器数为 12 台。 构造中可定义最多 20 个状态服务器，其中 12 个服务器可以处于活动状态且随时处于联机状态。