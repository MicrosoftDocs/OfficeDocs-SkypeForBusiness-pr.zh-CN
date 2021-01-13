---
title: Skype for Business Server 中的文件共享高可用性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 了解如何使用 DFS 确保 Skype for Business Server 中文件共享的高可用性。
ms.openlocfilehash: 4d443425f453d63694511d13c6d3a84893058daa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802892"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Skype for Business Server 中的文件共享高可用性
 
了解如何使用 DFS 确保 Skype for Business Server 中文件共享的高可用性。
  
为了确保 Skype for Business Server 部署中文件共享的高可用性，可以使用分布式文件系统 (DFS) 。 DFS 支持同一个数据中心内从一个文件服务器到另一个文件服务器的故障转移。 对于大型部署，建议您使用通过 DFS 配对的专用文件服务器。 有关 DFS 中Windows Server 2012，请参阅 [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) 。 有关 Windows Server 2008 上的 DFS 的信息，请参阅 [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) 。
  
根据您的网络规模和所需的恢复工作量，可以使用一对服务器来承载一个站点中的所有文件共享，也可以为每个前端池使用一对服务器。
  
DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。 DFS 服务器之间的故障转移应快速完成，但数据复制延迟可能会阻止用户在故障转移发生时继续工作。
  
如果使用 DFS 且文件共享上的数据存储至关重要，您应经常备份文件共享，例如每 4 到 8 小时备份一次。 如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。
  

