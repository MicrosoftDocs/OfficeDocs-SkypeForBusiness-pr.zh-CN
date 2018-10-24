---
title: Lync Server 2013：使用 Lync Room System 管理 Web 门户
TOCTitle: 使用 Lync Room System 管理 Web 门户
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62269022
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中使用 Lync Room System 管理 Web 门户

 

_**上一次修改主题：** 2014-11-10_

在服务器上部署 LRS 之后，您可以通过从浏览器登录到 LRS 管理 Web 门户来检查所有 LRS 聊天室的状态。

## 登录

1.  浏览到以下 URL：
    
    https://\<fe-server\>/lrs

2.  输入 LRSSupport 帐户或者已添加到 LRSSupportAdminGroup 安全组的帐户的凭据。

![Lync 聊天室系统管理门户登录屏幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 聊天室系统管理门户登录屏幕")

## LRS 管理 Web 门户摘要页面

摘要页面为服务器上部署的所有 LRS 聊天室提供以下信息：

  - **标记**   管理员为聊天室提供的自定义名称。可以通过在门户中单击聊天室名称来设置标记。

  - **运行状况**   聊天室的运行状况状态，源自聊天室的“聚合运行状况”状态，它显示在“聊天室设置”页面的“运行状况”部分下方。

  - **下次会议**   计划召开下次会议的日期和时间。

  - **LRS 版本、制造商、型号**   这些值在 LRS 中预设。根据制造商，这些字段可能留空。

  - **上次刷新**   显示上次刷新网页的时间。

![Lync 聊天室系统管理门户摘要视图](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 聊天室系统管理门户摘要视图")

## LRS 聊天室信息

门户的“聊天室信息”部分允许您查看和配置各个 LRS 聊天室。它包含四个部分：设置、详细信息、日志记录和运行状况。

## 设置

在“设置”部分中，您可以重置聊天室的密码、聊天室标记和默认音量。如果配置这些设置，那么只会在您重新启动 LRS 控制台之后复制更改。

![Lync 聊天室系统管理门户聊天室设置](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 聊天室系统管理门户聊天室设置")

## 详细信息

“详细信息”部分提供 LRS 聊天室设置的只读摘要，包括：上次刷新时间；下次会议；上次更新、维护和校准；默认扬声器、麦克风和铃声设置；版本；SIP URI；屏幕编号和有关每个屏幕的详细信息；状态和活动。

![Lync 聊天室系统管理门户详细信息视图](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 聊天室系统管理门户详细信息视图")

## 日志记录

“日志记录”部分可用于远程收集日志并将它们保存到指定位置。您还可以重新启动 LRS 控制台（LRS 用户界面）或重新启动整个系统。

![Lync 聊天室系统管理门户聊天室日志记录](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 聊天室系统管理门户聊天室日志记录")

## 运行状况

“运行状况”部分提供 Lync Server 服务器连接、音频设备、视频设备、复原状态和屏幕设备的运行状况的直观指示。

![Lync 聊天室系统管理门户聊天室运行状况](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 聊天室系统管理门户聊天室运行状况")

## 有关管理 Web 门户的其他说明

> [!NOTE]  
> <ul>
> <li><p>出于安全考虑，管理 Web 门户会每隔 15 分钟自动将您注销。</p></li>
> <li><p>只有在重新启动 LRS 系统之后，才会应用设置更改。</p></li>
> <li><p>LRS 管理 Web 门户上的通知是粘滞形式的；换言之，它们不会消失。</p></li>
> <li><p>通知仅在您刷新页面之后显示。</p></li>
> <li><p>LRS 聊天室的状态仅在您刷新页面之后显示。</p></li>
> <li><p>如果 LRSApp 帐户密码过期，您不能查看聊天室的状态。请配置 LRSAppuser 帐户密码以便它从不过期，或者确保在密码即将过期时更新密码。</p></li>
> <li><p>仅本地部署支持 LRS 管理 Web 模板。</p></li>
> </ul>

## 疑难解答

## 为什么我无法登录管理 Web 模板？

  - 当您打开 https://localhost/lrs 时，您将能够看到登录页面，但是当您键入您的凭据时，您无法登录。 在这种情况下，您必须打开 https://FQDNofFEserver/lrs 登录管理 Web 模板。

  - 如果您从中访问管理 Web 模板的计算机位于工作组中，则“http://”不起作用。请使用“https”。

## 为什么我在管理 Web 门户中看不到 LRS？

  - 确保您的部署中有 LRS 帐户，并且它们是按照 LRS 管理 Web 门户部署建议创建的。确保在 Lync 服务器上使用 Enable-CsMeetingRoom 而不是 Enable-CsUser 设置 LRS 帐户。

  - 如果您已创建 LRS，但是在管理 Web 门户中看不到帐户，请使用 Lync 服务器日志记录工具并选中 **MeetingPortal** 组件来收集服务器日志，然后将它们发送给您的 LRS 支持联系人。

## 为什么我在管理 Web 门户中看不到 LRS 的状态？

  - 确保 LRSApp 用户帐户已启用 SIP。

  - 如果仍然遇到问题，请从 D:\\Tracing\\LRSAdminLogs\\ 收集 LRS 系统中的 **Trace.log** 文件，然后将其发送给您的 LRS 支持联系人。

