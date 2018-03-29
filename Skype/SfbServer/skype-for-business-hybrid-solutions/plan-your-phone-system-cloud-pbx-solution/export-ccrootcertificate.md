---
title: 导出 CcRootCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Export-CcRootCertificate cmdlet 用于将根 CA 证书导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。
ms.openlocfilehash: 9af3701fd89cf881b4f966c2b00500ad4e55bc9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccrootcertificate"></a>导出 CcRootCertificate
 
Export-CcRootCertificate cmdlet 用于将根 CA 证书导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例将 Path 参数设置为目录路径，而非文件路径。 它将生成文件 c:\test\CCERootCertificates.p7b。
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

使用 Export-CcRootCertificate cmdlet 可以将根和中间证书保存到文件路径。 这在发生灾难恢复的情况下很有用。 
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|路径  <br/> |必需  <br/> |System.String  <br/> |将存储证书的文件路径。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Export-CcRootCertificate cmdlet 不接受通过管道传递的输入。 
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

