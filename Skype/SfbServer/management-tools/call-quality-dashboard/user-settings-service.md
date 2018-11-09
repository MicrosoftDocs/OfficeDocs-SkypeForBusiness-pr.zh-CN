---
title: 呼叫质量仪表板 (CQD) 的用户设置服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要： 了解用户设置服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 00d0662e777ef2f13c9783fe4b79d5c582faa8af
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035608"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>呼叫质量仪表板 (CQD) 的用户设置服务
 
**摘要：** 了解用户设置服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
用户设置服务是呼叫质量仪表板的存储库 API 的一部分。
  
## <a name="user-settings-service"></a>用户设置服务

用户设置是应用程序可用于多种目的，包括自定义应用程序行为每个用户分别为存储元数据的键 / 值对。 每个用户收到用户设置的存储。 只有所有者可以添加、 修改和删除用户设置。
  
 **全局设置**
  
全局设置是由系统用户拥有的用户设置，所有用户都具有对它们的只读访问。 全局设置的常量： 创建存储库在创建期间，以及它们永远不会更改。
  
通过使用相同的密钥创建用户设置，每个用户可以覆盖全局设置。 当应用程序请求的有效用户设置时，API 返回一组与取代各自全局设置键时相同的每个用户设置的用户设置，合并的全局设置。 API 还可以返回的用户设置，以便应用程序可以找出将重写的设置。 
  
下表中包含的其余部分操作。

|**操作**|**说明**|
|:-----|:-----|
|[获取用户设置](get-user-settings.md) <br/> |获取用户设置返回指定用户的设置的列表。  <br/> |
|[获取用户设置](get-user-setting.md) <br/> |获取用户设置返回的单个用户设置。  <br/> |
   

