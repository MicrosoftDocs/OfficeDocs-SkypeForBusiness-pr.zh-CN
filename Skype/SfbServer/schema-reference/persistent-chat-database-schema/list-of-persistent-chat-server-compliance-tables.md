---
title: 持久聊天服务器合规性表的列表Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持久聊天合规性数据库架构由下表组成。
ms.openlocfilehash: 673fe278f4b68af5e5d46925a6ef6184cb8cd47b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771888"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>持久聊天服务器合规性表的列表Skype for Business Server
 
持久聊天合规性数据库架构由下表组成。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>持久聊天服务器合规性表的列表

|**Table**|**说明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |包含已配置的适配器尚未处理的合规性事件。  <br/> 此表包括与持久聊天相关的事件，如聊天消息和文件下载。  (参与者事件由 tblComplianceParticipant 表.)   <br/> （处理该表中的事件的服务器列在 tblComplianceFanout 表中。）  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |包含处理合规性事件的服务器。该表与 tblComplianceData 表联系紧密。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |包含每个聊天服务和每台服务器的当前参与者。 它基于从持久聊天服务收到的加入和部分合规性事件进行维护。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |包含池范围的合规性状态信息。  <br/> |
   

