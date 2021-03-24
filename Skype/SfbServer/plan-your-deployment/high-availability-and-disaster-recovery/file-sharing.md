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
ms.openlocfilehash: f47d8207969063472af23d898ef8a52c2383df0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093090"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Skype for Business Server 中的文件共享高可用性
 
了解如何使用 DFS 确保 Skype for Business Server 中文件共享的高可用性。
  
为了确保文件共享在 Skype for Business Server 部署中的高可用性，可以使用分布式文件系统 (DFS) 。 DFS 支持同一个数据中心内从一个文件服务器到另一个文件服务器的故障转移。 对于大型部署，建议您使用通过 DFS 配对的专用文件服务器。 有关 DFS 中 DFS Windows Server 2012，请参阅 [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) 。 有关 Windows Server 2008 上的 DFS 的信息，请参阅 [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) 。
  
根据您的网络规模和所需的恢复工作量，可以使用一对服务器来承载一个站点中的所有文件共享，也可以为每个前端池使用一对服务器。
  
DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。 DFS 服务器之间的故障转移应快速完成，但数据复制延迟可能会阻止用户在故障转移发生时继续工作。
  
如果在文件共享上使用 DFS 和数据存储至关重要，应经常备份文件共享，如每 4 到 8 小时备份一次。 如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。
