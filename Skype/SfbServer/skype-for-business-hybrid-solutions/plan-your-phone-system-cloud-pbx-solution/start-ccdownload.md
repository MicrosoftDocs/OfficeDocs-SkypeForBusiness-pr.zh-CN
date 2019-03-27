---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Start-CcDownload cmdlet 可同步下载 Skype for Business 云连接器版本 bits 和 msi 文件。
ms.openlocfilehash: cc157825df75a4534422cb0a2fd07abb0ae0daea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893836"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Start-CcDownload cmdlet 可同步下载 Skype for Business 云连接器版本 bits 和 msi 文件。
  
使用云连接器 2.0 版和更高版本时，你还可以指定 DownloadBitsOnly 参数。
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例的云连接器位和 msi 文件同步将从云连接器公共下载网站下载：
  
```
Start-CcDownload
```

### <a name="example-2"></a>示例 2

下一个示例云连接器位和 msi 文件同步将从专用下载网站下载：
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>示例 3

第三个示例将从私有下载站点中同步下载云连接器 bits 和 msi 文件。
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

如果有新版本可用在下载站点中，开始 CcDownload 将下载和下载站点中，从安装 msi 文件，然后同步下载云连接器位。 如果没有新版本的 msi 文件，Start-CcDownload 将只下载云连接器 bits。 如果已下载云连接器 bits，则不执行 Start-CcDownload。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot   <br/> | 可选 <br/> |System.String  <br/> | 在私有云连接器的特定版本的完整 URL 下载站点。 请谨慎使用此参数，确保您知道要下载哪个版本的云连接器。 <br/> |
|DownloadBitsOnly   <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |跳过从下载站点下载和安装 MSI 的步骤，只下载云连接器 bits。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Start-CcDownload cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

无
  

