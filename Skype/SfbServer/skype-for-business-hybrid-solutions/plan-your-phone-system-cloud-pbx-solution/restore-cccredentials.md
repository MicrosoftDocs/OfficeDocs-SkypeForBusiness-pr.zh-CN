---
title: 还原-CcCredentials
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: 还原抄送凭据 cmdlet 将恢复商务云连接器版部署当前 Skype 的所有凭据。
ms.openlocfilehash: 045d7f651408b1cbdbd508966da3272ac61d7c04
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="restore-cccredentials"></a>还原-CcCredentials
 
还原抄送凭据 cmdlet 将恢复商务云连接器版部署当前 Skype 的所有凭据。 
  
此 cmdlet 适用于 Skype 业务云连接器版本 2.1。
  
```

Restore-CcCredentials 
```

## <a name="detailed-description"></a>详细说明

还原 CcCredentials cmdlet 清理所有凭据，并提示您重新输入所有用于业务云连接器部署当前 Skype 的凭据。
  
## <a name="parameters"></a>参数

无
  
## <a name="input-types"></a>输入类型

无。 还原-CcCredentials cmdlet 不接受管道的输入。
  
## <a name="return-types"></a>返回类型

无。
  
## <a name="example"></a>示例

下面的示例将恢复云连接器当前部署的所有凭据：
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>另请参阅

[获得 CcCredential](get-cccredential.md)
  
[一组 CcCredential](set-cccredential.md)
  

