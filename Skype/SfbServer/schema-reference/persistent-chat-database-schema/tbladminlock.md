---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行某些管理员命令所需的管理员锁。
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814690"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 包含运行某些管理员命令所需的管理员锁。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime，not null  <br/> |锁定到期日期和时间。 所有者可以定期延长此值。  <br/> |
|lockServerID  <br/> |int，not null  <br/> |拥有锁定的服务器的 ID。  <br/> |
|lockActorID  <br/> |int，not null  <br/> |拥有锁定的主体的 ID。  <br/> |
   

