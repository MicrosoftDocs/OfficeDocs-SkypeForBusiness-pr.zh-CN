---
title: 'Lync Server 2013: 配置高分辨率照片的使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efa45f6a7e3f561e56e5563b5024c84bb5731fd7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="35a5a-102">在 Microsoft Lync Server 2013 中配置高分辨率照片的使用</span><span class="sxs-lookup"><span data-stu-id="35a5a-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35a5a-103">_**主题上次修改时间:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="35a5a-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="35a5a-104">Microsoft Lync Server 2010 提供了用户查看其联系人照片的能力 (以及让其他人可以使用自己的照片)。</span><span class="sxs-lookup"><span data-stu-id="35a5a-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="35a5a-105">通常, 这些照片作为用户的 thumbnailPhoto 属性的一部分存储在 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="35a5a-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="35a5a-106">这对照片的大小和分辨率施加了严重限制: thumbnailPhoto 属性只能容纳最大大小为48像素的照片48像素。</span><span class="sxs-lookup"><span data-stu-id="35a5a-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="35a5a-107">但是, 在 Microsoft Lync Server 2013 中, 照片可以存储在用户的 Microsoft Exchange Server 2013 邮箱中;这允许最大为648像素的照片大小乘以648像素。</span><span class="sxs-lookup"><span data-stu-id="35a5a-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="35a5a-108">除此之外, Exchange 2013 可根据需要自动调整这些照片的大小, 以便在不同的产品中使用。</span><span class="sxs-lookup"><span data-stu-id="35a5a-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="35a5a-109">通常，这意味着有三种不同的照片大小和分辨率：</span><span class="sxs-lookup"><span data-stu-id="35a5a-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="35a5a-110">48像素 x 48 像素, 用于 Active Directory thumbnailPhoto 属性的大小。</span><span class="sxs-lookup"><span data-stu-id="35a5a-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="35a5a-111">如果将照片上传到 Exchange 2013 Exchange 将自动通过48像素版本的照片创建48像素, 并更新用户的 thumbnailPhoto 属性。</span><span class="sxs-lookup"><span data-stu-id="35a5a-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="35a5a-112">但请注意, 反之不成立: 如果手动更新 Active Directory 中的 thumbnailPhoto 属性, 用户的 Exchange 2013 邮箱中的照片将不会自动更新。</span><span class="sxs-lookup"><span data-stu-id="35a5a-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="35a5a-113">96像素 x 96 像素, 用于 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App 和 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="35a5a-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="35a5a-114">在 Lync 2013 和 Microsoft Lync Web App 中使用648像素 x 648 像素。</span><span class="sxs-lookup"><span data-stu-id="35a5a-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35a5a-p104">如果您具有资源，建议您上载 648x648 照片；这将在任何 Office 2013 应用程序中提供最高分辨率和最佳图片质量。每张大小为 648x648、深度为 24 位的 JPEG 照片均会生成一个约为 240 KB 的文件大小。这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="35a5a-p104">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="35a5a-118">高分辨率照片 (使用 Exchange Web 服务访问) 可由运行 Outlook 2013 Web App 的用户上传;仅允许用户更新其自己的照片。</span><span class="sxs-lookup"><span data-stu-id="35a5a-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="35a5a-119">但是, 管理员可以使用 Exchange 命令行管理器和一系列类似于以下内容的 Windows PowerShell 命令更新任何用户的照片:</span><span class="sxs-lookup"><span data-stu-id="35a5a-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="35a5a-120">前面示例中的第一个命令使用 Get 内容 cmdlet 读取文件 C:\\\\Kenmyer 的内容, 并将该数据存储在名为 $photo 的变量中。</span><span class="sxs-lookup"><span data-stu-id="35a5a-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="35a5a-121">在第二个命令中, 将使用 Exchange cmdlet UserPhoto 上载照片, 并将该照片附加到 Ken Myer 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="35a5a-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35a5a-122">在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。</span><span class="sxs-lookup"><span data-stu-id="35a5a-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="35a5a-123">也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。</span><span class="sxs-lookup"><span data-stu-id="35a5a-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="35a5a-124"><A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A>有关详细信息, 请参阅 UserPhoto cmdlet 的文档</span><span class="sxs-lookup"><span data-stu-id="35a5a-124">See the documentation for the Set-UserPhoto cmdlet at <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="35a5a-p108">上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“**保存**”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="35a5a-p108">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="35a5a-129">若要验证是否已将新照片分配给用户帐户, Ken Myer 可以登录到 Lync 2013, 选择 "**选项**", 然后选择 **"我的图片**"。</span><span class="sxs-lookup"><span data-stu-id="35a5a-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="35a5a-130">新上载的照片应显示为 Ken 的个人照片。</span><span class="sxs-lookup"><span data-stu-id="35a5a-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="35a5a-131">此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：</span><span class="sxs-lookup"><span data-stu-id="35a5a-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="35a5a-132">如果管理员可以使用 Internet Explorer 查看照片, 但用户无法在 Lync 2013 中查看他或她的照片, 这通常表示 Exchange Web 服务的连接问题或 Exchange 自动发现服务的连接问题。</span><span class="sxs-lookup"><span data-stu-id="35a5a-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="35a5a-133">请注意, 您也不需要额外的配置即可使此照片在 Lync 2013 中可用。</span><span class="sxs-lookup"><span data-stu-id="35a5a-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="35a5a-134">上载照片并运行 Set-UserPhoto cmdlet 后，照片将立即可供使用。</span><span class="sxs-lookup"><span data-stu-id="35a5a-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

