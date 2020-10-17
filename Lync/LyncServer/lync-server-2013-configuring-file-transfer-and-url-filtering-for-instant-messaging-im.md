---
title: 为即时消息 (IM) 配置文件传输和 URL 筛选
description: 为即时消息 (IM) 配置文件传输和 URL 筛选。
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
ms.openlocfilehash: 92f11c3f3bb924c1d92361c2635bfb37e1f03175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548348"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>在 Lync Server 2013 中配置即时消息 (IM) 的文件传输和 URL 筛选

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

智能 IM 筛选器工具可帮助保护您的 Lync Server 2013 部署不受最常见的病毒的传播，并降低用户体验的程度。 使用智能 IM 筛选器可以对筛选器进行配置，以阻止来自企业防火墙外部的未知终结点的未经请求或可能有害的即时消息。 通过指定用于确定要阻止的内容（例如，包含带有特定前缀的超链接的即时消息和具有特定扩展名的文件）的条件来配置筛选器。

智能 IM 筛选器提供下列功能：

  - 增强的 URL 筛选功能。

  - 增强的文件传输筛选功能。

配置智能 IM 筛选器包括以下内容：

  - 配置 URL 筛选功能。

  - 配置文件传输筛选功能。

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>如何将筛选选项应用于即时消息

在部署智能 IM 邮件筛选器工具之前，您需要了解在将邮件从一个 Lync Server 2013 服务器路由到另一个时如何应用筛选选项。 应用这些筛选选项的方式是一致的，不管服务器是位于单个组织中还是跨越多个组织。 在消息中插入自定义通知和警告文本以及在服务器之间发送这些消息的方式也是一致的。

<div>


> [!NOTE]
> 即时消息筛选器使得处理消息中的 URL 所需的 CPU 资源量增加。 这一增长的 CPU 需求也会影响 Lync Server 的性能。



</div>

通过使用 "Lync Server 控制面板" 中的 " **IM 和状态**" 组中的 " **URL 筛选器**" 页，可以阻止部分或全部超链接或配置警告。 选择“超链接前缀”**** 选项“发送警告消息”**** 后，警告将插入到包含超链接的即时消息的开头。

当即时消息从一台服务器传输到另一台服务器时，将适用下面的一般准则：

  - 如果服务器阻止即时消息（因为选中了“URL 筛选器”**** 页面上的“阻止带文件扩展名的 URL”**** 复选框，或因为选择了“超链接前缀”**** 选项“阻止超链接”****），客户端将收到一条错误消息。后续服务器将不会接收此即时消息。

  - 如果服务器 (Server1) 将警告添加到包含活动超链接的即时消息，则接收此即时消息的后续服务器 (Server2) 仍然可以基于该即时消息中存在的这个活动超链接来采取不同的操作，并阻止该即时消息或添加警告。如果 Server2 配置为仅为此 URL 添加警告，则以前由 Server1 添加的警告将被删除，在 Server2 上配置的警告将添加到该即时消息的开头。

<div>


> [!NOTE]
> 如果在混合环境中运行 Lync Server 2013，则使用智能 IM 筛选器应用程序所需的 Live 通信服务器2005（SP1）是最低版本。 不带 SP1 的 Live Communications Server 2005 不支持智能 IM 筛选器。



</div>

<div>

## <a name="url-filtering"></a>URL 筛选

将根据超链接前缀来筛选 URL。下面是有效前缀示例：

  - www \* 。

  - ftp.

  - http.sys

如果您没有将即时消息筛选器配置为执行任何 URL 筛选，则包含在即时消息中的所有 URL 未经修改就可通过服务器。如果将即时消息筛选器配置为执行 URL 筛选，则将根据“编辑 URL 筛选器”**** 或“新建 URL 筛选器”**** 对话框中选择的选项来筛选即时消息中的 URL。

  - **启用 URL 筛选器**    此选项为全局部署或您选择的网站启用 URL 筛选。

  - **使用文件扩展名**     阻止 url即时消息筛选器阻止任何活动 intranet 或 Internet URL，其中包含在 "**编辑文件筛选器**" 对话框中的 "**要阻止的文件类型扩展**" 下列出的扩展名的文件。 当阻止某个 URL 时，会向发件人显示一条错误消息。 如果选择此选项，则对于在 " **文件类型扩展**" 下定义的任何文件扩展名，此选项优先于所有其他筛选选项。
    
    <div>
    

    > [!IMPORTANT]
    > 文件扩展名筛选仅限于标准文件名。筛选对于嵌入在其他名称中的文件扩展名不起作用。

    
    </div>

