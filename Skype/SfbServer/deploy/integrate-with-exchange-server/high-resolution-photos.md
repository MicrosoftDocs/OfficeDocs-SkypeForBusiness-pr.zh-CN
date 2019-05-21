---
title: 在 Skype for Business 服务器中配置高分辨率照片的使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '摘要: 在 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器中配置高分辨率照片的使用。'
ms.openlocfilehash: d52cdb2d84fedba0dcbec97cbca4074b1ae12a84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278204"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置高分辨率照片的使用
 
**摘要:** 在 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器中配置高分辨率照片的使用。
  
在 Skype for Business 服务器照片中, 可以存储在用户的 Exchange Server 2016 或 Exchange Server 2013 邮箱中, 这允许照片大小最高为648像素的648像素。 此外, Exchange Server 可以根据需要自动调整这些照片的大小, 以便在不同的产品中使用。 通常，这意味着有三种不同的照片大小和分辨率：
  
- 64 像素 x 64 像素，用于 Active Directory thumbnailPhoto 属性的大小。 如果你将照片上传到 Exchange Server, Exchange 将自动创建64像素的64像素版本的该照片, 并更新用户的 thumbnailPhoto 属性。 但请注意, 反之不成立: 如果手动更新 Active Directory 中的 thumbnailPhoto 属性, 用户的 Exchange 邮箱中的照片将不会自动更新。
    
- 96像素 x 96 像素, 用于 Microsoft Outlook 2013 Web 应用、Microsoft Outlook 2013、Skype for business Web 应用和 Skype for business。
    
- 648像素 x 648 像素, 用于 skype for Business 和 Skype for business Web 应用 Skype for business Web 应用。
    
> [!NOTE]
> 如果你有这些资源, 建议你上载 648 x 648 照片;在任何 Office 2013 应用程序中提供最高分辨率和最佳图片质量。 每个大小为 648 x 648 的 JPEG 照片和一个深度为24位的照片将导致文件大小约为 240 kb。 这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。 
  
高分辨率照片 (使用 Exchange Web 服务访问) 可由运行 Outlook 2013 Web App 的用户上传;仅允许用户更新其自己的照片。 但是, 管理员可以使用 Exchange 命令行管理器和一系列类似于以下内容的 Windows PowerShell 命令更新任何用户的照片:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

前面示例中的第一个命令使用`Get-Content` cmdlet 读取文件 C:\Photos\Kenmyer.jpg 的内容, 并将该数据存储在名为 $photo 的变量中。 在第二个命令中, 将`Set-UserPhoto`使用 Exchange cmdlet 上载照片, 并将该照片附加到 Ken Myer 的用户帐户。
  
> [!NOTE]
> 在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。 也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。 [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)有关详细信息, 请参阅 UserPhoto cmdlet 的文档
  
上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“**保存**”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

若要验证是否已将新照片分配给用户帐户, Ken Myer 可以登录到 Skype for business, 选择 "**选项**", 然后选择 **"我的图片**"。 新上载的照片应显示为 Ken 的个人照片。 此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

如果管理员可以使用 Internet Explorer 查看照片, 但用户无法在 Skype for Business 中查看他或她的照片, 则可能是 Exchange Web 服务或 Exchange 自动发现服务存在连接问题。
  
请注意, 要使此照片在 Skype for Business 中可用, 还不需要额外的配置。 相反, 照片将在上载后立即可用, 并且`Set-UserPhoto` cmdlet 已运行。
