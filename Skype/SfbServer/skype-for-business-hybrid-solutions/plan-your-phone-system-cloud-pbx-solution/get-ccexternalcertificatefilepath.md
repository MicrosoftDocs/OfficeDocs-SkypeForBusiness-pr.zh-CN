---
title: 获得 CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Get-CcExternalCertificateFilePath cmdlet 将返回 Skype for Business 云连接器版本部署的外部证书文件路径。用户准备此证书。
ms.openlocfilehash: 9ceba99310ab25676a7cd3938ed386c4752f453e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccexternalcertificatefilepath"></a>获得 CcExternalCertificateFilePath
 
Get-CcExternalCertificateFilePath cmdlet 将返回 Skype for Business 云连接器版本部署的外部证书文件路径。用户准备此证书。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示了边缘服务器的证书路径：
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>示例 2

以下示例显示了为中介服务器设置的证书：
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

在部署期间或在修改拓扑时，需要为边缘服务器证书指定路径，也可以选择为中介服务器证书指定路径。如果将在网关与中介服务器之间使用 TLS，则需要中介服务器的证书。要更改路径，请使用 Set-CcExternalCertificateFilePath cmdlet。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|目标  <br/> |可选  <br/> | System.Management.Automation.SwitchParameter <br/> |要求的文件路径类型。类型包括：  <br/> EdgeServer（默认设置）  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

Get-CcExternalCertificateFilePath cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

该命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[一组 CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

