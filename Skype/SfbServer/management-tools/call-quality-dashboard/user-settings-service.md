---
title: 呼叫质量仪表板 (CQD) 的用户设置服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '摘要: 了解 "用户设置" 服务, 该服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274483"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>呼叫质量仪表板 (CQD) 的用户设置服务
 
**摘要:** 了解 "用户设置" 服务, 该服务是 "呼叫质量" 仪表板的 "存储库 API" 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。
  
## <a name="user-settings-service"></a>用户设置服务

用户设置是一些键值对, 应用程序可用于存储元数据以实现各种用途, 包括根据用户自定义应用程序行为。 每个用户都收到用户设置的存储空间。 只有所有者才能添加、修改和删除用户设置。
  
 **全局设置**
  
全局设置是系统用户拥有的用户设置, 并且所有用户都对其具有只读访问权限。 全局设置是常量: 它们是在创建存储库期间创建的, 它们永远不会更改。
  
每个用户都可以通过使用相同的密钥创建用户设置来覆盖全局设置。 当应用程序请求有效的用户设置时, API 将返回一组与用户设置合并的全局设置, 并且如果键相同, 则每个用户设置都将取代各自的全局设置。 API 还可以仅返回用户设置, 以便应用程序可以确定哪些设置被重写。 
  
下表中包括其余操作。

|**操作**|**说明**|
|:-----|:-----|
|[获取用户设置](get-user-settings.md) <br/> |获取用户设置返回指定用户的设置列表。  <br/> |
|[获取用户设置](get-user-setting.md) <br/> |获取用户设置返回单个用户设置。  <br/> |
   

