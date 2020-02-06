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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Set-CcCredential cmdlet 用于设置当前 Skype for Business 云连接器版本部署的凭据。
ms.openlocfilehash: b7620a6d76415e4e2a49ea9bd628d1e1cba7f4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824206"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Set-CcCredential cmdlet 用于设置当前 Skype for Business 云连接器版本部署的凭据。 
  
借助云连接器版本2.0 和更高版本，此 cmdlet 还可以为虚拟机管理员和域管理员设置帐户信息。
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例为租户管理员指定帐户名称和密码：
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Set-CcCredential cmdlet 用于为租户管理员设置帐户名称和密码。 对于 2.0 版之前的版本，此管理员必须为 Office 365 全局管理员。 云连接器使用此帐户获取配置信息、设置配置参数，并将装置状态更新到 Office 365 租户配置。 使用版本2.0 和更高版本，你也可以使用此 cmdlet 更新 VmAdmin 和 DomainAdmin 帐户的密码。
  
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
  

