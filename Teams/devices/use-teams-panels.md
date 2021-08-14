---
title: 如何使用Microsoft Teams面板设备
ms.author: v-mdhiman
author: ManikaDhiman
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
localization_priority: Normal
description: 本文提供有关如何使用 Teams设备的指南。
ms.openlocfilehash: 28026f53f53fcb7b489abe3cf7d12a82d25f335907b1044591f92d4884853e03
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325059"
---
# <a name="how-to-use-microsoft-teams-panels"></a>如何使用Microsoft Teams面板

Microsoft Teams面板是安装在会议空间外（通常位于入口旁）的紧凑数字显示设备。 这些触摸屏面板是专用的Microsoft Teams设备，可一目了然地查看会议空间和计划的会议。 使用颜色编码的 LED 和主屏幕指示器，可以确定空间是可用还是保留一定距离。 您可以使用Teams为临时会议保留可用的会议空间。

Teams面板设备预安装有Microsoft Teams，并显示通过日历或日历Outlook Teams详细信息。

本文为最终用户和管理员提供有关如何使用 Teams设备的指南。 它还提供有关使用这些 [设备的](#frequently-asked-questions) 常见问题的解答。

有关面板设备的概述，以及有关如何在组织中计划、传送和管理它们的指导，请参阅部署Microsoft Teams[面板](teams-panels.md)。

有关快速入门，请查看快速入门[Teams面板。](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

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

以下屏幕截图显示了"主页"面板上的Teams或磁贴：

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="此屏幕截图显示主屏幕上的Teams区域":::

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

对于通过会议或会议计划安排的会议 (会议空间，磁贴Outlook紫色Teams) 。 它以醒目文本显示会议标题、会议开始时间和结束时间以及会议组织者的姓名。 对于Teams会议，还会Teams徽标。 在突出显示会议详细信息后，与会者可以轻松确认他们位于正确的会议空间、适当的时间以及合适的会议。

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams面板主屏幕，显示会议空间已预留给计划的会议":::

> [!NOTE]
>
> - 安排会议后，最多可能需要 90 秒才能同步日历，并反映在面板屏幕上。
> - 对于 [标记为私密的计划](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)**会议，将显示** 私人会议，而不是实际的会议标题。

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>为临时会议保留会议空间

为临时会议保留的会议空间的磁贴显示为 [紫色](#reserve-meeting-spaces-for-ad-hoc-meetings)。 它以 **醒目** 文本显示"保留"以及会议开始时间和结束时间。 临时会议自动安排为Teams会议，因此Teams徽标始终显示在屏幕上。

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams面板主屏幕，显示为临时会议保留了会议空间":::

#### <a name="meeting-space-is-available"></a>会议空间可用

该磁贴以绿色显示，表示可用的会议空间。 它以 **醒目** 的文本显示"可用"，并且还会显示"保留"按钮，您可以点击来为临时 [会议保留会议空间](#reserve-meeting-spaces-for-ad-hoc-meetings)。 您可以在右下 (磁贴中查看即将) 日历，以决定临时会议结束时间。

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="此屏幕截图显示Teams可用会议空间时"主页"面板的显示方式":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>为临时会议保留会议空间

可以直接从 [临时会议](#meeting-space-is-available) 面板中保留可用的会议空间。 所有临时会议都自动安排为Teams会议。 但是，一旦保留，你无法通过面板释放或取消保留该会议空间。 只有设备资源帐户的管理员可以通过 Outlook 或 Teams 日历 (取消临时会议) 来取消预订空间。

对于直接从面板预订的临时会议：

- 开始时间始终是当前时间，因此不能计划将来的时间。
- 结束时间可以到下一次计划会议，也可以从当前小时开始最多 24 小时（以较早者为准）。 检查 **"开始"屏幕上的** "即将到来的日历"磁贴，确定会议空间可用或预定的时间段。

为临时会议保留可用的会议空间：

1. 在"主页"屏幕上，点击" **保留"** 按钮。
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams显示"保留"按钮的主屏幕":::
2. 在 **临时会议屏幕** 中，查看可用的结束时间选项。 可以使用向右或向左箭头浏览可用的结束时间选项。

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="显示结束时间槽位的临时会议屏幕":::

    > [!Note]
    >
    > - 结束时间选项以一小时的 15 分钟间隔显示。
    > - 结束时间默认为下一个 15 分钟时间间隔，该间隔至少是当前时间后的五分钟。 例如，如果当前时间是下午 1：57，则默认结束时间显示为下午 2：15，而不是下午 2：00。 这可以防止用户预订空间 5 分钟或更小时。 在以上屏幕截图中，默认结束时间显示为下午 2：00，这是当前时间 (1：53 pm) 之后至少五分钟的下一个 15 分钟时间间隔。
    > - 上述规则的例外情况是下一次会议的开始时间为从当前时间开始的五分钟内。 在这种情况下，您可以预订空间，直到下一次会议开始时间。 例如，如果当前时间是下午 1：57，下一个会议开始时间是下午 2：00，则下午 2：00 将显示为唯一的结束时间选项，你可以将空间保留三分钟。

3. 点击所需的结束时间间隔，然后点击"保留 **"。**

    将显示一个确认窗口，显示一个缩略图，显示表情符号、会议开始时间和结束时间以及会议空间名称。
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="临时会议确认消息":::
"开始"屏幕上的右磁贴现在以紫色显示，并显示保留文本和Teams徽标。 这表示现在为临时临时会议保留Teams空间。
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="显示为临时会议保留会议空间的主屏幕":::

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
6. 在"标题"下面的文本 **字段中**，键入其他详细信息（如有必要）。

    > [!NOTE]
    > 不要包含任何个人身份信息。

7. 查看条目，然后点击"发送 **"。**

### <a name="view-or-update-a-device-setting"></a>查看或更新设备设置

有几个设备设置，例如关于、辅助功能、重新启动和隐私策略，可以直接从面板查看或更新。 可用的设备设置可能因原始设备制造商或 OEM (设备) 不同。 有关特定于设备的设置的信息，请参阅 OEM 文档。

若要查看或更新设备设置，请：

1. 点击 **设置** 图标。
2. 在屏幕 **设置，** 点击"**设备设置"。**
3. 在 **"设置"** 屏幕中，点击要查看或更新的设置。
4. 按照屏幕上的提示查看或更新设置。

## <a name="teams-panels-admin-experience"></a>Teams面板管理员体验

如果你是面板的资源 [Teams](teams-panels.md\#resource-account-provisioning)管理员，则你是设备上 **"面板应用**"的管理员。 作为 **面板应用** 管理员，除了管理设备上面板应用设置之外，还可以执行最终用户体验部分 [](#teams-panels-end-user-experience)中提到的所有功能。 

你的面板设备提供两种类型的管理员设置。 只有设备管理员才能访问可用的管理员设置。 最终用户无法访问这些设置。

- 特定于设备的管理员设置，例如显示、时间和日期、语言、蓝牙、WiFi 等。 若要详细了解这些设置，请参阅 OEM 文档。
- 特定于设备上"面板应用"的管理员设置，例如壁纸和 LED 指示器颜色。 只有面板 **应用的管理员可以** 访问这些设置。 由于 **"面板"** 应用设置作为管理员设置的一部分提供，因此必须具有设备和面板应用的管理员登录凭据才能访问 **面板应用** 设置。

> [!NOTE]
> 通过设备 **对面板应用** 设置所做的任何更新都仅适用于该特定设备。 这些更新不会影响组织的其他面板设备。 例如，如果从"面板应用"设置更改主屏幕 **壁纸图像，** 则壁纸图像将仅针对该特定设备更改。

### <a name="access-panels-app-settings"></a>访问面板应用设置

可以使用管理员 **设置** 下的"面板应用"设置 **面板应用** 特定设置。 访问面板 **应用** 设置的步骤可能因设备的 OEM 不同而不同。

若要访问 **"面板应用"设置** 选项：

1. 点击 **设置** 图标。
2. 在屏幕 **设置，** 点击"**设备设置"。**
3. 点击"**管理员设置"。**

    > [!NOTE]
    > 根据设备的 OEM，可能需要现在或下一步后输入设备管理员密码。

4. 向下滚动找到"面板 **应用"设置** 选项。 点击它。
5. 点击右侧 **屏幕上的"设置** 应用"按钮。
    将显示具有可用 **面板应用设置的** 屏幕。

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="此屏幕截图显示具有可用"面板"应用设置的屏幕":::

    使用此屏幕更新设备的 **以下面板** 应用设置：

    - [壁纸](#update-the-wallpaper)
    - [LED 指示器](#change-the-busy-state-led-color)

#### <a name="update-the-wallpaper"></a>更新壁纸

更改主屏幕壁纸图像。

1. [访问 **面板应用设置。**](#access-panels-app-settings)
2. 点击 **"壁纸"。**
3. 从 **"选择图像**"中，选择要设置为主屏幕背景图像的图像。 预览"背景"下的 **所选图像**。
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="此屏幕截图显示壁纸设置屏幕":::
4. 返回到主屏幕，验证壁纸已更新。

#### <a name="change-the-busy-state-led-color"></a>更改繁忙状态 LED 颜色

管理员可以选择红色或紫色作为 LED 颜色，以指示会议空间正忙或已预留。 指示可用空间的 LED 颜色始终为绿色，不能更改。

1. [访问 **面板应用设置。**](#access-panels-app-settings)
2. 点击 **"LED 设置"。**
3. 从 **"选择 LED 颜色"** 中，选择所需的颜色。
:::image type="content" source="../media/panels-led-settings.png" alt-text="此屏幕截图显示 LED 颜色忙状态设置":::
4. 返回到主屏幕，验证是否更新了忙态的 LED 颜色。 如果会议空间当前可用，请尝试安排一个测试会议来验证忙状态 LED 颜色的变化。

## <a name="frequently-asked-questions"></a>常见问题解答

查找有关面板设备Teams问题的答案。

**我可以在将来的多远时间查看会议空间的计划详细信息？**  
在主屏幕 (右下角) "即将到来的日历"磁贴中，可以看到从当前小时开始最多 24 小时的会议空间的计划详细信息。

**能否从仪表板设备为将来的Teams空间？**  
否，不能从面板保留将来的会议空间。 开始时间始终是从面板安排临时会议的当前时间。

**我可以为临时会议保留可用会议空间多久？**  
你可以保留从当前时间开始到下一个计划会议时间，或者从当前小时开始最多 24 小时（以较早者为准）的可用会议空间。 例如，如果当前时间为上午 10 点，下一个会议开始时间为下午 2 点，您可以保留上午 10 点到下午 2 点的会议空间。
