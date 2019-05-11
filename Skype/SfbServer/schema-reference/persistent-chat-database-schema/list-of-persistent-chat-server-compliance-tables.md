---
title: 持久聊天服务器合规性中的表列表 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持久聊天合规性数据库架构由以下表组成。
ms.openlocfilehash: e17b2e52bdeb65ff4c77377cb913da212f20ecf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929887"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>持久聊天服务器合规性中的表列表 Skype 业务服务器
 
持久聊天合规性数据库架构由以下表组成。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>持久聊天服务器合规性表的列表

|**表格**|**说明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |包含配置的适配器尚未处理的合规性事件。  <br/> 此表包含持久聊天相关的事件，如聊天消息和文件下载。 （参与者事件跟踪由 tblComplianceParticipant 表。）  <br/> （处理该表中的事件的服务器排列 tblComplianceFanout 表中。）  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |包含处理合规性事件的服务器。 此表紧密结合 tblComplianceData 表。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |包含每个聊天服务和每台服务器的当前参与者。 维护根据从持久聊天服务接收的联接和部件合规性事件。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |包含池范围的合规性状态信息。  <br/> |
   

