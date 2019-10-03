---
title: 设置云自动助理
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解如何为 Microsoft 团队设置和测试云自动助理。
ms.openlocfilehash: 0cac6b1bb7d19e91e4042bcb0673f6c677e77d2e
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375705"
---
# <a name="set-up-a-cloud-auto-attendant"></a>设置云自动助理

自动助理允许与你的组织进行通话的人员，并导航到相应的菜单系统以将其转到相应的部门、呼叫队列、人员或运营商。 您可以使用 Microsoft 团队管理中心为您的组织创建自动助理。 若要创建新的自动助理，请在左侧导航中转到 "**语音**"，然后选择 "**自动助理** > **新增**"。

如果想要了解有关自动助理的详细信息，请参阅[什么是云自动助理？](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> 本文适用于 Microsoft 团队和 Skype for business Online。

## <a name="step-1--get-started"></a>步骤 1-入门

- 必须具有自动助理才能拥有关联的资源帐户。 有关资源帐户和所需的所有许可证的详细信息，请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。

> [!TIP]
> 要将呼叫重定向到使用**电话系统**许可证的联机用户的操作员或菜单选项，您需要为企业语音启用它们。 请参阅[分配 Skype For business 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。 你还可以使用 Windows PowerShell。 例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-a-new-auto-attendant"></a>步骤 2-创建新的自动助理

> [!IMPORTANT]
> 每个自动助理都必须具有关联的[资源帐户](manage-resource-accounts.md)。 必须先创建资源帐户，然后才能将其关联到自动助理。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

在 " **Microsoft 团队管理中心**" 中，单击 "**语音** > **自动助理**"，然后单击 " **+ 新建**"：

#### <a name="general-info-page"></a>常规信息页面

!["我的自动助理" 页面的屏幕截图](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

**名称**输入自动助理的描述性显示名称。 此名称为必填字段，最多可以包含 64 个字符，其中包括空格。 它列在 "**自动助理**" 选项卡上的 "**名称**" 列中。

* * *

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<a name="phonenumber"> </a>

**资源帐户**单击此按钮可选择一个或多个资源帐户以连接到新的自动助理。 所有自动助理都必须具有关联的资源帐户。 资源帐户可以有与帐户关联的电话号码，但不要求电话号码。 顶级自动助理通常有一个分配有电话号码的资源帐户，但嵌套的自动助理（用作第一级自动助理连接到的第2级菜单）可能没有分配给其资源帐户的电话号码。

* * *

![数字3的图标，引用上一个屏幕截图](media/sfbcallout3.png)
 <a name="timezone"> </a>中的标注

**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。 每个自动助理都可以具有不同的时区，并且基于您在此处选择的时区设置自动助理的 "营业时间" 设置。

* * *

![数字4的图标，引用上一个屏幕截图中的标注](media/sfbcallout4.png)

<a name="language"> </a>

**语言** 从列出的可用语言列表中选择自动助理使用的语言。 您在此处设置的语言是自动助理用于与呼叫此自动助理的用户进行交互的语言，并且所有系统提示均以这种语言播放。

* * *

![数字5的图标，引用上一个屏幕截图中的标注](media/sfbcallout5.png)

<a name="operator"> </a>

**运算符**这是可选的，但你可以设置 "**运算符**" 选项，以允许呼叫者跳出菜单并向某个人讲话。

默认情况下，0键分配给操作员。

如果您设置了一个操作员，您还需要在 "**工作时间" 通话处理**页面上的 "**编辑" 菜单选项**中告诉他们有关该选项的信息。 如果您在自动助理上设置了操作员，则需要在**呼叫者将听到**框中输入相应提示文本，或将音频文件更改为包含此选项。 例如，"如需接线员，请按零"。

可通过多种方法设置操作员：

- 拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。

     > [!Note]
     > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。

- **语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。
- 您可以对其进行设置，以便呼叫者将发送到语音邮件。 若要执行此操作，请选择**您的公司中的人员**，并将此人的来电设置为直接转发到语音邮件。

* * *

![数字6的图标，引用上一个屏幕截图中的标注](media/sfbcallout6.png)

**启用语音输入**如果选中此选项，则可以使用语音识别。 拨入的人员可以使用[您设置的语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的语音输入。 如果您希望仅让用户使用其电话键盘，则可以通过将语音识别设置为 "关闭" 来禁用语音识别。

* * *

完成选择后，单击 "**下一步**"。

#### <a name="business-hours-page"></a>营业时间页面

默认情况下，营业时间设置为从星期一到星期五的 9:00 am 到 5:00 pm。 营业时间内未包括的所有小时都将在营业时间后考虑。 您可以单击 "**选择 24/7** " 以完成所有工时的工作时间。 除非选择 "**选择 24/7** " 选项，否则将使用 "**在时间后的时间呼叫设置**" 页面来配置自动助理的工作时间后的呼叫处理规则。

!["营业时间" 页面的屏幕截图](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

默认情况下，"营业时间" 设置为 "星期一到星期五，上午 9:00-5:00 pm"。 选择 "**清除所有小时**" 选项以取消选择计划中的所有小时。 当您选择 "**重置为默认值**" 时，工作时间将重置为星期一到星期五（即 9:00 am-5:00 pm）。

* * *

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

若要更改工作时间，请突出显示要在日历中设置的营业时间。 日历允许你按30分钟的间隔选择营业时间，你在此处选择的工作时间基于你在 "**常规信息**" 页面上设置的时区。 要设置休息时间（如午餐时间），请取消选择或通过拖动取消选择某段时间。 您可以在营业时间内设置多个工间休息。

* * *

完成选择后，单击 "**下一步**"。

#### <a name="business-hours-call-settings"></a>营业时间通话设置

> [!TIP]
> 如果你使用自定义工作时间计划，你还需要在工作时间之后使用 "**下班后通话**" 页面设置呼叫处理页面，该页面将提供与**工作时间通话设置**相同的选项。

您可以设置问候语、提示和菜单，以便用户在工作时间内呼叫与组织的自动助理关联的电话号码时听到。

![工作时间呼叫处理页面问候语部分](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![屏幕截图的屏幕截图 "营业时间呼叫处理页面操作" 部分的屏幕截图](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<a name="greetingsandrouting"> </a>

**问候语**营业时间问候语是可选的，并且可以设置为 "**无问候语**"。 在这种情况下，在你选择的其中一个操作处理呼叫之前，呼叫者不会听到消息或问候语。 还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。
- **上载音频文件**如果选择此项，请录制问候语，然后上载音频文件（采用 .wav、mp3 或 .wma 格式）。
- **键入问候消息**如果选择此选项，请输入希望系统读取的文本（最多为1000个字符）。 例如，可能会输入"欢迎来到 Contoso 。 您的呼叫对我们非常重要。" 在 **呼叫者将听到** 框中。

* * *

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

你可以选择在营业时间内收到的通话所发生的情况。 你可以从以下操作中进行选择：

<a name="redirectcalls"> </a>

- **断开连接**如果您选中它，则在听到营业时间问候语后，拨入的人员将断开连接。
- **重定向呼叫** 这可用来将呼叫自动发送至：
  - **公司中**具有**电话系统**许可证的人员，可在 Office 365 中启用企业语音或分配的呼叫计划。 你可以通过此设置将呼叫者直接转到语音邮件。 若要执行此操作，请选择 "**公司中的人员**"，并将该用户设置为将呼叫直接转发到语音邮件。

    > [!Note]
    > **公司中的人员**可以是联机用户，也可以是使用 Skype For business server 2015 或 Lync Server 2013 的本地托管用户。

   - 另一个**自动助理**

   可以使用现有的自动助理来创建包含子菜单的第二级菜单选项。 These are called nested auto attendants. 若要将呼叫发送到嵌套的自动助理，请选择 "**公司" 中**的 "人员"，然后分配一个已具有关联的自动助理的资源帐户，或者在完成创建此自动助理后将与自动助理关联的帐户。

- "**播放" 菜单选项**也可用于设置要播放的提示。

* * *

![数字3的图标，引用上一个屏幕截图中的标注](media/sfbcallout3.png)

**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。 可以在 "设置呼叫者的**菜单导航**" 框中键入提示或录制音频文件，例如： "用于销售额"，说或按下或说出 "1"。 如需服务，请按或报 2。 如需客户支持，请按或报 3。 如需接线员，请按或报 0。 如需重听此菜单，请按星号键或报'重复'。 **键入问候消息**如果你选择此设置，则应输入希望系统读取的文本（最多为1000个字符）。 **上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。

* * *

![数字4的图标，引用上一个屏幕截图中的标注](media/sfbcallout4.png)

**菜单选项设置**可以添加或删除使用键盘上的键按钮的菜单选项。 若要添加菜单选项，请按 **+ 分配拨号键**。 相应的选项行如下所示。 若要删除菜单选项，只需单击小键盘控件上对应键的左侧，然后单击上面的 "删除" 图标。 将移除按键映射行。

> [!TIP]
> 添加到删除选项时，必须更新菜单提示文本或重新录制音频，因为它不会针对现有菜单提示自动完成。  
>
>可以按任意顺序添加和删除任何菜单选项，并且键映射不必是连续的。 例如，可以创建一个映射到选项的键为0、1和3的菜单，而不使用键2。

> [!NOTE]
> 键\* （重复）和\# （后退）由系统保留，无法重新分配。 如果启用语音识别，按 * 将与 "重复" 对应，并且 # 将与 "后退" 语音命令对应。

若要设置菜单选项，请在选择拨号键后，您需要：

- 输入选项的 "**语音" 命令**。 此长度最多可包含64个字符，并且可以包含多个词语，如 "客户服务" 或 "操作和用户"。 如果启用语音识别，将自动识别该名称，并且呼叫者可以按3、说 "三" 或说出 "客户服务" 以选择映射到键3的选项。
- 如果按下相应的键，或者使用语音识别选中该选项，请选择发送呼叫的位置。 可以将呼叫发送至：

  - **运算符**如果已设置操作员，则它会自动映射到 key 0，但也可以将其删除或重新分配给其他密钥。 If operator isn't set to any key, then the voice command "Operator" will be disabled too.
  - 拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。 你可以通过此设置将呼叫者直接转到语音邮件。 若要执行此操作，请选择**您的公司中的人员**，并将其呼叫直接转发到语音邮件。

    > [!Note]
    > **公司中的人员**可以是联机用户，也可以是使用 Skype For business Server 或 Lync server 2013 的本地托管用户。

  - 另一个**自动助理**

       可以使用现有的自动助理来创建包含子菜单的第二级菜单选项。 These are called nested auto attendants. 若要将呼叫发送到嵌套的自动助理，请选择 "**公司" 中**的 "人员"，然后分配一个已具有关联的自动助理的资源帐户，或者在完成创建此自动助理后将与自动助理关联的帐户。

        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.

    - **语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。

* * *

![数字5的图标，引用上一个屏幕截图中的标注](media/sfbcallout5.png)

**按名称拨号**如果选择此选项，将使使用目录搜索在你的组织中搜索人员的人员可以使用此选项。 在 **拨号范围** 页面上设置这些选项便可为“按名称拨号”选择哪些作为可选人列出或者哪些不作为可选人列出。 使用**电话系统**许可证的任何联机用户或任何使用 Skype For business 服务器或 Lync server 2013 的本地托管用户均可通过 "按名称拨号" 找到。

* * *

完成选择后，单击 "**下一步**"。

#### <a name="holiday-call-settings"></a>假期呼叫设置

<a name="holidaygreetings"> </a>

可以为每个自动助理添加最多 20 个计划假日。

> [!TIP]
> 您可以在**组织范围的设置** > **假日**处转到 "创建假日" 的屏幕，也可以创建新的调用处理程序的一部分。

!["假日呼叫设置" 页面的屏幕截图](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

如果您已经创建了其他自动助理，您可能会看到一个选项，您可以在此列表中使用或编辑所需内容。 如果不是，你将需要创建一个新的调用处理程序。

若要添加新的呼叫处理程序，请单击 " **+ 新建呼叫处理程序**"。

* * *

![显示添加新的调用处理程序的屏幕截图](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

在 "新建" 窗口中，在屏幕顶部输入新呼叫处理程序的名称。

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

如果你的假日名称已存在于 "**假日**" 下拉列表中，则可以使用它。 如果所需的假日名称尚不存在，请在下拉列表中选择 "**创建新假日**"，然后在出现的新屏幕中为新假日分配名称和日期。 准备就绪后，单击 "**保存**"。

假日名称可以包含最多 64 个字符，并且在同一自动助理中必须是唯一的。 例如，不能在同一自动助理中具有两个名为"感恩节"的假日。

![数字3的图标，引用上一个屏幕截图中的标注](media/sfbcallout3.png)

**问候语**问候语是可选的，可以设置为 "**无问候语**"。 在此情况下，在所选选项处理呼叫之前，呼叫者听不到消息或者问候语。 还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。

- **无问候语**当用户拨入自动助理电话号码时，将不会播放任何问候语。
- **上载音频文件**如果您选择此项，请录制假日问候语，然后上传音频文件（采用 .wav、mp3 或 .wma 格式）
- **键入问候消息**如果选择此选项，请输入希望系统读取的文本（最多为1000个字符）。 例如，可以输入"新年快乐！ 我们的办事处当前未营业。" 在 "**键入问候消息**" 框中。

![数字4的图标，引用上一个屏幕截图中的标注](media/sfbcallout4.png)

**操作**你可以选择在此节假日期间收到的通话所发生的情况。 可以从以下选项中进行选择：

- **断开连接** 呼叫者听到假日问候语以后被断开连接。
- **重定向呼叫** 这可用来将呼叫自动发送至：
  - 拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员 **。 你可以通过此设置将呼叫者直接转到语音邮件。 若要执行此操作，请选择**公司中的人员**，并将其设置为将呼叫直接转发到语音邮件。

    > [!Note]
    > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。

   - **语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。

    > [!Note]
    > 默认方式，将假日期间到达的所有呼叫设置为听到问候语（如果有）后断开连接，所以如果希望有不同的反应，则必须指定重定向。

<a name="dialscope"></a>
#### <a name="select-dial-scope-page"></a>"选择拨叫范围"页面

在此页面上，你可以设置你的组织中的哪些用户将在你的目录中列出，并且当呼叫加入你的组织的人员可以使用名称进行拨号。

![显示 "拨号作用域" 页面的屏幕截图](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![数字1的图标，在上一个屏幕截图](media/sfbcallout1.png)中使用 "**包括**" 选项引用标注，你有两个选项：

- **所有在线用户** 使用此选项可以将组织中的所有人包含在目录搜索中。 所有具有**电话系统**许可证的联机用户，以及使用 Office 365 中具有呼叫计划的 Skype For business 服务器或 Lync server 2013 的用户托管的用户。
- **自定义用户组**如果使用此选项，则可以搜索在你的组织中创建的 Office 365 组、通讯组列表或安全组，以及添加到此 Office 365 组、通讯组列表或安全组的人员，这些**用户是使用电话系统许可证**或使用 Skype For Business server 2015 或 Lync Server 2013 内部托管。 你可以添加多个 Office 365 组、通讯组列表和安全组。

* * *

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

使用 "**排除**" 选项，您有两个选项：

- **无** 使用此选项表示不会将任何在线用户从目录搜索中排除。
- **自定义用户组**如果使用此选项，则可以搜索在你的组织中创建的 Office 365 组、通讯组列表或安全组，并且添加到此 Office 365 组、通讯组列表或安全组的所有人员都将从目录搜索中排除。 你可以添加多个 Office 365 组、通讯组列表和安全组。

> [!NOTE]
> 当有人通过语音识别按名称使用 "拨号" 时，最多可能需要36小时才能让新用户在目录中列出其名称。

输入所有必填字段并设置呼叫处理菜单和选项后，单击 "**提交**"。

## <a name="editing-and-testing-auto-attendants"></a>编辑和测试自动助理

保存自动助理后，自动助理将在" **自动助理**"页面列出。 这将允许你快速查看已设置的一些选项，包括姓名、电话号码、语言和状态。

如果要更改自动助理，请选择 "自动助理"，然后在 "操作" 窗格中单击 "**编辑**"。

您还可以使用 "操作" 窗格中的 "**测试**" 按钮，快速将测试呼叫置于自动助理。

## <a name="auto-attendant-cmdlets"></a>自动助理 cmdlet

还可以使用 Windows PowerShell 来创建和设置自动助理。 下面是管理自动助理所需的 cmdlet：

- [新-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [新-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [新-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [新-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [新-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [Import-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [新-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，你可以使用单一的管理点管理 Office 365 和 Microsoft 团队，这样你有多个任务需要执行这些任务即可。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [为什么要使用 Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。 通过以下主题了解这些优势：

  - [通过 Office 365 PowerShell 管理 Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相关主题

[以下是 Office 365 中的电话系统功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[什么是云自动助理？](what-are-phone-system-auto-attendants.md)

[小型企业示例 - 设置自动助理](/microsoftteams/tutorial-org-aa)  
