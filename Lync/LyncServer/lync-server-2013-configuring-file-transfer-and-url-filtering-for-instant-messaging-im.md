---
title: 为即时消息（IM）配置文件传输和 URL 筛选
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6c5a6053118b14b68c49a7fdaa6f444aca7ad23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>在 Lync Server 2013 中为即时消息（IM）配置文件传输和 URL 筛选

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

智能 IM 筛选器工具可帮助保护 Lync Server 2013 部署，使其不受最常见的病毒形式的传播，最大程度地降低用户体验。 使用智能 IM 筛选器配置筛选器，阻止来自公司防火墙外的未知终结点的未经请求或可能有害的即时消息。 通过指定用于确定应阻止的条件的条件来配置筛选器，例如包含带有特定前缀的超链接的即时消息和具有特定扩展名的文件。

智能 IM 筛选器提供以下内容：

  - 增强的 URL 筛选。

  - 增强的文件传输筛选。

配置智能 IM 筛选器包括以下内容：

  - 配置 URL 筛选。

  - 配置文件传输筛选。

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>如何对即时消息应用筛选选项

在部署智能 IM 邮件筛选器工具之前，需要了解如何应用筛选选项，因为邮件是从一个 Lync Server 2013 服务器路由到另一个。 应用这些筛选选项的方式是一致的，无论服务器位于单个组织还是跨组织边界。 此一致性适用于将自定义通知和警告文本插入到邮件并跨服务器发送的方式。

<div>


> [!NOTE]
> 即时消息筛选器增加了处理消息中的 Url 所需的 CPU 资源量。 这种 CPU 需求的增加也会影响 Lync Server 的性能。



</div>

通过使用 Lync Server 控制面板中 " **IM 和联机状态**" 组中的**URL 筛选器**页面，你可以阻止部分或所有超链接或配置警告。 当选择 "**超链接前缀**选项**发送警告消息**" 时，将在包含超链接的即时消息的开头插入警告。

当即时消息从一台服务器传播到另一台服务器时，请遵循以下一般指南：

  - 如果服务器阻止即时消息（因为已选中 " **URL 筛选器**" 页面上的 "**阻止带有文件扩展名的 url** " 复选框，或者选择了**超链接前缀**选项**块超链接**），则会向客户端返回一条错误消息。 后续服务器不会收到此即时消息。

  - 如果服务器（Server1）将警告添加到包含活动超链接的即时消息中，则接收此即时消息的后续服务器（Server2）仍可根据此即时消息中显示的此活动超链接采取不同的操作，并阻止即时消息或添加警告。 如果将 Server2 配置为仅为此 URL 添加警告，则将删除 Server1 添加的较早警告，并将在 Server2 上配置的警告添加到即时消息的开头。

<div>


> [!NOTE]
> 如果在混合环境中运行 Lync Server 2013，则使用该智能 IM 筛选器应用程序所需的最小版本是使用 SP1 的实时通信服务器2005。 没有 SP1 的实时通信服务器2005上不支持智能 IM 筛选器。



</div>

<div>

## <a name="url-filtering"></a>URL 筛选

根据 Url 的超链接前缀对其进行筛选。 以下示例是有效的前缀：

  - www\*。

  - ftp.

  - http

如果未将即时消息筛选器配置为执行任何 URL 筛选，则即时消息中包含的所有 Url 都将通过服务器未修改。 如果将即时消息筛选器配置为执行 URL 筛选，则会根据你在 "**编辑 URL 筛选**" 或 "**新建 url 筛选器**" 对话框中选择的选项筛选即时消息中的 url。

  - **启用 url 筛选器**   此选项为全局部署或你选择的网站启用 url 筛选。

  - **使用文件扩展名**   阻止 url 即时消息筛选器阻止所有活动 intranet 或 Internet URL，其中包含在 "**编辑文件筛选器**" 对话框中 "**要阻止的文件类型扩展**" 下列出的扩展名的文件。 当某个 URL 被阻止时，会向发件人显示一条错误消息。 选中此选项后，此选项将优先于 "**文件类型扩展**" 下定义的任何文件扩展名的所有其他筛选选项。
    
    <div>
    

    > [!IMPORTANT]
    > 对文件扩展名的筛选仅限于标准文件名称。 筛选可能无法处理嵌入在其他名称中的文件扩展名。

    
    </div>

