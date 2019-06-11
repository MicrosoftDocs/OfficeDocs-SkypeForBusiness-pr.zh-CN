---
title: 用户照片在 Lync 中的显示方式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941c1ab56feea557dfc792ea0af6415dd2a56851
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>用户照片在 Lync 中的显示方式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-08-25_

**摘要:** 在 Lync 客户端中显示的用户照片可能会有所不同, 具体取决于你使用的是哪种 Lync 功能, 例如在会议或 IM 聊天中。

Lync 2010 引入了一张照片, 其中包含与 Lync 档案一起显示给其他 Lync 用户的照片。 您还可以选择是否在 Lync 客户端中显示联系人的照片。 在 Lync 2013 中, 支持高分辨率的照片供用户查看。 本主题介绍了 Lync 客户端如何获取和显示用户照片、存储图像的位置、每个图像源的限制以及不同 Lync 服务如何使用用户照片。

<div>

## <a name="planning-considerations"></a>规划注意事项

在计划实现对用户照片的支持时, 应考虑以下事项。

  - 高清晰度用户照片支持要求用户的邮箱位于 Exchange 2013 上, 而 Lync 用户帐户位于 Lync 2013 池中。

  - 只有在使用 Lync Server 2013 和 Exchange 2013 的环境中, 才支持高清晰度用户照片。

  - 在 Exchange 2010 上具有邮箱的用户将始终使用来自 AD DS 的**thumbnailPhoto**属性作为其用户照片的源。

  - 从 AD DS 存储为**thumbnailPhoto**属性的用户照片不会显示在外部/联盟联系人中。

  - 如果用户联系人的照片存储在 AD DS 中, 则使用的图像文件限制为96×96像素, 不超过 100 KB 的文件大小。

  - 如果 Lync Server 和 Exchange Server 之间的连接丢失, 则将显示用户的 AD DS 中的低分辨率**thumbnailPhoto**以及仅限内部用户。

  - 当活动扬声器未启用视频时, 将在 Lync 2013 会议中显示高分辨率用户照片。 同样, 将鼠标移到库中的缩略图照片上将显示高分辨率的照片。

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010 中的用户照片

在 Lync 2010 客户端中, 可以从两个选项中进行选择, 以显示个人资料的照片、**默认的企业图片**和**显示来自 web 地址的图片**。

<div>

## <a name="default-corporate-picture"></a>默认的企业图片

当您选择 "**默认企业图片**" 选项时, Lync 将从 Active Directory 域服务中获取为您显示的照片。 所使用的图像是在 Active Directory 域服务中定义为**thumbnailPhoto**属性的值的图像。 这是 Exchange 在 Outlook 中显示图像时使用的相同文件。

使用来自 Active Directory 域服务中的图像的注意事项包括以下几项:

  - 仅支持尺寸最高为96像素 x 96 像素的图像。 图像的文件大小限制为 100 KB。

  - 默认情况下, 用户可以更改用于**thumbnailPhoto**属性的图像, 但不直接通过 Lync 客户端。 你可以通过 Active Directory 域服务禁用此操作。

  - 存储在 Active Directory 域服务中的图像不会显示给您的组织外部的联系人, 即使他们是联盟联系人也是如此。

  - 在大型组织中, 为大量用户存储和检索图像可能会影响 Active Directory 域服务数据库的大小和性能。

  - 有限的图像尺寸和文件大小意味着仅可以使用低分辨率图像。

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>用户如何在 Active Directory 域服务中管理其用户照片

