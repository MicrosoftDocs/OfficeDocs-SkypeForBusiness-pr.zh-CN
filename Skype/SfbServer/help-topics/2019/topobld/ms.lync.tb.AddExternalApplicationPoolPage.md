---
title: 添加受信任应用程序池 FQDN
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 要定义受信任应用程序池完全限定的域名 (FQDN)，请指定以下内容：
ms.openlocfilehash: 1a6bd10d1091d5e3b494a5c20e3ff294c279ccba
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976849"
---
# <a name="add-trusted-application-pool-fqdn"></a>添加受信任应用程序池 FQDN
 
要定义受信任应用程序池完全限定的域名 (FQDN)，请指定以下内容：
  
服务器或服务器将承载受信任应用程序池的 FQDN。
  
如果您要部署的服务器从负载平衡和高可用性的受信任应用程序池，或选择**单计算机池**，如果您不需要负载平衡或高可用性，请选择**多计算机池**。
  
> [!IMPORTANT]
> 单一的受信任应用程序服务器无法转换为的更高版本服务器池。 如果您认为您将来可能需要一个池，您可以部署多个服务器池现在，包含一台计算机，并添加时所需的服务器。 
  
关于受信任应用程序池的详细信息，请参阅[New-cstrustedapplicationpool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。
  

