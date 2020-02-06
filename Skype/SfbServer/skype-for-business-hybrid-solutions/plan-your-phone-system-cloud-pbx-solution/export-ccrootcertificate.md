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
description: 'Export-CcRootCertificate cmdlet 用于将根 CA 证书导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。 '
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800912"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Export-CcRootCertificate cmdlet 用于将根 CA 证书导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。  
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将 Path 参数设置为目录路径，而非文件路径。 它将生成文件 c:\test\CCERootCertificates.p7b。
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

使用 Export-CcRootCertificate cmdlet 可以将根和中间证书保存到文件路径。 这在发生灾难恢复的情况下很有用。  
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|路径  <br/> |必需  <br/> |System.String  <br/> |将存储证书的文件路径。   <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Export-CcRootCertificate cmdlet 不接受通过管道传递的输入。  
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

