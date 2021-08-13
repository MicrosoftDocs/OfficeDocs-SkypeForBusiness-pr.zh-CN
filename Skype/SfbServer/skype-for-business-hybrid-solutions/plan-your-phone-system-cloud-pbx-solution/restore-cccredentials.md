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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Restore Cc-Credentials cmdlet 可还原当前部署Skype for Business 云连接器版本凭据。
ms.openlocfilehash: 95b93e28bb109c26927a940324edef20479bed8c193efea6923c74058995a5bd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340668"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Restore Cc-Credentials cmdlet 可还原当前部署Skype for Business 云连接器版本凭据。 
  
此 cmdlet 适用于 Skype for Business 云连接器版本 2.1。
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>详细说明

the Restore-CcCredentials cmdlet cleans all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.
  
## <a name="parameters"></a>参数

无
  
## <a name="input-types"></a>输入类型

无。 Restore-CcCredentials cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型

无。
  
## <a name="example"></a>示例

以下示例还原当前云连接器部署的所有凭据：
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>另请参阅

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

