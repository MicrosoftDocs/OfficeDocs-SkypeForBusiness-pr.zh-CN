---
title: 用户设置服务呼叫质量仪表板 (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要： 了解用户设置服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: fe51c96546903e09f28ffadf06451efc8c1a88b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>用户设置服务呼叫质量仪表板 (CQD)
 
**摘要：**了解用户设置服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
用户设置服务被呼叫质量仪表板存储库 API 的一部分。
  
## <a name="user-settings-service"></a>用户设置服务

用户设置被应用程序可用于多种目的，包括自定义应用程序行为每个用户为基础的存储元数据的键 / 值对。 每个用户将收到为用户设置存储。 只有所有者才可以添加、 修改和删除用户的设置。
  
 **全局设置**
  
全局设置是系统用户，拥有的用户设置，所有用户都有只读访问它们。 全局设置为常量： 在存储库中创建，创建它们，它们永远不会更改。
  
每个用户可以通过创建具有相同键的用户设置覆盖全局设置。 当应用程序请求的有效用户设置时，该 API 返回一套合并在一起的用户设置，与每个用户设置取代各自全局设置如果键相同的全局设置。 API 还可以返回的用户设置，以便应用程序可以找出哪些设置将重写。 
  
下表中包括的其余操作。

|**操作**|**说明**|
|:-----|:-----|
|[获取用户设置](get-user-settings.md) <br/> |获取用户设置返回设置为指定的用户的列表。  <br/> |
|[获取用户的设置](get-user-setting.md) <br/> |获取用户设置返回的单个用户设置。  <br/> |
   

