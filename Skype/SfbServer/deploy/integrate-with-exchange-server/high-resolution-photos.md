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
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server-2015"></a><span data-ttu-id="4d8d1-103">在 Skype for Business Server 2015 中配置使用高分辨率照片</span><span class="sxs-lookup"><span data-stu-id="4d8d1-103">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4d8d1-104">**摘要：**在 Exchange Server 2016年或 Exchange Server 2013年和 Skype 为业务服务器 2015年配置使用的高分辨率照片。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4d8d1-105">在 Skype 业务服务器 2015年的照片可以存储在用户的 Exchange Server 2016年或 Exchange Server 2013年邮箱，这使照片大小达 648 648 个像素的像素。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-105">In Skype for Business Server 2015 photos can be stored in a user's Exchange Server 2016 or Exchange Server 2013 mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="4d8d1-106">此外，Exchange Server 可以自动在不同产品中使用这些照片根据需要调整大小。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="4d8d1-107">通常，这意味着有三种不同的照片大小和分辨率：</span><span class="sxs-lookup"><span data-stu-id="4d8d1-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="4d8d1-108">64 像素 x 64 像素，用于 Active Directory thumbnailPhoto 属性的大小。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="4d8d1-109">如果您将照片上载到 Exchange Server 时，Exchange 将自动由该照片的 64 像素版本创建 64 像素并更新用户的 thumbnailPhoto 属性。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="4d8d1-110">但是请注意，反之不成立： 如果手动更新 Active Directory 中的 thumbnailPhoto 属性用户的 Exchange 邮箱中的照片将不会自动更新。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="4d8d1-111">由 96 个像素，在 Microsoft Outlook 2013 Web 应用程序、 Microsoft Outlook 2013、 为企业 Web 应用程序中，Skype 和 Skype 业务中使用的 96 个像素。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="4d8d1-112">648 648 个像素的像素用于在 Skype 业务和 Skype 业务 Web App Skype 为企业 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4d8d1-113">如果有资源，建议您上载 648 x 648 照片;所提供的最大分辨率和任何 Office 2013 应用程序中的最佳图片质量。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="4d8d1-114">每个 JPEG 图片的 648 x 648 大小、 深度为 24 位导致大约 240 千字节为单位的文件大小。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="4d8d1-115">这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="4d8d1-116">高分辨率照片，并通过使用 Exchange Web 服务可以访问，可以通过运行 Outlook 2013 Web 应用程序; 用户上载仅允许用户更新他们自己的照片。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="4d8d1-117">管理员，但是，可以使用 Exchange 管理外壳程序以及 Windows PowerShell 命令类似于下面的一系列更新的任何用户的照片：</span><span class="sxs-lookup"><span data-stu-id="4d8d1-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte ] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData -Preview $photo -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="4d8d1-118">在上面的示例中，第一个命令使用 Get-Content cmdlet 读取文件 C:\Photos\Kenmyer.jpg 的内容，并将数据存储在名为 Preview$photo 的变量中。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-118">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named Preview$photo.</span></span> <span data-ttu-id="4d8d1-119">在第二个命令中，Exchange cmdlet 集 UserPhoto 用于上载照片，该照片附着 Ken Myer 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-119">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d8d1-120">在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="4d8d1-121">也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="4d8d1-122">请参阅文档集 UserPhoto cmdlet 在[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)的详细信息</span><span class="sxs-lookup"><span data-stu-id="4d8d1-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="4d8d1-p107">上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“**保存**”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="4d8d1-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="4d8d1-127">要验证新的照片，已分配给用户帐户，Ken Myer 可以登录 Skype 业务以及选择**选项**，然后选择**我的图片**。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="4d8d1-128">新上载的照片应显示为 Ken 的个人照片。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="4d8d1-129">此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：</span><span class="sxs-lookup"><span data-stu-id="4d8d1-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

<span data-ttu-id="4d8d1-130">如果管理员可以查看使用 Internet Explorer 的照片，但用户不能查看他或她的照片在 Skype 业务可能与 Web 服务交换或 Exchange 自动发现服务的连接问题。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="4d8d1-131">还请注意，任何附加的配置所需业务的 Skype 提供此照片。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="4d8d1-132">上载照片并运行 Set-UserPhoto cmdlet 后，照片将立即可供使用。</span><span class="sxs-lookup"><span data-stu-id="4d8d1-132">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>
  

