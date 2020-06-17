---
title: 删除旧存档和监控服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果您的旧部署包含存档服务器或监视服务器，则在迁移到 Skype for Business Server 2019 之后，可以从旧环境中删除这些服务器，前提是所有用户都已从任何剩余的旧池中删除。 可以任意顺序删除存档服务器或监控服务器。 关键要求是所有用户均已从其余任何旧池中删除。
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752164"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>删除旧存档和监控服务器

如果您的旧部署包含存档服务器或监视服务器，则在迁移到 Skype for Business Server 2019 之后，可以从旧环境中删除这些服务器，前提是所有用户都已从任何剩余的旧池中删除。 可以任意顺序删除存档服务器或监控服务器。 关键要求是所有用户均已从其余任何旧池中删除。
  
您可以按照[第4阶段：将测试用户移动到试点池](phase-4-move-test-users-to-the-pilot-pool.md)中所述的过程，将用户移动到 Skype For business Server 2019。
  
确认所有用户都已从任何剩余的池中删除后，decommision 服务器并删除角色。 一个已过期但相关的示例是 "卸载 Microsoft Lync Server 并删除服务器角色"，可以从下载 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) 。
  

