---
title: Lync Server 2013：客户端的新增功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6103c6cd8ae762402a94412a56eda107f43a58fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518199"
---
# <a name="whats-new-for-clients-in-lync-server-2013"></a>Lync Server 2013 中客户端的新增功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-19_

Microsoft Lync 2013 具有重新设计的用户界面和重要的新功能。 对于管理员，客户端现已包含在 Office 安装程序中，提供了更简单的方法来部署 Office 和自定义组织中的客户端。

<div>


> [!NOTE]  
> 有关 Lync 2013 用户界面更新的图解视图，请参阅中的 "Lync 2013 的新增功能" <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A> 。



</div>

<div>

## <a name="integration-with-office-setup"></a>与 Office 安装程序的集成

Lync 2013 客户端和用于 Lync 2013 的联机会议外接程序（它支持从 Outlook 消息和协作客户端中进行会议管理）现在都包含在 Office 2013 安装程序中。

在早期版本的 Lync 和 Office Communicator 中，可以使用 Windows Installer 属性自定义和控制 Office 安装。 由于 Lync 2013 与 Office 安装程序集成，因此您可以使用以下方法来自定义 Lync 2013 安装程序：

  - 使用 Office 自定义工具 (OCT)

  - 使用 Config.xml 执行安装任务

  - 使用安装程序命令行参数选项

<div>


> [!NOTE]  
> Lync 2013 安装程序不会卸载早期版本的 Lync 或 Office Communicator。 Lync 2013 客户端与其他 Lync 或 Office Communicator 客户端并行安装



</div>

有关详细信息，请参阅 [在 Lync Server 2013 中部署 Lync 客户端](lync-server-2013-deploying-lync-clients.md)。

</div>

<div>

## <a name="group-policy-deployment"></a>组策略部署

由于 Lync 2013 现在包含在 Office 安装程序中，因此用于部署 Lync 组策略设置的方法已更改。 在早期版本的 Lync 和 Office Communicator 中，可以使用 Communicator 定义组策略设置，而在 Lync 2013 中，现在可以使用 Lync ADMX 和 ADML 管理模板，这些模板与 Office 组策略管理模板一起提供。

有关详细信息，请参阅 [Lync 2013 的组策略设置](lync-server-2013-group-policy-settings-for-lync-2013.md)。

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Outlook 计划外接程序更新

Lync 2013 的联机会议外接程序包括会议邀请自定义和新会议选项。

  - 管理员可通过添加自定义徽标、支持 URL、法律免责声明 URL 或自定义页脚文本自定义组织的会议邀请。 有关详细信息，请参阅 [在 Lync Server 2013 中自定义联机会议外接程序](lync-server-2013-customizing-the-online-meeting-add-in.md)。

  - 新与会者静音控件允许会议组织者安排默认将与会者音频和视频设置为静音的会议。

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>虚拟桌面基础结构插件

Lync 2013 客户端现在支持虚拟桌面基础结构中的音频和视频 (VDI) 环境。 用户可以将音频或视频设备（例如，耳机或网络摄像头）连接到本地计算机（例如，瘦客户端或已调整用途的计算机）。 用户可以连接到虚拟机，登录到在虚拟机上运行的 Lync 2013 客户端，并参与实时音频和视频通信，如同客户端在本地运行一样。 虚拟桌面环境中支持以下功能：

  - 用于音频和视频的设备集成，包括以下内容：
    
      - 设备中的呼叫控制
    
      - 设备中的状态集成
    
      - 多 HID（人体学接口设备）支持

  - 位置和紧急服务支持。

  - 支持所有 Lync 形式，包括即时消息、音频、视频、应用程序共享、桌面共享、PowerPoint 共享、白板和文件传输。

  - 定人电话和电话会议中的音频和视频支持。

有关部署 VDI 插件的信息，请参阅 [在 Lync Server 2013 中部署 LYNC VDI 插件](lync-server-2013-deploying-the-lync-vdi-plug-in.md)。

</div>

<div>

## <a name="video-enhancements"></a>视频增强功能

