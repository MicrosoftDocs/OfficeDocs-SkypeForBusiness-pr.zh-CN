---
title: '呼叫质量仪表板项目服务 (CQD) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 摘要：了解项目服务，它是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 3be67c2455a299c6643238b966c9cb04545bc5d6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628664"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>呼叫质量仪表板项目服务 (CQD) 
 
**摘要：** 了解项目服务，它是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
项目服务是通话质量仪表板存储库 API 的一部分。
  
## <a name="item-service"></a>项目服务

存储库 API 提供了一个简单的内容管理服务（称为项目服务）来存储用户的任何应用程序定义的内容。 
  
系统内容归系统用户所有，并且由具有只读访问权限的所有用户共享。 专用用户内容归常规用户所有，只有所有者可以修改或删除这些内容，但所有用户仍具有对这些内容的只读访问权限。
  
> [!NOTE]
> 此 API 文档介绍了存储库 API 的只读操作。 
  
呼叫质量仪表板将报告和查询保存为存储库数据库中的项目。 项目可以具有可选的子项目，呼叫质量仪表板使用子项目功能在层次结构中组织报表和查询。
  
项目服务包括以下概念：
  
- **Item** - 存储库的基本元素。 每个项目只归一个用户所有。
    
- **子项** - 存储库的基本组织机制。 项目可以有零个、一个或多个从属项目。
    
- **项目上级** - 项目列表，从最顶端的项开始，这是用户的默认项，可引导到给定的项。
    
- **项目内容** - 存储在"项"中的特定于应用程序的内容。 呼叫质量仪表板将报告和查询的 JSON 表示形式保存在内容中。
    
REST 操作包含在下表中。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取项目](get-items.md) <br/> |Get Items 返回存储库中的所有项。  <br/> |
|[获取项目](get-item.md) <br/> |Get Item 返回特定 Item。  <br/> |
|[获取子项](get-sub-items.md) <br/> |获取Sub-Items返回特定项目的子项。  <br/> |
|[获取项目上级](get-item-ancestors.md) <br/> |获取项目上级返回特定项的上级。  <br/> |
|[更新项目](update-item.md) <br/> |更新存储库中的特定项。  <br/> |
   

