---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行一些管理员命令所需的管理员锁。
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809882"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 包含运行一些管理员命令所需的管理员锁。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime，不为 null  <br/> |锁到期日期和时间。所有者可以定期延长该值。  <br/> |
|lockServerID  <br/> |int，不为 null  <br/> |拥有锁的服务器的 ID。  <br/> |
|lockActorID  <br/> |int，不为 null  <br/> |拥有锁的主体的 ID。  <br/> |
   

