---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Set-CcCredential cmdlet 用于设置当前 Skype for Business 云连接器版本部署的凭据。
ms.openlocfilehash: 547f0b87b006347a337a2c25222aecbd4f402669
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876639"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Set-CcCredential cmdlet 用于设置当前 Skype for Business 云连接器版本部署的凭据。 
  
使用云连接器 2.0 及更高版本，此 cmdlet 还可以设置的帐户信息的虚拟机管理员和域管理员。
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例为租户管理员指定帐户名称和密码：
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Set-CcCredential cmdlet 用于为租户管理员设置帐户名称和密码。 对于 2.0 版之前的版本，此管理员必须为 Office 365 全局管理员。 云连接器使用此帐户获取配置信息，请将配置参数和更新装置状态设置为 Office 365 租户配置。 使用版本 2.0 和更高版本，您还可以使用此 cmdlet 更新 VmAdmin 和 DomainAdmin 帐户的密码。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 必需 <br/> |System.String  <br/> | 参数值必须为“TenantAdmin”、“VmAdmin”或“DomainAdmin”。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Set-CcCredential cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

