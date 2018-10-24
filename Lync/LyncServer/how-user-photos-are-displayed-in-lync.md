---
title: 用户照片在 Lync 中的显示方式
TOCTitle: 用户照片在 Lync 中的显示方式
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62832971
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用户照片在 Lync 中的显示方式

 

_**上一次修改主题：** 2016-12-08_

摘要：根据您使用的具体 Lync 功能（例如在会议中还是在 IM 聊天中），Lync 客户端中显示的用户照片可能有所不同。

Lync 2010 引入了在 Lync 个人资料中包含显示给其他 Lync 用户的照片的功能。您可以在 Lync 客户端中选择是否要为联系人显示照片。Lync 2013 中支持高分辨率的用户照片。本主题介绍了 Lync 客户端如何获取和显示用户照片、图像将存储在何处、各图像来源的限制以及各种 Lync 服务如何使用用户的照片。

## 规划注意事项

在规划实施用户照片支持时，您应考虑以下事项。

  - 高分辨率用户照片支持要求用户邮箱位于 Exchange 2013 上，并且 Lync 用户帐户处于 Lync 2013 池中。

  - 仅在同时使用 Lync Server 2013 和 Exchange 2013 的环境中支持高分辨率用户照片。

  - 使用 Exchange 2010 邮箱的用户总是可以使用 AD DS 的 **thumbnailPhoto** 属性作为其用户照片的来源。

  - 存储为 AD DS **thumbnailPhoto** 属性的用户照片不会对外部/联盟联系人显示。

  - 如果用户联系人的照片存储在 AD DS 中，则所用图像文件限为 96×96 像素，文件大小不能超过 100 KB。

  - 如果 Lync Server 与 Exchange Server 之间的连接丢失，将显示 AD DS 中的用户低分辨率 **thumbnailPhoto**，并且仅对内部用户显示。

  - 在 Lync 2013 会议中，如果当前发言人未启用视频，则显示高分辨率用户照片。此外，在库中的照片缩略图上移动鼠标也会显示高分辨率照片。

## Lync 2010 中的用户照片

在 Lync 2010 客户端中，您可以选择两种显示个人资料照片的选项：“默认企业图片”和“显示 Web 地址中的图片”。

## 默认企业图片

选择“默认企业图片”选项时，Lync 将从 Active Directory 域服务 获取为您显示的照片。所用图片是定义为 Active Directory 域服务 的 **thumbnailPhoto** 属性值的图片。这与 Exchange 用于在 Outlook 中显示图片的文件相同。

使用 Active Directory 域服务 中的图像时，注意事项如下：

  - 仅支持尺寸不超过 96x96 像素的图像。图像文件的大小不能超过 100 KB。

  - 默认情况下，用户可以更改 **thumbnailPhoto** 属性所用的图像，但不能直接通过 Lync 客户端更改。可以通过 Active Directory 域服务 禁用此功能。

  - Active Directory 域服务 中存储的图像不会对组织外部的联系人显示，即便是联盟联系人也是如此。

  - 在大型组织中，为大量用户存储和检索图像可能会影响 Active Directory 域服务 数据库的大小和性能。

  - 限制图像尺寸和文件大小意味着仅能使用低分辨率图像。

## 用户如何在 Active Directory 域服务 中管理用户照片