若干个新功能可显著增强会议参与者的视频体验。

  - 通过人脸检测和智能取景增强了视频，从而使参与者的视频移动以帮助将它们的位置保持在框架中间。

  - 双方呼叫和多方会议中现在支持高清视频。用户可体验高达 HD 1080P 的分辨率。

  - 参与者可从不同的会议布局中进行选择：库视图显示所有参与者的图片或视频；发言人视图显示会议内容并且只显示当前发言人的视频或图片；演示文稿视图只显示会议内容；紧凑视图只显示会议控件。

  - 利用新的库功能，参与者可同时查看多个视频源。如果会议参与者超过五名，则只有最活跃的参与者的视频源显示在最上面一行，并对其他参与者显示图片。

  - 用户随时都可以使用视频固定选择要处于可见状态的一个或多个可用视频源。

  - 发言人可以使用视频聚焦功能选择一个人员的视频源，从而使每个会议参与者都能看到该参与者。

</div>

<div>

## <a name="chat-room-integration"></a>聊天室集成

Lync 2013 现在集成了 Lync 2010 组聊天以前提供的功能。 将不再需要单独的群聊客户端。

  - 在 Lync 2013 中，用户可以搜索聊天室、向联系人添加聊天室、监视聊天室活动以及阅读和发布邮件。

  - 用户可以创建主题源，这样当某一个聊天室中有人添加包含特定关键词的公告时，用户便可得到通知。

  - 利用新的“持久聊天”**** 选项页，用户可以设置在人员向其聊天室发布消息时应用的通知警报和声音。

</div>

<div>

## <a name="lync-web-app-updates"></a>Lync Web App 更新

Lync Web App 是基于 Web 的会议客户端（Lync Server 2013 会议）。 在此版本中，将计算机音频和视频添加到 Lync Web App 为没有本地安装 Lync 客户端的用户提供了完整的会议体验。 会议参与者有权访问所有协作和共享功能以及演示者会议控件。

当用户尝试加入会议，但未安装本地客户端时，将打开 Lync Web App。 如果您想要允许其他选项加入会议，则可以配置会议加入页面;请参阅部署文档中的在 [Lync Server 2013 中配置会议加入页面](lync-server-2013-configuring-the-meeting-join-page.md) 。

由于 Lync Web App 的增强功能，更新版本的与会者对 Lync Server 2013 不可用。 Lync Web App 是您组织外部的参与者的首选客户端。 不需要安装本地客户端，但在首次使用音频、视频和共享功能时需要安装插件。

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>适用于移动客户端更新的 Lync 2013

除了增强状态、联系人和即时消息功能之外，Lync 2013 移动客户端现在还通过 Internet 和手机网络数据连接提供语音和视频呼叫。 通过单击日历项目中的会议链接，移动用户可以加入 Lync 语音和视频会议。 有关 Lync 2013 移动客户端的详细信息，请参阅 [在 Lync Server 2013 中规划移动客户端](lync-server-2013-planning-for-mobile-clients.md)。

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Lync 2013 用户界面更新

<div>

## <a name="accessibility-updates"></a>辅助功能更新

Lync 2013 包含几个新的辅助功能。

  - Lync 2013 支持高 DPI 分辨率，使用户能够缩放每英寸125% 和每英寸150% 点的文本和图形。

  - Lync 提供高对比度支持，以便在 Windows 中与高对比度主题配合使用时，用户界面保持完全正常工作。

  - Lync 提供了100个以上的键盘快捷方式，以便用户无需鼠标即可访问重要的功能。 例如，用户可按 Alt+C 接受呼叫或按 Alt + I 忽略呼叫而不必通过 Tab 切换或设置焦点。 按 (Alt+Q) 可结束呼叫，按 (Ctrl+N) 可启动 OneNote，按 (Alt+T) 可打开“工具”菜单。

  - Lync 2013 中的广泛屏幕阅读器支持可确保在启用屏幕阅读器时高声阅读所有通知、传入请求和即时消息。

</div>

<div>

## <a name="presence-while-sharing"></a>共享时的状态

当 Lync 检测到某个用户正在共享时，Lync 会自动为该用户分配演示状态。 此状态阻止所有传入通信，除非发送者分配有“工作组”私人关系。 如果用户在辅助监视器上完全使用共享功能，则 Lync 不会分配演示状态。

</div>

<div>

## <a name="conversation-window-updates"></a>对话窗口更新

