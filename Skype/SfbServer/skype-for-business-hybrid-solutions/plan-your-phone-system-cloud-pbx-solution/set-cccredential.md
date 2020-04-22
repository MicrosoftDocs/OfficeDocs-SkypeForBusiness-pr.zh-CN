---
title: Set-cccredential
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
description: Set-cccredential cmdlet 设置当前 Skype for Business 云连接器版本部署的凭据。
ms.openlocfilehash: a97d85ef6fec31383b349e9a0c3b3d9e25d04337
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780671"
---
# <a name="set-cccredential"></a>Set-cccredential
 
Set-cccredential cmdlet 设置当前 Skype for Business 云连接器版本部署的凭据。 
  
使用云连接器版本2.0 及更高版本，此 cmdlet 还可以为虚拟机管理员和域管理员设置帐户信息。
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例指定租户管理员的帐户名称和密码：
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Set-cccredential cmdlet 用于设置租户管理员的帐户名称和密码。 对于2.0 之前的版本，此管理员必须是全局管理员。 云连接器使用此帐户获取配置信息、设置配置参数并将设备状态更新为 Office 365 组织配置。 在版本2.0 及更高版本中，您还可以使用此 cmdlet 更新 VmAdmin 和 DomainAdmin 帐户的密码。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 必需 <br/> |System.String  <br/> | 参数值必须是 "TenantAdmin"、"VmAdmin" 或 "DomainAdmin"。 <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Set-cccredential cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-cccredential](get-cccredential.md)
  

