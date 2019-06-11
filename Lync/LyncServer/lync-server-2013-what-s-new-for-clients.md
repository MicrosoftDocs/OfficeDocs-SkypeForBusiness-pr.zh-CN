---
title: Lync Server 2013：面向客户端的新内容
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf37f68d0ea11e17a799956f285d8ca82eb2a27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Lync Server 2013 中面向客户端的新内容

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-19_

Microsoft Lync 2013 具有重新设计的用户界面和重要的新功能。 对于管理员, 客户端现已包含在 Office 安装程序中, 可提供更简单的方法来部署 Office 和自定义组织中的客户端。

<div>


> [!NOTE]  
> 有关 Lync 2013 用户界面更新的图解视图, 请参阅 "Lync 2013 中的新增功能" <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>。



</div>

<div>

## <a name="integration-with-office-setup"></a>与 Office 安装程序集成

Lync 2013 客户端和适用于 Lync 2013 的联机会议加载项 (它支持来自 Outlook 消息传递和协作客户端的会议管理) 现在都包含在 Office 2013 设置程序中。

在早期版本的 Lync 和 Office Communicator 中, 你可以使用 Windows Installer 属性自定义和控制 Office 安装。 由于 Lync 2013 与 Office 安装程序集成, 因此您可以使用以下方法自定义 Lync 2013 设置:

  - 使用 Office 自定义工具 (OCT)

  - 使用 Config.xml 执行安装任务

  - 使用设置命令行选项

<div>


> [!NOTE]  
> Lync 2013 安装程序不会卸载以前版本的 Lync 或 Office Communicator。 Lync 2013 客户端与其他 Lync 或 Office Communicator 客户端并行安装



</div>

有关详细信息, 请参阅[在 Lync Server 2013 中部署 Lync 客户端](lync-server-2013-deploying-lync-clients.md)。

</div>

<div>

## <a name="group-policy-deployment"></a>组策略部署

由于 Lync 2013 现已包含在 Office 安装程序中, 因此用于部署 Lync 组策略设置的方法已更改。 在早期版本的 Lync 和 Office Communicator 中, 你可以使用 Communicator 定义组策略设置, 而在 Lync 2013 中, 你现在可以使用与 Office 组策略一起提供的 Lync ADMX 和 ADML 管理模板管理模板。

有关详细信息, 请参阅[Lync 2013 的组策略设置](lync-server-2013-group-policy-settings-for-lync-2013.md)。

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Outlook 计划外接程序更新

Lync 2013 的联机会议加载项包括 "会议邀请自定义" 和 "新建会议" 选项。

  - 管理员可以通过添加自定义徽标、支持 URL、合法免责声明 URL 或自定义页脚文本来自定义组织的会议邀请。 有关详细信息, 请参阅[在 Lync Server 2013 中自定义联机会议加载项](lync-server-2013-customizing-the-online-meeting-add-in.md)。

  - 新与会者静音控件允许会议组织者安排在默认情况下将与会者音频和视频设为静音的会议。

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>虚拟桌面基础结构插件

Lync 2013 客户端现在支持虚拟桌面基础结构 (VDI) 环境中的音频和视频。 用户可以将音频或视频设备 (例如, 耳机或相机) 连接到本地计算机 (例如, 瘦客户端或重新使用用途的计算机)。 用户可以连接到虚拟机, 登录到在虚拟机上运行的 Lync 2013 客户端, 并参与实时音频和视频通信, 就像客户端在本地运行一样。 虚拟桌面环境支持以下功能:

  - 音频和视频设备集成, 包括以下内容:
    
      - 从设备调用控件
    
      - 设备上的联机状态集成
    
      - 多个 HID (人体学接口设备) 支持

  - 位置和紧急服务支持。

  - 支持所有 Lync 形式, 包括即时消息、音频、视频、应用程序共享、桌面共享、PowerPoint 共享、白板和文件传输。

  - 在联系人通话和电话会议中进行音频和视频支持。

有关部署 VDI 插件的信息, 请参阅[在 Lync Server 2013 中部署 LYNC VDI 插件](lync-server-2013-deploying-the-lync-vdi-plug-in.md)。

</div>

<div>

## <a name="video-enhancements"></a>视频增强

