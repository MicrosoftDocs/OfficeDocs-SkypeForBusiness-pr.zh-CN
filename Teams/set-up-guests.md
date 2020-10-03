---
title: 打开或关闭对 Microsoft 团队的来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: 了解如何在 Microsoft 团队中打开或关闭来宾访问功能，作为 Office 365 管理员。
ms.openlocfilehash: aa4530979054efc5a1aeb2c8fe0afa622b893f9d
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346323"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>打开或关闭对 Microsoft 团队的来宾访问

默认情况下会关闭来宾访问。 必须先为团队启用来宾访问权限，管理员或团队所有者才能添加来宾。

启用来宾访问后，可能需要几个小时才能使更改生效。 如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员"，则很可能是来宾访问尚未打开，或者设置尚未生效。

> [!IMPORTANT]
> 启用来宾访问取决于 Azure Active Directory、Microsoft 365、SharePoint 和团队中的设置。 有关详细信息，请参阅 [与团队中的来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。

## <a name="configure-guest-access-in-the-teams-admin-center"></a>配置团队管理中心中的来宾访问

1. 登录到 [Microsoft 团队管理中心](https://admin.teams.microsoft.com/)。

2. 选择 "**组织范围设置**"  >  **来宾访问**。

3. 将 " **允许 Microsoft 团队中的来宾访问** " 设置为 **"打开"**。

    ![允许来宾访问开关设置为 "开" ](media/set-up-guests-image1.png)

4. 在 " **呼叫**、 **会议**和 **消息**" 下，为每个功能选择 **"开" 或 "** **关** "，具体取决于您希望来宾用户允许的功能。

      - **进行专用通话** –打开此设置可允许来宾 **进行对等** 呼叫。
      - **允许使用 IP 视频** -打开此 **设置可允许来宾在其** 呼叫和会议中使用视频。
      - **屏幕共享模式** -此设置控制来宾用户的屏幕共享的可用性。 
          - 将此设置启用为 " **已禁用** "，以删除来宾在团队中共享其屏幕的功能。 
          - 将此设置转换为 " **单应用程序** " 以允许共享单个应用程序。 
          - 将此设置转换为 **整个屏幕** ，以允许完成屏幕共享。
      - **允许立即开会** –打开 **此设置可允许来宾在 Microsoft** 团队中使用 "立即开会" 功能。
      - **编辑已发送的邮件** -打开 **此设置可** 允许来宾编辑以前发送的邮件。
      - **来宾可以删除已发送的邮件** -打开 **此设置可** 允许来宾删除以前发送的邮件。
      - **聊天** -启用 **此设置，让来宾能够在** 团队中使用聊天功能。
      - **在对话中使用 giphy** -打开此 **设置可允许来宾在对话** 中使用 giphy。 Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。 每个 Giphy 都分配有一个内容分级。
      - **Giphy 内容分级** -从下拉列表中选择分级：
          - **允许所有内容** -无论内容分级如何，来宾都能够插入聊天中的所有 giphy。
          - "**中等**"-来宾将能够在聊天中插入 giphy，但将按成人内容适度限制。
          - **严格** -来宾将能够在聊天中插入 giphy，但将受到限制，无法插入成人内容。
      - **在对话中使用 meme** -打开此 **设置可允许来宾在对话** 中使用 meme。
      - **在对话中使用贴纸** -启用 **此设置可允许来宾在对话** 中使用贴纸。 

    ![团队中的来宾权限设置](media/manage-guest-access-image1.png)

5. 单击“**保存**”。

## <a name="external-access-federation-vs-guest-access"></a>外部访问（联合身份验证）与来宾访问

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>另请参阅

[与 Microsoft 365 建立安全协作](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[阻止来自特定团队的来宾用户](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)