用户无法直接通过 Lync 2010 客户端更改其 Active Directory 域服务配置文件中使用的图像。 如果可用, 他们可以使用以下选项之一执行此操作:

  - **Sharepoint server**   用户可以将照片上传到 sharepoint 服务器上的 "我的网站", 然后[配置 sharepoint 中的配置文件同步](http://go.microsoft.com/fwlink/p/?linkid=507466)以将照片同步到 Active Directory 域中的**thumbnailPhoto**属性服务.

  - **存储在可公开访问的 URL**   的照片上, 用户可以配置其用户照片, 指定要使用的图像的公共可访问 url。 在没有密码的情况下, 必须能够公开访问图像。 存储在指定 web 地址处的图像通过状态信息中的 "联系人卡片" 类别传输给其他用户。 当 Lync 客户端需要显示用户照片时, 它将从指定的 web 地址检索图像。

  - **适用于 Windows PowerShell**   管理员的 exchange 2010 cmdlet 可在 exchange 2010 管理外壳中运行[RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet 以管理**thumbnailPhoto**属性。 当将图像导入 Exchange 2010 cmdlet 时, 文件大小限制为 10 KB。

  - **第三方工具**   用户只能将自己的照片上载到**thumbnailPhoto**属性。

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>显示来自 web 地址的图片

选择 "**显示来自 web 地址的图片**" 选项时, Lync 将获取您输入的地址中的图像, 并在 Lync 中为您的用户照片显示该图像。

使用来自 web 地址的图像的注意事项包括以下内容:

  - 文件大小限制由客户端策略中的**MaxPhotoSizeKB**属性确定, 该属性使用[set-csclientpolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet 定义。 默认大小限制为 30 KB。 最大值为 100 KB。 对图像的分辨率没有限制, 但是如果你尝试使用超过大小限制的图像文件, 则不会将其下载到 Lync 客户端。 你可以将值设置为 0, 以禁用在 Lync 中使用所有用户照片。

  - 外部联盟联系人可以看到来自 web 地址的用户照片。

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>使用客户端策略 cmdlet 管理用户的照片

在 Lync Server 2010 中, 客户端策略设置配置了 Set-csclientpolicy cmdlet。 配置的策略设置通过带内设置发送到客户端。 确定用户照片体验的 Set-csclientpolicy cmdlet 的两个参数是**DisplayPhoto**和**MaxPhotoSizeKB**。 **DisplayPhoto**和**MaxPhotoSizeKB**的对应带内预配参数名为**PhotoUsage**。 **PhotoUsage**参数的值通过**endpointConfiguration** **provisionGroup**发送到客户端。 有关详细信息, 请参阅[客户端策略概述和设置](http://go.microsoft.com/fwlink/?linkid=507470)。

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
<td><p>尚</p></td>
<td><p><strong>不显示我的图片</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>默认的企业图片</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Web 地址</p></td>
<td><p><strong>显示来自 web 地址的图片</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 客户端如何获取照片

在 Lync 2010 中, 通过通讯簿服务在服务器上管理用户照片。 Lync 客户端通过首先在服务器上查询通讯簿 Web 查询 (ABWQ) 服务来获取用户照片, 该服务通过通讯组列表展开 Web 服务公开。 客户端接收图像文件, 然后将其复制到用户的缓存中, 避免每次需要显示图像时都下载图像。 从查询返回的属性值也存储在用户的缓存通讯簿服务条目中。 通讯簿服务每隔24小时删除所有缓存的图像, 这意味着最多需要24小时才能在服务器上的缓存中更新新用户图像。 你可以使用[CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet 强制对缓存进行更新。

联机状态中包含的用户照片也有一个关联的哈希值, Lync 客户端使用该哈希值确定是否有较新的可用图像。 客户会自动收到有关状态中使用的图像文件更改的通知。

<div class=" ">


> [!NOTE]  
> 由于照片未存储在 GalContacts 数据库中, 因此下载用户照片不依赖于客户端策略中的<STRONG>AddressBookAvailability</STRONG>设置 (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-set-csclientpolicy</A>)。



</div>

对 ABWQ 服务的查询包括以下属性:

  - **PhotoHash**   二进制照片数据的哈希值, 并用于确定当前照片是否已更改。

  - **PhotoRelPath**   服务器上存储的图像文件的相对路径。

  - **PhotoSize**   图像文件的大小 (以字节为单位)。

  - **时间戳**   上次从服务器下载图像文件并将其复制到客户端缓存的日期和时间。

接下来, 在检索图像文件之后, Lync 2010 客户端会将从查询返回的属性值与客户端从带内配置接收的属性值进行比较, 以查看它们是否不同。 如果值不同, 客户端将使用 HTTP GET 请求检索登录用户的图像文件。

此外, 自创建图像文件的缓存版本后, 客户端每隔24小时检查一次服务器, 以比较服务器上**PhotoHash**属性的值与客户端上的值。 如果值不同, 则客户端知道图像文件已更改。 若要获取已更新的图像文件, 客户端再次查询 ABWQ 服务以更新客户端缓存中的图像文件和服务器上的映像文件, 后者还会在客户端缓存中重置文件上的**时间戳**。

下面是对 ABWQ 服务的查询的示例响应:

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

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Lync 2013 中的用户照片

Lync 2013 为用户照片引入了对高分辨率图像的支持。 Lync 2013 还包括对在 Exchange 2013 上的用户邮箱中存储用户照片的支持, 这将删除 Lync 2010 中存在的图像分辨率和大小限制。 Lync 2013 中的用户照片最高可达 648 648 像素, 其文件大小最高可达 20 MB。 Lync 2013 中的高分辨率照片必须位于 Exchange 2013 的用户邮箱中, 并且仅受 Lync 2013 客户端支持。 与 Exchange 的这种集成充分利用了2013版本的 Lync、Exchange 和 SharePoint (名为 Oauth) 中包含的新授权框架。

如果你的部署中未使用 Exchange 2013, 则对用户照片的支持与 Lync 2010 的支持相同。 但是, 在 Lync 2013 客户端中选择要使用的照片的用户选项有所不同。 在 Lync 2013 客户端中, 用户可以选择 "**隐藏我的图片**" 或 "**显示我的图片**"。 默认情况下, "**显示来自网站的图片**" 选项不可用, 但可通过分配客户端策略启用。

<div>

## <a name="hide-my-picture"></a>隐藏我的图片

用户照片的设置位于 Lync 2013 的 "**选项**" 对话框中。 选择 "**隐藏我的图片**" 时, 将不会在 lync 客户端中显示任何用户照片, 但你的照片仍将显示在联系人卡片上和 Lync 外部。

</div>

<div>

## <a name="show-my-picture"></a>显示我的图片

选择 "**显示我的图片**" 选项时, 你的用户照片将显示在 lync 客户端和 lync 对话中的其他用户。 使用的图像是存储在 AD DS 中的图像。

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>显示网站中的图片

将客户端策略设置为启用后, Lync 2013 中的 "**显示图片**" 选项将在 Lync 中可用。 客户端版本必须比与 Lync 累积更新一起安装的15.0.4535.1002 更新[: 2013 年11月](http://go.microsoft.com/fwlink/p/?linkid=509908)。 用户可能需要注销, 然后重新登录, 才能查看客户端中的更改。

你可以通过在 Lync Server 命令行管理程序中运行[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)策略, 将客户端策略设置为允许**从网站设置显示图片**。 下面的示例 cmdlet 演示如何为你的部署中的所有用户全局设置策略:

   ```
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```
    $po.PolicyEntry.Add($pe)
   ```

   ```
    Set-CsClientPolicy -Instance $po
   ```


将图像上载到用户的邮箱后, Exchange 会自动创建可在客户端应用程序中使用的图像的较低分辨率版本。 用户照片也会在 AD DS 中更新。

<div class=" ">


> [!NOTE]  
> 在 AD DS 中更新图像文件时, 将创建一个 48 x 48 像素的图像, 并将其用于 AD DS 中的 thumbnailPhoto。 将替换任何现有图像。 因此, 如果将 96 x 96 图像添加到 AD DS, 它将被新的 48 x 48 图像覆盖。 这只是很重要, 因为你的环境中有用户使用 Lync 2010 客户端, 因为这些客户将从 AD DS 获取用户照片。 如果你的组织中有 Lync 2010 客户端, 你可以导入 96 x 96 像素图像以替换 AD DS 创建的图像。



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013 中的用户照片支持

在 Lync 2013 中, 用户照片支持三种图像分辨率, 如下表所述。 所使用的图像由分配给 Lync 用户的客户端策略设置确定。 有关详细信息, 请参阅本主题中的 "使用客户端策略 cmdlet 管理用户的照片"。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>图像分辨率 (像素)</th>
<th>应用程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>如果未选择更高分辨率的图像, 则使用</p></td>
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


任何在 Exchange 2013 中启用了邮箱的用户都可以通过 Outlook Web Access 或 Lync 2013 客户端选项上载不同的图像, 包括高分辨率的照片。 所使用的图像的推荐设置包括:

  - **图像分辨率**   648 x 648 像素

  - **颜色深度**   24 位

  - **图像文件大小**   最多为 20 MB

  - **JPEG 文件格式**   

648像素乘以648像素的典型24位 JPEG 图像的文件大小约为 240 KB, 因此每4个用户照片需要 1 MB 的存储空间。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