用户不能直接通过 Lync 2010 客户端更改其 Active Directory 域服务 个人资料中使用的图像。他们可以通过以下选项之一（如果可用）完成此更改：

  - **SharePoint Server**   用户可以将照片上载到 SharePoint Server 中的“我的网站”，然后[在 SharePoint 中配置个人资料同步](http://go.microsoft.com/fwlink/p/?linkid=507466)，将照片同步到 Active Directory 域服务 的 **thumbnailPhoto** 属性。

  - **在可公开访问的 URL 处存储的照片**   在配置用户照片时，用户可以指定希望使用的图像的可公开访问 URL。此图像必须能在不需要密码的情况下公开访问。所指定 Web 地址处存储的图像将通过状态信息中的联系人卡片类别传输给其他用户。Lync 客户端需要显示用户照片时将从指定 Web 地址检索图像。

  - **Exchange 2010 Windows PowerShell cmdlet**   管理员可以在 Exchange 2010 Management Shell 中运行 [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet，以管理 **thumbnailPhoto** 属性。使用 Exchange 2010 cmdlet 导入图像时，文件大小不能超过 10 KB。

  - **第三方工具**   用户可以仅上载自己的照片，以供 **thumbnailPhoto** 属性使用。

## 显示 Web 地址中的图片

选择“显示 Web 地址中的图片”选项时，Lync 将在您输入的地址处获取图像，并在 Lync 中显示为用户照片。

使用 Web 地址中的图像时，注意事项如下：

  - 文件大小限制由客户端策略中的 **MaxPhotoSizeKB** 属性决定，可使用 [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet 定义。默认大小限制为 30 KB。最大值为 100 KB。图像分辨率无限制，但如果尝试使用超出大小限制的图像文件，文件将无法下载到 Lync 客户端。您可以将此值设置为 0，以禁用在 Lync 中使用任何用户照片。

  - 外部联盟联系人可以查看 Web 地址中的用户照片。

## 使用客户端策略 cmdlet 管理用户照片

在 Lync Server 2010 中，客户端策略的设置是使用 CsClientPolicy cmdlet 配置的。所配置的策略设置将通过带内设置发送至客户端。决定用户照片体验的两个 CsClientPolicy cmdlet 参数分别是 **DisplayPhoto** 和 **MaxPhotoSizeKB**。**DisplayPhoto** 和 **MaxPhotoSizeKB** 对应的带内设置参数名为 **PhotoUsage**。**PhotoUsage** 参数的值将通过 **endpointConfigurationprovisionGroup** 发送到客户端。如需了解更多信息，请参阅[客户端策略和设置概述](http://go.microsoft.com/fwlink/?linkid=507470)。

**DisplayPhoto** 参数值决定用户照片图像的来源。下表列出了支持的值。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto 参数值</th>
<th>图像来源</th>
<th>Lync 2010 客户端设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>无</p></td>
<td><p>不显示我的图片</p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p>默认企业图片</p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Web 地址</p></td>
<td><p>显示 Web 地址中的图片</p></td>
</tr>
</tbody>
</table>


## Lync 2010 客户端如何获取图片

在 Lync 2010 中，用户照片由通讯簿服务在服务器上管理。Lync 客户端首先查询服务器上通过通讯组列表扩展 Web 服务公开的通讯簿 Web 查询 (ABWQ) 服务。客户端接收图像文件，然后将其复制到用户的缓冲中，避免在每次需要显示图片时重新下载。查询返回的属性值也会存储在对应用户缓存的通讯簿服务条目中。通讯簿服务每隔 24 小时删除全部缓存的图像，也就是说服务器缓存中的新用户图像最多可能要经过 24 小时才能得到更新。您可以使用 [Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook) cmdlet 强制更新缓存。

状态中包含的用户照片还有相关的哈希值，Lync 客户端利用此哈希值确定是否有更新的图像可用。在状态中使用的图像文件发生更改时，客户端将自动获得通知。

> [!NOTE]  
> 由于照片并未存储在 GalContacts.db 数据库中，因此用户照片的下载不依赖于客户端策略 (<a href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</a>) 中的 <strong>AddressBookAvailability</strong> 设置。



ABWQ 服务的查询包括以下属性：

  - **PhotoHash**   二进制图片数据的哈希值，用于确定当前照片是否已更改。

  - **PhotoRelPath**   图像文件在服务器上的相对存储路径。

  - **PhotoSize**   图像文件的大小，单位为字节。

  - **TimeStamp**   最后从服务器下载图像文件并将其复制到客户端缓存中的日期和时间。

接下来，在检索图像文件后，Lync 2010 客户端会将查询返回的属性值与客户端通过带内设置接收到的属性值进行对比，判断两者是否不同。如果两个值不同，客户端将通过 HTTP GET 请求检索已登录用户的图像文件。

此外，从图像文件的缓冲版本创建之时起，客户端每隔 24 小时检查一次服务器，将服务器上的 **PhotoHash** 属性值与客户端上的值对比。如果两个值不同，客户端就可以得知图像文件发生了更改。为获取更新的图像文件，客户端再次查询 ABWQ 服务，使用服务器上的图像文件更新客户端缓存中的图像文件，同时也会重置客户端缓存中文件的 **TimeStamp** 属性。

下面是 ABWQ 服务查询的示例响应：

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

## Lync 2013 中的用户照片

Lync 2013 为用户照片引入了高分辨率图像支持。Lync 2013 还支持在 Exchange 2013 用户邮箱中存储用户照片，这将消除 Lync 2010 中的图像分辨率和大小限制。Lync 2013 中的用户照片可以达到 648x648 像素，文件尺寸最大可为 20 MB。Lync 2013 中的高分辨率照片必须位于 Exchange 2013 用户邮箱中，并且仅受 Lync 2013 客户端支持。与 Exchange 的这种集成利用了 2013 版本的 Lync、Exchange 和 SharePoint 中称为 Oauth 的新授权框架。

如果您的部署中未使用 Exchange 2013，用户照片支持将与 Lync 2010 相同。但 Lync 2013 客户端中选择要使用的照片时的用户选项有所不同。在 Lync 2013 客户端中，用户可以选择“隐藏我的图片”或“显示我的图片”。“显示网站中的图片”选项默认不可用，但可以通过分配客户端策略启用。

## 隐藏我的图片

在 Lync 2013 中，用户照片的设置位于“选项”对话框中。选择“隐藏我的图片”时，Lync 客户端中不会显示您的任何用户照片，但联系人卡片和 Lync 以外的照片仍然会正常显示。

## 显示我的图片

选择“显示我的图片”选项时，您的用户照片将会显示在您的 Lync 客户端中，也会对 Lync 对话中的其他用户显示。所用图像为 AD DS 中存储的图像。

## 显示网站中的图片

通过客户端策略设置启用“显示网站中的图片”选项后，即可在 Lync 2013 中使用该选项。客户端版本必须高于 15.0.4535.1002，该版本安装有 [2013 年 11 月版 Lync 累积更新](http://go.microsoft.com/fwlink/p/?linkid=509908)。用户可能需要注销后再次登录才能在客户端中看到更改。

您可以在 Lync Server 命令行管理程序 中运行 [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) 策略，将客户端策略设置为启用“显示网站中的图片”设置。以下示例 cmdlet 展示了如何在您的部署中以全局方式为所有用户设置此策略：

    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True

   &nbsp;

    $po=Get-CsClientPolicy -Identity Global

   &nbsp;

    $po.PolicyEntry.Add($pe)

   &nbsp;

    Set-CsClientPolicy -Instance $po

图像上载到用户邮箱时，Exchange 会自动创建可在客户端应用程序中使用的较低分辨率图像版本。AD DS 中的用户照片也会更新。

> [!NOTE]  
> 在 AD DS 中更新图像文件时，将创建一个 48 x 48 像素的图像，供 AD DS 的 thumbnailPhoto 使用。任何现有图像都将被此图像所取代。如果您先前在 AD DS 中添加了一个 96 x 96 的图像，则会被这个新的 48 x 48 图像所取代。只有在您的环境中仍有用户使用 Lync 2010 客户端时，才应注意这一点，因为该版本的客户端将从 AD DS 获取用户照片。如果组织内确有 Lync 2010 客户端，您可以导入 96 x 96 像素的图像，取代 AD DS 创建的图像。



## Lync 2013 中的用户照片支持

Lync 2013 中的用户照片支持三种图像分辨率，如下表所述。所用图像由分配给 Lync 用户的客户端策略设置决定。如需了解更多信息，请参阅本主题中的“使用客户端策略 cmdlet 管理用户照片”。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>图像分辨率（像素）</th>
<th>应用程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>在未选择更高分辨率的图像时使用</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>用于 Outlook Web App 和 Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>用于 Lync 2013 桌面客户端和 Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


任何在 Exchange 2013 中启用了邮箱的用户都可以通过 Outlook Web Access 或 Lync 2013 客户端选项上载不同的图像，包括高分辨率照片在内。所用图像的推荐设置如下：

  - **图像分辨率**   648 x 648 像素

  - **颜色深度**   24 位

  - **图像文件大小**   不超过 20 MB

  - **文件格式**   JPEG

648 x 648 像素的典型 24 位 JPEG 图像的文件大小约为 240 KB，因此每 4 张用户照片需要占用 1 MB 存储空间。

