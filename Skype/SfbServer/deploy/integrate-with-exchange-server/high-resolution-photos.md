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
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="2a654-103">在 Skype for Business Server 中配置使用高分辨率照片</span><span class="sxs-lookup"><span data-stu-id="2a654-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="2a654-104">**摘要：** 在 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 配置使用高分辨率照片。</span><span class="sxs-lookup"><span data-stu-id="2a654-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="2a654-105">在业务服务器的 Skype 照片可以存储在用户的 Exchange Server 2016 或 Exchange Server 2013 邮箱，从而实现照片大小达 648 像素 x 648 像素。</span><span class="sxs-lookup"><span data-stu-id="2a654-105">In Skype for Business Server photos can be stored in a user's Exchange Server 2016 or Exchange Server 2013 mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="2a654-106">此外，Exchange Server 可以自动为在不同的产品中使用这些照片根据需要调整大小。</span><span class="sxs-lookup"><span data-stu-id="2a654-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="2a654-107">通常，这意味着有三种不同的照片大小和分辨率：</span><span class="sxs-lookup"><span data-stu-id="2a654-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="2a654-108">64 像素 x 64 像素，用于 Active Directory thumbnailPhoto 属性的大小。</span><span class="sxs-lookup"><span data-stu-id="2a654-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="2a654-109">如果将照片上载到 Exchange 服务器后，Exchange 将自动创建的照片 64 像素版本 64 像素和更新用户 thumbnailPhoto 属性。</span><span class="sxs-lookup"><span data-stu-id="2a654-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="2a654-110">但请注意，反向不为 true： 如果您手动更新 Active Directory 中的 thumbnailPhoto 属性在用户的 Exchange 邮箱的照片将不自动更新。</span><span class="sxs-lookup"><span data-stu-id="2a654-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="2a654-111">96 像素 x 96 像素，适用于在 Microsoft Outlook 2013 Web 应用程序、 Microsoft Outlook 2013、 Skype 业务 Web 应用程序和 Skype for Business 中使用。</span><span class="sxs-lookup"><span data-stu-id="2a654-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="2a654-112">648 像素 x 648 像素 x 的用于在 Skype 商业和 Skype 的业务 Web 应用程序 Skype 企业 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2a654-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2a654-113">如果您具有资源，则建议您上载 648 x 648 照片;提供的最大分辨率和最佳图片中任意 Office 2013 应用程序的质量。</span><span class="sxs-lookup"><span data-stu-id="2a654-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="2a654-114">深度为 24 位结果的文件大小约为 240 千字节为单位的大小为 648 x 648 与每个 JPEG 照片。</span><span class="sxs-lookup"><span data-stu-id="2a654-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="2a654-115">这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="2a654-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="2a654-116">可以通过运行 Outlook 2013 Web 应用程序; 用户上载高分辨率照片，通过使用 Exchange Web 服务访问仅允许用户更新自己的照片。</span><span class="sxs-lookup"><span data-stu-id="2a654-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="2a654-117">但是，，管理员可以使用 Exchange 命令行管理程序和一系列类似于以下的 Windows PowerShell 命令更新任何用户的照片：</span><span class="sxs-lookup"><span data-stu-id="2a654-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="2a654-118">在上述示例中的第一个命令使用`Get-Content`cmdlet 可读取文件 C:\Photos\Kenmyer.jpg 的内容，并将该数据存储在变量名为 $photo。</span><span class="sxs-lookup"><span data-stu-id="2a654-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="2a654-119">在第二个命令中，Exchange cmdlet`Set-UserPhoto`用于照片上载并将该照片附加到 Ken Myer 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2a654-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a654-120">在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。</span><span class="sxs-lookup"><span data-stu-id="2a654-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="2a654-121">也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2a654-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="2a654-122">请参阅文档集 UserPhoto cmdlet 在[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)的详细信息</span><span class="sxs-lookup"><span data-stu-id="2a654-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="2a654-p107">上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“**保存**”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="2a654-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="2a654-127">若要验证的新的照片，已分配给该用户帐户，Ken myer 的用户可以登录到 Skype 的业务和选择的**选项**，然后选择**我的图片**。</span><span class="sxs-lookup"><span data-stu-id="2a654-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="2a654-128">新上载的照片应显示为 Ken 的个人照片。</span><span class="sxs-lookup"><span data-stu-id="2a654-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="2a654-129">此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：</span><span class="sxs-lookup"><span data-stu-id="2a654-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

<span data-ttu-id="2a654-130">如果管理员可以查看使用 Internet Explorer 的照片，但用户无法在 Skype for Business 中查看联系人的照片可能有连接问题与 Exchange Web 服务或 Exchange 自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="2a654-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="2a654-131">请注意，任何其他配置所需才能使此照片 Skype for Business 中可用。</span><span class="sxs-lookup"><span data-stu-id="2a654-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="2a654-132">相反，照片将上载完之后可立即使用和`Set-UserPhoto`已运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2a654-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
