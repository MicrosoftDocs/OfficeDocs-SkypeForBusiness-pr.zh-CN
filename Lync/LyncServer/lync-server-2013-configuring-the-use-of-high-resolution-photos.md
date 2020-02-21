---
title: Lync Server 2013：配置高分辨率照片的使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a49618cd4039163f22d44f358c29a802037b8b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>在 Microsoft Lync Server 2013 中配置高分辨率照片的使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

Microsoft Lync Server 2010 提供了用户查看其联系人照片的能力（并使自己的照片可供其他人使用）。 通常，这些照片已作为用户的 thumbnailPhoto 属性的一部分存储在 Active Directory 中。 这对照片的大小和分辨率施加了一个重大限制：thumbnailPhoto 属性只能保存最大大小为 48 像素 x 48 像素的照片。

但在 Microsoft Lync Server 2013 中，可以将照片存储在用户的 Microsoft Exchange Server 2013 邮箱中。，允许最大为648像素的照片尺寸乘以648像素。 此外，Exchange 2013 可以根据需要自动调整这些照片的大小，以便在不同的产品中使用。 通常，这意味着有三种不同的照片大小和分辨率：

  - 48 像素 x 48 像素，用于 Active Directory thumbnailPhoto 属性的大小。 如果将照片上传到 Exchange 2013 Exchange 将自动创建48像素的48像素版本的照片，并更新用户的 thumbnailPhoto 属性。 但请注意，反之不成立：如果手动更新 Active Directory 中的 thumbnailPhoto 属性，用户的 Exchange 2013 邮箱中的照片将不会自动更新。

  - 96像素 x 96 像素，用于 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App 和 Lync 2013。

  - 在 Lync 2013 和 Microsoft Lync Web App 中使用的648像素 x 648 像素。

<div>


> [!NOTE]  
> 如果您具有资源，建议您上载 648x648 照片；这将在任何 Office 2013 应用程序中提供最高分辨率和最佳图片质量。每张大小为 648x648、深度为 24 位的 JPEG 照片均会生成一个约为 240 KB 的文件大小。这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。



</div>

使用 Exchange Web 服务访问的高分辨率照片可由运行 Outlook 2013 Web App 的用户上载;仅允许用户更新其自己的照片。 但是，管理员可以使用 Exchange 命令行管理程序和一系列类似于以下的 Windows PowerShell 命令来更新任何用户的照片：

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

上面的示例中的第一个命令使用 Get Content cmdlet 读取 file C：\\相片\\Kenmyer 的内容，并将该数据存储在名为 $photo 的变量中。 在第二个命令中，Exchange cmdlet Set-userphoto 用于上传照片，并将该照片附加到 Ken Myer 的用户帐户。

<div>


> [!NOTE]  
> 在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。 也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。 <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A>有关详细信息，请参阅 set-userphoto cmdlet 的文档。



</div>

上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“保存”**** 或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

若要验证是否已将新照片分配给用户帐户，Ken Myer 可以登录到 Lync 2013，选择 "**选项**"，然后选择 **"我的图片**"。 新上载的照片应显示为 Ken 的个人照片。 此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

如果管理员可以使用 Internet Explorer 查看照片，但用户无法在 Lync 2013 中查看他或她的照片，这通常表明 Exchange Web 服务或 Exchange 自动发现服务存在连接问题。

请注意，在 Lync 2013 中，不需要进行其他配置即可使用此照片。 相反，照片将在上传后立即可用，并且已运行 Set-userphoto cmdlet。

</div>

<span> </span>

</div>

</div>

</div>