许多新功能显著增强了会议参与者的视频体验。

  - 视频通过 "面孔检测" 和 "智能框架" 进行了增强, 以便参与者的视频可以在框架中移动以帮助保持其居中。

  - 现在, 在两方呼叫和多方会议中支持高清晰度视频。 用户可以体验高达 HD 1080P 的分辨率。

  - 参与者可以从不同的会议版式中进行选择: 库视图显示所有参与者的图片或视频;"演讲者" 视图显示会议内容, 并且仅显示当前演讲者的视频或图片;演示文稿视图仅显示会议内容;紧凑视图仅显示会议控件。

  - 利用新的库功能, 参与者可以同时查看多个视频源。 如果会议具有超过五个参与者, 则只有最活跃参与者的视频源显示在顶部行中, 并且为其他参与者显示图片。

  - 参与者可以使用视频固定来选择一个或多个可用视频源, 以便在任何时候都可见。

  - 演示者可以使用视频聚焦功能选择一个人的视频源, 以便会议中的每个参与者仅看到该参与者。

</div>

<div>

## <a name="chat-room-integration"></a>聊天室集成

现在, lync 2013 集成了 Lync 2010 群组聊天以前提供的功能。 不再需要单独的群组聊天客户端。

  - 在 Lync 2013 中, 用户可以搜索聊天室、向其联系人添加聊天室、监视聊天室活动以及阅读和发布消息。

  - 用户可以创建主题源, 以便在其中一个聊天室中的某人添加包含特定关键字的帖子时收到通知。

  - 使用新的**持久聊天**选项页面, 用户可以设置在用户向其聊天室发布消息时应用的通知通知和声音。

</div>

<div>

## <a name="lync-web-app-updates"></a>Lync Web App 更新

Lync Web App 是适用于 Lync Server 2013 会议的基于 Web 的会议客户端。 在此版本中, 向 Lync Web App 添加计算机音频和视频可为没有本地安装 Lync 客户端的任何人提供完整的会议体验。 会议参与者可访问所有协作和共享功能以及演示者会议控件。

当用户尝试加入会议, 但没有本地安装的客户端时, 将打开 Lync Web App。 如果想要允许其他选项加入会议, 可以配置会议加入页面;请参阅在部署文档中的[Lync Server 2013 中配置会议加入页面](lync-server-2013-configuring-the-meeting-join-page.md)。

由于 Lync Web App 的增强功能, "更新版本的与会者" 在 Lync Server 2013 中不可用。 Lync Web App 是您的组织外部参与者选择的客户。 不需要本地客户端安装, 尽管音频、视频和共享功能需要插件在首次使用时安装。

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>适用于移动客户端更新的 Lync 2013

除了增强的状态、联系人和即时消息功能, Lync 2013 移动客户现在还通过 Internet 和手机网络数据连接提供语音和视频通话。 通过点击 "日历" 项目中的会议链接, 移动用户可以加入 Lync 语音和视频会议。 有关 Lync 2013 移动客户端的详细信息, 请参阅[在 Lync Server 2013 中规划移动客户端](lync-server-2013-planning-for-mobile-clients.md)。

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Lync 2013 用户界面更新

<div>

## <a name="accessibility-updates"></a>辅助功能更新

Lync 2013 包含几个新的辅助功能。

  - Lync 2013 支持高 DPI 分辨率, 从而使用户能够针对 125% 和 150% 点/英寸缩放文本和图形。

  - Lync 提供高对比度支持, 以便在 Windows 中与高对比度主题配合使用时, 用户界面保持完全正常工作。

  - Lync 提供了100多个键盘快捷方式, 以便用户无需鼠标即可访问重要的功能。 例如, 用户可以按 Alt + C 接受呼叫, 或按 Alt + I 忽略它, 而无需 tab 或设置焦点。 按下 (Alt + Q) 结束呼叫 (Ctrl + N) 启动 OneNote, (Alt + T) 将打开 "工具" 菜单。

  - Lync 2013 中的扩展屏幕阅读器支持可确保在启用屏幕阅读器时高声阅读所有通知、传入的请求和即时消息。

</div>

<div>

## <a name="presence-while-sharing"></a>共享时的状态

当 Lync 检测到用户正在共享时, Lync 会自动为用户分配演示状态。 除非向发件人分配了工作组私人关系, 否则此状态将阻止所有传入通信。 如果用户完全在辅助监视器上使用共享功能, 则 Lync 不会分配演示状态。

</div>

<div>

## <a name="conversation-window-updates"></a>对话窗口更新

