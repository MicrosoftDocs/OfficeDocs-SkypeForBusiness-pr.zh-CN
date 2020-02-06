---
title: 添加受信任应用程序池 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 若要定义受信任的应用程序池完全限定的域名（FQDN），请指定以下内容：
ms.openlocfilehash: 5dcf5317c3234db310ed7b80bca6403190690348
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820564"
---
# <a name="add-trusted-application-pool-fqdn"></a>添加受信任应用程序池 FQDN
 
若要定义受信任的应用程序池完全限定的域名（FQDN），请指定以下内容：
  
将托管受信任的应用程序的服务器或服务器池的 FQDN。
  
如果要为受信任的应用程序部署负载平衡和高可用性的服务器池，或者选择 "**单个计算机池**" （如果不需要负载平衡或高可用性），请选择 "**多台计算机池**"。
  
> [!IMPORTANT]
> 一个受信任的应用程序服务器稍后无法转换为服务器池。 如果你认为将来可能需要一个池，你可以部署包含一台计算机的多个服务器池，并根据需要添加服务器。 
  
有关受信任的应用程序池的详细信息，请参阅[CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。
  

