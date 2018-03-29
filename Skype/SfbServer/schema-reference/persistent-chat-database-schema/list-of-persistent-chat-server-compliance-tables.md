---
title: 持久的聊天服务器的法规遵从性中的表列表 Skype 业务服务器
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持续聊天的法规遵从性数据库架构包含，以下各表。
ms.openlocfilehash: 801e8d5457a26ef968f700df16a68d36560548c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>持久的聊天服务器的法规遵从性中的表列表 Skype 业务服务器
 
持续聊天的法规遵从性数据库架构包含，以下各表。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>持久的聊天服务器的法规遵从性表的列表

|**表**|**说明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |包含配置适配器尚未处理的法规遵从性事件。  <br/> 此表包括持久聊天相关的事件，如聊天消息和文件下载。 （参与者事件进行跟踪的 tblComplianceParticipant 表。）  <br/> （服务器处理此表中的事件表中列出 tblComplianceFanout。）  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |包含处理法规遵从性事件的服务器。 此表被紧密关联的 tblComplianceData 表。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |包含当前参与者每个聊天服务，每个服务器。 它维护基于联接和部分从持久聊天服务接收到的法规遵从性事件。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |包含池范围的法规遵从性状态的信息。  <br/> |
   

