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
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 若要定义受信任的应用程序池完全限定的域名（FQDN），请指定以下内容：
ms.openlocfilehash: bb473aaab771038c0556234d865edcb19eca23f8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697957"
---
# <a name="add-trusted-application-pool-fqdn"></a>添加受信任应用程序池 FQDN
 
若要定义受信任的应用程序池完全限定的域名（FQDN），请指定以下内容：
  
将托管受信任的应用程序的服务器或服务器池的 FQDN。
  
如果要为受信任的应用程序部署负载平衡和高可用性的服务器池，或者选择 "**单个计算机池**" （如果不需要负载平衡或高可用性），请选择 "**多台计算机池**"。
  
> [!IMPORTANT]
> 一个受信任的应用程序服务器稍后无法转换为服务器池。 如果你认为将来可能需要一个池，你可以部署包含一台计算机的多个服务器池，并根据需要添加服务器。 
  
有关受信任的应用程序池的详细信息，请参阅[CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。
  

