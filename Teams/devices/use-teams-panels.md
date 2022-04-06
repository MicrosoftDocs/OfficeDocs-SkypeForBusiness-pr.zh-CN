---
title: 如何使用Microsoft Teams面板设备
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: 本文提供有关如何使用 Teams设备的指南。
ms.openlocfilehash: 2928bb64881cad5fb5c6615d26767e963f725dcd
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2022
ms.locfileid: "64643036"
---
# <a name="how-to-use-microsoft-teams-panels"></a>如何使用Microsoft Teams面板

Microsoft Teams面板是安装在会议空间外（通常位于入口旁）的紧凑数字显示设备。 这些触摸屏面板是专用的Microsoft Teams设备，可一目了然地查看会议空间和计划的会议。 使用颜色编码的 LED 和主屏幕指示器，可以确定空间是可用还是保留一定距离。 您可以使用Teams为临时会议保留可用的会议空间。

Teams面板设备预安装有 Microsoft Teams，并显示通过日历或日历Outlook Teams会议详细信息。

本文为最终用户和管理员提供有关如何使用 Teams设备的指南。 它还提供有关使用这些 [设备的](#frequently-asked-questions) 常见问题的解答。

有关面板设备的概述，以及有关如何在组织中计划、传送和管理它们的指导，请参阅部署Microsoft Teams[面板](teams-panels.md)。

有关快速入门，请查看开始[面板Teams功能](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)。

## <a name="teams-panels-end-user-experience"></a>Teams面板最终用户体验

浏览[会议面板设备的](#explore-teams-panels-home-screen)Teams屏幕以查看会议空间和会议详细信息。 或者，点击并滚动触摸屏面板以执行其他操作。

使用Teams面板设备可以：

- [查看会议空间详细信息和可用性、会议详细信息、即将到来的预订](#explore-teams-panels-home-screen)
- [保留可用的会议空间](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [报告问题](#report-a-problem)
- [查看或更新设备设置](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>浏览Teams"主屏幕"

主屏幕是主机面板设备的主要Teams界面。  

在主屏幕中，可以查看位置和会议详细信息、预留空间、查看即将到来的预订，以及确定当前可用性状态。

以下屏幕截图显示"主页"面板上的Teams或磁贴：

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="此屏幕截图显示主屏幕上的Teams区域。":::

请参阅下表，了解每个磁贴的说明：

磁贴 | 说明
:---|:---
**1-当前时间、日期、日期和会议空间详细信息** | 显示当前时间、日期、日期和会议空间名称。 会议空间名称是登录到面板的资源帐户的名称。
**2-会议空间可用性和会议详细信息** | 指示会议空间可用性并显示会议详细信息。 请参阅 [会议空间可用性和会议详细信息磁贴](#meeting-space-availability-and-meeting-details-tile)。
**3-即将到来的日历** | 显示从当前小时开始最多 24 小时的会议空间日历和可用性。 向上或向下滚动，确定哪些时间段可用，哪些是保留的。
**4-设置** | 显示 **设置** 图标。 点击它以报告问题或更新可用的设备设置。

### <a name="meeting-space-availability-and-meeting-details-tile"></a>会议空间可用性和会议详细信息磁贴

此磁贴的外观及其功能因会议空间可用性和预订类型而异。

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>为计划的会议保留会议空间

对于为通过会议或会议计划的会议 (保留的会议空间，磁贴Outlook Teams) 。 它以醒目文本显示会议标题、会议开始时间和结束时间以及会议组织者的姓名。 对于Teams会议，还会Teams徽标。 在突出显示会议详细信息后，与会者可以轻松确认他们位于正确的会议空间、适当的时间以及正确的会议。

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams面板主屏幕，显示会议空间已预留给计划的会议。":::

> [!NOTE]
>
> - 安排会议后，最多可能需要 90 秒才能同步日历，并反映在面板屏幕上。
> - 对于[标记为私密的计划](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)会议，将显示"私人会议"，而不是实际的会议标题。

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>为临时会议保留会议空间

为临时会议保留的会议空间的磁贴显示为 [紫色](#reserve-meeting-spaces-for-ad-hoc-meetings)。 它以 **醒目** 文本显示"保留"以及会议开始时间和结束时间。 临时会议自动安排为Teams会议，因此Teams徽标始终显示在屏幕上。

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams面板主屏幕，显示为临时会议保留了会议空间。":::

#### <a name="meeting-space-is-available"></a>会议空间可用

该磁贴以绿色显示，表示可用的会议空间。 它 **以** 醒目的文本显示"可用"，并且还会显示"保留"按钮，您可以点击以保留临时 [会议的会议空间](#reserve-meeting-spaces-for-ad-hoc-meetings)。 您可以在右下 (磁贴中查看即将) 日历，以决定临时会议结束时间。

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="此屏幕截图显示Teams可用会议空间时，&quot;开始&quot;面板的显示方式。":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>为临时会议保留会议空间

可以直接从 [临时会议](#meeting-space-is-available) 面板中保留可用的会议空间。 所有临时会议都自动安排为Teams会议。 但是，一旦保留，你无法通过面板释放或取消保留该会议空间。 只有设备资源帐户的管理员可以通过 (或 Outlook 日历取消临时Teams) 来取消空间。

对于直接从面板预订的临时会议：

- 开始时间始终是当前时间，因此不能计划将来的时间。
- 结束时间可以到下一次计划会议，也可以从当前小时开始最多 24 小时（以较早者为准）。 检查 **"开始"屏幕上的** "即将到来的日历"磁贴，确定会议空间可用或预定的时间段。

为临时会议保留可用的会议空间：

1. 在"主页"屏幕上，点击" **保留"** 按钮。
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams显示&quot;保留&quot;按钮的主屏幕。":::
2. 在 **临时会议屏幕** 中，查看可用的结束时间选项。 可以使用向右或向左箭头浏览可用的结束时间选项。

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="显示结束时间槽位的临时会议屏幕。":::

    > [!Note]
    >
    > - 结束时间选项以一小时的 15 分钟间隔显示。
    > - 结束时间默认为下一个 15 分钟时间间隔，该间隔至少是当前时间后的五分钟。 例如，如果当前时间为下午 1：57，则默认结束时间显示为下午 2：15，而不是下午 2：00。 这可以防止用户预订空间 5 分钟或更小时。 在以上屏幕截图中，默认结束时间显示为下午 2：00，这是当前时间 (1：53 pm) 之后至少五分钟的下一个 15 分钟时间间隔。
    > - 上述规则的例外情况是，下一次会议的开始时间为从当前时间开始的五分钟内。 在这种情况下，您可以预订空间，直到下一次会议开始时间。 例如，如果当前时间是下午 1：57，下一个会议开始时间是下午 2：00，则下午 2：00 将显示为唯一的结束时间选项，你可以将空间保留三分钟。

3. 点击所需的结束时间间隔，然后点击"保留 **"**。

    将显示一个确认窗口，显示一个缩略图，显示表情符号、会议开始时间和结束时间以及会议空间名称。
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="临时会议确认消息。":::
"开始"屏幕上的右磁贴现在以紫色显示，并显示保留文本和Teams徽标。 这表示现在为临时临时会议保留Teams空间。
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="显示为临时会议保留会议空间的主屏幕。":::

    > [!NOTE]
    > 如果会议室是会议室Microsoft Teams，您可以使用会议室Teams会议室或Microsoft Teams加入Surface Hub会议。

### <a name="report-a-problem"></a>报告问题

若要报告设备或会议空间的问题、请求功能更新或提供任何反馈，请使用主屏幕上的"设置"图标。

1. 点击 **设置** 屏幕上的"齿轮"图标。

2. 点击" **报告问题"** 选项。

    " **发送反馈** "屏幕以表单格式显示。
3. 从 **"类型** "下拉列表中，选择请求的类型。
4. 从" **问题** "下拉列表中，选择类别。
5. 在" **标题** "文本字段中，使用面板键盘键入标题。
6. 如有必要，在"标题 **"** 下面的文本字段中键入其他详细信息。

    > [!NOTE]
    > 请勿包含任何个人身份信息。

7. 查看条目，然后点击"发送 **"**。

### <a name="view-or-update-a-device-setting"></a>查看或更新设备设置

有几个设备设置，例如关于、辅助功能、重新启动和隐私策略，可以直接从面板查看或更新。 可用的设备设置可能因原始设备制造商 (OEM) 设备。 有关特定于设备的设置的信息，请参阅 OEM 文档。

若要查看或更新设备设置，请：

1. 点击 **设置** 屏幕上的"设置"图标。
2. 在屏幕 **设置**，点击"**设备设置"**。
3. 在 **"设置**"屏幕中，点击要查看或更新的设置。
4. 按照屏幕上的提示查看或更新设置。

## <a name="teams-panels-admin-experience"></a>Teams面板管理员体验

如果你是用户资源Teams 面板管理员，则 [](teams-panels.md\#resource-account-provisioning)你是设备上 **"面板应用**"的管理员。 作为 **面板应用** 管理员，除了管理设备上面板应用设置之外，还可以执行最终用户体验部分 [](#teams-panels-end-user-experience)中提到的所有功能。

你的面板设备提供两种类型的管理员设置。 只有设备管理员才能访问可用的管理员设置。 最终用户无法访问这些设置。

- 特定于设备的管理员设置，例如显示、时间和日期、语言、蓝牙、WiFi 等。 若要详细了解这些设置，请参阅 OEM 文档。
- 特定于设备上"面板应用"的管理员设置，例如壁纸和 LED 指示器颜色。 只有面板 **应用的管理员可以** 访问这些设置。 由于 **"面板"** 应用设置作为管理员设置的一部分提供，因此必须具有设备和面板应用的管理员登录凭据才能访问 **面板应用** 设置。

> [!NOTE]
> 通过设备 **对面板应用** 设置所做的任何更新都仅适用于该特定设备。 这些更新不会影响组织的其他面板设备。 例如，如果从"面板应用"设置更改主屏幕 **壁纸图像，** 则壁纸图像将仅针对该特定设备更改。

### <a name="access-panels-app-settings"></a>访问面板应用设置

可以使用管理员 **设置** 下的"面板应用"**设置访问"** 面板"应用特定的设置。 访问面板 **应用** 设置步骤可能因设备的 OEM 不同而不同。

若要访问 **"面板应用"设置** 选项：

1. 点击 **设置** 屏幕上的"设置"图标。
2. 在屏幕 **设置**，点击"**设备设置"**。
3. 点击"**管理员设置"**。

    > [!NOTE]
    > 根据设备的 OEM，你可能需要现在或下一步后输入设备管理员密码。

4. 向下滚动找到"面板 **应用"设置** 选项。 点击它。
5. 点击右侧 **屏幕上的"设置** 应用"按钮。
    将显示具有可用 **面板应用设置的** 屏幕。

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="此屏幕截图显示具有可用&quot;面板&quot;应用设置的屏幕。":::

    使用此屏幕更新设备的 **以下面板** 应用设置：

    - [壁纸](#update-the-wallpaper)
    - [LED 指示器](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>将 Teams 面板 与 android Microsoft Teams 会议室配对

若要在 Android Teams 面板与 Teams会议室配对，这两台设备必须登录到同一资源帐户。

在Teams 面板，使用管理员凭据登录。

1. 转到"**设置 >设备设置 >"设置 >"应用设置 >">设备配对"。**

2. 会议室显示前 Android Teams 会议室上会显示一个六位数的代码。 在"操作面板"Teams代码。  

#### <a name="meeting-check-in-and-room-release"></a>会议签入和会议室释放

签入和会议室释放设置允许用户在会议开始时Teams会议室的面板上签入会议。 如果用户未在会议开始时间后的一定时间内签入，会议室将释放，可供其他人预订。

当Teams面板与 Android Microsoft Teams 会议室配对时，当会议延迟运行时，签入通知可以显示在会议室前显示器上。

若要启用签入和房间释放，请参阅面板上的签入和[Microsoft Teams发布](check-in-and-room-release.md)。

#### <a name="room-capacity-warning"></a>会议室容量警告

Teams Android 上的会议室Teams，当会议室容量超过或超过容量时，可显示警告消息。 若要使用此功能，Teams会议室必须具有支持人员计数的摄像机。 Teams 会议室 Android 支持会议室容量警告，无需Teams 面板。

默认情况下，会议室容量警告已关闭。 若要从设备打开Teams 面板，请首先将 Teams 面板 与 Android Microsoft Teams[会议室配对](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)。 面板和Teams必须登录到同一资源帐户。

 然后，转到"**设置 >设置">"">"面板应用设置"**。 然后，在" **会议"** 下，打开 **"最大占用空间"通知**。

#### <a name="view-room-equipment"></a>查看会议室设备

启用此功能后，最终用户可以查看空间中空间内可用的设备Teams 面板。

默认情况下，此功能已关闭，并且可以按设备启用。 若要将其打开，请使用 PowerShell 中的 ["](/powershell/module/exchange/set-place?view=exchange-ps) 设置位置" `AudioDeviceName`配置 、 `DisplayDeviceName`、 `VideoDeviceName`、 `Tags`和 的显示名称 `IsWheelChairAccessible`。

或者，可以在管理中心Exchange此功能。 有关详细信息 [，请参阅](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) 编辑资源。



#### <a name="update-the-wallpaper"></a>更新壁纸

更改主屏幕壁纸图像。

1. [访问 **面板应用设置**](#access-panels-app-settings)。
2. 点击 **"壁纸"**。
3. 从 **"选择图像**"中，选择要设置为主屏幕背景图像的图像。 预览"背景"下的所选 **图像**。
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="此屏幕截图显示壁纸设置屏幕。":::
4. 返回主屏幕，并验证壁纸是否更新。

#### <a name="change-the-busy-state-led-color"></a>更改繁忙状态 LED 颜色

管理员可以选择红色或紫色作为 LED 颜色，以指示会议空间正忙或已预留。 指示可用空间的 LED 颜色始终为绿色，不能更改。

1. [访问 **面板应用设置**](#access-panels-app-settings)。
2. 点击 **"LED 设置"**。
3. 从 **"选择 LED 颜色"** 中选择所需的颜色。
:::image type="content" source="../media/panels-led-settings.png" alt-text="此屏幕截图显示 LED 颜色忙状态设置。":::
4. 返回主屏幕，并验证忙态的 LED 颜色已更新。 如果会议空间当前可用，请尝试安排一个测试会议来验证忙状态 LED 颜色的变化。

## <a name="frequently-asked-questions"></a>常见问题解答

查找有关面板设备Teams问题的答案。

**我可以在将来的多远时间查看会议空间的计划详细信息？**  
在"开始"屏幕 (右下角) "即将到来的日历"磁贴中，你可以看到从当前小时开始最多 24 小时的会议空间的计划详细信息。

**能否从仪表板设备为将来的Teams空间？**  
否，不能从面板保留将来的会议空间。 开始时间始终是从面板安排临时会议的当前时间。

**我可以为临时会议保留可用会议空间多久？**  
你可以保留从当前时间开始到下一个计划会议时间，或者从当前小时开始最多 24 小时（以较早者为准）的可用会议空间。 例如，如果当前时间为上午 10 点，下一个会议开始时间为下午 2 点，您可以保留上午 10 点到下午 2 点的会议空间。
