---
title: 一组 CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Set-CcExternalCertificateFilePath cmdlet 指定中介服务器或边缘服务器的证书的存储路径。
ms.openlocfilehash: 89216fb2b56130dd76b711a483c6279ac1073392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccexternalcertificatefilepath"></a>一组 CcExternalCertificateFilePath
 
Set-CcExternalCertificateFilePath cmdlet 指定中介服务器或边缘服务器的证书的存储路径。
  
在部署过程中或添加 Skype for Business 云连接器版本的新设备时，需要此证书。该命令还用于在部署后为中介服务器导入新证书。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例设置边缘服务器的证书路径：
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>示例 2

以下示例设置中介服务器的证书路径：
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>示例 3

以下示例更新中介服务器的证书：
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

在部署过程中或修改拓扑时，需要为边缘服务器证书指定路径，也可以选择为中介服务器证书指定路径。 
  
如果将在网关与中介服务器之间使用 TLS，需要中介服务器的证书。 当您部署云接头装置并希望部署 TLS 时，您只能指定中介服务器上部署证书的路径。 但是，如果你希望更新已部署的设备上的中介证书，则需要指定路径和 -Import 参数。 要查看参数，请使用 Get-CCExternalCertificateFilePath cmdlet。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| 目标 <br/> | 必需 <br/> |System.String  <br/> |要求的文件路径类型。类型包括：  <br/> EdgeServer（默认设置）  <br/> MediationServer  <br/> |
|导入  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |指示必须将证书导入中介服务器。如果是首次部署设备，则不需要此参数。如果你要更改已部署的版本上的现有证书，则需要此参数。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

Set-CcExternalCertificateFilePath cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[获得 CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

