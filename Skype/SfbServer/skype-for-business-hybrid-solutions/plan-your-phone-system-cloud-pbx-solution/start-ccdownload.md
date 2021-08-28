---
title: Start-CcDownload
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
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: 此Start-CcDownload cmdlet 可同步下载Skype for Business 云连接器版本位和 msi 文件。
ms.openlocfilehash: 0d5974bb4d4fb5bc16f467410865fb571073246e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631566"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
此Start-CcDownload cmdlet 可同步下载Skype for Business 云连接器版本位和 msi 文件。
  
对于云连接器 2.0 版和更高版本，还可以指定 DownloadBitsOnly 参数。
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例从云连接器公共下载站点同步下载云连接器 bits 和 msi 文件：
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>示例 2

下一个示例从专用下载站点同步下载云连接器 bits 和 msi 文件：
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>示例 3

第三个示例从专用下载站点同步下载云连接器 bits 和 msi 文件。
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果下载站点中提供了新版本，Start-CcDownload下载站点下载并安装 msi 文件，然后同步下载云连接器 bits。 如果没有新版本的 msi 文件，Start-CcDownload将仅下载云连接器 bits。 如果已下载云连接器位，Start-CcDownload不执行。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | 可选 <br/> |System.String  <br/> | 专用下载站点中云连接器特定版本的完整 URL。 请谨慎使用此参数 ，确保了解要下载的云连接器版本。 <br/> |
|DownloadBitsOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |跳过从下载站点下载并安装 MSI 的步骤，仅下载云连接器 bits。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Start-CcDownload cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

