---
title: 在 Skype for Business Server 2015 中配置使用高分辨率照片
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 摘要： 在 Exchange Server 2016年或 Exchange Server 2013年和 Skype 为业务服务器 2015年配置使用的高分辨率照片。
ms.openlocfilehash: 9d5117f2774a928e520aa211007fffb0740a2b52
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置使用高分辨率照片
 
**摘要：**在 Exchange Server 2016年或 Exchange Server 2013年和 Skype 为业务服务器 2015年配置使用的高分辨率照片。
  
在 Skype 业务服务器 2015年的照片可以存储在用户的 Exchange Server 2016年或 Exchange Server 2013年邮箱，这使照片大小达 648 648 个像素的像素。 此外，Exchange Server 可以自动在不同产品中使用这些照片根据需要调整大小。 通常，这意味着有三种不同的照片大小和分辨率：
  
- 64 像素 x 64 像素，用于 Active Directory thumbnailPhoto 属性的大小。 如果您将照片上载到 Exchange Server 时，Exchange 将自动由该照片的 64 像素版本创建 64 像素并更新用户的 thumbnailPhoto 属性。 但是请注意，反之不成立： 如果手动更新 Active Directory 中的 thumbnailPhoto 属性用户的 Exchange 邮箱中的照片将不会自动更新。
    
- 由 96 个像素，在 Microsoft Outlook 2013 Web 应用程序、 Microsoft Outlook 2013、 为企业 Web 应用程序中，Skype 和 Skype 业务中使用的 96 个像素。
    
- 648 648 个像素的像素用于在 Skype 业务和 Skype 业务 Web App Skype 为企业 Web 应用程序。
    
> [!NOTE]
> 如果有资源，建议您上载 648 x 648 照片;所提供的最大分辨率和任何 Office 2013 应用程序中的最佳图片质量。 每个 JPEG 图片的 648 x 648 大小、 深度为 24 位导致大约 240 千字节为单位的文件大小。 这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。 
  
高分辨率照片，并通过使用 Exchange Web 服务可以访问，可以通过运行 Outlook 2013 Web 应用程序; 用户上载仅允许用户更新他们自己的照片。 管理员，但是，可以使用 Exchange 管理外壳程序以及 Windows PowerShell 命令类似于下面的一系列更新的任何用户的照片：
  
```
$photo = ([Byte ] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData -Preview $photo -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

在上面的示例中，第一个命令使用 Get-Content cmdlet 读取文件 C:\Photos\Kenmyer.jpg 的内容，并将数据存储在名为 Preview$photo 的变量中。 在第二个命令中，Exchange cmdlet 集 UserPhoto 用于上载照片，该照片附着 Ken Myer 的用户帐户。
  
> [!NOTE]
> 在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。 也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。 请参阅文档集 UserPhoto cmdlet 在[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)的详细信息
  
上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“**保存**”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

要验证新的照片，已分配给用户帐户，Ken Myer 可以登录 Skype 业务以及选择**选项**，然后选择**我的图片**。 新上载的照片应显示为 Ken 的个人照片。 此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

如果管理员可以查看使用 Internet Explorer 的照片，但用户不能查看他或她的照片在 Skype 业务可能与 Web 服务交换或 Exchange 自动发现服务的连接问题。
  
还请注意，任何附加的配置所需业务的 Skype 提供此照片。 上载照片并运行 Set-UserPhoto cmdlet 后，照片将立即可供使用。
  

