---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 此Set-CcCredential cmdlet 设置当前部署Skype for Business 云连接器版本凭据。
ms.openlocfilehash: fa0d5f69e3263d273fabe17ae74ea46e0af40908
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617658"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
此Set-CcCredential cmdlet 设置当前部署Skype for Business 云连接器版本凭据。 
  
通过云连接器 2.0 版和更高版本，此 cmdlet 还可以为虚拟机管理员和域管理员设置帐户信息。
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例指定租户管理员的帐户名称和密码：
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

the Set-CcCredential cmdlet sets the account name and password for the tenant administrator. 对于 2.0 以前的版本，此管理员必须是全局管理员。 云连接器使用此帐户获取配置信息、设置配置参数，以及将设备状态更新为Microsoft 365或Office 365配置。 在 2.0 版和更高版本中，您还可以使用此 cmdlet 更新 VmAdmin 和 DomainAdmin 帐户的密码。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 必需 <br/> |System.String  <br/> | 参数值必须为"TenantAdmin"、"VmAdmin"或"DomainAdmin"。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Set-CcCredential cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

