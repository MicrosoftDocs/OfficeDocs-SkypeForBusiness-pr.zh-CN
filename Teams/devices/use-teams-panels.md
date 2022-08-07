---
title: 如何使用 Microsoft Teams 面板设备
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: 本文提供有关如何使用 Teams 面板设备的指导。
ms.openlocfilehash: f9d67ce6c41e351239457edc4a605964c7bcae27
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268437"
---
# <a name="how-to-use-microsoft-teams-panels"></a>如何使用 Microsoft Teams 面板

Microsoft Teams 面板是小型数字显示设备，安装在会议空间外部，通常位于入口旁边。 这些触摸屏面板是专用的 Microsoft Teams 设备，可提供有关会议空间和计划会议的一览视图。 使用充满活力的彩色编码 LED 和主屏幕指示器，可以确定空间是可用的还是从远处保留的。 可以使用 Teams 面板现场为临时会议保留可用会议空间。

Teams 面板设备预安装 Microsoft Teams，并显示通过 Outlook 或 Teams 日历安排的会议详细信息。

本文向最终用户和管理员提供有关如何使用 Teams 面板设备的指导。 它还提供有关使用这些设备的 [常见问题的解答](#frequently-asked-questions) 。

有关面板设备的概述，以及有关如何在组织中规划、交付和管理这些设备的指南，请参阅 [“部署 Microsoft Teams”面板](teams-panels.md)。

有关快速入门，请查看 [Teams 面板入门](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)。

## <a name="teams-panels-end-user-experience"></a>Teams 面板最终用户体验

浏览 Teams 面板设备的 [主屏幕](#explore-teams-panels-home-screen) 以查看会议空间和会议详细信息。 或者，点击触摸屏面板并滚动以执行其他操作。

使用 Teams 面板设备执行以下操作：

- [查看会议空间详细信息和可用性、会议详细信息、即将进行的预留](#explore-teams-panels-home-screen)
- [保留可用的会议空间](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [报告问题](#report-a-problem)
- [查看或更新设备设置](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>浏览 Teams 面板主屏幕

主屏幕是 Teams 面板设备的主视觉界面。  

在“主页”屏幕中，可以查看位置和会议详细信息、保留空间、查看即将进行的预留以及确定当前可用性状态。

以下屏幕截图显示 Teams 面板主屏幕上的不同部分或磁贴：

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="此屏幕截图显示 Teams 面板主屏幕上的不同区域。":::

有关每个磁贴的说明，请参阅下表：

瓦 | 说明
:---|:---
**1-Current 时间、日期、日期和会议空间详细信息** | 显示当前时间、日期、日期和会议空间名称。 会议空间名称是登录到面板的资源帐户的名称。
**2 会议空间可用性和会议详细信息** | 指示会议空间可用性并显示会议详细信息。 请参阅 [会议空间可用性和会议详细信息磁贴](#meeting-space-availability-and-meeting-details-tile)。
**3-即将推出的日历** | 显示会议空间日历和可用性，从当前小时开始最多 24 小时。 向上或向下滚动以确定哪些时间段可用，哪些时间段是保留的。
**4-Settings** | 显示 **“设置”** 图标。 点击它以报告问题或更新可用设备设置。

### <a name="meeting-space-availability-and-meeting-details-tile"></a>会议空间可用性和会议详细信息磁贴

此磁贴的外观及其功能因会议空间可用性和预留类型而异。

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>为计划的会议保留会议空间

磁贴以紫色显示，用于为通过 Outlook 或 Teams) 安排的计划会议 (保留的会议空间。 它以突出文本、会议开始和结束时间以及会议组织者的姓名显示会议标题。 对于 Teams 会议，也会显示 Teams 徽标。 突出显示会议详细信息后，与会者可以轻松确认他们在正确的会议空间、正确的时间和正确的会议。

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams 面板主屏幕显示会议空间是为计划的会议保留的。":::

> [!NOTE]
>
> - 安排会议后，日历可能需要长达 90 秒的时间才能同步并在面板屏幕上进行反映。
> - 对于 [标记为专用的预定会议](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)，将显示 **专用会议** ，而不是实际会议标题。

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>为临时会议保留会议空间

该磁贴以紫色显示为 [临时会议保留的会议](#reserve-meeting-spaces-for-ad-hoc-meetings)空间。 它以突出文本显示 **保留** ，以及会议开始和结束时间。 临时会议自动安排为 Teams 会议，因此 Teams 徽标始终显示在屏幕上。

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams 面板主屏幕显示为临时会议保留会议空间。":::

#### <a name="meeting-space-is-available"></a>会议空间可用

磁贴以绿色显示为可用会议空间。 它以突出文本显示 **“可用** ”，同时还会显示一个 **“保留** ”按钮，你可以点击此按钮 [来保留临时会议的会议空间](#reserve-meeting-spaces-for-ad-hoc-meetings)。 可以查看即将开始的会议空间日历 (右下磁贴) 以确定临时会议的结束时间。

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="此屏幕截图显示了当会议空间可用时 Teams 面板主屏幕的显示方式。":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>为临时会议保留会议空间

可以直接从临时会议的面板中保留 [可用的会议空间](#meeting-space-is-available) 。 所有临时会议将自动安排为 Teams 会议。 但是，保留后，无法通过面板释放或保留该会议空间。 只有设备资源帐户的管理员才能通过 Outlook 或 Teams 日历取消临时会议 () 以保留空间。

对于直接从面板预订的临时会议：

- 开始时间始终是当前时间，因此无法在将来安排它。
- 结束时间可以是到下一次计划的会议，或者从当前时间（以更早者为准）的 24 小时。 检查主屏幕上 **的“即将开始的日历”** 磁贴，以确定会议空间可用或预订的时间段。

为临时会议保留可用会议空间：

1. 在“主页”屏幕上，点击 **“保留** ”按钮。
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams 面板主屏幕显示“保留”按钮。":::
2. 在 **临时会议** 屏幕中，查看可用的结束时间选项。 可以使用向右或向左箭头浏览可用的结束时间选项。

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="显示结束时间段的临时会议屏幕。":::

    > [!Note]
    >
    > - 结束时间选项以 15 分钟的间隔显示，间隔为 1 小时。
    > - 结束时间默认为下一个 15 分钟间隔，即在当前时间之后至少 5 分钟。 例如，如果当前时间是下午 1：57，则默认结束时间显示为下午 2：15，而不是下午 2：00。 这会阻止用户预订空间 5 分钟或更短的时间。 在上面的屏幕截图中，默认结束时间显示为下午 2：00，这是下一个 15 分钟的间隔，在当前时间 (下午 1：53) 后至少 5 分钟。
    > - 上述规则的例外情况是下一次会议的开始时间在当前时间的五分钟内。 在这种情况下，可以预订空间，直到下一次会议开始时间。 例如，如果当前时间是下午 1：57，而下一次会议开始时间是下午 2：00，则下午 2：00 将显示为唯一的结束时间选项，你可以将空间保留三分钟。

3. 点击所需的结束时间间隔，然后点击 **“保留**”。

    此时会显示一个确认窗口，其中包含竖起大拇指的表情符号、会议开始和结束时间以及会议空间名称。
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="临时会议确认消息。":::
“主页”屏幕上的右侧磁贴现在以紫色显示，并显示 **保留** 文本和 Teams 徽标。 这表示会议空间现在已保留给临时 Teams 会议。
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="显示临时会议保留会议空间的主屏幕。":::

    > [!NOTE]
    > 如果会议空间是 Microsoft Teams 会议室，则可以使用会议室内的 Microsoft Teams 会议室或 Surface Hub 设备 _加入_ 此 Teams 会议。

### <a name="report-a-problem"></a>报告问题

若要报告设备或会议空间的问题，若要请求功能更新或提供任何反馈，请使用主屏幕上的 **“设置”** 图标。

1. 点击“主页”屏幕上 **的“设置”** 齿轮图标。

2. 点击 **“报表问题** ”选项。

    **“发送反馈**”屏幕以窗体格式显示。
3. 从 **“类型** ”下拉列表中，选择请求的类型。
4. 从 **“问题** ”下拉列表中，选择类别。
5. 在 **“标题** ”文本字段中，使用面板键盘键入标题。
6. 在 **“标题”** 下方的文本字段中，键入其他详细信息（如有必要）。

    > [!NOTE]
    > 请勿包含任何个人身份信息。

7. 查看条目并点击 **“发送**”。

### <a name="view-or-update-a-device-setting"></a>查看或更新设备设置

可直接从面板查看或更新多个设备设置，例如关于、辅助功能、重启和隐私策略。 可用设备设置可能因设备的原始设备制造商 (OEM) 而有所不同。 有关特定于设备的设置的信息，请参阅 OEM 文档。

若要查看或更新设备设置，请执行以下操作：

1. 点击“主页 **”屏幕上的“设置”** 图标。
2. 在 **“设置”** 屏幕中，点击 **“设备设置**”。
3. 在 **“设备设置”** 屏幕中，点击要查看或更新的设置。
4. 按照屏幕上的提示查看或更新设置。

## <a name="teams-panels-admin-experience"></a>Teams 面板管理员体验

如果你是 [Teams 面板资源帐户的](teams-panels.md\#resource-account-provisioning)管理员，那么你也是设备上的 **面板应用** 的管理员。 作为 **面板应用** 管理员，除了管理设备上的 **面板应用** 设置外，还可以执行 [最终用户体验](#teams-panels-end-user-experience)部分中提到的所有函数。

面板设备提供两种类型的管理员设置。 必须是设备管理员才能访问可用的管理员设置。 最终用户无法访问这些设置。

- 管理员特定于设备的设置，例如显示、时间和日期、语言、蓝牙、WiFi 等。 请参阅 OEM 文档，详细了解这些设置。
- 管理员特定于设备上的 **面板应用** 的设置，例如壁纸和 LED 指示器颜色。 只有 **面板应用** 的管理员才能访问这些设置。 由于 **面板应用** 设置作为管理员设置的一部分可用，因此必须具有设备和 **面板应用** 的管理员登录凭据才能访问 **面板应用** 设置。

> [!NOTE]
> 通过设备完成的 **面板应用** 设置的任何更新都仅适用于该特定设备。 这些更新不会影响组织中的其他面板设备。 例如，如果从 **面板应用** 设置更改主屏幕壁纸图像，则墙纸图像将仅针对该特定设备进行更改。

### <a name="access-panels-app-settings"></a>访问面板应用设置

可以使用管理员设置下的 **“面板应用设置”** 选项访问 **面板应用** 特定的设置。 访问 **面板应用设置的** 步骤可能因设备的 OEM 而异。

若要访问 **“面板应用设置”** 选项：

1. 点击“主页 **”屏幕上的“设置”** 图标。
2. 在 **“设置”** 屏幕上，点击 **“设备设置**”。
3. 点击 **管理员设置**。

    > [!NOTE]
    > 根据设备的 OEM，可能需要立即或在下一步之后输入设备管理员密码。

4. 向下滚动以查找 **“面板应用设置”** 选项。 点击它。
5. 点击右侧屏幕上 **的“面板应用设置”** 按钮。
    将显示具有可用 **面板应用** 设置的屏幕。

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="此屏幕截图显示具有可用面板应用设置的屏幕。":::

    使用此屏幕更新设备的以下 **面板应用** 设置：

    - [壁纸](#update-the-wallpaper)
    - [LED 指示器](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>将Teams 面板与 Android 上的 Microsoft Teams 会议室配对

若要将 Android 上的Teams 面板和 Teams 会议室配对，必须将这两个设备登录到同一资源帐户。

在Teams 面板上，使用管理员凭据登录。

1. 转到 **“设置>设备设置> 管理员设置>面板应用设置>会议>设备配对。**

2. Android 会议室前台显示的Teams 会议室上将显示一个六位数的代码。 在 Teams 面板上输入代码。  

#### <a name="meeting-check-in-and-room-release"></a>会议签入和会议室发布

通过签入和会议室发布设置，用户可在会议开始时保留的会议室的 Teams 面板上签入会议。 如果用户在会议开始时间之后的一定时间内未签入，则会释放会议室并可供其他人保留。

当 Teams 面板与 Android 上的 Microsoft Teams 会议室配对时，可以启用签入通知，以便在会议运行较晚时显示在会议室前显示。

若要启用签入和会议室版本，请 [参阅 Microsoft Teams 面板上的签入和会议室版本](check-in-and-room-release.md)。

#### <a name="room-capacity-warning"></a>会议室容量警告

与 Android 上的 Teams 会议室配对的 Teams 面板可以在会议室容量达到或超过容量时显示警告消息。 若要使用此功能，Teams 会议室必须具有支持人员计数的相机。 Android 上的Teams 会议室支持没有Teams 面板的房间容量警告。

默认情况下，会议室容量警告处于关闭状态。 若要从Teams 面板打开设置，请先将[Teams 面板与 Android 上的 Microsoft Teams 会议室配对](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)。 面板和 Teams 会议室必须登录到同一资源帐户。

 然后，转到 **“设置>设备设置> 管理员”面板应用设置>设置**。 然后，在 **“会议**”下，打开 **Max 会议室占用通知**。

#### <a name="view-room-equipment"></a>查看会议室设备

启用此功能后，最终用户可以查看Teams 面板空间中可用的设备。

默认情况下，此功能处于关闭状态，并且可以为每个设备启用此功能。 若要打开它，请在 PowerShell [中使用 Set-Place](/powershell/module/exchange/set-place?view=exchange-ps) 来配置显示名称`AudioDeviceName`、`Tags``DisplayDeviceName``VideoDeviceName`、和 。`IsWheelChairAccessible`

或者，可以在 Exchange 管理中心启用此功能。 有关详细信息，请参阅 [“编辑资源](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) ”。



#### <a name="update-the-wallpaper"></a>更新壁纸

更改主屏幕壁纸图像。

1. [访问 **面板应用设置**](#access-panels-app-settings)。
2. 点击 **壁纸**。
3. 从 **“选择图像**”中，选择要设置为主屏幕背景图像的图像。 在“ **背景**”下预览所选图像。
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="此屏幕截图显示壁纸设置屏幕。":::
4. 返回到主屏幕并验证壁纸是否已更新。

#### <a name="change-the-busy-state-led-color"></a>更改忙碌状态 LED 颜色

管理员可以选择红色或紫色作为 LED 颜色，以指示会议空间繁忙或保留。 指示可用空间的 LED 颜色始终为绿色，无法更改。

1. [访问 **面板应用设置**](#access-panels-app-settings)。
2. 点击 **LED 设置**。
3. 从 **“选择 LED 颜色**”中，选择所需的颜色。
:::image type="content" source="../media/panels-led-settings.png" alt-text="此屏幕截图显示 LED 颜色忙状态设置。":::
4. 返回到主屏幕，并验证忙碌状态的 LED 颜色是否已更新。 如果会议空间当前可用，请尝试安排测试会议，以验证忙碌状态的 LED 颜色更改。

## <a name="frequently-asked-questions"></a>常见问题解答

查找有关 Teams 面板设备的常见问题的解答。

**将来能看出会议空间的计划详细信息有多远？**  
在主屏幕右下)  (**“即将到来的日历”** 磁贴中，可以看到会议空间的日程安排详细信息（从当前时间开始长达 24 小时）。

**是否可以从 Teams 面板设备保留会议空间以供将来使用？**  
不可以，不能在将来从面板中保留会议空间。 开始时间始终是从小组安排的临时会议的当前时间。

**可以为临时会议保留可用会议空间多长时间？**  
可以保留从当前时间开始到下一个计划会议时间的可用会议空间，或者从当前时间（以更早者为准）最多 24 小时。 例如，如果当前时间是上午 10 点，而下一个会议开始时间是下午 2 点，则可以保留上午 10 点到下午 2 点的会议空间。