通过重新设计的对话窗口可以更快速地访问重要功能。

  - 通过新的选项卡式对话功能，用户现在可将所有 IM 和聊天室都保留在一个对话窗口中。通过对话窗口左侧的选项卡，用户可在所有活动对话中轻松导航。

  - 用户可在单独的窗口中弹出一个对话，然后调整窗口的大小。他们还可将该窗口弹回主对话窗口。

  - 在用户注销并重新登录 Lync 时，Lync 2013 将重新打开用户对话。

  - 用户可将 IM、视频、程序共享、桌面共享或 Web 会议工具（白板、会议纪录、共享笔记本和附件）快速添加到任何对话中。

  - 在共享视频或内容的会议中，用户可以弹出会议视频或共享内容，然后调整窗口大小。

</div>

<div>

## <a name="lync-main-window-updates"></a>Lync 主窗口更新

简化的新外观保留了熟悉的功能，如“今天发生了什么事?”**** 说明字段、状态选择器和“设置您的位置”**** 选择器。

  - 启用聊天室时，用户会在主 Lync 页面上看到一个新的 **聊天室** 图标。 通过“聊天室”**** 图标，用户可以快速访问其聊天室和筛选器。

  - 用户可通过单击视图图标切换到“联系人”**** 视图、“聊天室”**** 视图、“对话”**** 视图或“电话”**** 视图。

  - 如果用户已迁移到 Exchange 2013，则可以上传高分辨率图片。

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>联系人视图和联系人卡片更新

Lync 2013 为用户提供了在其 **联系人** 视图中查看联系人和组的不同方法。

  - 在新的统一联系人存储中，在将用户的 Lync 联系人迁移到 Exchange 2013 之后，用户可以从 Lync 2013、Outlook 或 Outlook Web App 访问和管理其联系人，并且他们的收藏夹保持同步。 例如，如果用户将联系人添加到 Outlook 中的 "收藏夹"，则该联系人将显示在 Lync 2013 的 "收藏夹" 组中。

  - 如果已添加和配置 XMPP 代理和 XMPP 网关，用户可从基于 XMPP 的合作伙伴添加联系人以查看即时消息和状态。

  - 利用新的“添加不在我的组织中的联系人”**** 功能，用户可以轻松添加组织以外的人员。

  - 通过新的“收藏夹”**** 组，用户可以生成最常联系的人员列表，以加快访问速度。

  - 用户可以使用新“联系人列表”**** 选项页选择用户希望的联系人的排序和显示方式。用户可以选择展开的两行视图（显示联系人的图片）或紧缩的一行视图。用户还可以按字母顺序或按可用性对联系人排序。

</div>

<div>

## <a name="conferencing-updates"></a>会议更新

Lync 2013 提供了几项针对会议功能的增强功能。

  - 根据会议类型，现在用户可在安排会议时使观众静音并允许或阻止视频共享。这些选项在“会议选项”**** 页中提供，建议用于参与者人数多于 20 的大型会议。

  - 会议室中易用的音频控件使用户可以控制音频选项，如静音、取消静音、更改设备等。

  - 在共享程序时，如果用户需要使用多个程序，则可选择要共享的多个程序。

  - 现在，用户可通过上载 PowerPoint 文件并将鼠标指向幻灯片以显示视频控件（如播放、暂停和音频控件）来上载包含视频剪辑的演示文稿。

  - 在会议中，用户可以使用“更多选项(…)”******** 菜单上的“将此呼叫合并为”**** 将打开的对话合并到会议中。

  - 若要查看参与者的姓名，用户可将光标悬停于“查看参与者”**** 按钮上，或单击“显示参与者列表”**** 以便在会议中停靠面板。

  - 根据会议类型，用户可从若干个不同的内容和参与者视图中进行选择。

  - 会议记录自动以可在 Windows Media Player (MP4) 中播放的格式保存。用户可以轻松地与任何人共享该文件，或使用记录管理器中的“发布”**** 功能在共享位置发布记录。

  - OneNote 启用了在会议中协作的新方式。在会议期间，用户可用 OneNote 记笔记以便在会后供个人使用，也可以使用共享笔记本并与会议参与者实时共同编辑。所有团队成员都可以访问共享笔记，以贡献信息、集体讨论或将笔记本页用作虚拟白板。会议中共享的人员和内容会自动添加到“笔记”中。

  - 用户可使用会议室底部的“共享内容和主持会议活动”**** 在内容类型之间进行切换。用户还可以使用“管理可演示的内容”**** 菜单选择要共享的内容。

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划客户端](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

