---
title: 在图像中配置高分辨率照片Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 摘要：在 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 和 Skype for Business Server 中配置高分辨率照片的使用。
ms.openlocfilehash: 8a28e151d99440b1ec682eab2a473f3cffac7ac4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856989"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>在图像中配置高分辨率照片Skype for Business Server
 
**摘要：** 在 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 和 Skype for Business Server 中配置对高分辨率照片的使用。
  
在 Skype for Business Server 中，照片可存储在用户的 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 邮箱中，允许照片大小最高为 648 像素 x 648 像素。 此外，Exchange Server可根据需要自动调整这些照片的大小以用于不同的产品。 通常，这意味着有三种不同的照片大小和分辨率：
  
- 64 像素 x 64 像素，用于 Active Directory thumbnailPhoto 属性的大小。 如果将照片上传到Exchange Server，Exchange会自动创建该照片的 64 x 64 像素版本，并更新用户的 thumbnailPhoto 属性。 但是请注意，相反的情况并不成立：如果在 Active Directory 中手动更新 thumbnailPhoto 属性，用户的 Exchange 邮箱中的照片将不会自动更新。
    
- 96 像素 x 96 像素，用于 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Skype for Business Web应用 和 Skype for Business。
    
- 648 像素 x 648 像素，用于Skype for Business Skype for Business Web应用 Skype for Business Web应用。
    
> [!NOTE]
> 如果你有资源，建议上传 648 x 648 照片;在 2013 年 3 月的任何应用程序中提供最大分辨率和Office图片质量。 每个大小为 648 x 648 且深度为 24 位的 JPEG 照片都会导致文件大小约为 240 KB。 这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。 
  
运行 Exchange 2013 Web App 的用户可以上载高分辨率照片Outlook Web 服务;仅允许用户更新自己的照片。 但是，管理员可以使用命令行管理程序以及一系列Exchange命令行管理程序Windows PowerShell更新任何用户的照片：
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

上述示例中的第一个命令使用 cmdlet 读取文件文件C:\Photos\Kenmyer.jpg将数据存储在名为 $photo 的 `Get-Content` 变量中。 第二个命令Exchange cmdlet 上载照片并将该照片附加到 `Set-UserPhoto` Ken Myer 的用户帐户。
  
> [!NOTE]
> 在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。 也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。 有关详细信息，请参阅 Set-UserPhoto cmdlet 的文档。 [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto)
  
上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“保存”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

若要验证新照片已分配给用户帐户，Ken Myer 可以登录到Skype for Business，选择选项，然后选择我的 **图片**。  新上载的照片应显示为 Ken 的个人照片。 此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

如果管理员可以使用 Internet Explorer但用户无法在 Skype for Business查看其照片，则 Exchange Web 服务或 Exchange 自动发现服务可能有连接问题。
  
另请注意，无需其他配置，此照片在 Skype for Business。 相反，照片在上载并运行 `Set-UserPhoto` cmdlet 后会立即可用。