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
# <a name="how-user-photos-are-displayed-in-lync"></a>如何在 Lync 中显示用户照片

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-08-25_

**摘要：** 在 Lync 客户端中显示的用户照片可能会有所不同，具体取决于所使用的 Lync 功能，如会议或 IM 聊天中的时间。

Lync 2010 引入了在 Lync 配置文件中加入照片的功能，该照片显示给其他 Lync 用户。 您还可以选择是否在 Lync 客户端中显示联系人的照片。 在 Lync 2013 中，支持适用于用户的高分辨率照片。 本主题介绍 Lync 客户端如何获取和显示存储图像的用户照片、每个图像源的限制以及不同 Lync 服务如何使用用户照片。

<div>

## <a name="planning-considerations"></a>规划注意事项

在计划实现对用户照片的支持时，应考虑以下事项。

  - 高定义用户照片支持要求用户的邮箱位于 Exchange 2013，而 Lync 用户帐户位于 Lync 2013 池中。

  - 仅在使用 Lync Server 2013 和 Exchange 2013 的环境中支持高清晰度用户照片。

  - 拥有 Exchange 2010 邮箱的用户将始终使用 AD DS 中的 **thumbnailPhoto** 属性作为其用户照片的源。

  - 作为 **thumbnailPhoto** 属性存储在 AD DS 中的用户照片不会显示在外部/联合联系人中。

  - 如果用户联系人照片存储在 AD DS 中，则使用的图像文件的大小限制为 96 x 96 像素，且不超过 100 KB 的文件大小。

  - 如果 Lync Server 和 Exchange Server 之间的连接丢失，则用户的低分辨率 **thumbnailPhoto** 将显示在 AD DS 中，并且仅供内部用户。

  - 当活动扬声器未启用视频时，会在 Lync 2013 会议中显示高分辨率用户照片。 此外，将鼠标移到库中的缩略图照片上也会显示高分辨率照片。

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010 中的用户照片

在 Lync 2010 客户端中，可以从以下两个选项中选择用于显示配置文件的照片、 **默认的企业图片** 并 **显示来自 web 地址的图片**。

<div>

## <a name="default-corporate-picture"></a>默认企业图片

当您选择 " **默认企业图片** " 选项时，Lync 将从 Active Directory 域服务中获取为您显示的照片。 使用的图像是定义为 Active Directory 域服务中的 **thumbnailPhoto** 属性的值的图像。 这是 Exchange 在 Outlook 中显示图像时使用的同一文件。

使用 Active Directory 域服务中的图像时的注意事项包括以下各项：

  - 仅支持尺寸最大为96像素 x 96 像素的图像。 图像的文件大小限制为 100 KB。

  - 默认情况下，用户可以更改用于 **thumbnailPhoto** 属性的图像，但不直接通过 Lync 客户端。 您可以通过 Active Directory 域服务禁用此。

  - 存储在 Active Directory 域服务中的图像不会显示给组织外部的联系人，即使它们是联盟联系人也是如此。

  - 在大型组织中，存储和检索大量用户的图像可能会影响 Active Directory 域服务数据库的大小和性能。

  - 有限的图像尺寸和文件大小意味着只有低分辨率图像可以使用。

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>用户如何在 Active Directory 域服务中管理其用户照片

