---
title: '通话设置仪表板的用户服务 (CQD) '
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要：了解 User 设置 Service，该服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: ec710b018e05ac887214d180bb76b847fec1cf10
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608039"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>通话设置仪表板的用户服务 (CQD) 
 
**摘要：** 了解 User 设置 Service，该服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
User 设置 Service 是通话质量仪表板存储库 API 的一部分。
  
## <a name="user-settings-service"></a>用户设置服务

用户设置是键值对，应用程序可以使用这些键值对来存储各种用途的元数据，包括基于每个用户的应用程序行为的自定义。 每个用户会收到一个存储，用于存储用户设置。 只有所有者才能添加、修改和删除用户设置。
  
 **全局设置**
  
全局设置是系统用户拥有的用户设置，所有用户均具有对这些设置的只读访问权限。 全局设置是常量：它们是在存储库创建期间创建的，并且永远不会更改。
  
每个用户都可以通过使用相同的键创建用户设置来覆盖全局设置。 当应用程序请求有效的用户设置时，API 将返回一组与用户设置合并的全局设置，如果键相同，则每个用户的设置将取代各自的全局设置。 API 还可以仅返回用户设置，以便应用程序可以找出被覆盖的设置。 
  
REST 操作包含在下表中。

|**操作**|**说明**|
|:-----|:-----|
|[获取用户设置](get-user-settings.md) <br/> |Get User 设置返回指定用户的设置列表。  <br/> |
|[获取用户设置](get-user-setting.md) <br/> |获取用户设置返回单个用户设置。  <br/> |
   

