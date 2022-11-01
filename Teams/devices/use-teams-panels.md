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
description: 本文提供有关如何使用 Teams 面板设备的指南。
ms.openlocfilehash: fff3df797e043b83662aacc9a67ef1af45b733a4
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801773"
---
# <a name="how-to-use-microsoft-teams-panels"></a>如何使用 Microsoft Teams 面板

Microsoft Teams 面板是安装在会议空间外的小型数字显示设备，通常位于入口旁边。 这些触摸屏面板是专用的 Microsoft Teams 设备，可提供有关会议空间和已安排会议的概览视图。 使用充满活力的彩色编码 LED 和主屏幕指示器，可以确定空间是可用还是从远处保留。 可以使用 Teams 面板在现场为临时会议保留可用会议空间。

Teams 面板设备预装了 Microsoft Teams，并显示通过 Outlook 或 Teams 日历安排的会议详细信息。

本文为最终用户和管理员提供有关如何使用 Teams 面板设备的指南。 它还提供了有关使用这些设备的 [常见问题的](#frequently-asked-questions) 解答。

有关面板设备的概述，以及如何在组织中规划、交付和管理这些设备，请参阅 [部署 Microsoft Teams 面板](teams-panels.md)。

有关快速入门，请查看 [Teams 面板入门](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)。

## <a name="teams-panels-end-user-experience"></a>Teams 面板最终用户体验

浏览 Teams 面板设备 [的主屏幕](#explore-teams-panels-home-screen) 以查看会议空间和会议详细信息。 或者，在触摸屏面板上点击并滚动以执行其他操作。

使用 Teams 面板设备：

- [查看会议空间详细信息和可用性、会议详细信息、即将预订](#explore-teams-panels-home-screen)
- [保留可用会议空间](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [报告问题](#report-a-problem)
- [查看或更新设备设置](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>浏览 Teams 面板主屏幕

主屏幕是 Teams 面板设备的主要可视界面。  

在主屏幕中，可以查看位置和会议详细信息、预留空间、查看即将进行的预留以及确定当前可用性状态。

以下屏幕截图显示了 Teams 面板“主页”屏幕上的不同部件或磁贴：

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="此屏幕截图显示 Teams 面板“主页”屏幕上的不同区域。":::

有关每个磁贴的说明，请参阅下表：

瓦 | 说明
:---|:---
**1-当前时间、日期和会议空间详细信息** | 显示当前时间、日期、日期和会议空间名称。 会议空间名称是登录到面板的资源帐户的名称。
**2- 会议空间可用性和会议详细信息** | 指示会议空间可用性并显示会议详细信息。 请参阅 [会议空间可用性和会议详细信息磁贴](#meeting-space-availability-and-meeting-details-tile)。
**3-即将推出的日历** | 显示会议空间日历和从当前小时开始最多 24 小时的可用性。 向上或向下滚动，以确定哪些时间段可用，哪些时间段是保留的。
**4-设置** | 显示 **“设置”** 图标。 点击它以报告问题或更新可用的设备设置。

### <a name="meeting-space-availability-and-meeting-details-tile"></a>会议空间可用性和会议详细信息磁贴

此磁贴的外观及其功能因会议空间可用性和预留类型而异。

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>会议空间是为安排的会议保留的

对于为通过 Outlook 或 Teams) 安排的会议 (安排的会议空间，该磁贴显示为紫色。 它以醒目的文本显示会议标题、会议开始和结束时间以及会议组织者的名称。 对于 Teams 会议，也会显示 Teams 徽标。 会议详细信息突出显示后，与会者可以轻松确认自己在正确的会议空间、正确的时间和正确的会议中。

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams 面板主屏幕，显示会议空间是为安排的会议保留的。":::

> [!NOTE]
>
> - 安排会议后，日历最多可能需要 90 秒才能同步并反映在面板屏幕上。
> - 对于 [标记为私密的已安排会议](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)，将显示 **“私人会议** ”，而不是实际会议标题。

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>会议空间是为临时会议保留的

对于 [为临时会议保留](#reserve-meeting-spaces-for-ad-hoc-meetings)的会议空间，磁贴将以紫色显示。 它以突出显示的文本以及会议开始和结束时间显示 **“保留** ”。 临时会议自动安排为 Teams 会议，因此 Teams 徽标始终显示在屏幕上。

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams 面板主屏幕显示会议空间是为临时会议保留的。":::

#### <a name="meeting-space-is-available"></a>会议空间可用

磁贴在可用会议空间中显示为绿色。 它以醒目文本显示 **“可用** ”，并显示“ **保留** ”按钮，你可以点击该按钮 [为临时会议保留会议空间](#reserve-meeting-spaces-for-ad-hoc-meetings)。 可以在右下 (磁贴) 查看会议空间的即将召开的日历，以确定临时会议的结束时间。

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="此屏幕截图显示了当会议空间可用时 Teams 面板“主页”屏幕的显示方式。":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>为临时会议保留会议空间

可以直接从面板为临时 [会议保留可用会议空间](#meeting-space-is-available) 。 所有临时会议都自动安排为 Teams 会议。 但是，保留后，无法通过面板释放或取消保留该会议空间。 只有设备资源帐户的管理员可以通过 Outlook 或 Teams 日历取消临时会议 (，) 取消预留空间。

对于直接从面板预订的临时会议：

- 开始时间始终是当前时间，因此不能将其安排在将来的时间。
- 结束时间可以持续到下一个安排的会议，也可以从当前小时开始最多 24 小时（以较早者为准）。 检查“主页”屏幕上的“ **即将推出的日历”** 磁贴，确定会议空间可用或预订的时间段。

若要为临时会议保留可用会议空间，请执行以下操作：

1. 在“主页”屏幕上，点击“ **保留** ”按钮。
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams 面板显示“保留”按钮的主屏幕。":::
2. 在 **“临时会议** ”屏幕中，查看可用的结束时间选项。 可以使用向右或向左箭头浏览可用的结束时间选项。

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="显示结束时间段的临时会议屏幕。":::

    > [!Note]
    >
    > - 结束时间选项以每小时 15 分钟的间隔显示。
    > - 结束时间默认为下一个 15 分钟间隔，即至少比当前时间晚 5 分钟。 例如，如果当前时间为下午 1：57，则默认结束时间显示为下午 2：15，而不是下午 2：00。 这可以防止用户预订空间五分钟或更短的时间。 在上面的屏幕截图中，默认结束时间显示为下午 2：00，这是下一个 15 分钟间隔，即至少在当前时间 (下午 1：53) 5 分钟之后的 5 分钟间隔。
    > - 上述规则的一个例外是，下一次会议的开始时间距离当前时间不到 5 分钟。 在这种情况下，可以预订空间，直到下一次会议开始时间。 例如，如果当前时间是下午 1：57，下一个会议开始时间为下午 2：00，则下午 2：00 将显示为唯一的结束时间选项，你可以保留空间 3 分钟。

3. 点击所需的结束时间间隔，然后点击“ **预留**”。

    此时会显示一个确认窗口，其中包含竖起的表情符号、会议开始和结束时间以及会议空间名称。
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="临时会议确认消息。":::
“主页”屏幕上的右侧磁贴现在显示为紫色，并显示 **“保留** 文本”和“Teams”徽标。 这表示会议空间现在是为临时 Teams 会议保留的。
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="显示会议空间是为临时会议保留的主屏幕。":::

    > [!NOTE]
    > 如果会议空间是 Microsoft Teams 会议室，则可以使用会议室内 Microsoft Teams 会议室或 Surface Hub 设备 _加入_ 此 Teams 会议。

### <a name="report-a-problem"></a>报告问题

若要报告设备或会议空间的问题、请求功能更新或提供任何反馈，请使用“主页”屏幕上的 **“设置”** 图标。

1. 点击“主页”屏幕上的 **“设置”** 齿轮图标。

2. 点击“ **报告问题”** 选项。

    “ **发送反馈”** 屏幕以窗体格式显示。
3. 从 **“类型** ”下拉列表中，选择请求的类型。
4. 从“ **问题** ”下拉列表中，选择类别。
5. 在 **“标题** 文本”字段中，使用面板键盘键入标题。
6. 如有必要，在 **“标题”** 下面的文本字段中键入其他详细信息。

    > [!NOTE]
    > 请勿包含任何个人身份信息。

7. 查看条目，然后点击“ **发送**”。

### <a name="view-or-update-a-device-setting"></a>查看或更新设备设置

有几个设备设置，例如关于、辅助功能、重新启动和隐私策略，你可以直接从面板查看或更新这些设置。 可用设备设置可能因设备的原始设备制造商 (OEM) 而异。 有关特定于设备的设置的信息，请参阅 OEM 文档。

若要查看或更新设备设置，请执行以下操作：

1. 点击“主页”屏幕上的 **“设置”** 图标。
2. 在 **“设置”** 屏幕中，点击“ **设备设置**”。
3. 在 **“设备设置”** 屏幕中，点击要查看或更新的设置。
4. 按照屏幕上的提示查看或更新设置。

## <a name="teams-panels-admin-experience"></a>Teams 面板管理体验

如果你是 [Teams 面板 的资源帐户的](teams-panels.md\#resource-account-provisioning)管理员，则你也是设备上的 **Panels App** 的管理员。 作为 **面板应用** 管理员，除了管理设备上的 **面板应用** 设置外，还可以执行 [最终用户体验](#teams-panels-end-user-experience)部分中提到的所有功能。

面板设备提供两种类型的管理员设置。 必须是设备管理员才能访问可用的管理员设置。 最终用户无法访问这些设置。

- 管理员特定于设备的设置，例如显示、时间和日期、语言、蓝牙、WiFi 等。 有关这些设置的详细信息，请参阅 OEM 文档。
- 管理员设备上特定于 **面板应用的** 设置，例如壁纸和 LED 指示灯颜色。 只有 **面板应用的** 管理员才能访问这些设置。 由于 **面板应用** 设置作为管理员设置的一部分提供，因此你必须拥有设备和 **面板应用的** 管理员登录凭据才能访问 **面板应用** 设置。

> [!NOTE]
> 通过设备完成的 **面板应用** 设置的任何更新仅适用于该特定设备。 这些更新不会影响组织中的其他面板设备。 例如，如果从 **“面板应用** 设置”更改主屏幕壁纸图像，则壁纸图像将仅针对该特定设备更改。

### <a name="access-panels-app-settings"></a>访问面板应用设置

可以使用管理员设置下的 **Teams 管理员设置** 选项访问 **面板应用** 特定的设置。 访问 **Teams 管理员设置** 的步骤可能因设备的 OEM 而异。

若要访问 **Teams 管理员设置** 选项，请执行以下操作：

1. 点击“主页”屏幕上的 **“设置”** 图标。
2. 在 **“设置”** 屏幕上，点击“ **设备设置**”。

    > [!NOTE]
    > 根据设备的 OEM，你可能需要立即或下一步之后输入设备管理员密码。

3. 向下滚动以找到 **“Teams 管理员设置”** 选项。 点击它。

> [!NOTE]
> 某些 OEM 可能会将 **Teams 管理员设置** 选项替换为自己的自定义选项。 如果未看到 **Teams 管理员设置** 选项，请查看设备文档，获取有关如何访问面板的管理员设置的说明。

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>将Teams 面板与 Android 上的 Microsoft Teams 会议室配对

若要在 Android 上配对Teams 面板和 Teams 会议室，两台设备必须登录到同一资源帐户。

在Teams 面板，使用管理员凭据登录。

1. 转到 **“设置”>“设备设置”，> Teams 管理员设置>设备配对。**

2. 6 位代码将显示在 Android 会议室显示器前面的Teams 会议室上。 在 Teams 面板中输入代码。  

#### <a name="enable-or-disable-meeting-check-in-and-automatic-room-release"></a>启用或禁用会议签入和自动会议室发布

通过签入和会议室发布设置，用户可以在会议开始时预留的会议室中签入 Teams 面板上的会议。 如果用户在会议开始时间之后的一定时间内未签入，会议室将释放并可供其他人预订。

当 Teams 面板与 Android 上的 Microsoft Teams 会议室配对时，可以启用签入通知，以便在会议迟到时显示在会议室前面的显示器上。

若要启用签入和会议室发布，请参阅 [Microsoft Teams 面板上的签入和会议室发布](check-in-and-room-release.md)。

#### <a name="enable-or-disable-check-out-manual-room-release"></a>启用或禁用签出 (手动会议室发布) 

启用签出后，最终用户可以使用Teams 面板手动释放会议室。 释放会议室将结束当前预订，并使该房间可供其他人安排。

此功能默认处于禁用状态，但可以根据设备启用此功能。 若要启用此功能，请转到 **“设置”>“设备设置”，>“会议”> Teams 管理员设置** ，然后打开“ **签出**”。

> [!NOTE]
> 如果与它配对的Teams 会议室设备处于活动呼叫中，则Teams 面板不能用于释放房间。

#### <a name="enable-or-disable-room-reservations"></a>启用或禁用会议室预留

启用会议室预订后，最终用户可以使用Teams 面板来预订当前可用的会议室。 预留在点击“ **预留** ”按钮时开始，其持续时间可以以 15 分钟的增量增加到下一个预留的开始时间，或最多 24 小时。

此功能默认处于启用状态，但可以按设备禁用。 若要禁用此功能，请转到 **“设置”>“设备设置”，> Teams 管理员设置>会议** “，然后打开 **”禁用会议室预留**”。

#### <a name="enable-or-disable-extension-of-existing-room-reservations"></a>启用或禁用现有会议室预留的延期

启用会议室预订延期后，如果会议室在原始结束时间之后可用，则最终用户可以使用Teams 面板来延长会议室的现有预留。 预留可以以 15 分钟的增量延长到下一次会议的开始时间，或将来最多 24 小时（以较快者为准）。

此功能默认处于禁用状态，但可以根据设备启用此功能。 若要启用此功能，请转到 **“设置”>“设备设置”，>“会议> Teams 管理员设置** ”，然后打开 **“延长会议室预留**”。

#### <a name="enable-or-disable-room-capacity-warnings"></a>启用或禁用会议室容量警告

与 Android 上的 Teams 会议室配对的 Teams 面板可以在会议室容量超过或超出容量时显示警告消息。 若要使用此功能，Teams 会议室必须具有支持人员计数的摄像头。 Android 上的Teams 会议室支持会议室容量警告，无需Teams 面板。

默认情况下，会议室容量警告处于禁用状态，但可以按设备启用它们。 若要启用该功能，请执行以下操作：

1. 按照将[Teams 面板与 Android 上的 Microsoft Teams 会议室配对](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)中的步骤操作。 面板和 Teams 会议室设备必须登录到同一资源帐户。
2. 转到 **“设置”>“设备设置”，>“会议> Teams 管理员设置** ”，然后打开 **“最大会议室占用通知**”。

#### <a name="enable-or-disable-viewing-of-room-equipment"></a>启用或禁用会议室设备的查看

启用此功能后，最终用户可以查看Teams 面板空间中可用的设备。

此功能默认处于关闭状态，并且可以按设备启用。 若要将其打开，请在 PowerShell 中使用 [Set-Place](/powershell/module/exchange/set-place) 配置 、、`DisplayDeviceName``VideoDeviceName`、 `Tags`和 `IsWheelChairAccessible`的`AudioDeviceName`显示名称。

或者，可以在 Exchange 管理中心启用此功能。 有关详细信息 [，请参阅编辑资源](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) 。

#### <a name="update-the-wallpaper"></a>更新壁纸

更改主屏幕壁纸图像。

1. [访问 **Teams 管理员设置**](#access-panels-app-settings)。
2. 点击 **“壁纸**”。
3. 从 **“选择图像**”中，选择要设置为主屏幕背景图像的图像。 在 **“背景**”下预览所选图像。
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="此屏幕截图显示壁纸设置屏幕。":::
4. 返回到主屏幕并验证壁纸是否已更新。

#### <a name="change-the-busy-state-led-color"></a>更改忙状态 LED 颜色

管理员可以选择红色或紫色作为 LED 颜色，以指示会议空间正忙或已保留。 指示可用空间的 LED 颜色始终为绿色，无法更改。

1. [访问 **Teams 管理员设置**](#access-panels-app-settings)。
2. 点击“ **LED 设置**”。
3. 从 **“选择 LED 颜色**”中，选择所需的颜色。
:::image type="content" source="../media/panels-led-settings.png" alt-text="此屏幕截图显示 LED 颜色忙碌状态设置。":::
4. 返回到主屏幕，并验证忙碌状态的 LED 颜色是否已更新。 如果会议空间当前可用，请尝试安排测试会议，以验证忙状态的 LED 颜色变化。

## <a name="frequently-asked-questions"></a>常见问题解答

查找有关 Teams 面板设备的常见问题解答。

**将来可以在多远查看会议空间的日程安排详细信息？**  
在“主页”屏幕上右下)  (“ **即将推出的日历”** 磁贴中，可以看到从当前小时开始，未来最多 24 小时的会议空间的日程安排详细信息。

**是否可以从 Teams 面板设备预留会议空间供将来使用？**  
否，不能在将来从面板保留会议空间。 对于从小组安排的临时会议，开始时间始终为当前时间。

**我可以为临时会议保留可用会议空间多长时间？**  
可以保留从当前时间开始到下一个计划会议时间的可用会议空间，或从当前时间开始最多保留 24 小时（以较早者为准）。 例如，如果当前时间是上午 10 点，下一个会议开始时间为下午 2 点，则可以保留上午 10 点到下午 2 点的会议空间。
