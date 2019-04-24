---
title: 在 Skype for Business Server 中配置使用高分辨率照片
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 摘要： 在 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 配置使用高分辨率照片。
ms.openlocfilehash: 56fef2cfa8c62a66698c2232c9273cdb5604b5b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216667"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>在 Skype for Business Server 中配置使用高分辨率照片
 
**摘要：** 在 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 配置使用高分辨率照片。
  
在业务服务器的 Skype 照片可以存储在用户的 Exchange Server 2016 或 Exchange Server 2013 邮箱，从而实现照片大小达 648 像素 x 648 像素。 此外，Exchange Server 可以自动为在不同的产品中使用这些照片根据需要调整大小。 通常，这意味着有三种不同的照片大小和分辨率：
  
- 64 像素 x 64 像素，用于 Active Directory thumbnailPhoto 属性的大小。 如果将照片上载到 Exchange 服务器后，Exchange 将自动创建的照片 64 像素版本 64 像素和更新用户 thumbnailPhoto 属性。 但请注意，反向不为 true： 如果您手动更新 Active Directory 中的 thumbnailPhoto 属性在用户的 Exchange 邮箱的照片将不自动更新。
    
- 96 像素 x 96 像素，适用于在 Microsoft Outlook 2013 Web 应用程序、 Microsoft Outlook 2013、 Skype 业务 Web 应用程序和 Skype for Business 中使用。
    
- 648 像素 x 648 像素 x 的用于在 Skype 商业和 Skype 的业务 Web 应用程序 Skype 企业 Web 应用程序。
    
> [!NOTE]
> 如果您具有资源，则建议您上载 648 x 648 照片;提供的最大分辨率和最佳图片中任意 Office 2013 应用程序的质量。 深度为 24 位结果的文件大小约为 240 千字节为单位的大小为 648 x 648 与每个 JPEG 照片。 这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。 
  
可以通过运行 Outlook 2013 Web 应用程序; 用户上载高分辨率照片，通过使用 Exchange Web 服务访问仅允许用户更新自己的照片。 但是，，管理员可以使用 Exchange 命令行管理程序和一系列类似于以下的 Windows PowerShell 命令更新任何用户的照片：
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

在上述示例中的第一个命令使用`Get-Content`cmdlet 可读取文件 C:\Photos\Kenmyer.jpg 的内容，并将该数据存储在变量名为 $photo。 在第二个命令中，Exchange cmdlet`Set-UserPhoto`用于照片上载并将该照片附加到 Ken Myer 的用户帐户。
  
> [!NOTE]
> 在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。 也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。 请参阅文档集 UserPhoto cmdlet 在[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)的详细信息
  
上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“**保存**”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

若要验证的新的照片，已分配给该用户帐户，Ken myer 的用户可以登录到 Skype 的业务和选择的**选项**，然后选择**我的图片**。 新上载的照片应显示为 Ken 的个人照片。 此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

如果管理员可以查看使用 Internet Explorer 的照片，但用户无法在 Skype for Business 中查看联系人的照片可能有连接问题与 Exchange Web 服务或 Exchange 自动发现服务。
  
请注意，任何其他配置所需才能使此照片 Skype for Business 中可用。 相反，照片将上载完之后可立即使用和`Set-UserPhoto`已运行 cmdlet。
