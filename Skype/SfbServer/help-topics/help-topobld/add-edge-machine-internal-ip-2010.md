---
title: 添加边缘机内部 IP 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 使用此页可以指定的内部 IP 地址和边缘服务器的内部完全合格的域名称 (FQDN)。
ms.openlocfilehash: 2fedde361e252d400f4362add4757df3f0c40057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-machine-internal-ip-2010"></a>添加边缘机内部 IP 2010
 
使用此页可以指定的内部 IP 地址和边缘服务器的内部完全合格的域名称 (FQDN)。
  
- 在**内部的 IPv4 地址**中，键入您想要添加到池中的边缘服务器的 IP 地址。
    
- 在**内部的 FQDN**，键入您想要添加到池中的边缘服务器的完全合格的域名称 (FQDN)。
    
您指定的 FQDN 必须与服务器配置的计算机名称相同。 默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。 拓扑生成器使用 FQDN，而不是短名称。 因此，您必须配置域名系统 (DNS) 后缀作为未加入到域边缘服务器进行部署的计算机的名称。 有关将 DNS 后缀添加到计算机名称的详细信息，请参阅[边缘支持配置 DNS](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)
  