若要配置在即时消息对话中如何处理超链接，请在 "**超链接前缀**" 下选择以下选项之一：

  - **不筛选**   邮件中的 url 通过服务器发送。 选择此选项时，将显示 "**允许" 消息**框。 在 "**允许消息**" 框中，指定要在包含超链接的每条即时消息的开头插入的通知。 此通知包含的字符数不超过65535。

  - **阻止超链接**   包含活动超链接的即时消息的传递被 Lync Server 阻止，并且向发件人显示一条错误消息。

  - **发送警告消息**   Lync Server 允许即时消息中的活动超链接，但包含警告。 选择此选项时，将显示 "**警告消息**" 框。 在 "**警告消息**" 框中，必须键入要包含在包含有效超链接的即时消息中的警告。 例如，此警告可能会声明单击未知链接的潜在危险，或者它可能会引用你组织的相关策略和要求。 警告不能超过65535个字符。

如果选择 "**阻止超链接**" 或 "**发送警告消息**"，则可以使用以下选项：

  - **排除本地 intranet 超链接**   即时消息筛选器仅阻止 Internet url。 Intranet 内的位置的 Url 通过服务器进行未修改的传递。 但是，运行 Lync Server 的单个服务器通过的 intranet Url 取决于本地网站的哪些类型被视为其 intranet 区域的一部分。 若要检查服务器的 intranet 区域设置，请参阅在[Lync server 2013 中修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)中的 "在 Internet Explorer 中配置 intranet 设置" 过程。

  - **筛选这些超链接前缀**   若要选择要阻止的前缀，请单击 "**选择**"，然后在 "**选择超链接前缀**" 中，将前缀添加到 "**超链接前缀**" 列表。
    
    除**href**之外的所有前缀必须以句点或冒号结尾，或星号后跟句点。 有效的前缀可以包含有效 URL 字符组中除星号（\*）之外的任何字符。 有效的 URL 字符集\# \*为： +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>文件传输筛选

筛选器传输筛选会影响即时消息和会议。 对于会议，这些设置影响 Office Live Meeting 2007 客户端和多媒体播放功能中的讲义功能。

<div>


> [!NOTE]
> Lync 服务器还提供文件传输设置选项。 除了 Lync Server 中提供的客户端控件之外，还提供此服务器端选项。



</div>

当你使用 Office Live Meeting 2007 客户端中的讲义功能时，你可以在即时消息对话中筛选文件传输，以及针对所有文件类型使用多媒体播放功能。 你可以设置以下选项来控制文件传输：

  - **启用文件筛选器**   此选项为全局部署或你选择的网站启用文件筛选。
    
    启用文件筛选器时，可以在 "**文件传输**" 中选择以下选项之一：
    
      - **阻止特定文件类型**   通过指定要阻止的文件扩展名的列表，指定由服务器筛选的文件传输请求。 列表中的条目可以包含所有标准字符，但不能包含通配符（\*）。 在 Office Live Meeting 2007 客户端中启用讲义功能，但不能上载或下载具有此扩展名的任何文件。 如果在 " **Url 筛选器**" 选项卡上列出的 url 筛选器的设置中选中 "**阻止文件扩展名的 url** " 复选框，则 url 筛选器将使用此相同列表来阻止包含这些文件扩展名的活动超链接。 若要选择要阻止的文件类型，请单击 "**选择**"，然后在 "**选择文件类型**" 中，将文件类型扩展名添加到**所选文件类型扩展名**列表。
    
      - **"阻止所有**   服务器" 将丢弃所有包含文件传输请求的即时消息，并向请求的发件人返回一条错误消息。 Office Live Meeting 2007 客户端中的讲义功能被禁用。

<div>


> [!IMPORTANT]
> 对文件扩展名的筛选仅限于标准文件名称。 筛选可能无法处理嵌入在其他名称中的文件扩展名。



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中修改默认文件传输筛选器](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [在 Lync Server 2013 中为特定网站创建新的文件传输筛选器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [在 Lync Server 2013 中修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)

  - [在 Lync Server 2013 中创建新的 URL 筛选器以处理即时消息对话中的超链接](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理 IM 和状态设置](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

