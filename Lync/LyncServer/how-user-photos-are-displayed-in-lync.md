---
title: 如何在 Lync 中显示用户照片
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b77d515ebe743b038f3f0099a9702a383e7b797
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505149"
---
# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="564d6-102">如何在 Lync 中显示用户照片</span><span class="sxs-lookup"><span data-stu-id="564d6-102">How user photos are displayed in Lync</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="564d6-103">_**上次修改的主题：** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="564d6-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="564d6-104">**摘要：** 在 Lync 客户端中显示的用户照片可能会有所不同，具体取决于所使用的 Lync 功能，如会议或 IM 聊天中的时间。</span><span class="sxs-lookup"><span data-stu-id="564d6-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="564d6-105">Lync 2010 引入了在 Lync 配置文件中加入照片的功能，该照片显示给其他 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="564d6-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="564d6-106">您还可以选择是否在 Lync 客户端中显示联系人的照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="564d6-107">在 Lync 2013 中，支持适用于用户的高分辨率照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="564d6-108">本主题介绍 Lync 客户端如何获取和显示存储图像的用户照片、每个图像源的限制以及不同 Lync 服务如何使用用户照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="564d6-109">规划注意事项</span><span class="sxs-lookup"><span data-stu-id="564d6-109">Planning considerations</span></span>

<span data-ttu-id="564d6-110">在计划实现对用户照片的支持时，应考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="564d6-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="564d6-111">高定义用户照片支持要求用户的邮箱位于 Exchange 2013，而 Lync 用户帐户位于 Lync 2013 池中。</span><span class="sxs-lookup"><span data-stu-id="564d6-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="564d6-112">仅在使用 Lync Server 2013 和 Exchange 2013 的环境中支持高清晰度用户照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="564d6-113">拥有 Exchange 2010 邮箱的用户将始终使用 AD DS 中的 **thumbnailPhoto** 属性作为其用户照片的源。</span><span class="sxs-lookup"><span data-stu-id="564d6-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="564d6-114">作为 **thumbnailPhoto** 属性存储在 AD DS 中的用户照片不会显示在外部/联合联系人中。</span><span class="sxs-lookup"><span data-stu-id="564d6-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="564d6-115">如果用户联系人照片存储在 AD DS 中，则使用的图像文件的大小限制为 96 x 96 像素，且不超过 100 KB 的文件大小。</span><span class="sxs-lookup"><span data-stu-id="564d6-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="564d6-116">如果 Lync Server 和 Exchange Server 之间的连接丢失，则用户的低分辨率 **thumbnailPhoto** 将显示在 AD DS 中，并且仅供内部用户。</span><span class="sxs-lookup"><span data-stu-id="564d6-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="564d6-117">当活动扬声器未启用视频时，会在 Lync 2013 会议中显示高分辨率用户照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="564d6-118">此外，将鼠标移到库中的缩略图照片上也会显示高分辨率照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="564d6-119">Lync 2010 中的用户照片</span><span class="sxs-lookup"><span data-stu-id="564d6-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="564d6-120">在 Lync 2010 客户端中，可以从以下两个选项中选择用于显示配置文件的照片、 **默认的企业图片** 并 **显示来自 web 地址的图片**。</span><span class="sxs-lookup"><span data-stu-id="564d6-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="564d6-121">默认企业图片</span><span class="sxs-lookup"><span data-stu-id="564d6-121">Default corporate picture</span></span>

