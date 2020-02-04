---
title: Lync Server 2013：使用 Lync Room System 管理 Web 门户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c891309d76dda20f875592841925c852fe2e3351
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Lync Room System 管理 Web 门户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-11-10_

在服务器上部署 LRS 后，你可以通过从浏览器登录到 LRS 管理 Web 门户来检查所有 LRS 聊天室的状态。

<div>

## <a name="sign-in"></a>登录

1.  浏览到以下 URL：
    
    https://\<fe-服务器\>/lrs

2.  输入 LRSSupport 帐户或已添加到 LRSSupportAdminGroup 安全组的帐户的凭据。

![Lync 聊天室系统管理门户登录屏幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 聊天室系统管理门户登录屏幕")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>LRS 管理 Web 门户摘要页面

"摘要" 页面为服务器上部署的所有 LRS 聊天室提供以下信息：

  - **标记**   管理员提供给聊天室的自定义名称。 可以通过在门户中单击会议室名称来设置标记。

  - **运行状况**   运行空间的运行状况，该状态派生自会议室的聚合运行状况，它显示在 "房间设置" 页面的 "运行状况" 部分下方。

  - **下一个会议**   安排下一个会议的日期和时间。

  - **LRS 版本、制造商、型号**   在 LRS 中预设这些值。 根据制造商，这些字段可能留空。

  - **上次刷新**   显示上次刷新网页的时间。

![Lync 聊天室系统管理门户摘要视图](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 聊天室系统管理门户摘要视图")

</div>

<div>

## <a name="lrs-room-information"></a>LRS 会议室信息

门户的 "房间信息" 部分允许你查看和配置单个 LRS 会议室。 其中包含四个部分：设置、详细信息、疑难解答和运行状况。

<div>

## <a name="settings"></a>设置

在“设置”部分中，你可以设置会议室的密码、会议室标记和默认音量大小。 如果配置这些设置，则仅在重新启动 LRS 控制台后才会复制更改。 你将仅看到版本15.12 和更高版本的 Lync 会议室系统的系统更新设置。

![Lync 聊天室系统管理门户聊天室设置](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 聊天室系统管理门户聊天室设置")

</div>

<div>

## <a name="details"></a>详细信息

详细信息部分提供 LRS 聊天室设置的只读摘要，包括：上次刷新的时间;下一次会议;上次更新、维护和校准;默认扬声器、麦克风和铃声设置;版本SIP URI;屏幕数和每个屏幕的详细信息;状态和活动。

![Lync 聊天室系统管理门户详细信息视图](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 聊天室系统管理门户详细信息视图")

</div>

<div>

## <a name="troubleshooting"></a>疑难解答

“疑难解答”部分可用于远程收集日志并将它们保存到指定位置。 您也可以重新启动 LRS 控制台（LRS 用户界面）或重启整个系统。 若要收集日志，请以指定格式提供文件夹路径，并确保文件夹具有授予 LRS 计算机帐户的写入权限。 如果日志太大，可能需要长达 5 分钟才能完成日志的收集。 刷新页面将显示最新状态。

![Lync 聊天室系统管理门户聊天室日志记录](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 聊天室系统管理门户聊天室日志记录")

</div>

<div>

## <a name="health"></a>运行状况

"运行状况" 部分提供了 Lync 服务器连接、音频设备、视频设备、复原状态和屏幕设备的运行状况的可视指示。

![Lync 聊天室系统管理门户聊天室运行状况](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 聊天室系统管理门户聊天室运行状况")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>有关管理 Web 门户的其他说明

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>仅在重新启动 LRS 系统后应用设置更改。</P>
> <LI>
> <P>如果 LRSApp 帐户密码过期，你不能查看会议室的状态。 配置 LRSAppuser 帐户密码，使其永不过期，或者确保在密码即将过期时更新密码。</P>
> <LI>
> <P>只有本地部署才支持 LRS 管理 web 门户。</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>常见问题

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>为什么我无法登录管理 Web 门户？

  - 打开https://localhost/lrs时，你将能够看到 "登录" 页面，但当你键入凭据时，无法登录。 在这种情况下，必须https://FQDNofFEserver/lrs打开才能登录到管理 web 门户。

  - 如果您要从中访问管理 web 门户的计算机在工作组中，"http://" 将不起作用。 请改用 "https"。

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>为什么我在管理 web 门户中看不到 LRS？

  - 请确保你在部署中拥有 LRS 帐户，并且根据 LRS 管理 Web 门户部署建议创建这些帐户。 请确保在 Lync server 上使用 Enable-CsMeetingRoom，而不是 Enable-Move-csuser 来设置 LRS 帐户。

  - 如果已创建 LRS 帐户，并且在管理 web 门户中看不到帐户，请使用选定**MeetingPortal**组件的 Lync Server 日志记录工具收集服务器日志，然后将其发送到 LRS 支持联系人。

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>为什么我在管理 web 门户中看不到 LRS 的状态？

  - 请确保 LRSApp 用户帐户已启用 SIP。

  - 如果仍有问题，请从 D： **** \\LRS 系统中收集跟踪\\LRSAdminLogs\\的日志文件，然后将其发送到 LRS 支持联系人。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

