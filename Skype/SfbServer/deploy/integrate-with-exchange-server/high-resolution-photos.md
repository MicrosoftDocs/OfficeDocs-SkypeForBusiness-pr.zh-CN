---
title: 在 Skype for Business Server 中配置高分辨率照片的使用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 摘要：在 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 和 Skype for Business Server 中配置高分辨率照片的使用。
ms.openlocfilehash: f5cc44f9f390c1d3241e7fae68054754ff7b0f76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109798"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="ad399-103">在 Skype for Business Server 中配置高分辨率照片的使用</span><span class="sxs-lookup"><span data-stu-id="ad399-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="ad399-104">**摘要：** 在 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 和 Skype for Business Server 中配置高分辨率照片的使用。</span><span class="sxs-lookup"><span data-stu-id="ad399-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="ad399-105">在 Skype for Business Server 中，照片可存储在用户的 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 邮箱中，允许照片大小最高为 648 像素 x 648 像素。</span><span class="sxs-lookup"><span data-stu-id="ad399-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="ad399-106">此外，Exchange Server可根据需要自动调整这些照片的大小以用于不同的产品。</span><span class="sxs-lookup"><span data-stu-id="ad399-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="ad399-107">通常，这意味着有三种不同的照片大小和分辨率：</span><span class="sxs-lookup"><span data-stu-id="ad399-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="ad399-108">64 像素 x 64 像素，用于 Active Directory thumbnailPhoto 属性的大小。</span><span class="sxs-lookup"><span data-stu-id="ad399-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="ad399-109">如果将照片上传到Exchange Server，Exchange 将自动创建该照片的 64 x 64 像素版本，并更新用户的 thumbnailPhoto 属性。</span><span class="sxs-lookup"><span data-stu-id="ad399-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="ad399-110">但请注意，相反的情况并不成立：如果在 Active Directory 中手动更新 thumbnailPhoto 属性，用户的 Exchange 邮箱中的照片将不会自动更新。</span><span class="sxs-lookup"><span data-stu-id="ad399-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="ad399-111">96 像素 x 96 像素，用于 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Skype for Business Web App 和 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="ad399-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="ad399-112">648 像素 x 648 像素，用于 Skype for Business 和 Skype for Business Web App Skype for Business Web App。</span><span class="sxs-lookup"><span data-stu-id="ad399-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ad399-113">如果你有资源，建议上传 648 x 648 照片;在任何 Office 2013 应用程序中提供最大分辨率和最佳图片质量。</span><span class="sxs-lookup"><span data-stu-id="ad399-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="ad399-114">每个大小为 648 x 648 且深度为 24 位的 JPEG 照片都会导致文件大小约为 240 KB。</span><span class="sxs-lookup"><span data-stu-id="ad399-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="ad399-115">这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="ad399-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="ad399-116">高分辨率照片（通过使用 Exchange Web 服务访问）可通过运行 Outlook 2013 Web App 的用户上载;仅允许用户更新自己的照片。</span><span class="sxs-lookup"><span data-stu-id="ad399-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="ad399-117">但是，管理员可以使用 Exchange 命令行管理程序 以及一系列类似如下的 Windows PowerShell 命令来更新任何用户的照片：</span><span class="sxs-lookup"><span data-stu-id="ad399-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="ad399-118">上述示例中的第一个命令使用 cmdlet 读取文件文件C:\Photos\Kenmyer.jpg将数据存储在名为 $photo 的 `Get-Content` 变量中。</span><span class="sxs-lookup"><span data-stu-id="ad399-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="ad399-119">第二个命令使用 Exchange cmdlet 上载照片并将该照片附加到 `Set-UserPhoto` Ken Myer 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ad399-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad399-120">在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。</span><span class="sxs-lookup"><span data-stu-id="ad399-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="ad399-121">也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ad399-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="ad399-122">有关详细信息，请参阅 Set-UserPhoto cmdlet [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) 的文档。</span><span class="sxs-lookup"><span data-stu-id="ad399-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) for more information</span></span>
  
<span data-ttu-id="ad399-p107">上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“保存”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="ad399-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="ad399-127">若要验证新照片已分配给用户帐户，Ken Myer 可以登录到 Skype for Business，选择 **选项，然后选择** 我的 **图片**。</span><span class="sxs-lookup"><span data-stu-id="ad399-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="ad399-128">新上载的照片应显示为 Ken 的个人照片。</span><span class="sxs-lookup"><span data-stu-id="ad399-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="ad399-129">此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：</span><span class="sxs-lookup"><span data-stu-id="ad399-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="ad399-130">如果管理员可以使用 Internet Explorer但用户无法在 Skype for Business 中查看其照片，则 Exchange Web 服务或 Exchange 自动发现服务可能存在连接问题。</span><span class="sxs-lookup"><span data-stu-id="ad399-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="ad399-131">另请注意，在 Skype for Business 中提供此照片不需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="ad399-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="ad399-132">相反，照片在上载并运行 `Set-UserPhoto` cmdlet 后会立即可用。</span><span class="sxs-lookup"><span data-stu-id="ad399-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>