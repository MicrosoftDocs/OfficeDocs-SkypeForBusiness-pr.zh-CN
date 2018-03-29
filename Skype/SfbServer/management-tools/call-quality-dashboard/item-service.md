---
title: 项目服务呼叫质量仪表板 (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 摘要： 了解项目服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 218fdb4f2c4b3d73fb4e7f78b5679b66eecf34cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>项目服务呼叫质量仪表板 (CQD)
 
**摘要：**了解项目服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
此项服务是呼叫质量仪表板存储库 API 的一部分。
  
## <a name="item-service"></a>项目服务

知识库 API 提供了简单的内容管理服务，称为项服务，可用于存储用户的任何应用程序定义的内容。 
  
系统的内容是系统用户所拥有的并具有只读访问权限的所有用户都共享。 专用的用户内容均由普通用户，并只有所有者才可以修改或删除它们，但所有用户仍然都有它们的只读访问权限。
  
> [!NOTE]
> 此 API 文档介绍存储库 API 的只读的操作。 
  
通话质量仪表板以项的形式保存的报告和查询知识库数据库中。 一个项目可以有可选的子项目，并呼叫质量仪表板使用子项目功能层次结构中组织的报告和查询。
  
项目服务包括以下概念：
  
- **项目**的存储库的基本元素。 每个项由一个用户拥有。
    
- **子项目**-存储库中的基本组织结构。 项可以有零，一个或多个从属项。
    
- **项上级**的项目，开始从最上面的项目，这是默认的用户来说，通向给定项的项的列表。
    
- **项目内容**的项中存储的特定于应用程序的内容。 通话质量仪表板中内容保存报告和查询的 JSON 的表示。
    
下表中包括的其余操作。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取项](get-items.md) <br/> |在存储库中获取项目返回所有项。  <br/> |
|[获取项](get-item.md) <br/> |获取项返回的特定项。  <br/> |
|[获取子项目](get-sub-items.md) <br/> |获取子项目返回特定项的子项。  <br/> |
|[获取项的祖先](get-item-ancestors.md) <br/> |获取项上级返回特定项的祖先。  <br/> |
|[更新项目](update-item.md) <br/> |更新存储库中的特定项。  <br/> |
   