重新设计的对话窗口可更快地访问重要功能。

  - 通过新的选项卡式对话功能, 用户现在可以在一个对话窗口中保留其所有 Im 和聊天室。 沿对话窗口左侧的选项卡使用户可以轻松地在所有活动对话中导航。

  - 用户可以将单个对话弹出到单独的窗口中, 然后调整窗口大小。 他们还可以将窗口弹出回到主对话窗口中。

  - 当用户注销并重新登录到 Lync 时, Lync 2013 将重新打开用户的对话。

  - 用户可以向任何对话快速添加即时消息、视频、程序共享、桌面共享或 web 会议工具 (白板、会议笔记、共享的笔记本和附件)。

  - 在正在共享视频或内容的会议中, 用户可以弹出会议视频或共享内容, 然后调整窗口大小。

</div>

<div>

## <a name="lync-main-window-updates"></a>Lync 主窗口更新

新的精简外观保留了熟悉的功能, 如**今天所发生的情况？** 备注域、状态选择器和 "**设置您的位置**选择器"。

  - 启用聊天室时, 用户可在主 Lync 页面上看到新的**聊天室**图标。 使用聊天室**** 图标, 用户可以快速访问其聊天室和筛选器。

  - 用户可以单击 "视图" 图标切换到 "**联系人**" 视图、"**聊天室**" 视图、"**对话**" 视图或 "**电话**" 视图。

  - 如果用户已迁移到 Exchange 2013, 他们可以上载高分辨率的图片。

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>联系人视图和联系人卡片更新

Lync 2013 为用户提供了在其 "**联系人**" 视图中查看联系人和组的不同方式。

  - 使用新的统一联系人存储, 将用户的 Lync 联系人迁移到 Exchange 2013 之后, 用户可以从 Lync 2013、Outlook 或 Outlook Web App 访问和管理其联系人, 其收藏夹保持同步。 例如, 如果用户将联系人添加到 Outlook 中的 "收藏夹", 则该联系人将显示在 Lync 2013 的 "收藏夹" 组中。

  - 如果你已添加并配置 XMPP 代理和 XMPP 网关, 则用户可以添加来自基于 XMPP 的合作伙伴的联系人, 以便发送即时消息和状态。

  - 新的 **"添加不在我的组织中的联系人"** 功能为用户提供了一种添加组织外部人员的简便方法。

  - 新的 **"常用联系人"** 组让用户可以构建用户最常联系的人员列表, 以便快速访问。

  - 用户可以使用新的 "**联系人列表**" 选项页来选择用户希望如何排序和显示联系人。 用户可以选择一个展开的两行视图, 显示联系人的图片或简洁的单行视图。 用户还可以按字母顺序或按可用性对联系人进行排序。

</div>

<div>

## <a name="conferencing-updates"></a>会议更新

Lync 2013 提供了多项会议功能增强功能。

  - 根据会议的类型, 用户现在可以将观众设为静音, 并在安排会议时允许或阻止视频共享。 "**会议选项**" 页面上提供了这些选项, 建议使用超过20个参与者的大型会议。

  - 在会议室中轻松使用音频控件允许用户控制音频选项, 如静音、取消静音、更改设备等。

  - 当共享程序时, 如果需要使用多个程序, 用户可以选择多个要共享的程序。

  - 用户现在可以上载 PowerPoint 文件, 并将鼠标指针悬停在幻灯片上以显示视频控件 (如播放、暂停和音频控件), 从而上载包含视频剪辑的演示文稿。

  - 在会议中, 用户可以通过将**此呼叫合并到**"**更多选项**" (**...**) 菜单中, 将另一个打开的对话合并到会议中。

  - 若要查看参与者的姓名, 用户可以将鼠标悬停在 "**视图参与者**" 按钮上, 或单击 "**显示参与者列表**" 以在会议中停靠面板。

  - 用户可以从多个不同的内容和参与者视图中进行选择, 具体取决于会议类型。

  - 会议录制将自动保存为在 Windows Media Player (工作表示) 中播放的格式。 用户可以轻松地与任何人共享文件, 或使用录制管理器中的 "**发布**" 功能将录制内容发布到共享位置。

  - OneNote 支持在会议中进行协作的新方法。 在会议期间, 用户可以使用 OneNote 做笔记, 以便在会议后个人使用, 或者与会议参与者实时使用共享笔记本和共同编辑会议参与者。 所有团队成员都可以访问共享笔记来参与信息、集体讨论创意或将笔记本页面用作虚拟白板。 会议中共享的人员和内容会自动添加到笔记中。

  - 用户可以使用会议室底部的 "**共享内容" 和 "主持会议活动**" 在内容类型之间进行切换。 用户还可以使用 "**管理可演示内容**" 菜单选择要共享的内容。

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

