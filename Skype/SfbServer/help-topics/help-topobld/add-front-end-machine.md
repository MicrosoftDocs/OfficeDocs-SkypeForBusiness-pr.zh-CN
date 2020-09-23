---
title: 添加前端计算机
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
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 指定在该池中要添加为前端服务器的每台计算机的完全限定域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。 有关向拓扑中添加前端池的详细信息，请参阅部署文档中的定义和配置前端池。
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218313"
---
# <a name="add-front-end-machine"></a>添加前端计算机

指定在该池中要添加为前端服务器的每台计算机的完全限定域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。 有关向拓扑中添加前端池的详细信息，请参阅部署文档中的[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。

> [!IMPORTANT]
> 请注意，拓扑生成器指示可以在池中拥有最高20台前端服务器。 支持的最大服务器数为12个。 您最多可以在 fabric 中定义20个 statefull 服务器，其中12个服务器可以处于活动状态，并且可以在任何时间联机。


