---
title: 添加前端机器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: 指定要添加为此池中的前端服务器的每台计算机的完全限定的域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后, 更改 FQDN 需要先在拓扑生成器中删除服务器, 然后使用新的 FQDN 将新服务器添加到池中。 有关将前端池添加到拓扑的详细信息, 请参阅在部署文档中定义和配置前端池。
ms.openlocfilehash: a97437f9775c603ca768403f44699cfffc069fbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281477"
---
# <a name="add-front-end-machine"></a>添加前端机器

指定要添加为此池中的前端服务器的每台计算机的完全限定的域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后, 更改 FQDN 需要先在拓扑生成器中删除服务器, 然后使用新的 FQDN 将新服务器添加到池中。 有关将前端池添加到拓扑的详细信息, 请参阅在部署文档中[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。

> [!IMPORTANT]
> 请注意, 拓扑生成器指示池中最多可以有20个前端服务器。 支持的最大服务器数为12。 结构中最多可以有20个 statefull 服务器, 其中12个服务器在任何时间都处于活动状态且处于联机状态。


