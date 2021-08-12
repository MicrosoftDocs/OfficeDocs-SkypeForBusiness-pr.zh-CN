---
title: Get-CcSiteLogDirectory
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
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 此Get-CcSiteLogDirectory cmdlet 显示存储网站级别日志的当前Skype for Business 云连接器版本目录。
ms.openlocfilehash: 7c15d0b715384fd18522122571da69f58a83ed337d46420e83f7ac35cfd0c018
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349514"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
此Get-CcSiteLogDirectory cmdlet 显示存储网站级别日志的当前Skype for Business 云连接器版本目录。 
  
此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>参数

无
  
## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例显示存储云连接器站点的日志文件的当前文件夹：
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

默认文件夹为 C：\Users \% userprofile%\CloudConnector\SiteRoot\Logs。 可以通过运行 Set-CcSiteDirectory cmdlet 来更改文件夹。 没有单独的 cmdlet 可以只更改日志文件夹位置而不更改网站目录。
  
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Get-CcSiteLogDirectory cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

该命令返回文件路径。
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

