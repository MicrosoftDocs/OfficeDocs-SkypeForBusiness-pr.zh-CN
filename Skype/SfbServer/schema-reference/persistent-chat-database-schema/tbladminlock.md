---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行某些管理员命令所需的管理员锁定。
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 包含运行某些管理员命令所需的管理员锁定。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |日期时间不为空  <br/> |锁定到期日期和时间。 所有者可以定期扩展此值。  <br/> |
|lockServerID  <br/> |int，不为空  <br/> |拥有的锁的服务器 ID。  <br/> |
|lockActorID  <br/> |int，不为空  <br/> |拥有的锁的主要用户的 ID。  <br/> |
   

