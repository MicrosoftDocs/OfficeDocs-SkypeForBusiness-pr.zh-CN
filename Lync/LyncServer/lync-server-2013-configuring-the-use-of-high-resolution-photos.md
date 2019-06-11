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

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>在 Microsoft Lync Server 2013 中配置高分辨率照片的使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-02-05_

Microsoft Lync Server 2010 提供了用户查看其联系人照片的能力 (以及让其他人可以使用自己的照片)。 通常, 这些照片作为用户的 thumbnailPhoto 属性的一部分存储在 Active Directory 中。 这对照片的大小和分辨率施加了严重限制: thumbnailPhoto 属性只能容纳最大大小为48像素的照片48像素。

但是, 在 Microsoft Lync Server 2013 中, 照片可以存储在用户的 Microsoft Exchange Server 2013 邮箱中;这允许最大为648像素的照片大小乘以648像素。 除此之外, Exchange 2013 可根据需要自动调整这些照片的大小, 以便在不同的产品中使用。 通常，这意味着有三种不同的照片大小和分辨率：

  - 48像素 x 48 像素, 用于 Active Directory thumbnailPhoto 属性的大小。 如果将照片上传到 Exchange 2013 Exchange 将自动通过48像素版本的照片创建48像素, 并更新用户的 thumbnailPhoto 属性。 但请注意, 反之不成立: 如果手动更新 Active Directory 中的 thumbnailPhoto 属性, 用户的 Exchange 2013 邮箱中的照片将不会自动更新。

  - 96像素 x 96 像素, 用于 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App 和 Lync 2013。

  - 在 Lync 2013 和 Microsoft Lync Web App 中使用648像素 x 648 像素。

<div>


> [!NOTE]  
> 如果您具有资源，建议您上载 648x648 照片；这将在任何 Office 2013 应用程序中提供最高分辨率和最佳图片质量。每张大小为 648x648、深度为 24 位的 JPEG 照片均会生成一个约为 240 KB 的文件大小。这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。



</div>

高分辨率照片 (使用 Exchange Web 服务访问) 可由运行 Outlook 2013 Web App 的用户上传;仅允许用户更新其自己的照片。 但是, 管理员可以使用 Exchange 命令行管理器和一系列类似于以下内容的 Windows PowerShell 命令更新任何用户的照片:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

前面示例中的第一个命令使用 Get 内容 cmdlet 读取文件 C:\\\\Kenmyer 的内容, 并将该数据存储在名为 $photo 的变量中。 在第二个命令中, 将使用 Exchange cmdlet UserPhoto 上载照片, 并将该照片附加到 Ken Myer 的用户帐户。

<div>


> [!NOTE]  
> 在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。 也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。 <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A>有关详细信息, 请参阅 UserPhoto cmdlet 的文档



</div>

上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“**保存**”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

若要验证是否已将新照片分配给用户帐户, Ken Myer 可以登录到 Lync 2013, 选择 "**选项**", 然后选择 **"我的图片**"。 新上载的照片应显示为 Ken 的个人照片。 此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

如果管理员可以使用 Internet Explorer 查看照片, 但用户无法在 Lync 2013 中查看他或她的照片, 这通常表示 Exchange Web 服务的连接问题或 Exchange 自动发现服务的连接问题。

请注意, 您也不需要额外的配置即可使此照片在 Lync 2013 中可用。 上载照片并运行 Set-UserPhoto cmdlet 后，照片将立即可供使用。

</div>

<span> </span>

</div>

</div>

</div>

