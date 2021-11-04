---
title: 添加信任的应用程序池 FQDN
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 要定义受信任应用程序池的完全限定的域名 (FQDN)，请指定以下内容：
ms.openlocfilehash: 2f08944c55d5a265c01f449c062a1e6d411cc533
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776792"
---
# <a name="add-trusted-application-pool-fqdn"></a>添加信任的应用程序池 FQDN
 
要定义受信任应用程序池的完全限定的域名 (FQDN)，请指定以下内容：
  
将托管受信任应用程序的服务器或服务器池的 FQDN。
  
如果要部署受信任应用程序服务器池以获取负载平衡和高可用性，请选择“多计算机池”，如果不需要负载平衡或高可用性，请选择“单计算机池”。
  
> [!IMPORTANT]
> 以后无法将单个受信任应用程序服务器转换成服务器池。如果认为将来可能需要池，则现在可以部署包含单个计算机的多服务器池并在需要时添加服务器。 
  
有关受信任应用程序池的详细信息，请参阅 [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。
