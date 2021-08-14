---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 此Export-CcRootCertificate cmdlet 将根 CA 证书导出到主机服务器上Skype for Business 云连接器版本文件。
ms.openlocfilehash: 04ba7af5801f124a76e515b311a0507e3cbb764a6f2769d9f1d9080ec8c7d9d9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326248"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
此Export-CcRootCertificate cmdlet 将根 CA 证书导出到主机服务器上Skype for Business 云连接器版本文件。 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将 Path 参数设置为目录路径，而不是文件路径。 它生成文件 c：\test\CCERootCertificates.p7b。
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

此Export-CcRootCertificate cmdlet 允许您将根证书和中间证书保存到文件路径。 对于灾难恢复方案，这非常有用。 
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |必需  <br/> |System.String  <br/> |将存储证书的文件路径。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Export-CcRootCertificate cmdlet 不接受通过管道的输入。 
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

