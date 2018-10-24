---
title: Lync Server 2013：向 Lync 错误消息添加自定义链接
TOCTitle: 向 Lync 错误消息添加自定义链接
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398979(v=OCS.15)
ms:contentKeyID: 52061159
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中向 Lync 错误消息添加自定义链接

 

_**上一次修改主题：** 2013-02-20_

通过添加指向自己的疑难问题解答或技术支持信息的链接来自定义 Lync 2013 错误消息。为执行此操作，请使用带有 CustomLinkInErrorMessages 参数的 **New-CSClientPolicy** 或 **Set-CSClientPolicy** Lync Server 命令行管理程序 cmdlet。自定义链接的文本是“单击此处以获取来自管理员的支持主题” ，且无法自定义。

例如，以下命令会使自定义链接显示在每个 Lync 2013 错误消息的脚注区域，并且会将链接目标设置为 http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

使用 **Grant-CSClientPolicy** 将此新策略分配给用户。有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 **New-CSClientPolicy** 和 **Grant-CSClientPolicy**。

