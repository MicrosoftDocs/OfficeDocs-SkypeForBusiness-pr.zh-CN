---
title: 通话质量仪表板 (CQD) 的项目服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '摘要: 了解项目服务, 它是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274609"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>通话质量仪表板 (CQD) 的项目服务
 
**摘要:** 了解项目服务, 该服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。
  
## <a name="item-service"></a>项目服务

知识库 API 提供了一个简单的内容管理服务 (称为项目服务), 可用于为用户存储任何应用程序定义的内容。 
  
系统内容由系统用户拥有, 并且由具有只读访问权限的所有用户共享。 专用用户内容由普通用户拥有, 只有所有者可以修改或删除它们, 但所有用户仍具有对它们的只读访问权限。
  
> [!NOTE]
> 此 API 文档介绍知识库 API 的只读操作。 
  
通话质量仪表板将报表和查询保存为存储库数据库中的项目。 项目可以具有可选子项目, 而通话质量仪表板使用子项目功能组织报表和查询的层次结构。
  
项目服务包括以下概念:
  
- **Item** -存储库的基本元素。 每个项目仅归一个用户所有。
    
- **子项目**-存储库的基本组织结构。 项目可以有零个、一个或多个下属项目。
    
- **项目上级**-从最顶层项目 (即用户的默认项目) 开始, 指向给定项目的项目列表。
    
- **项目内容**-存储在项目中的特定于应用程序的内容。 通话质量仪表板在内容中保存报表和查询的 JSON 表示形式。
    
下表中包括其余操作。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取项目](get-items.md) <br/> |获取项目将返回存储库中的所有项目。  <br/> |
|[获取项目](get-item.md) <br/> |获取项目返回特定项目。  <br/> |
|[获取子项](get-sub-items.md) <br/> |获取子项目返回特定项目的子项目。  <br/> |
|[获取项目上级](get-item-ancestors.md) <br/> |获取项目祖先返回特定项目的上级。  <br/> |
|[更新项目](update-item.md) <br/> |更新存储库中的特定项目。  <br/> |
   

