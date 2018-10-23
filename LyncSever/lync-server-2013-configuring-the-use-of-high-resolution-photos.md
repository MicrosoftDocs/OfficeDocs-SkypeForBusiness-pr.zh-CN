---
title: 在 Microsoft Lync Server 2013 中配置使用高分辨率照片
TOCTitle: 在 Microsoft Lync Server 2013 中配置使用高分辨率照片
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49888526
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Microsoft Lync Server 2013 中配置使用高分辨率照片

 

_**上一次修改主题：** 2016-12-08_

利用 Microsoft Lync Server 2010，用户可以查看其联系人的照片（并使其自己的照片对其他人可见）。通常，这些照片已作为用户的 thumbnailPhoto 属性的一部分存储在 Active Directory 中。这对照片的大小和分辨率施加了一个重大限制：thumbnailPhoto 属性只能保存最大大小为 48 像素 x 48 像素的照片。

但在 Microsoft Lync Server 2013 中，照片可存储在用户的 Microsoft Exchange Server 2013 邮箱中；这将允许照片的大小最大为 648 像素 x 648 像素。除此之外，Exchange 2013 可以根据需要自动调整这些照片的大小以便用于不同的产品。通常，这意味着有三种不同的照片大小和分辨率：

  - 48 像素 x 48 像素，用于 Active Directory thumbnailPhoto 属性的大小。如果您将一张照片上载到 Exchange 2013 中，Exchange 将自动创建该照片的 48 像素 x 48 像素版本，并更新用户的 thumbnailPhoto 属性。但请注意，反过来并不成立：如果手动更新 Active Directory 中的 thumbnailPhoto 属性，则用户的 Exchange 2013 邮箱中的照片将不会自动更新。

  - 96 像素 x 96 像素，适用于 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App 和 Lync 2013。

  - 648 像素 x 648 像素，适用于 Lync 2013 和 Microsoft Lync Web App。

> [!NOTE]  
> 如果您具有资源，建议您上载 648x648 照片；这将在任何 Office 2013 应用程序中提供最高分辨率和最佳图片质量。每张大小为 648x648、深度为 24 位的 JPEG 照片均会生成一个约为 240 KB 的文件大小。这意味着，每四张用户照片将占用约 1 MB 的磁盘空间。



高分辨率照片是使用 Exchange Web Services 访问的，此类照片可由运行 Outlook 2013 Web App 的用户上载；只允许用户更新其自己的照片。但是，管理员可使用 Exchange 命令行管理程序和与以下命令类似的一系列 Windows PowerShell 命令来更新任何用户的照片：

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

在上面的示例中，第一个命令使用 Get-Content cmdlet 读取文件 C:\\Photos\\Kenmyer.jpg 的内容，并将数据存储在名为 $photo 的变量中。在第二个命令中，Exchange cmdlet Set-UserPhoto 用于上载照片并将该照片附加到 Ken Myer 的用户帐户。

> [!NOTE]  
> 在此示例中，Ken Myer 的 Active Directory 显示名称将用作用户帐户标识。也可以通过使用其他标识符（例如，用户的 SMTP 地址或其用户主体名称）来引用用户帐户。有关详细信息，请参阅 Set-UserPhoto cmdlet 的文档，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=268536%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=268536&amp;clcid=0x804</a>



上载照片并不等同于将照片分配给 Ken Myer 的用户帐户。相反，上载照片只是会生成将显示在“Outlook Web App 选项”页上的照片预览。若要将照片实际分配给用户帐户，用户必须在“选项”页上单击“保存”或管理员必须执行本示例中的第三个命令。此第三个命令使用 Save 参数将照片分配给 Ken Myer 的用户帐户：

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

若要验证是否已将新照片分配给用户帐户，Ken Myer 可以登录到 Lync 2013，选择“选项”，然后选择“我的图片”。新上载的照片应显示为 Ken 的个人照片。此外，管理员可通过启动 Internet Explorer 并导航到与以下 URL 类似的 URL 来验证任何用户的照片：

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

如果管理员可使用 Internet Explorer 查看照片但用户无法在 Lync 2013 中查看其照片，这通常表明与 Exchange Web Services 或 Exchange 自动发现服务的连接出现问题。

注意，不需要进行其他配置以使此照片在 Lync 2013 中可以显示。上载照片并运行 Set-UserPhoto cmdlet 后，照片将立即可供使用。

