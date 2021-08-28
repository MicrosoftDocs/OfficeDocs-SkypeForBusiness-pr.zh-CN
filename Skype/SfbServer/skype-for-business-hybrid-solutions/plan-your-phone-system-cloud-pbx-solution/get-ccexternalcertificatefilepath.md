---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: 此Get-CcExternalCertificateFilePath cmdlet 返回用于部署Skype for Business 云连接器版本文件路径。 用户准备此证书。
ms.openlocfilehash: 9b06958d68d73bc68fc0fda4e681af2e7b9b4f9e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622034"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
此Get-CcExternalCertificateFilePath cmdlet 返回用于部署Skype for Business 云连接器版本文件路径。 用户准备此证书。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示边缘服务器的证书路径：
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>示例 2

以下示例显示中介服务器的证书集：
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

在部署期间或修改拓扑时，需要指定边缘服务器证书的路径，以及（可选）中介服务器的路径。 如果在网关服务器和中介服务器之间使用 TLS，则 (服务器) 证书。 若要更改路径，请使用 Set-CcExternalCertificateFilePath cmdlet。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|目标  <br/> |可选  <br/> | System.Management.Automation.SwitchParameter <br/> |请求的文件路径的类型。 类型包括：  <br/> EdgeServer (默认)   <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

Get-CcExternalCertificateFilePath cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

该命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

