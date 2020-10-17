---
title: Lync Server 2013：配置会议邀请
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bc948f81ddbc9bf4881b2188fc378315b3824ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532329"
---
# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>在 Lync Server 2013 中配置会议邀请

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-16_

您可以通过在会议邀请正文中添加以下可选项目，从而自定义由 Lync 2013 的联机会议外接程序发送的会议邀请：

  - **你组织的徽标** 使用 "徽标 URL" 选项将组织的徽标添加到会议邀请中。 如果将会议邀请发送给组织外部的人员，则该图像应位于公开发布的 URL 中。 支持的图像格式为 GIF 和 JPG。 尽管 Lync Server 2013 将无大小限制的 URL 存储在图像上，但为了获得最佳效果，图像的最大大小应为30像素（高为188像素宽）。

  - **自定义帮助或支持链接** 为您的组织的帮助或支持团队网站添加 URL。 如果将会议邀请发送给组织外部的人员，则 URL 应公开可用。 最大 URL 长度为 1 KB。

  - **法律免责声明文本** 添加将在所有会议邀请中显示的法律文本或免责声明的 URL。 如果将会议邀请发送给组织外部的人员，则 URL 应公开可用。 最大 URL 长度为 1 KB。

  - **自定义页脚文本** 添加将在邀请中呈现为自定义页脚的文本。 可添加的文本的最大长度为 2 KB。

您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序配置这些选项。

<div>


**使用 Lync Server 控制面板自定义会议邀请的具体方法**

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“会议”**，然后单击 **“会议配置”**。

4.  在 **“会议配置”** 页上，单击 **“新建”**，然后执行下列操作之一：
    
      - 要创建站点级别的策略，请单击 **“站点配置”**。在 **“选择站点”** 搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击 **“确定”**。
    
      - 要创建池级别的策略，请单击 **“池配置”**。在 **“选择服务”** 搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击 **“确定”**。

5.  执行下列任意操作：
    
      - 在 " **徽标 URL** " 字段中，键入您组织的徽标图像的 URL。
    
      - 在 " **帮助 URL** " 字段中，键入您的组织的帮助或支持网站的 URL。
    
      - 在 " **法律文本** " 字段中，键入要包含在会议邀请中的法律文本或免责声明的 URL。
    
      - 在 " **自定义页脚" 文本** 字段中，键入页脚文本，最高为 2 KB。

**使用 Lync Server 命令行管理程序自定义会议邀请**

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 **get-csmeetingconfiguration** 或 **get-csmeetingconfiguration** cmdlet 以创建或配置会议邀请选项。 例如，运行：
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

