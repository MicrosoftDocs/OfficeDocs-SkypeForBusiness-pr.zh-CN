---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Restore Cc-凭据 cmdlet 用于还原当前 Skype for business Cloud Connector Edition 部署的所有凭据。
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003242"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Restore Cc-凭据 cmdlet 用于还原当前 Skype for business Cloud Connector Edition 部署的所有凭据。 
  
此 cmdlet 适用于 Skype for Business 云连接器版本2.1。
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>详细说明

Restore-CcCredentials cmdlet 将清理所有凭据，并提示你重新输入用于当前 Skype for Business 云连接器部署的所有凭据。
  
## <a name="parameters"></a>参数

无
  
## <a name="input-types"></a>输入类型

无。 Restore CcCredentials cmdlet 不接受流水线输入。
  
## <a name="return-types"></a>返回类型

无。
  
## <a name="example"></a>示例

以下示例将还原当前云连接器部署的所有凭据：
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>另请参阅

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

