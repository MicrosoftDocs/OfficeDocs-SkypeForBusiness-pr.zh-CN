---
title: 呼叫质量仪表板 (CQD) 的项服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 摘要： 了解项服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 5e5198afd95d6c9e1de517054053b724a54b1105
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035622"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>呼叫质量仪表板 (CQD) 的项服务
 
**摘要：** 了解项服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
项服务是呼叫质量仪表板的存储库 API 的一部分。
  
## <a name="item-service"></a>项服务

存储库 API 提供了一个简单的内容管理服务，亦称项服务，可用于存储用户的任何应用程序定义的内容。 
  
系统的内容是由系统用户拥有，由具有只读访问权限的所有用户共享。 专用的用户内容归一般用户和只有所有者可以修改或删除，但所有用户仍都具有对它们的只读访问。
  
> [!NOTE]
> 此 API 文档介绍存储库 API 的只读的操作。 
  
呼叫质量仪表板可将报告和查询保存为项目，在存储库数据库中。 项目可具有可选子项目，并且呼叫质量仪表板以使用子项功能层次结构组织报告和查询。
  
项服务包括以下概念：
  
- **项目**的存储库的基本元素。 由准确按照一用户拥有每个项目。
    
- **子项目**的存储库的基本组织机制。 项目可具有零，一个或多个从属项目。
    
- **项目祖先**-项目，开始从顶层项目，这是默认的用户，从而给定项的项的列表。
    
- **项目内容**-存储项中的特定于应用程序的内容。 呼叫质量仪表板中内容将保存报告和查询的 JSON 表示的形式。
    
下表中包含的其余部分操作。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取项](get-items.md) <br/> |在存储库中获取项目返回的所有项目。  <br/> |
|[获取项目](get-item.md) <br/> |获取项返回的特定项目。  <br/> |
|[获取子项](get-sub-items.md) <br/> |获取子项目返回的特定项目的子项目。  <br/> |
|[获取项祖先](get-item-ancestors.md) <br/> |获取项祖先返回特定项目的上级。  <br/> |
|[更新项](update-item.md) <br/> |更新存储库中的特定项目。  <br/> |
   

