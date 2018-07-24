---
title: 添加边缘计算机内部 IP 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 此页用于指定的内部 IP 地址和内部完全限定的域名 (FQDN) 边缘服务器。
ms.openlocfilehash: 1caa3dba0b1b40d7f207b10da2075082face12b0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987710"
---
# <a name="add-edge-machine-internal-ip-2010"></a>添加边缘计算机内部 IP 2010
 
此页用于指定的内部 IP 地址和内部完全限定的域名 (FQDN) 边缘服务器。
  
- 在**内部 IPv4 地址**框中，键入要向池中添加边缘服务器的 IP 地址。
    
- 在**内部 FQDN**中，键入要向池中添加边缘服务器的完全限定的域名 (FQDN)。
    
您指定的 FQDN 必须与服务器配置的计算机名称相同。 默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。 拓扑生成器使用 FQDN，而不是短名称。 因此，您必须在要部署为边缘服务器的未加入域的计算机的名称配置域名系统 (DNS) 后缀。 有关向计算机名称添加 DNS 后缀的详细信息，请参阅[配置边缘支持的 DNS](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)
  

