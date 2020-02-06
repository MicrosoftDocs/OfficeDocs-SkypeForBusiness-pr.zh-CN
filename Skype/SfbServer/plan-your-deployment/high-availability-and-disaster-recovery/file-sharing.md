---
title: Skype for Business 服务器中的文件共享高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 了解如何使用 DFS 确保 Skype for Business 服务器中文件共享的高可用性。
ms.openlocfilehash: c04c3acd009dd59a3894a62d08395db19c6d2368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815930"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Skype for Business 服务器中的文件共享高可用性
 
了解如何使用 DFS 确保 Skype for Business 服务器中文件共享的高可用性。
  
为确保 Skype for Business Server 部署中文件共享的高可用性，您可以使用分布式文件系统（DFS）。 DFS 支持从一台文件服务器故障转移到相同数据中心内的其他文件服务器。 对于大规模部署，我们建议您使用通过 DFS 配对的专用文件服务器。 有关 Windows Server 2012 中的 DFS 的详细信息， [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)请参阅。 有关 Windows Server 2008 上的 DFS 的详细信息[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)，请参阅。
  
根据你的网络大小以及所需的复原量，你可以使用一对服务器来托管网站中的所有文件共享，或者对每个前端池使用一对。
  
DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。 应快速完成 DFS 服务器之间的故障转移，但数据复制延迟可能会阻止用户在发生故障转移时继续进行工作。
  
如果需要在文件共享上使用 DFS 和数据存储，则应经常备份文件共享，如每 4 小时到 8 小时备份一次。如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。
  

