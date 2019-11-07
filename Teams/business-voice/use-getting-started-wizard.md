---
title: 使用“入门”向导设置商务语音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46f6f75ce0ac14193a4f7a8cfccadf8312f92a98
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972193"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>使用“入门”向导设置商务语音

借助 Microsoft 365 商务语音的“入门”向导，用户可以轻松快速地开始在 Microsoft Teams 中接听和拨打电话。 如果是一家刚创立的小型企业，此向导可在几分钟内启动并运行电话号码、呼叫菜单、问候语等。 如果是已创建电话解决方案的大型企业，此向导可帮助设置商务语音试点，这样可以先对一些用户试用它，然后再面向所有人进行设置。 无论你的企业是哪种规模，都可以在完成向导后立刻开始使用商务语音！

启动向导前，建议先阅读本文。 准备就绪时，可以从 [Microsoft 365 管理中心](https://admin.microsoft.com/AdminPortal/Home#/homepage)打开向导。 请务必使用创建订阅所用的帐户或作为全局管理员的其他帐户登录。

> [!IMPORTANT]
> 目前商务语音适用于加拿大和英国。 在 2020 年，它将适用于更多国家和地区。
>
> 只有在用户的邮箱位于 Microsoft 365 中时，Microsoft Teams 和商务语音才可用。  不支持位于本地 Exchange Server 的邮箱。

<!-- After you've finished the wizard, here are a couple articles you can check out to see what you can do with Business Voice and learn how to customize it. If you don't want to customize anything, you're done! You can start using Business Voice right away.

* [Things to try with Business Voice](things-to-try.md)
* [Customize Business Voice](customize-business-voice.md)
-->

## <a name="emergency-services-location"></a>紧急服务位置

<table>
    <tr>
        <td>若要更改紧急地址，请单击“编辑”，然后输入新地址<b></b>。 系统将验证所提供的地址，确保它合规并且符合紧急响应服务的正确格式。 如果该地址有效，系统会将它分配给所有用户（将在下一步中为这些用户分配号码）。 如果你的员工分布在多个位置，在完成“入门”向导后，“自定义商务语音”主题将向你介绍如何添加并分配多个紧急地址。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

若要了解更多信息，请参阅[什么是紧急位置、地址和呼叫路由？](../what-are-emergency-locations-addresses-and-call-routing.md)

## <a name="company-phone-number"></a>公司电话号码

<table>
    <tr>
        <td>除设置新的本地电话号码以外，还可以选择购买免付费号码，或将现有号码移植到 Microsoft 365。 如果选择设置免付费号码，必须购买通话套餐。 若要将号码移植到 Microsoft 365，在向导完成后，可选择在 [Teams 管理中心](https://admin.teams.microsoft.com)执行此操作。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 如果选择将现有的电话号码移植到 Microsoft 365，向导仍然会显示临时电话号码。 这是正常的。 完成向导并完成移植过程后，你的电话号码将替代临时电话号码。

## <a name="assigning-licenses-to-users"></a>将许可证分配给用户

<table>
    <tr>
        <td>选择要呼叫或接听 Teams 外部电话（例如呼叫供应商）的组织人员。 可选择的人数最多可为你可以提供的可用商务语音许可证数。 如果需要选择更多人数，可在完成向导后购买额外的许可证。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 若要为单个用户将现有的电话号码移植到 Microsoft 365，可在完成向导后执行此操作。 完成移植过程后，移植的电话号码将替代向导选择的临时电话号码。

## <a name="incoming-call-greeting"></a>传入呼叫问候语

<table>
    <tr>
        <td>可以上传多达 5 MB 的声音文件（MP3 或 WAV）来用作问候语。也可以输入自己的问候语，Microsoft 365 将使用文本到语音转换向呼叫方播放它。 呼叫方呼叫你的公司电话号码时，将首先听到问候语。 可能需要将字词拼错或使用音标拼写，以确保发音正确。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>呼叫菜单和转接

<table>
    <tr>
        <td>可以将所有呼叫转接到特定用户，也可以设置呼叫菜单供用户选择选项。 如果创建呼叫菜单，可以指定选项，使呼叫方可以通过在电话拨号键盘上按号码或通过语音命令读出选项进行选择。 每个菜单选项均可以转接到一位用户。 <br>
可以选择是上传声音文件（MP3 或 WAV，最高达 5MB ）向呼叫方提供指令，还是输入指令。 Microsoft 365 将使用文本到语音转换向呼叫方播放指令。 可能需要根据发音拼写字词，以确保发音正确。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

<table>
    <tr>
        <td> <p>在“概述”页上，“入门”向导采用已输入的所有内容，为你设置商务语音<b></b>。 可以查看将为用户分配哪些电话号码，查看呼叫菜单，听取你的问候语。 </p>
             <p>设置商务语音需要几分钟的时间。 可以单击“完成”，我们将继续在后台设置商务语音，也可以等待它完成<b></b>。 完成后，转到 <a href="https://admin.teams.microsoft.com" target="_blank">Teams 管理中心</a>中的“语音”，设置其他商务语音功能<b></b>。</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>