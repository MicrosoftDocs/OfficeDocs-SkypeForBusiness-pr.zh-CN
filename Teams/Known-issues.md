---
title: "Microsoft Teams 的已知问题"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 12/20/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams 客户端应用和管理体验的已知问题当前列表"
ms.openlocfilehash: a9642d43f26d06c759f606d360520c92d053ac77
ms.sourcegitcommit: 5ab90d4bd39bf45198ef73d0fd45dd3d8baa6acb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="known-issues-for-microsoft-teams"></a>Microsoft Teams 的已知问题
  
下表列出了 Microsoft Teams 的已知问题。
## 

|**问题标题**|**行为/症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|欧盟地区和亚太地区的客户在从其他租户添加来宾用户时收到错误    <br/> | 欧盟地区和亚太地区的客户遇到 Microsoft Teams 与 Azure Active Directory 之间出现复制延迟的问题。 当来自欧盟地区或亚太地区某个租户的用户尝试从任何其他租户添加来宾用户时，收到要求他们重试的错误消息。   <br/> |再次单击重试按钮以执行来宾用户添加操作。  <br/> |11/8/17  <br/> |
|当你尝试从 Internet Explorer 或 Edge 加入 Teams 时，程序持续循环或崩溃并且无法登录。   <br/> | 贵组织使用 Internet Explorer 中的受信任站点，基于 Web 的 Teams 应用程序无法正常登录，因为 Teams 的受信任站点不被允许。 <br/>|使用管理员权限或群组策略对象，对 IE 设置进行下列更改：<br/><ol><li>在“Internet 选项”&gt;“隐私”&gt;“高级”下，接受第一方和第三方 Cookie，并选中“总是允许会话 Cookie”复选框。</li><li>单击“Internet 选项”&gt;“受信任站点”&gt;“站点”，然后添加下列所有站点：<ul><li>https://\*.microsoft.com</li><li>https://\*.microsoftonline.com</li><li>https://\*.teams.skype.com</li><li>https://\*.teams.microsoft.com</li><li>https://\*.sfbassets.com</li><li>https://\*.skypeforbusiness.com</li></ul></li></ol><br/><b>注意</b>：始终验证并允许 Teams 的所有受信任 URL 以及以下文档中的要求：[Office 365 URL 和 IP 地址范围](httpds://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)   <br/> <br/>|11/1/17  <br/> |
|按照策略要求，在 OWA/Outlook 上未阻止向 Teams 上载照片   <br/> | Teams 允许用户直接将照片上载到 Office 365，不论策略设置如何，而不是对 OWA 阻止照片上载。   <br/> <br/> |10/16/17  <br/> |
|带参数的 Teams URL 在登录重定向后被截断  <br/> | 在 Internet Explorer 和 Edge 中，登录后第一次在 Teams Web 应用上打开共享 Teams 文件链接时，你将被重定向到错误的文档。 如果你已登录 Teams Web 应用并单击共享文件链接，链接将按预期正常工作。   <br/> <br/> |10/11/17  <br/> |
|在 Intune 管理的移动设备上，用户可能无法切换帐户  <br/> |在 Intune 管理的移动设备上，用户可能无法切换帐户。  <br/> |无解决方法。  <br/> |9/20/17  <br/>|
|对于来宾创建的频道未创建 Wiki  <br/> |来宾创建新频道时，未创建“**Wiki**”选项卡。 无法手动将“**Wiki**”选项卡附加到频道。 <br/> |无解决方法。  <br/> |9/20/17  <br/>|
|在 Chrome 中呈现视频时，出现绿色非自然信号  <br/> |使用 Chrome 在通话或聚会中查看视频或共享屏幕时，出现绿色非自然信号。  <br/> |在 Chrome 中禁用硬件加速设置。  <br/> |2017 年 8 月 3 日  <br/> |
|Outlook 外接程序限制  <br/> |要使用 Outlook 外接程序，必须使用多重身份验证 (MFA) 登录 Teams。 如果在登录过程中 MFA 中途失败，你仍能够登录 Teams，但当你尝试使用外接程序时，会显示错误消息。  <br/> 目前，外接程序仅供 Windows 用户使用。  <br/> 如果你使用身份验证代理，将无法使用外接程序。  <br/> | 无解决方法。 <br/> |2017 年 8 月 2 日  <br/> |
|为 Microsoft Teams SharePoint 网站创建的 SharePoint 用户不正确  <br/> |Microsoft Teams 组的 SharePoint 创建者显示为 SharePoint 管理员，而不是正确的用户。  <br/> 从 SharePoint 管理控制台审核时，与根据 Microsoft Teams 中的团队创建的 Office 365 组关联的网站集合页面的创建者是 SharePoint 管理员。  <br/> |无解决方法。  <br/> |2017 年 7 月 21 日  <br/> |
|公用团队列表未显示所有团队  <br/> |公用团队列表是基于 Microsoft Graph 的。  <br/> |如果你未看到某个团队，请尝试在右上方的搜索框中搜索该团队。  <br/> | 2017 年 7 月 21 日  <br/>|
|在一对一聊天中无法访问 OneNote  <br/> |在进行一对一聊天时单击“笔记”，设置可能无法打开 OneNote。   <br/> |首先，在一对一聊天中，从“文件”打开 OneDrive，然后单击“笔记”，将打开 OneNote。 如果聊天中的其他用户收到权限被拒错误，他们必须先在 Teams 中打开 OneDrive，这将设置个人网站 URL。    <br/> | 2017 年 7 月 21 日  <br/>|
|日期格式和数字分隔符使用美国格式，而不是欧盟格式。  <br/> |在 Microsoft Teams 中更改语言设置时，日期格式和数字分隔符未更改为国家/地区特定的设置。  <br/> |无解决方法。  <br/> |2017 年 7 月 13 日  <br/> |
|“**最小化**”和“**关闭**”工具提示留在主显示器上。 <br/> |在 Windows 客户端中，最小化或关闭窗口后，“**最小化**”和“**关闭**”可能会留在主显示器上。 <br/> |悬停在“**最小化**”按钮上并等待工具提示显示，然后再单击，可以避免此问题。 <br/> |2017 年 7 月 3 日  <br/>|
|有些团队缺少连接器选项  <br/> |右键单击频道时，团队的任何成员都不显示连接器选项。  <br/> |团队的创建者必须有联机邮箱；否则，将不提供连接器选项。 这是预期行为。  <br/> |2017 年 6 月 26 日  <br/> |
|包含 &amp; 符号的团队名称中断连接器功能  <br/> |创建的团队名称中包含 &amp; 符号时，无法在团队/组中建立连接器。  <br/> |请勿在团队名称中使用特殊字符。  <br/> |2017 年 6 月 21 日  <br/> |
|新式身份验证失败  <br/> |多重身份验证首次失败后，使用 Web 应用进行身份验证。  <br/> 有关详细信息，请参阅 [https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/ad-fs-prompt-login](http://technet.microsoft.com/library/https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/ad-fs-prompt-login.aspx)。  <br/> |检查此设置：Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled。  <br/> |2017 年 6 月 19 日  <br/> |
|用户无法重新预先存在的频道名称  <br/> |一旦创建了某个频道名称，即使已将其删除，仍无法重新创建该名称。 我们的系统按信息保护方案维护此数据。  <br/> |无解决方法。  <br/> |2017 年 3 月 13 日  <br/> |
|使用移动应用时无法插入表情图片  <br/> |无法在移动应用上使用表情图片。  <br/> |无解决方法。  <br/> |2017 年 3 月 13 日  <br/> |
|某些会议需要 Skype for Business  <br/> |你的约会日历方便地显示在 Microsoft Teams 中。 为了进入会议，单击“**加入**”按钮。 <br/> 目前我们仍在此方面一直进行开发，如果此会议是使用 Skype for Business 安排的，则你单击“**加入**”后，Microsoft Teams 将启动你的 Skype for Business 客户端以便你进入会议。 在 Microsoft Teams 中安排的会议将在该产品中直接启动。  <br/> 将来，我们将改进此体验。  <br/> |单击“**加入**”。 Microsoft Teams 将智能地根据会议说明中包含的 URL 确定用户是否需要 Skype for Business 才能加入会议。  <br/> |2017 年 3 月 13 日  <br/> |
|左侧导航栏中缺少**会议**图标。 <br/> |目前仅对其邮箱在 Office 365 多租户上的用户和可以使用 Exchange 自动发现功能发现其邮箱位置的一些挑选的专用用户启用应用栏中的**会议**图标。 <br/> Microsoft Teams 还不支持位于本地 Exchange 和 Exchange Dedicated 的邮箱。 正在调查此情况；但没有提供此功能的时间安排。  <br/> |无解决方法。  <br/> |2017 年 3 月 13 日  <br/>|
|会议的与会者上限  <br/> |每个 Microsoft Teams 会议最多可以有 80 个与会者。  <br/> |无解决方法。  <br/> |2017 年 3 月 13 日  <br/> |
|无法从 Windows 移动客户端加入会议  <br/> |无法从 Windows Phone 应用加入团队会议。  <br/> |不久以后将支持从 Windows Phone 加入会议。  <br/> |2017 年 3 月 13 日  <br/>|
|移动 Teams 客户端布局差异  <br/> |在移动客户端上，团队按字母顺序列出，频道无法折叠。  <br/> |无解决方法。  <br/> |2017 年 3 月 13 日  <br/> |
|工作区列表未按字母顺序排序  <br/> |在添加 PowerBI 选项卡时切换工作区的用户将遇到要在之间切换的工作区列表未按字母顺序排序。  <br/> |无解决方法。  <br/> |2017 年 3 月 13 日  <br/>|
|选择报告时滚动栏消失  <br/> |添加 PowerBI 报告的用户滚动浏览的列表长于一屏报告时，滚动栏就会消失。  <br/> |使用向上和向下箭头滚动浏览列表。  <br/> |2017 年 3 月 13 日  <br/>|
|用户无法创建团队  <br/> |贵公司可以设置策略用于限制可以创建 Office 365 组或团队的人员。  <br/> |与 IT 管理员联系以了解贵公司的组和团队创建策略。  <br/> |2017 年 3 月 13 日  <br/> |
|团队成员上限为 2500  <br/> |Microsoft Team 中每个团队最多可以有 2500 个成员。  <br/> |无解决方法。  <br/> |2017 年 3 月 13 日  <br/> |
|删除团队还将删除与之关联的组。  <br/> |用户可能不了解删除团队时会删除基础 Office 365 组。 此外，如果删除基础 Office 365 组，也会删除团队。  <br/> |Microsoft Teams 其他语言版本向用户提供此信息。 Office 365 组界面上未提供此信息。  <br/> |2017 年 3 月 13 日  <br/> |
|Planner 单一登录 (SSO)  <br/> |SSO 不适用于 Planner。 在每个客户端上首次使用 Planner 时，必须重新登录。  <br/> |无解决方法。 正在准备进一步的身份验证增强功能。  <br/> |2017 年 2 月 28 日  <br/> |
|无法保存个人资料图片  <br/> |Exchange 邮箱在本地托管时，用户无法保存其个人资料图片。  <br/> |无解决方法。  <br/> |2017 年 2 月 28 日  <br/> |
|会议不可用  <br/> |Exchange 邮箱在本地托管时，不提供会议功能和图标。  <br/> |将本地部署升级到 Exchange 2016 CU3 或更高版本  <br/> |2017 年 2 月 28 日  <br/> |
|没有为组邮箱启用存档（额外存储）功能  <br/> |在 Office 365 安全性和合规性中心中，全局管理员无法对组邮箱启用存档。 他们只能对用户邮箱执行此操作。  <br/> |如果组邮箱容量几乎已满，请联系 Microsoft Office 支持以扩展邮箱大小。  <br/> |2017 年 2 月 1 日  <br/> |
|Safari Web 客户端支持  <br/> |尝试在 Safari 上打开 Microsoft Teams Web 客户端的用户被导向到下载桌面客户端。 Microsoft 正在着手准备 Safari 支持，并将通过公开 Office 365 路线图共享更新。  <br/> |使用支持的浏览器，包括：Microsoft Edge 12+、Internet Explorer 11+、Firefox 47.0+ 和 Chrome 51.0+。  <br/> |2016 年 11 月 2 日  <br/> |  
|团队成员无法加入临时会议。  <br/> |如果双方都使用最新的应用，则支持临时会议。 Windows Phone 应用尚不支持会议。  <br/> |下载并安装最新的桌面、iOS 或 Android 应用以加入会议。  <br/> |2016 年 11 月 2 日  <br/> |
|本地 Skype for Business 用户无法收到我的消息  <br/> |Microsoft Teams 用户尝试向使用本地 Skype for Business 的其他人发送消息，无法完成消息传递。  <br/> | 支持 Teams 与 Skype for Business Online 上托管的用户之间的互操作性。 Teams 用户可以向使用 Skype for Business Online 的非 Teams 用户发送一对一聊天。 <br/> 不支持 Teams 与本地 Skype for Business 上托管的用户之间的互操作性。 Teams 用户无法向使用本地 Skype for Business 的非 Teams 用户发送一对一聊天。  <br/> |2016 年 11 月 2 日  <br/> |
