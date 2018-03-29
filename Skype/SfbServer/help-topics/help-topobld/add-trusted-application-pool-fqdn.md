---
title: 添加受信任的应用程序池的 FQDN
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 要定义受信任的应用程序池完全合格的域名称 (FQDN)，请指定以下项：
ms.openlocfilehash: af21ab09797a5b81f2071a37a2668d556f0a4012
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-trusted-application-pool-fqdn"></a>添加受信任的应用程序池的 FQDN
 
要定义受信任的应用程序池完全合格的域名称 (FQDN)，请指定以下项：
  
服务器将承载受信任的应用程序池或服务器的 FQDN。
  
如果您正在部署一个池的负载平衡和高可用性，从受信任的应用程序服务器或选择**单台计算机池**，如果您不需要负载平衡或高可用性，请选择**多个计算机池**。
  
> [!IMPORTANT]
> 单个受信任的应用程序服务器不能转换为更高版本的服务器池。 如果您认为将来可能需要一个池，可以部署多个服务器池中包含一台计算机，并添加服务器时所需。 
  
有关受信任的应用程序池的详细信息，请参阅[新建 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。
  

