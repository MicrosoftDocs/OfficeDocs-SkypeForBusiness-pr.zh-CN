---
title: 使用“入门”向导设置商务语音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
- m365initiative-voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b084afa7730d849f221de1d297f07359d200c79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102828"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>使用“入门”向导设置商务语音

> [!IMPORTANT]
> 本文中的信息仅适用于 **包含** 通话套餐的商务语音。 含通话套餐的商业语音仅在所选国家和地区可用。 阅读本文前，请查看[商务语音的国家和地区可用性](country-region-availability.md)，查看你所在的国家或地区是否支持使用包含通话套餐的商务语音。
>
> 如果你的租户所在的国家或地区不支持含通话套餐的商务语音，请查看[从 Microsoft 经销商或合作伙伴处获取帮助](reseller-partner-support.md)。

Microsoft 365 商务语音“入门”向导可让你快速设置以在 Microsoft Teams 中拨打和接听电话。 如果是一家刚创立的小型企业，此向导可在几分钟内启动并运行电话号码、呼叫菜单、问候语等。 如果是已创建电话解决方案的大型企业，此向导可帮助设置试点，这样可以让一些用户先试用它，然后再面向所有人推出。 无论你的企业是哪种规模，都可以在完成向导后立刻开始使用商务语音！

启动向导前，建议先阅读本文。 当你做好运行此向导的准备后，请选择“[开始使用 Microsoft 365 商务语音](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice)”页面上的“**入门**”。 请使用创建订阅所用的帐户或作为全局管理员的其他帐户登录。

> [!IMPORTANT]
> 只有在用户的邮箱位于 Microsoft 365 中时，Microsoft Teams 和商务语音才可用。  不支持本地 Exchange Server 上的邮箱。
>
> 入门向导不支持 Skype for Business 混合部署。 如果你有 Skype for Business 混合部署，并且想要设置商务语音，请检查[在组织中设置电话系统](../setting-up-your-phone-system.md)。

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

如果你不想立即自定义任何内容，那就完成了！ 你可以立即开始使用商务语音。

## <a name="emergency-services-location"></a>紧急服务位置

<table>
    <tr>
        <td>若要更改紧急地址，请单击“<b>编辑</b>”，然后输入新地址。 系统将验证所提供的地址，确保它合规并且符合紧急响应服务的正确格式。 系统会将此地址分配给所有用户（将在下一步中为这些用户分配号码）。 如果你的员工分布在多个位置，请参阅<a href="./customize-business-voice.md">商务语音设计自定义</a>，以便在准备好“入门”向导后添加和分配更多紧急地址。</td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400" alt="wizard choose number"></td></tr>
</table>

有关详细信息，请参阅[什么是紧急位置、地址和呼叫路由？](../what-are-emergency-locations-addresses-and-call-routing.md)

## <a name="company-phone-number"></a>公司电话号码

<table>
    <tr>
        <td>除新的本地电话号码以外，还可以购买免付费号码，或将现有号码移植到 Microsoft 365。 若要设置免费电话号码，需购买通讯信用额度。 若要将一个或多个号码移植到 Microsoft 365，请在向导完成后，转到 <a href="https://admin.teams.microsoft.com">Teams 管理中心</a>。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400" alt="choose number">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 如果将现有的电话号码移植到 Microsoft 365，向导仍然会显示临时电话号码。 这是正常情况。 完成向导和移植过程后，预先存在的号码将替代临时电话号码。

## <a name="user-licenses"></a>用户许可证

<table>
    <tr>
        <td>若要分配用户许可证，请选择要呼叫或接听 Teams 外部电话（例如呼叫供应商）的组织人员。 你只能分配可供使用的商务语音许可证数量。 如果需要选择更多许可证，可在完成向导后购买额外的许可证。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400" alt="get numbers">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 向导完成后，可将现有的电话号码移植到 Microsoft 365。 完成移植过程后，移植的电话号码将替代向导提供的临时电话号码。

## <a name="incoming-call-greeting"></a>传入呼叫问候语

<table>
    <tr>
        <td>可以上传高达 5 MB 的声音文件（MP3 或 WAV）来用作呼叫问候语，也可以输入自己的问候语，Microsoft 365 将使用文本到语音转换向呼叫方播放它。 呼叫方呼叫你的公司电话号码时，将首先听到问候语。 对于文本到语音转换，可能需要使用音标拼写来确保发音正确。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400" alt="greeting">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>呼叫菜单和转接

<table>
    <tr>
        <td>可以将所有呼叫转接到特定用户，也可以设置菜单供呼叫方选择选项。 如果创建呼叫菜单，则可以指定选项，使呼叫方可以通过语音或通过按下电话键盘上的数字来进行选择。 每个菜单选项都可以将用户转接到特定用户。<br><br>
        你可以上传高达 5 MB 的声音文件（MP3 或 WAV），以便向呼叫方提供指令，也可以输入指令。 Microsoft 365 将使用文本到语音转换向呼叫方播放这些指令。 可能需要根据发音拼写字词，以确保发音正确。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400" alt="call forwarding">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 入门向导可帮助你设置简单的呼叫菜单，让你快速启动并运行。 如果你有多个想要设置呼叫菜单的电话号码，或者如果想要设置更复杂的呼叫菜单（也称为自动助理），请在完成该向导后参阅[设置云自动助理](./create-a-phone-system-auto-attendant-smb.md)。

<table>
    <tr>
        <td> <p>“入门”向导可获取你输入的信息并设置商务语音。 在“<b>概述</b>”页面上，可以查看将为用户分配哪些电话号码，查看呼叫菜单，听取你的问候语。</p>
             <p>设置需要几分钟时间。 如果你选择“<b>完成</b>”，我们将继续在后台设置商务语音。 或者只是等到设置完成。 完成后，转到 <a href="https://admin.teams.microsoft.com" target="_blank">Teams 管理中心</a>中的“语音”，设置其他商务语音功能<b></b>。</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400" alt="finish page">
        </td>
    </tr>
</table>