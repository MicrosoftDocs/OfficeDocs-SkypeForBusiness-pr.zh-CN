---
title: 添加受信任应用程序池 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定义受信任的应用程序池完全限定的域名（FQDN），请指定以下内容：
ms.openlocfilehash: 52b0e10246c9c54ed5c38a44816992d2dc17e1ef
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41787732"
---
# <a name="add-trusted-application-pool-fqdn"></a>添加受信任应用程序池 FQDN
 
若要定义受信任的应用程序池完全限定的域名（FQDN），请指定以下内容：
  
将托管受信任的应用程序的服务器或服务器池的 FQDN。
  
如果要为受信任的应用程序部署负载平衡和高可用性的服务器池，或者选择 "**单个计算机池**" （如果不需要负载平衡或高可用性），请选择 "**多台计算机池**"。
  
> [!IMPORTANT]
> 一个受信任的应用程序服务器稍后无法转换为服务器池。 如果你认为将来可能需要一个池，你可以部署包含一台计算机的多个服务器池，并根据需要添加服务器。 
  
有关受信任的应用程序池的详细信息，请参阅[CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。
  

