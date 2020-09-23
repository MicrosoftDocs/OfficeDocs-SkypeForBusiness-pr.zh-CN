---
title: 添加边缘计算机内部 IP 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 使用此页指定边缘服务器的内部 IP 地址和内部完全限定域名 (FQDN)。
ms.openlocfilehash: 857e2041779efd02007939b7046860cc295cb7b8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219373"
---
# <a name="add-edge-machine-internal-ip-2010"></a>添加边缘计算机内部 IP 2010

使用此页指定边缘服务器的内部 IP 地址和内部完全限定域名 (FQDN)。

- 在 " **内部 IPv4 地址**" 中，键入要添加到池中的边缘服务器的 IP 地址。

- 在 " **内部 FQDN**" 中，键入要添加到池的边缘服务器 (FQDN) 的完全限定的域名称。

指定的 FQDN 必须与在服务器上配置的计算机名称相同。 默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。 拓扑生成器使用 FQDN，而不是短名称。 因此，必须在要部署为未加入域的边缘服务器的计算机名称上配置域名系统 (DNS) 后缀。 有关向计算机名称添加 DNS 后缀的详细信息，请参阅[Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)。