用户无法通过 Lync 2010 客户端直接更改 Active Directory 域服务配置文件中使用的图像。 如果可用，他们可以使用下列选项之一来执行此操作：

  - **SharePoint Server**    用户可以将照片上传到 SharePoint Server 上的 "我的网站"，然后[在 sharepoint 中配置配置文件同步](https://go.microsoft.com/fwlink/p/?linkid=507466)，以便将照片同步到 Active Directory 域服务中的**thumbnailPhoto**属性。

  - **存储在可公开访问的 URL**     上的照片用户可以配置其用户照片，以指定要使用的图像的公开访问的 URL。 在没有密码的情况下，图像必须可公开访问。 存储在指定 web 地址的图像通过状态信息中的联系人卡片类别传输给其他用户。 当 Lync 客户端需要显示用户照片时，它将从指定的 web 地址检索图像。

  - **用于 Windows PowerShell**     的 Exchange 2010 cmdlet管理员可以在 Exchange 2010 命令行管理程序中运行[import-recipientdataproperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet 来管理**thumbnailPhoto**属性。 在使用 Exchange 2010 cmdlet 导入图像时，文件大小限制为 10 KB。

  - **第三方工具**    用户只能将自己的照片上载到**thumbnailPhoto**属性。

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>显示 Web 地址中的图片

当您选择 " **显示来自 web 地址的图片** " 选项时，Lync 将获取您输入的地址中的图像，并在 Lync 中为用户照片显示该图像。

使用来自 web 地址的图像的注意事项包括以下各项：

  - 文件大小限制由客户端策略中使用[set-csclientpolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet 定义的**MaxPhotoSizeKB**属性决定。 默认大小限制为 30 KB。 最大值为 100 KB。 对图像的分辨率没有限制，但如果您尝试使用超过大小限制的图像文件，则不会将其下载到 Lync 客户端。 您可以将该值设置为0，以禁止在 Lync 中使用所有用户照片。

  - 来自 web 地址的用户照片可以通过外部联盟联系人查看。

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>使用客户端策略 cmdlet 管理用户照片

在 Lync Server 2010 中，客户端策略设置是使用 Set-csclientpolicy cmdlet 配置的。 配置的策略设置通过带内设置发送到客户端。 用于确定用户照片体验的 Set-csclientpolicy cmdlet 的两个参数是 **DisplayPhoto** 和 **MaxPhotoSizeKB**。 **DisplayPhoto**和**MaxPhotoSizeKB**的对应带内设置参数被命名为**PhotoUsage**。 **PhotoUsage**参数的值通过**endpointConfiguration** **provisionGroup**发送到客户端。 有关详细信息，请参阅 [客户端策略和设置概述](https://go.microsoft.com/fwlink/?linkid=507470) 。

**DisplayPhoto**参数值确定用户的照片图像的来源。 下表中包含受支持的值。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto 参数值</th>
<th>图像源</th>
<th>Lync 2010 客户端设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>无</p></td>
<td><p><strong>不显示我的图片</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>默认企业图片</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Web 地址</p></td>
<td><p><strong>显示 Web 地址中的图片</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 客户端如何获取照片

在 Lync 2010 中，用户照片通过通讯簿服务在服务器上进行管理。 Lync 客户端通过首先查询服务器上的通讯簿 Web 查询 (ABWQ) 服务（通过通讯组列表展开 Web 服务公开）获取用户照片。 客户端接收图像文件，然后将其复制到用户的缓存中，以避免在每次需要显示图像时都进行下载。 从查询返回的属性值也存储在用户的缓存通讯簿服务条目中。 通讯簿服务每24小时删除一次缓存的图像，这意味着在服务器上的缓存中更新新用户图像可能需要长达24小时。 您可以使用 [CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet 强制对缓存进行更新。

状态状态中包含的用户照片也具有关联的哈希值，Lync 客户端使用它来确定是否有可用的较新的映像。 将自动通知客户端对状态中使用的图像文件所做的更改。

<div class=" ">


> [!NOTE]  
> 由于照片未存储在 GalContacts 数据库中，因此下载用户照片并不依赖于客户端策略 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">set-csclientpolicy</A>) 中的<STRONG>AddressBookAvailability</STRONG>设置。



</div>

对 ABWQ 服务的查询包括以下属性：

  - **PhotoHash**    二进制照片数据的哈希值，用于确定当前照片是否已更改。

  - **PhotoRelPath**    存储在服务器上的图像文件的相对路径。

  - **PhotoSize**    图像文件的大小（以字节为单位）。

  - **时间戳**    上次从服务器下载图像文件并将其复制到客户端缓存的日期和时间。

接下来，在检索图像文件后，Lync 2010 客户端将从查询返回的属性值与客户端从带内设置中接收的属性值进行比较，以查看它们是否不同。 如果值不同，客户端将使用 HTTP GET 请求检索已登录用户的图像文件。

此外，客户端在创建图像文件的缓存版本的时间与服务器之间每隔24小时进行一次检查，以将服务器上的 **PhotoHash** 属性的值与客户端上的值进行比较。 如果值不同，客户端会知道图像文件已更改。 若要获取更新后的图像文件，客户端将再次查询 ABWQ 服务，以使用服务器上的映像文件更新客户端缓存中的图像文件，该文件也会重置客户端缓存中的文件上的 **时间戳** 。

下面是对 ABWQ 服务的查询的示例响应：
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

## <a name="user-photos-in-lync-2013"></a>Lync 2013 中的用户照片

Lync 2013 为用户照片引入了对高分辨率图像的支持。 Lync 2013 还支持在 Exchange 2013 上将用户照片存储在用户的邮箱中，这将删除 Lync 2010 中存在的图像分辨率和大小限制。 Lync 2013 中的用户照片最高可达648像素，可达648像素，文件大小最高为 20 MB。 Lync 2013 中的高分辨率照片必须位于 Exchange 2013 上的用户邮箱中，并且仅支持 Lync 2013 客户端。 与 Exchange 的这种集成充分利用了2013版本的 Lync、Exchange 和 SharePoint （称为 Oauth）中包含的新的授权框架。

如果部署中未使用 Exchange 2013，则对用户照片的支持与 Lync 2010 相同。 但是，在 Lync 2013 客户端中，选择要使用的照片的用户选项有所不同。 在 Lync 2013 客户端中，用户可以选择 " **隐藏我的图片** " 或 " **显示我的图片**"。 默认情况下，" **显示来自网站的图片** " 选项是不可用，但可以通过分配客户端策略来启用。

<div>

## <a name="hide-my-picture"></a>隐藏我的图片

用户照片的设置位于 Lync 2013 的 " **选项** " 对话框中。 选择 " **隐藏我的图片**" 时，在 lync 客户端中不会显示任何用户照片，但您的照片仍显示在联系人卡片上和 Lync 之外。

</div>

<div>

## <a name="show-my-picture"></a>显示我的图片

当您选择 " **显示我的图片** " 选项时，您的用户照片将显示在 lync 客户端和 lync 对话中的其他用户中。 使用的图像是存储在 AD DS 中的图像。

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>显示网站中的图片

在将客户端策略设置为启用后，Lync 2013 中的 " **显示来自网站的图片** " 选项将变为可用。 客户端版本必须比15.0.4535.1002 （与 Lync 累积更新一起安装）更新 [：2013年11月](https://go.microsoft.com/fwlink/p/?linkid=509908)。 用户可能需要注销，然后再重新登录，以查看客户端中的更改。

您可以通过在 Lync Server 命令行管理程序中运行[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)策略，将客户端策略设置为启用以**显示网站设置中的图片**。 下面的示例 cmdlet 演示如何为部署中的所有用户全局设置策略：

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


将图像上载到用户的邮箱时，Exchange 会自动创建可在客户端应用程序中使用的图像的低分辨率版本。 用户照片也会在 AD DS 中进行更新。

<div class=" ">


> [!NOTE]  
> 在 AD DS 中更新图像文件时，将创建一个 48 x 48 像素的图像，并将其用于 AD DS 中的 thumbnailPhoto。 任何现有的图像都将被替换。 因此，如果向 AD DS 添加了一个 96 x 96 的图像，它将被新的 48 x 48 图像覆盖。 这只是重要的一点是，您的环境中有用户使用 Lync 2010 客户端，因为这些客户端将从 AD DS 获取用户照片。 如果您的组织中有 Lync 2010 客户端，则可以导入 96 x 96 像素的图像以替换 AD DS 创建的图像。



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013 中的用户照片支持

在 Lync 2013 中，支持以下表格中所述的用户照片的三种图像分辨率。 所使用的图像由分配给 Lync 用户的客户端策略设置决定。 有关详细信息，请参阅本主题中的 "使用客户端策略 cmdlet 管理用户的照片"。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>图像分辨率 (像素) </th>
<th>应用程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>如果没有选择更高分辨率的图像，则使用</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>在 Outlook Web App 和 Outlook 2013 中使用</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>在 Lync 2013 桌面客户端和 Lync 2013 Web App 中使用</p></td>
</tr>
</tbody>
</table>


任何在 Exchange 2013 中启用了邮箱的用户都可以通过 Outlook Web Access 或 Lync 2013 客户端选项上传不同的图像，包括高分辨率照片。 使用的图像的推荐设置包括：

  - **图像分辨率**    648 x 648 像素

  - **颜色深度**    24位

  - **图像文件大小**    最高 20 MB

  - **文件格式**    JPEG

一个典型的24位 JPEG 图像为648像素 x 648 像素的文件大小约为 240 KB，因此每4个用户照片需要 1 MB 的存储空间。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

