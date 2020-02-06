---
title: Skype for Business 服务器中持久聊天服务器合规性表的列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持久聊天合规性数据库架构由下表组成。
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814760"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Skype for Business 服务器中持久聊天服务器合规性表的列表
 
持久聊天合规性数据库架构由下表组成。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>持久聊天服务器合规性表列表

|**表格**|**说明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |包含已配置的适配器尚未处理的合规性事件。  <br/> 此表包括与聊天相关的持久事件，例如聊天消息和文件下载。 （参与者事件由 tblComplianceParticipant 表跟踪。）  <br/> （处理此表中的事件的服务器在 tblComplianceFanout 表中列出。）  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |包含处理合规性事件的服务器。 此表与 tblComplianceData 表紧密耦合。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |包含每个聊天服务和每台服务器的当前参与者。 它根据从持久聊天服务接收的联接和部件合规性事件进行维护。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |包含池范围的合规性状态信息。  <br/> |
   

