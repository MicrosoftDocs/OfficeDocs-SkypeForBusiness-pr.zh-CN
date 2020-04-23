---
title: 设置云自动助理
ms.author: kenwith
author: kenwith
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 了解如何为 Microsoft 团队设置和测试云自动助理。
ms.openlocfilehash: dee263c08751f21e1fde19965d23595d5da27e39
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43788974"
---
# <a name="set-up-a-cloud-auto-attendant"></a>设置云自动助理

自动助理允许用户呼叫你的组织，并导航菜单系统以与右部门通话、呼叫队列、人员或操作员。 你可以通过 Microsoft 团队管理中心或通过 Powershell 为你的组织创建自动助理。 若要创建自动助理，请在左侧导航中转到 "**语音**"，然后选择 "**自动助理** > **新增**"。

如果想要了解有关自动助理的详细信息，请参阅[什么是云自动助理？](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> 本文适用于 Microsoft 团队和 Skype for business Online。

电话号码不会直接分配给自动助理，而是分配给与自动助理相关联的[资源帐户](manage-resource-accounts.md)。

自动助理实现通常涉及多个自动助理。 *第一级*自动助理通常有一个分配有电话号码的资源帐户。 嵌套的自动助理用作第*一级*自动助理作为呼叫连接的二级菜单。 将电话号码分配给其资源帐户时，不需要*嵌套*的自动助理。

## <a name="step-1--get-started"></a>步骤 1-入门

- 必须具有自动助理才能拥有关联的资源帐户。 有关资源帐户和所需的所有许可证的详细信息，请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> 要将呼叫重定向到使用电话系统许可证的联机用户的操作员或菜单选项，您需要为企业语音启用它们。 请参阅[分配 Skype For business 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。 你还可以使用 Windows PowerShell。 例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-auto-attendants"></a>步骤 2-创建自动助理

> [!IMPORTANT]
> 每个自动助理都必须具有关联的[资源帐户](manage-resource-accounts.md)。 必须先创建资源帐户，然后才能将其关联到自动助理。

### <a name="with-the-microsoft-teams-admin-center"></a>Microsoft 团队管理中心

在 " **Microsoft 团队管理中心**" 中，单击 "**语音** > **自动助理**"，然后单击 " **+ 添加**"：

#### <a name="general-info-page"></a>常规信息页面

!["我的自动助理" 页面的屏幕截图](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![数字1的图标，上一个屏幕截图](media/teamscallout1.png)
**名称**中的标注输入自动助理的显示名称。 此名称为必填字段，最多可以包含 64 个字符，其中包括空格。 此处指定的**名称**列在 "**自动助理**" 选项卡上的列中。

<a name="phonenumber"> </a>

* * *

![数字2的图标，上一个屏幕截图](media/teamscallout2.png)
 <a name="operator"> </a> 
**运算符**中的标注这是可选的（但建议使用）。 你可以将 "**操作员**" 选项设置为允许呼叫者跳出菜单，并向指定的人讲话。

默认情况下，0键分配给操作员。

如果您设置了一个操作员，请在 "**调用流**" 页面上的 "**编辑菜单选项**" 中告诉他们有关该选项的信息。 如果你在自动助理上设置了操作员，则在**呼叫者将听到**box 或将音频文件更改为包含此选项的情况下，输入相应的提示文本。 例如，"如需接线员，请按零"。

可通过多种方法设置操作员：

- **No 运算符**禁用 "operator" 和 "按 0" 选项。 这是当前默认值。
- **您的组织中的人员**为 Office 365 中的企业语音或分配的呼叫计划分配了电话系统许可证的人员。 您也可以对其进行设置，以便呼叫者发送到语音邮件。 若要将呼叫者发送到语音邮件，请选择**您的组织中的人员**，并将该帐户的设置设置为直接将呼叫发送到语音邮件。

     > [!Note]
     > **组织中的人员**可以是联机用户，也可以是使用 Skype For business 服务器内部托管的用户。

- **语音应用** 选择链接到已创建的自动助理或通话队列的资源帐户的名称。 请求操作员的调用方将被重定向。  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<a name="timezone"> </a>

![数字3的图标（上一个屏幕截图](media/teamscallout3.png) **时区**中的标注）您需要为自动助理设置时区。 该设置可以与为你的组织列出的主地址或不同时区的主地址的时区相同。 每个自动助理都可以具有不同的时区。 为自动助理设置的 "营业时间" 还使用 "时区"。 请确保设置正确的时区以避免工作时间差异，因为并非所有地区都有夏时制。 

* * *

![数字4的图标，上一个屏幕截图](media/teamscallout4.png)
 <a name="language"> </a> 
**语言**中的标注选择要用于自动助理的语言。 自动助理将该语言与呼叫者配合使用，并以这种语言播放所有系统提示。

 * * *

![数字5的图标，如果选择此选项，则上](media/teamscallout5.png)
一个屏幕截图中的标注将**启用语音输入**语音识别。 呼叫者可以使用[您设置的语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中的语音输入。 如果您希望仅让用户使用其电话键盘进行选择，您可以将语音识别设置为 "**关闭**"。

* * *  

完成选择后，单击 "**下一步**"。

#### <a name="call-flow"></a>通话流

<a name="greetingsandrouting"> </a>

> [!TIP]
> 您可以选择设置自定义的工作时间计划，并在工作时间内和之后使用不同的通话流行为。 若要设置自定义日程安排，请设置[在下班后的可选通话流程](#call-flow-for-after-hours)。 默认情况下，自动助理使用营业时间通话流。

您可以设置自定义的问候语、提示和菜单，以便用户在到达您的自动助理时听到。

![屏幕截图：呼叫处理页面问候语部分](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

**第一条播放问候语**问候语是可选的，可以设置为 "**无问候语**"、"**播放音频文件**" 或 "**键入问候语**"。

> [!NOTE]
> 对于第一级别的自动助理，问候语非常有用。 嵌套的自动助理通常不需要问候语。

![数字1的图标，上一屏幕截图](media/teamscallout1.png)中的标注如果选择 "**无问候语**"，则呼叫者在您稍后选择的其中一个操作处理之前，不会听到消息或问候语。 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

![数字2的图标，上一个屏幕截图](media/teamscallout2.png)中的标注如果选择 "**播放音频文件**"，则可以使用 "**上传文件**" 按钮上载另存为音频的录制问候语消息。WAV，。MP3 或。WMA 格式。 录制内容不能大于 5 MB。

![数字3的图标，上一个屏幕截图](media/teamscallout3.png)中的标注**键入问候消息**如果选择此选项，请在提供的字段中输入希望系统读取的文本（最多1000个字符）。 例如，输入 "欢迎使用 Contoso。 您的呼叫对我们非常重要。" 输出由文本到语音软件创建。

* * *

您可以从 "**发送呼叫**" 部分中选择 "呼叫" 下的 "呼叫" 旁边的内容。 设置为 "**断开连接**"、"**重定向呼叫**" 或 "**播放菜单" 选项**。

如果您选择 "**断开连接**"，则呼叫者在问候语播放后将断开连接。 

<a name="redirectcalls"> </a>

![数字4的图标，上一个屏幕截图](media/teamscallout4.png)中的标注**重定向呼叫**会将呼叫者发送到所选目的地，而无需选择 "从选项"。 可能的设置包括：

  - **组织中的人员**您选择的帐户必须具有为企业语音启用的电话系统许可证或在 Office 365 中分配了呼叫计划。 您可以对其进行设置，以便呼叫者可以发送到语音邮件：选择**组织中的人员**，并将该帐户设置为将呼叫直接转发到语音邮件。

  > [!Note]
  > **组织中的人员**可以是联机用户，也可以是使用 Skype For business 服务器内部托管的用户。

  - **语音应用**选择已设置的自动助理或呼叫队列。 按与服务关联的资源帐户的名称搜索自动助理或呼叫队列。
  - **语音邮件**选择包含组织中需要访问此自动助理接收的语音邮件的用户的 Office 365 组。 语音邮件将发送到您指定的 Office 365 组。 若要访问语音邮件，组成员可以通过导航到 Outlook 中的组来打开它们。

      切换**到** **"打开"** 以支持语音语音语音消息。

 * * *

![屏幕截图： "调用处理页面操作" 部分](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

![数字1的图标，当你选择 "**播放菜单**"](media/teamscallout1.png)选项时，上一个屏幕截图中的标注，你可以选择是使用音频文件，还是输入将呈现为文本到语音的文本，以向调用方提供拨号键盘菜单选项。 选择此项，而不是 "**重定向**" 或 "**断开连接**" 选项。


![数字2的图标，上一屏幕截图](media/teamscallout2.png)中的标注**播放音频文件**，你可以为呼叫者设置提示和选项以供呼叫者选择。 
- 如果选择 "**播放音频文件**"，你可以使用 "**上传文件**" 按钮上载另存为音频的录制问候语消息。WAV，。MP3 或。WMA 格式。 录制内容不能大于 5 MB。

- **键入问候消息**如果选择此选项，请在提供的字段中输入希望系统读取的文本（最多1000个字符）。 例如，输入 "欢迎使用 Contoso。 您的呼叫对我们非常重要。" 输出由文本到语音软件创建。

**设置菜单选项**可以在此对话框中添加或删除电话键盘或语音命令。 若要删除菜单选项，请删除语音命令条目，然后将 "**重定向**" 设置为 "返回" 以**选择**。

> [!TIP]
> 当删除选项时，更新菜单提示文本或重新录制音频提示。 为呼叫者播放的菜单提示不会自动更新。  
>
> 可以按任意顺序添加和删除任何菜单选项，并且键映射不必是连续的。 例如，可以创建一个映射到选项的键为0、1和3的菜单，而不使用键2。

> [!NOTE]
> 键\* （重复）和\# （后退）由系统保留，无法重新分配。 如果启用语音识别，按 * 将与 "重复" 对应，并且 # 将与 "后退" 语音命令对应。

![数字3的图标，上一个屏幕截图](media/teamscallout3.png)中的标注若要设置菜单选项，请单击 "按 **+ 分配拨号键**"，然后输入以下选项的信息：

![数字4的图标，上一个屏幕截图](media/teamscallout4.png)的 "**语音命令**" 列中的标注长度最多可为64个字符，并且可以包含多个词语，如 "客户服务" 或 "操作和共线"。   如果启用语音识别，将自动识别名称，并且呼叫者可以按3、说 "三" 或说出 "客户服务" 以选择映射到键3的选项。 此文本还会由用于服务确认提示的文本（如 "将你的呼叫转移到操作员"）呈现为语音。

![数字5的图标，上一个屏幕截图](media/teamscallout5.png)中的标注。如果按下相应的键，或者使用语音识别选择选项，则调用将转到该选项集的 "**重定向到**" 选项集。 可以将呼叫发送至：

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- **运算符**如果已设置操作员，则该选项将自动映射到 key 0，但也可以删除或重新分配给其他密钥。 选择此选项的呼叫者将被发送到指定的操作员。 如果运算符未设置为任何键，则语音命令 "Operator" 也会被禁用。 
- **组织中的人员**可以是联机用户，也可以是使用 Skype For business 服务器内部托管的用户。 用户必须具有在 Office 365 中启用企业语音或已分配呼叫计划的电话系统许可证。 在 "**按名称搜索**" 字段中搜索人员。

- **语音应用**选择已设置的自动助理或呼叫队列。 按与应用程序关联的资源帐户的名称搜索自动助理或呼叫队列。

- **语音邮件**选择包含组织中需要访问此自动助理接收的语音邮件的用户的 Office 365 组。 语音邮件将发送到您指定的 Office 365 组。 若要访问语音邮件，组成员可以通过导航到 Outlook 中的组来打开它们。

    切换**到** **"打开"** 以支持语音语音语音消息。

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

![数字6的图标（上一个屏幕截图](media/teamscallout6.png)  **目录**中的标注）在此部分中搜索，您可以启用 "**按姓名拨号**" 和 "自动助理的**分机**"。 可以在 "可选拨号作用域" 页面设置这些服务中和不包含的人员。 默认情况下，目录搜索设置为 "**无**"。

**按名称拨号**如果启用此选项，则呼叫者可以使用 "**按名称拨号**" 搜索组织中的人员。 他们说出用户的姓名和语音识别将其与用户相匹配。 可以在 "可选拨号作用域" 页面设置这些服务中和不包含的人员。 任何带电话系统许可证的在线用户或使用 Skype for Business Server 本地托管的任何用户都是符合条件的用户，可通过 "按名称拨号" 找到。


**通过分机号码拨号**如果启用此选项，则呼叫者可以通过输入其电话分机连接到您的组织中的用户。 你可以在 "可选拨号作用域" 页面中选择列为 "可供**拨号**" 或 "不可用" 的用户。 任何具有电话系统许可证的在线用户或使用 Skype for Business Server 本地托管的任何用户都是符合条件的用户，并且可以通过 "通过分机拨入" 找到。

> [!IMPORTANT]
> 请注意以下事项：
>- 希望可供拨号使用的用户需要将扩展指定为在 Active Directory 或 Azure Active Directory [Microsoft 365 管理中心](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users)中定义的以下某个电话属性的一部分。
>    - HomePhone
>    - 手机/MobilePhone
>    - TelephoneNumber/电话号码
>    - OtherTelephone
>- 在 "用户电话号码" 字段中输入扩展名所需的格式是`+<phonenumber>;ext=<extension>` " `x<extension>`或"。
>- 当前不支持在团队管理中心中分配扩展。 你必须使用[MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) PowerShell 命令或 Microsoft 365 管理中心。
>- 在对 AAD 电话号码和 MobilePhone 属性的更改可用之前，最多可能需要12小时。
>- 请不要为用户的 LineUri 定义扩展名。 目前不支持这种情况。
>- 自动助理可配置为通过名称拨号或通过分机号码拨号，但不能同时进行这两种操作。

> [!NOTE]
> 如果想要同时使用 "**按姓名**拨号" 和 "**按分机号码拨号**" 功能，您可以创建主自动助理（**按名称进行拨号**），如果用户知道用户的扩展名，则会提示呼叫者选择菜单选项，并将该选项设置为将呼叫转移到启用了 "通过分机拨号" 的自动助理。

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

完成选择后，如果要更改高级设置，可以单击 "**下一步**"，如果要使用以下内容的默认设置，请单击 "**提交**"：
- 下班后的通话流程
- 假期的通话流程
- 拨号作用域
- 资源帐户

由于自动助理需要拥有资源帐户，因此你可以选择继续到 "**资源帐户**" 页面并关联已配置的资源帐户，或者创建资源帐户并将其与自动助理相关联，如 "[管理 Microsoft 团队中的资源帐户](manage-resource-accounts.md)" 中所述。 您将无法使用此自动助理，直到它已与资源帐户相关联。 若要执行此操作，请单击屏幕底部的 "**下一步**" 按钮，然后单击左侧导航中的 "**资源帐户**" 以直接转到 "资源帐户" 页面，并将自动助理与资源帐户相关联。

#### <a name="advanced-settings-optional"></a>高级设置（可选）

你可以配置其他四个屏幕，也可以在你选择的情况中保留默认值。

##### <a name="call-flow-for-after-hours"></a>下班后的通话流程

默认情况下，自动助理的工作时间设置为上午9点，星期一到星期五  <!--24/7-->，并且将禁用*小时通话后*的呼叫流选项，因为所有小时都被视为 "*营业时间*"。 选择 "**设置自定义工作时间**" 选项时，"**时间段后的呼叫流程**" 页面将配置自动助理在下班后使用的呼叫处理规则。 可用的选项是相同的，区别在于为不同的菜单和行为设置计划的能力。

自动助理的系统可能仅需要设置为第一级自动助理的小时调用处理行为。 嵌套的自动助理甚至可能无法由第一级自动助理调用，但系统可以为其使用的每个自动助理定义小时的行为。

最初，营业时间定义为从 12:00 am 开始，到星期日到星期六的 12:00 pm 结束。 工作时间后的所有小时数均被视为*时间*。


![下班后通话流设置的屏幕截图](media/aa-afterhour.png)
 * * *

![数字1（前一个屏幕截图](media/teamscallout1.png)中的标注）的图标，您可以单击 "**选择 24/7** " 以使该自动助理的所有工时为工作时间。

![数字2的图标，上一个屏幕截图](media/teamscallout2.png)中的标注选择 "**重置为默认值**" 选项以还原计划中的所有更改，并返回到星期五上午 9:00 am 到 5:00 pm 的默认工作时间定义为 am。

![数字3的图标，上一个屏幕截图](media/teamscallout3.png)中的标注选择 "**清除所有小时**" 以完全清除该计划。 不建议选择此项并保留未设置的小时，因此，仅当你想要完全恢复你的工作时间时，请使用此选项。

![数字4的图标，第4个屏幕截图](media/teamscallout4.png)![图标中的标注，第一个屏幕截图](media/teamscallout5.png)中的标注自定义一周中某一天的开始或结束时间，单击要重置的 "**开始**" 或 "结束" 时间，然后从显示的列表中选择新时间。 **End at**   该列表允许你按15分钟的间隔选择营业时间，你在此处选择的工作时间基于你在 "**常规信息**" 页面上设置的时区。

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

![数字6的图标，上一屏幕截图](media/teamscallout6.png)中的标注设置工间休息（例如，午餐休息时间），选择 "为一周的某一天**添加新时间**" 以创建新的表行，然后选择 "新开始时间" 和 "结束时间"。 您可以在营业时间内设置多个工间休息。

小时后可用的[通话流](#call-flow)选项与工作时间内可用的选项相同。 在 "信息输入" 页面上向下滚动以设置时间呼叫流选项。

* * *

完成选择后，单击 "**下一步**"。 您也可以单击左侧导航中的 "**资源帐户**" 直接转到 "资源帐户" 页面，并将自动助理与资源帐户相关联。

##### <a name="call-flow-during-holidays"></a>假期期间的通话流

<a name="holidaygreetings"> </a>

可以为每个自动助理添加最多 20 个计划假日。 您的组织可能已经定义了假日，如在[Microsoft 团队中设置假日](set-up-holidays-in-teams.md)中所述。 如果不是，您将看到以下屏幕： 

![屏幕截图：未配置任何假日](media/aa-no-holidays.png)

![数字1的图标，以前的屏幕截图](media/teamscallout1.png)中的标注若要为自动助理上的假日设置自定义调用流，请单击 " **+ 添加**" "查看**新假日呼叫流程**" 屏幕。
> [!TIP]
> 若要创建假日，您可以在**组织范围设置** > 的**假日**内转到屏幕。  



![屏幕截图：添加呼叫处理程序](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

![数字1的图标，上一个屏幕截图](media/teamscallout1.png)中的标注为新的调用流输入**名称**。

![数字2的图标，上一个屏幕截图](media/teamscallout2.png)中的标注如果你已创建了假日，则会在 "**假日**" 下拉菜单中看到它们，并且可以选择它们。 你可能会看到一个未使用的选项，你可以根据需要进行编辑。 如果不是，请单击下拉列表底部的 "**添加**" 以创建新的假日。  有关用于创建假日的步骤，请参阅[在 Microsoft 团队中设置假日](set-up-holidays-in-teams.md)。 

假日通话流名称最长可以为64个字符，并且对于组织必须是唯一的。 例如，在同一个组织中，您不能有两个假期通话流，名为 "感恩节"。 您的自动助理可以为您设置的每个假日都有一个呼叫流，但您可能希望具有计划的一组通用的行为，而不是自定义的问候语。

![数字3的图标，上一个屏幕截图](media/teamscallout3.png)中的标注。可用于假日呼叫流的[问候语](#call-flow)选项与工作时间内可用的选项相同。 在播放问候语后执行的**操作**也类似，不同之处在于仅有的可用操作是 "**断开连接** **" 或 "重**定向到" 选项，并且当选择 "**重定向到**" 选项时，操作员不是可用选项之一。 您不能设置特定于节日流的菜单。

> [!NOTE]
> 默认情况下，节假日期间收到的所有通话均设置为在问候语后**断开**（如果有），因此，如果需要自定义行为，则必须指定重定向。

!["假日" 页面期间的通话流的屏幕截图](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

单击 "保存" 以完成假日呼叫流程的创建。 创建假期呼叫流程后，它将显示在 "假日" 屏幕的 "**呼叫流程" 中**。

单击 "设置拨号作用域"，**返回**到 **"在小时**后进行更改"，然后**提交**（如果已完成）。 您也可以单击左侧导航中的 "**资源帐户**" 直接转到 "资源帐户" 页面，并将自动助理与资源帐户相关联。

#### <a name="dial-scope"></a>拨号作用域

<a name="dialscope"> </a>

![显示 "拨号作用域" 页面的屏幕截图](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

在此页面上，您可以设置在您的目录中列出的人员，并可在某人呼叫您的组织时使用 "按名称拨号"。 在以前的屏幕中，按名称拨号将默认设置为 "**关闭**"。 如果之前选择了 "**按分机拨号**"，则所有具有分机的用户都将可用。

![数字 1](media/teamscallout1.png)的图标，上一个屏幕截图中的标注**包括**本部分中的选项是**所有联机用户**或**自定义用户组**

如果选择 "**所有联机用户**"，则所有符合条件的用户都将包含在目录搜索中。

**自定义用户组**此选项允许你搜索并选择已在你的组织中创建的 Office 365 组、通讯组列表或安全组。 如果用户在所选的 Office 365 组、通讯组列表或安全组中，并且它们是使用**电话系统许可证的在线用户**，或者是使用 Skype For business 服务器内部托管的，则会将用户添加到目录中。 你可以将多个 Microsoft 365 组、通讯组列表和安全组添加到目录中。

<a name="dialscope"> </a>

在此页面上，你可以设置你的组织中的哪些用户将在你的目录中列出，并且当呼叫加入你的组织的人员可以使用名称进行拨号。

![数字2的图标，上一个屏幕截图](media/teamscallout2.png)中的标注将**排除**本部分中的选项，使您可以从组织的目录中排除特定用户或用户组。

如果您选择 "**无**"，则所有符合条件的用户都将包含在目录搜索中。

**自定义用户组**你可以搜索在你的组织中创建的 Office 365 组、通讯组列表或安全组。 将从目录搜索中排除该组中的用户。 你可以添加多个 Microsoft 365 组、通讯组列表和安全组。


如果启用 "按名称拨号" 时保留默认设置，则所有符合条件的用户都将包含在目录搜索中。

> [!NOTE]
> 新用户可能需要长达36小时才能在目录中列出其名称。 当有人通过语音识别按名称使用 "拨号" 时，新帐户可能不能用于此功能。

输入所有必填字段并设置呼叫处理菜单和选项后，单击 "**下一步**" 以继续关联资源帐户。

#### <a name="resource-accounts"></a>资源帐户

所有自动助理都必须具有关联的资源帐户。  第一级自动助理绝对需要至少一个具有关联服务号码的资源帐户。 如果需要，您可以将多个资源帐户分配给自动助理，每个帐户都有一个单独的服务编号。

如果尚未将资源帐户配置为自动助理，您将看到以下屏幕： 

![屏幕截图：可选的资源帐户管理](media/aa-ra-optional.png) 

![数字1的图标，上一个屏幕截图](media/teamscallout1.png)中的标注要将一个或多个现有和未分配的资源帐户添加到自动助理，请单击 "**添加帐户**" 和 "搜索"，然后从提供的对话框中选择它们。

![新的 "助理摘要" 视图的屏幕截图](media/aa-assigned.png)

![数字1的图标，上一个屏幕截图](media/teamscallout1.png)中的标注若要添加其他资源帐户，请单击 " **+ 添加帐户**"。

![数字2的图标，上一个屏幕截图中的标注](media/teamscallout2.png) 分配给此自动助理的资源帐户或帐户显示在列表中。

## <a name="edit-auto-attendants"></a>编辑自动助理

保存新的自动助理后，它将列在 "**自动助理**" 页面上。 该页面允许你快速查看已设置的某些选项，包括名称、关联的资源帐户、语言和已分配的操作员。

![助理列表的屏幕截图](media/aa-list.png)

如果要更改自动助理设置，请选择 "自动助理"，然后在 "操作" 窗格中单击 "**编辑**"。

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a>使用 Powershell 创建自动助理

您也可以使用 PowerShell 创建和设置自动助理。 下面是管理自动助理所需的 cmdlet：

- [新-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
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

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，您可以从单个管理点管理 Office 365 和 Microsoft 团队，从而简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [为什么要使用 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如为多个用户同时进行设置更改。 通过以下主题了解这些优势：

  - [通过 Office 365 PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相关主题

[以下是 Office 365 中的电话系统功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[什么是云自动助理？](what-are-phone-system-auto-attendants.md)

[小型企业版示例-设置自动助理](/microsoftteams/tutorial-org-aa)  
