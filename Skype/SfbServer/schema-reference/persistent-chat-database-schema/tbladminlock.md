---
title: tblAdminLock
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行一些管理员命令所需的管理员锁。
---

# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 包含运行一些管理员命令所需的管理员锁。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime，不为 null  <br/> |锁到期日期和时间。所有者可以定期延长该值。  <br/> |
|lockServerID  <br/> |int，不为 null  <br/> |拥有锁的服务器的 ID。  <br/> |
|lockActorID  <br/> |int，不为 null  <br/> |拥有锁的主体的 ID。  <br/> |
   

