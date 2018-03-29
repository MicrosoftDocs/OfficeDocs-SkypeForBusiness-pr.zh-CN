---
title: Skype for Business Server 2015 中的文件共享高可用性
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 了解有关使用 DFS 的业务服务器确保高可用性的文件共享在 Skype。
ms.openlocfilehash: f96e4aaca70c501425528b12207eeab01027c9a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="file-sharing-high-availability-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的文件共享高可用性
 
了解有关使用 DFS 的业务服务器确保高可用性的文件共享在 Skype。
  
若要确保您 Skype 业务服务器部署中的文件共享的高可用性，您可以使用分布式文件系统 (DFS)。 DFS 支持从一台文件服务器故障转移到相同数据中心内的其他文件服务器。 对于大规模部署，我们建议您使用通过 DFS 配对的专用文件服务器。 在 DFS 中 Windows Server 2012 的详细信息，请参阅[https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)。 Windows Server 2008 上的 DFS 的信息，请参阅[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)。
  
根据您的网络的大小和复原所需的量，可以使用一对服务器来承载站点中的所有文件共享或使用每个前端池的一对。
  
DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。 应迅速完成 DFS 服务器之间进行故障切换，但数据复制延迟可能会阻止用户能够在发生故障切换时继续正在进行的工作。
  
如果需要在文件共享上使用 DFS 和数据存储，则应经常备份文件共享，如每 4 小时到 8 小时备份一次。如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。
  

