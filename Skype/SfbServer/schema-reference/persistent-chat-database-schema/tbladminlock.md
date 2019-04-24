---
title: tblAdminLock
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行一些管理员命令所需的管理员锁。
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212661"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 包含运行一些管理员命令所需的管理员锁。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime，不为 null  <br/> |锁定到期日期和时间。 所有者可以定期扩展此值。  <br/> |
|lockServerID  <br/> |int，不为 null  <br/> |拥有锁的服务器的 ID。  <br/> |
|lockActorID  <br/> |int，不为 null  <br/> |拥有锁的主体的 ID。  <br/> |
   

