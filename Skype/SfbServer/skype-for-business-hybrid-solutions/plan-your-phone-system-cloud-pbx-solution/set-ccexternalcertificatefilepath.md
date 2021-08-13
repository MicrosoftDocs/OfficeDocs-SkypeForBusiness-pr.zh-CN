---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: 此Set-CcExternalCertificateFilePath cmdlet 指定存储中介服务器或边缘服务器的证书的路径。
ms.openlocfilehash: 7b9b494b27f3ed05dd1ef1cdb91bd583abf2d2b391f1a49c0b2615fd3485187c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344561"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
此Set-CcExternalCertificateFilePath cmdlet 指定存储中介服务器或边缘服务器的证书的路径。
  
此证书在部署期间或添加新设备时Skype for Business 云连接器版本。 该命令还允许在部署后导入中介服务器的新证书。
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例设置边缘服务器的证书路径：
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>示例 2

下一个示例设置中介服务器的证书路径：
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>示例 3

下一个示例更新中介服务器的证书：
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

在部署期间或修改拓扑时，需要指定边缘服务器证书的路径，并选择性地指定中介服务器证书的路径。 
  
如果在网关服务器和中介服务器之间使用 TLS，则 (服务器) 证书。 部署云连接器设备并想要部署 TLS 时，只能指定将在中介服务器上部署的证书的路径。 但是，如果要更新已部署的设备的中介证书，则需要指定路径和 -Import 参数。 若要查看路径，请使用 Get-CCExternalCertificateFilePath cmdlet。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| Target <br/> | 必需 <br/> |System.String  <br/> |请求的文件路径的类型。 类型包括：  <br/> EdgeServer (默认)   <br/> MediationServer  <br/> |
|导入  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |指示必须将证书导入中介服务器。 如果首次部署设备，则不需要此参数。 如果要更改已部署版本上的现有证书，则参数是必需的。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

Set-CcExternalCertificateFilePath cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