<span data-ttu-id="564d6-122">当您选择 " **默认企业图片** " 选项时，Lync 将从 Active Directory 域服务中获取为您显示的照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="564d6-123">使用的图像是定义为 Active Directory 域服务中的 **thumbnailPhoto** 属性的值的图像。</span><span class="sxs-lookup"><span data-stu-id="564d6-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="564d6-124">这是 Exchange 在 Outlook 中显示图像时使用的同一文件。</span><span class="sxs-lookup"><span data-stu-id="564d6-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="564d6-125">使用 Active Directory 域服务中的图像时的注意事项包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="564d6-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="564d6-126">仅支持尺寸最大为96像素 x 96 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="564d6-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="564d6-127">图像的文件大小限制为 100 KB。</span><span class="sxs-lookup"><span data-stu-id="564d6-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="564d6-128">默认情况下，用户可以更改用于 **thumbnailPhoto** 属性的图像，但不直接通过 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="564d6-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="564d6-129">您可以通过 Active Directory 域服务禁用此。</span><span class="sxs-lookup"><span data-stu-id="564d6-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="564d6-130">存储在 Active Directory 域服务中的图像不会显示给组织外部的联系人，即使它们是联盟联系人也是如此。</span><span class="sxs-lookup"><span data-stu-id="564d6-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="564d6-131">在大型组织中，存储和检索大量用户的图像可能会影响 Active Directory 域服务数据库的大小和性能。</span><span class="sxs-lookup"><span data-stu-id="564d6-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="564d6-132">有限的图像尺寸和文件大小意味着只有低分辨率图像可以使用。</span><span class="sxs-lookup"><span data-stu-id="564d6-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="564d6-133">用户如何在 Active Directory 域服务中管理其用户照片</span><span class="sxs-lookup"><span data-stu-id="564d6-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="564d6-134">用户无法通过 Lync 2010 客户端直接更改 Active Directory 域服务配置文件中使用的图像。</span><span class="sxs-lookup"><span data-stu-id="564d6-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="564d6-135">如果可用，他们可以使用下列选项之一来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="564d6-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="564d6-136">**SharePoint Server**    用户可以将照片上传到 SharePoint Server 上的 "我的网站"，然后[在 sharepoint 中配置配置文件同步](https://go.microsoft.com/fwlink/p/?linkid=507466)，以便将照片同步到 Active Directory 域服务中的**thumbnailPhoto**属性。</span><span class="sxs-lookup"><span data-stu-id="564d6-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="564d6-137">**存储在可公开访问的 URL**     上的照片用户可以配置其用户照片，以指定要使用的图像的公开访问的 URL。</span><span class="sxs-lookup"><span data-stu-id="564d6-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="564d6-138">在没有密码的情况下，图像必须可公开访问。</span><span class="sxs-lookup"><span data-stu-id="564d6-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="564d6-139">存储在指定 web 地址的图像通过状态信息中的联系人卡片类别传输给其他用户。</span><span class="sxs-lookup"><span data-stu-id="564d6-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="564d6-140">当 Lync 客户端需要显示用户照片时，它将从指定的 web 地址检索图像。</span><span class="sxs-lookup"><span data-stu-id="564d6-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="564d6-141">**用于 Windows PowerShell**     的 Exchange 2010 cmdlet管理员可以在 Exchange 2010 命令行管理程序中运行[import-recipientdataproperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet 来管理**thumbnailPhoto**属性。</span><span class="sxs-lookup"><span data-stu-id="564d6-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="564d6-142">在使用 Exchange 2010 cmdlet 导入图像时，文件大小限制为 10 KB。</span><span class="sxs-lookup"><span data-stu-id="564d6-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="564d6-143">**第三方工具**    用户只能将自己的照片上载到**thumbnailPhoto**属性。</span><span class="sxs-lookup"><span data-stu-id="564d6-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="564d6-144">显示 Web 地址中的图片</span><span class="sxs-lookup"><span data-stu-id="564d6-144">Show a picture from a web address</span></span>

<span data-ttu-id="564d6-145">当您选择 " **显示来自 web 地址的图片** " 选项时，Lync 将获取您输入的地址中的图像，并在 Lync 中为用户照片显示该图像。</span><span class="sxs-lookup"><span data-stu-id="564d6-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="564d6-146">使用来自 web 地址的图像的注意事项包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="564d6-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="564d6-147">文件大小限制由客户端策略中使用[set-csclientpolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet 定义的**MaxPhotoSizeKB**属性决定。</span><span class="sxs-lookup"><span data-stu-id="564d6-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="564d6-148">默认大小限制为 30 KB。</span><span class="sxs-lookup"><span data-stu-id="564d6-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="564d6-149">最大值为 100 KB。</span><span class="sxs-lookup"><span data-stu-id="564d6-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="564d6-150">对图像的分辨率没有限制，但如果您尝试使用超过大小限制的图像文件，则不会将其下载到 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="564d6-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="564d6-151">您可以将该值设置为0，以禁止在 Lync 中使用所有用户照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="564d6-152">来自 web 地址的用户照片可以通过外部联盟联系人查看。</span><span class="sxs-lookup"><span data-stu-id="564d6-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="564d6-153">使用客户端策略 cmdlet 管理用户照片</span><span class="sxs-lookup"><span data-stu-id="564d6-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="564d6-154">在 Lync Server 2010 中，客户端策略设置是使用 Set-csclientpolicy cmdlet 配置的。</span><span class="sxs-lookup"><span data-stu-id="564d6-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="564d6-155">配置的策略设置通过带内设置发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="564d6-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="564d6-156">用于确定用户照片体验的 Set-csclientpolicy cmdlet 的两个参数是 **DisplayPhoto** 和 **MaxPhotoSizeKB**。</span><span class="sxs-lookup"><span data-stu-id="564d6-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="564d6-157">**DisplayPhoto**和**MaxPhotoSizeKB**的对应带内设置参数被命名为**PhotoUsage**。</span><span class="sxs-lookup"><span data-stu-id="564d6-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="564d6-158">**PhotoUsage**参数的值通过**endpointConfiguration** **provisionGroup**发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="564d6-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="564d6-159">有关详细信息，请参阅 [客户端策略和设置概述](https://go.microsoft.com/fwlink/?linkid=507470) 。</span><span class="sxs-lookup"><span data-stu-id="564d6-159">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="564d6-160">**DisplayPhoto**参数值确定用户的照片图像的来源。</span><span class="sxs-lookup"><span data-stu-id="564d6-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="564d6-161">下表中包含受支持的值。</span><span class="sxs-lookup"><span data-stu-id="564d6-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="564d6-162">DisplayPhoto 参数值</span><span class="sxs-lookup"><span data-stu-id="564d6-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="564d6-163">图像源</span><span class="sxs-lookup"><span data-stu-id="564d6-163">Image source</span></span></th>
<th><span data-ttu-id="564d6-164">Lync 2010 客户端设置</span><span class="sxs-lookup"><span data-stu-id="564d6-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="564d6-165">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="564d6-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="564d6-166">无</span><span class="sxs-lookup"><span data-stu-id="564d6-166">none</span></span></p></td>
<td><p><span data-ttu-id="564d6-167"><strong>不显示我的图片</strong></span><span class="sxs-lookup"><span data-stu-id="564d6-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="564d6-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="564d6-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="564d6-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="564d6-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="564d6-170"><strong>默认企业图片</strong></span><span class="sxs-lookup"><span data-stu-id="564d6-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="564d6-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="564d6-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="564d6-172">Web 地址</span><span class="sxs-lookup"><span data-stu-id="564d6-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="564d6-173"><strong>显示 Web 地址中的图片</strong></span><span class="sxs-lookup"><span data-stu-id="564d6-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="564d6-174">Lync 2010 客户端如何获取照片</span><span class="sxs-lookup"><span data-stu-id="564d6-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="564d6-175">在 Lync 2010 中，用户照片通过通讯簿服务在服务器上进行管理。</span><span class="sxs-lookup"><span data-stu-id="564d6-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="564d6-176">Lync 客户端通过首先查询服务器上的通讯簿 Web 查询 (ABWQ) 服务（通过通讯组列表展开 Web 服务公开）获取用户照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="564d6-177">客户端接收图像文件，然后将其复制到用户的缓存中，以避免在每次需要显示图像时都进行下载。</span><span class="sxs-lookup"><span data-stu-id="564d6-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="564d6-178">从查询返回的属性值也存储在用户的缓存通讯簿服务条目中。</span><span class="sxs-lookup"><span data-stu-id="564d6-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="564d6-179">通讯簿服务每24小时删除一次缓存的图像，这意味着在服务器上的缓存中更新新用户图像可能需要长达24小时。</span><span class="sxs-lookup"><span data-stu-id="564d6-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="564d6-180">您可以使用 [CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet 强制对缓存进行更新。</span><span class="sxs-lookup"><span data-stu-id="564d6-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="564d6-181">状态状态中包含的用户照片也具有关联的哈希值，Lync 客户端使用它来确定是否有可用的较新的映像。</span><span class="sxs-lookup"><span data-stu-id="564d6-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="564d6-182">将自动通知客户端对状态中使用的图像文件所做的更改。</span><span class="sxs-lookup"><span data-stu-id="564d6-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="564d6-183">由于照片未存储在 GalContacts 数据库中，因此下载用户照片并不依赖于客户端策略 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">set-csclientpolicy</A>) 中的<STRONG>AddressBookAvailability</STRONG>设置。</span><span class="sxs-lookup"><span data-stu-id="564d6-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="564d6-184">对 ABWQ 服务的查询包括以下属性：</span><span class="sxs-lookup"><span data-stu-id="564d6-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="564d6-185">**PhotoHash**    二进制照片数据的哈希值，用于确定当前照片是否已更改。</span><span class="sxs-lookup"><span data-stu-id="564d6-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="564d6-186">**PhotoRelPath**    存储在服务器上的图像文件的相对路径。</span><span class="sxs-lookup"><span data-stu-id="564d6-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="564d6-187">**PhotoSize**    图像文件的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="564d6-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="564d6-188">**时间戳**    上次从服务器下载图像文件并将其复制到客户端缓存的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="564d6-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="564d6-189">接下来，在检索图像文件后，Lync 2010 客户端将从查询返回的属性值与客户端从带内设置中接收的属性值进行比较，以查看它们是否不同。</span><span class="sxs-lookup"><span data-stu-id="564d6-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="564d6-190">如果值不同，客户端将使用 HTTP GET 请求检索已登录用户的图像文件。</span><span class="sxs-lookup"><span data-stu-id="564d6-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="564d6-191">此外，客户端在创建图像文件的缓存版本的时间与服务器之间每隔24小时进行一次检查，以将服务器上的 **PhotoHash** 属性的值与客户端上的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="564d6-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="564d6-192">如果值不同，客户端会知道图像文件已更改。</span><span class="sxs-lookup"><span data-stu-id="564d6-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="564d6-193">若要获取更新后的图像文件，客户端将再次查询 ABWQ 服务，以使用服务器上的映像文件更新客户端缓存中的图像文件，该文件也会重置客户端缓存中的文件上的 **时间戳** 。</span><span class="sxs-lookup"><span data-stu-id="564d6-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="564d6-194">下面是对 ABWQ 服务的查询的示例响应：</span><span class="sxs-lookup"><span data-stu-id="564d6-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="564d6-195">Lync 2013 中的用户照片</span><span class="sxs-lookup"><span data-stu-id="564d6-195">User photos in Lync 2013</span></span>

<span data-ttu-id="564d6-196">Lync 2013 为用户照片引入了对高分辨率图像的支持。</span><span class="sxs-lookup"><span data-stu-id="564d6-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="564d6-197">Lync 2013 还支持在 Exchange 2013 上将用户照片存储在用户的邮箱中，这将删除 Lync 2010 中存在的图像分辨率和大小限制。</span><span class="sxs-lookup"><span data-stu-id="564d6-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="564d6-198">Lync 2013 中的用户照片最高可达648像素，可达648像素，文件大小最高为 20 MB。</span><span class="sxs-lookup"><span data-stu-id="564d6-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="564d6-199">Lync 2013 中的高分辨率照片必须位于 Exchange 2013 上的用户邮箱中，并且仅支持 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="564d6-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="564d6-200">与 Exchange 的这种集成充分利用了2013版本的 Lync、Exchange 和 SharePoint （称为 Oauth）中包含的新的授权框架。</span><span class="sxs-lookup"><span data-stu-id="564d6-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="564d6-201">如果部署中未使用 Exchange 2013，则对用户照片的支持与 Lync 2010 相同。</span><span class="sxs-lookup"><span data-stu-id="564d6-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="564d6-202">但是，在 Lync 2013 客户端中，选择要使用的照片的用户选项有所不同。</span><span class="sxs-lookup"><span data-stu-id="564d6-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="564d6-203">在 Lync 2013 客户端中，用户可以选择 " **隐藏我的图片** " 或 " **显示我的图片**"。</span><span class="sxs-lookup"><span data-stu-id="564d6-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="564d6-204">默认情况下，" **显示来自网站的图片** " 选项是不可用，但可以通过分配客户端策略来启用。</span><span class="sxs-lookup"><span data-stu-id="564d6-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="564d6-205">隐藏我的图片</span><span class="sxs-lookup"><span data-stu-id="564d6-205">Hide my picture</span></span>

<span data-ttu-id="564d6-206">用户照片的设置位于 Lync 2013 的 " **选项** " 对话框中。</span><span class="sxs-lookup"><span data-stu-id="564d6-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="564d6-207">选择 " **隐藏我的图片**" 时，在 lync 客户端中不会显示任何用户照片，但您的照片仍显示在联系人卡片上和 Lync 之外。</span><span class="sxs-lookup"><span data-stu-id="564d6-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="564d6-208">显示我的图片</span><span class="sxs-lookup"><span data-stu-id="564d6-208">Show my picture</span></span>

<span data-ttu-id="564d6-209">当您选择 " **显示我的图片** " 选项时，您的用户照片将显示在 lync 客户端和 lync 对话中的其他用户中。</span><span class="sxs-lookup"><span data-stu-id="564d6-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="564d6-210">使用的图像是存储在 AD DS 中的图像。</span><span class="sxs-lookup"><span data-stu-id="564d6-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="564d6-211">显示网站中的图片</span><span class="sxs-lookup"><span data-stu-id="564d6-211">Show a picture from a website</span></span>

<span data-ttu-id="564d6-212">在将客户端策略设置为启用后，Lync 2013 中的 " **显示来自网站的图片** " 选项将变为可用。</span><span class="sxs-lookup"><span data-stu-id="564d6-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="564d6-213">客户端版本必须比15.0.4535.1002 （与 Lync 累积更新一起安装）更新 [：2013年11月](https://go.microsoft.com/fwlink/p/?linkid=509908)。</span><span class="sxs-lookup"><span data-stu-id="564d6-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="564d6-214">用户可能需要注销，然后再重新登录，以查看客户端中的更改。</span><span class="sxs-lookup"><span data-stu-id="564d6-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="564d6-215">您可以通过在 Lync Server 命令行管理程序中运行[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)策略，将客户端策略设置为启用以**显示网站设置中的图片**。</span><span class="sxs-lookup"><span data-stu-id="564d6-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="564d6-216">下面的示例 cmdlet 演示如何为部署中的所有用户全局设置策略：</span><span class="sxs-lookup"><span data-stu-id="564d6-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="564d6-217">将图像上载到用户的邮箱时，Exchange 会自动创建可在客户端应用程序中使用的图像的低分辨率版本。</span><span class="sxs-lookup"><span data-stu-id="564d6-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="564d6-218">用户照片也会在 AD DS 中进行更新。</span><span class="sxs-lookup"><span data-stu-id="564d6-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="564d6-219">在 AD DS 中更新图像文件时，将创建一个 48 x 48 像素的图像，并将其用于 AD DS 中的 thumbnailPhoto。</span><span class="sxs-lookup"><span data-stu-id="564d6-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="564d6-220">任何现有的图像都将被替换。</span><span class="sxs-lookup"><span data-stu-id="564d6-220">Any existing image is replaced.</span></span> <span data-ttu-id="564d6-221">因此，如果向 AD DS 添加了一个 96 x 96 的图像，它将被新的 48 x 48 图像覆盖。</span><span class="sxs-lookup"><span data-stu-id="564d6-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="564d6-222">这只是重要的一点是，您的环境中有用户使用 Lync 2010 客户端，因为这些客户端将从 AD DS 获取用户照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="564d6-223">如果您的组织中有 Lync 2010 客户端，则可以导入 96 x 96 像素的图像以替换 AD DS 创建的图像。</span><span class="sxs-lookup"><span data-stu-id="564d6-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="564d6-224">Lync 2013 中的用户照片支持</span><span class="sxs-lookup"><span data-stu-id="564d6-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="564d6-225">在 Lync 2013 中，支持以下表格中所述的用户照片的三种图像分辨率。</span><span class="sxs-lookup"><span data-stu-id="564d6-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="564d6-226">所使用的图像由分配给 Lync 用户的客户端策略设置决定。</span><span class="sxs-lookup"><span data-stu-id="564d6-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="564d6-227">有关详细信息，请参阅本主题中的 "使用客户端策略 cmdlet 管理用户的照片"。</span><span class="sxs-lookup"><span data-stu-id="564d6-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="564d6-228">图像分辨率 (像素) </span><span class="sxs-lookup"><span data-stu-id="564d6-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="564d6-229">应用程序</span><span class="sxs-lookup"><span data-stu-id="564d6-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="564d6-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="564d6-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="564d6-231">如果没有选择更高分辨率的图像，则使用</span><span class="sxs-lookup"><span data-stu-id="564d6-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="564d6-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="564d6-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="564d6-233">在 Outlook Web App 和 Outlook 2013 中使用</span><span class="sxs-lookup"><span data-stu-id="564d6-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="564d6-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="564d6-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="564d6-235">在 Lync 2013 桌面客户端和 Lync 2013 Web App 中使用</span><span class="sxs-lookup"><span data-stu-id="564d6-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="564d6-236">任何在 Exchange 2013 中启用了邮箱的用户都可以通过 Outlook Web Access 或 Lync 2013 客户端选项上传不同的图像，包括高分辨率照片。</span><span class="sxs-lookup"><span data-stu-id="564d6-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="564d6-237">使用的图像的推荐设置包括：</span><span class="sxs-lookup"><span data-stu-id="564d6-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="564d6-238">**图像分辨率**    648 x 648 像素</span><span class="sxs-lookup"><span data-stu-id="564d6-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="564d6-239">**颜色深度**    24位</span><span class="sxs-lookup"><span data-stu-id="564d6-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="564d6-240">**图像文件大小**    最高 20 MB</span><span class="sxs-lookup"><span data-stu-id="564d6-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="564d6-241">**文件格式**    JPEG</span><span class="sxs-lookup"><span data-stu-id="564d6-241">**File format**   JPEG</span></span>

<span data-ttu-id="564d6-242">一个典型的24位 JPEG 图像为648像素 x 648 像素的文件大小约为 240 KB，因此每4个用户照片需要 1 MB 的存储空间。</span><span class="sxs-lookup"><span data-stu-id="564d6-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

