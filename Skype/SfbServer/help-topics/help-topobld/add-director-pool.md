---
title: 添加导演池
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: 若要定义主任池的 FQDN，请选择将由两个或多个董事中的负载平衡池，组成多个计算机池或单个计算机池。 您还必须键入的完全合格的域名称 (FQDN) 将用来连接到总监池或单个控制器的 FQDN。 对于控制器的计算机的池，这将是一个硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享的 DNS 条目。
ms.openlocfilehash: d71219f6e9c51d69bee8d2457cc30c19f4fa6c89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-pool"></a>添加导演池
 
**定义控制器池的 FQDN**，请将由两个或多个董事中的负载平衡池，组成**多个计算机池**，或者**单个计算机池**。 您还必须键入的完全合格的域名称 (FQDN) 将用来连接到总监池或单个控制器的 FQDN。 对于控制器的计算机的池，这将是一个硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享的 DNS 条目。
  
> [!TIP]
> 如果打算在将来实现导演池，可选择**多个计算机池**。 即使池指两个或多个计算机的负载平衡，可以创建单个计算机池并创建池的 FQDN 的单个计算机。 当准备好以后向池中添加更多的计算机时，您必须运行拓扑生成器再次以定义新的池成员，发布新的拓扑，然后设置新导演池成员通过 Skype 业务服务器部署向导。 您还必须将新的池成员添加到该池的域名系统 (DNS) 负载平衡，适当的负载平衡器或硬件负载平衡器。 在许多情况下，将有两种负载平衡系统中的位置。 请确保同时添加新的成员服务器。 
  