要配置即时消息对话中处理超链接的方式，请选择“超链接前缀”**** 下的以下选项之一：

  - 不**筛选**    邮件中的 Url 通过服务器发送。 选择此选项时，将显示 " **允许" 消息** 框。 在 " **允许消息** " 框中，指定要在包含超链接的每个即时消息的开头插入的通知。 此通知包含的字符数不超过65535。

  - **阻止超链接**    传递包含活动超链接的即时消息将被 Lync Server 阻止，并向发件人显示一条错误消息。

  - **发送警告消息**    Lync Server 允许在即时消息中使用活动超链接，但它包含警告。 选择此选项后，将显示“警告消息”**** 框。 在“警告消息”**** 框中，必须键入希望在包含有效超链接的即时消息中包含的警告。 例如，此警告可以声明单击未知链接的潜在危险，或者引用您所在组织的相关策略和要求。 此警告最多可包含 65535 个字符。

如果选择“阻止超链接”**** 或“发送警告消息”****，则下列选项可用：

  - **排除本地 intranet 超链接**    即时消息筛选器仅阻止 Internet Url。 Intranet 内的位置 Url 通过服务器未修改。 但是，运行 Lync Server 的各个服务器传递的 intranet Url 取决于将哪些类型的本地网站视为其 intranet 区域的一部分。 若要检查服务器的 intranet 区域设置，请参阅 [修改 Lync server 2013 中的默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)中的 "在 Internet Explorer 中配置 intranet 设置" 过程。

  - **筛选这些超链接前缀**    若要选择要阻止的前缀，请单击 "**选择**"，然后在 "**选择超链接前缀**" 中，将前缀添加到 "**超链接前缀**" 列表中。
    
    除了 **href** 之外，所有前缀都必须以句点或冒号结尾，或以星号后面跟一个句点结尾。 有效前缀可以包含一组有效 URL 字符（星号 () 除外）中的任何字符 \* 。 有效的 URL 字符集为： \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>文件传输筛选

文件传输筛选既影响即时消息，又影响会议。对于会议来说，这些设置影响 Office Live Meeting 2007 客户端中的讲义功能和多媒体播放功能。

<div>


> [!NOTE]
> Lync Server 还提供文件传输设置选项。 除了在 Lync Server 中提供的客户端控件之外，还提供了此服务器端选项。



</div>

可以在即时消息对话过程中、使用 Office Live Meeting 2007 客户端的讲义功能以及多媒体播放功能时，针对所有文件类型筛选文件传输。可以设置以下选项来控制文件传输：

  - **启用文件筛选器**    此选项为全局部署或您选择的网站启用文件筛选。
    
    启用文件筛选器后，可以在“文件传输”**** 中选择以下选项之一：
    
      - **阻止特定的文件类型**    通过指定要阻止的文件扩展名的列表，指定由服务器筛选的文件传输请求。 列表中的条目可包含所有标准字符，但不能包含通配符 (\*) 。 在 Office Live Meeting 2007 客户端中，讲义功能处于启用状态，但不能上载或下载任何具有此扩展名的文件。 如果在 " **Url 筛选器**" 选项卡上列出的 url 筛选器的设置中选中 "**阻止带文件扩展名的 url** " 复选框，则 url 筛选器将使用此相同列表来阻止包含这些文件扩展名的活动超链接。 若要选择要阻止的文件类型，请单击 " **选择**"，然后在 " **选择文件类型**" 中，将文件类型扩展名添加到 " **选定的文件类型扩展名** " 列表中。
    
      - **阻止所有**    服务器将丢弃包含文件传输请求的所有即时消息，并向请求的发件人返回一条错误消息。 Office Live Meeting 2007 客户端中的讲义功能被禁用。

<div>


> [!IMPORTANT]
> 文件扩展名筛选仅限于标准文件名。筛选对于嵌入在其他名称中的文件扩展名不起作用。



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中修改默认文件传输筛选器](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [在 Lync Server 2013 for a 特定网站中创建新的文件传输筛选器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [在 Lync Server 2013 中修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)

  - [在 Lync Server 2013 中创建一个新的 URL 筛选器，以处理 IM 对话中的超链接](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

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

