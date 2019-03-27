---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: 还原抄送凭据 cmdlet 还原所有业务云连接器 Edition 部署中的当前 Skype 的凭据。
ms.openlocfilehash: 0b790b9f2edab9fade2738c3c95348be864f9017
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891466"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
还原抄送凭据 cmdlet 还原所有业务云连接器 Edition 部署中的当前 Skype 的凭据。 
  
此 cmdlet 适用于 Skype 的业务云连接器 Edition 2.1。
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a>详细说明

还原 CcCredentials cmdlet 清除所有凭据，并提示您重新输入用于当前 Skype 商业云连接器部署的所有凭据。
  
## <a name="parameters"></a>参数

无
  
## <a name="input-types"></a>输入类型

无。 还原 CcCredentials cmdlet 不接受通过管道传递的输入。
  
## <a name="return-types"></a>返回类型

无。
  
## <a name="example"></a>示例

以下示例恢复所有凭据的当前云连接器部署：
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>另请参阅

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

