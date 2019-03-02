---
title: 设置电话系统自动助理
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解如何设置和测试高效处理您的组织的呼叫的电话系统 (云 PBX) 自动助理。
ms.openlocfilehash: f055a6851610bc2071e1705a4b5739544c5d72bd
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353295"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>设置电话系统自动助理

自动助理让人们呼叫您的组织和导航菜单系统，以使其向右部门、 队列、 人员或运算符呼叫。 通过使用 Microsoft 团队管理中心，您可以为您的组织创建自动助理。 若要创建新的自动助理，在左侧导航窗格中，转到**语音**，然后选择**自动助理** > **添加新**。

如果您想要了解有关自动助理的详细信息，请参阅[电话系统自动助理是什么？](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> 本文同时适用于 Microsoft 团队和 Skype 业务 online。

## <a name="step-1---getting-started"></a>第 1 步 - 开始

- 您可以创建和设置在自动助理，如果将自动助理电话号码之前 (以及许多二级提示或不嵌套自动助理将需要一个电话号码) 您将需要获取或转移您现有的收费电话或免费电话服务号码. 获得收费电话或免费电话服务号码后，他们会显示在**Microsoft 团队管理中心** > **语音** > **电话号码**页。 若要获取服务号码，请参阅[Getting 服务电话号码](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)，或如果您希望进行传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。 **User (subscriber)** numbers can't be assigned to auto attendants. 如果您在美国以外，您无法使用的 Microsoft 团队管理中心获取服务号码;转[此处](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

    > [!CAUTION]
    > 若要获取并使用免费电话号码，则需要设置通信点数。 若要执行此操作，请参阅 [通信点数是什么？](what-are-communications-credits.md) 和 [为组织设置通信点数](set-up-communications-credits-for-your-organization.md) 。
  
- 企业版 E3 以及**电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低要求）。 已分配的**电话系统**用户许可证数量影响的可用于自动助理服务号码数。 取决于您的组织中分配的号码**电话系统**和**音频会议**许可证的自动助理可以具有的数字。 若要了解有关授权的详细信息转[此处](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

    > [!TIP]
    > 要重定向呼叫的运算符或联机用户与**电话系统**许可证的菜单选项，您将需要启用企业语音或分配给它们的调用计划在 Office 365 中。 请参阅[业务和 Microsoft 团队许可证分配 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 你还可以使用 Windows PowerShell。 例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2---create-a-new-auto-attendant"></a>第 2 步 - 创建新的自动助理

> [!IMPORTANT]
> 每个呼叫队列需要具有关联的[资源帐户](manage-resource-accounts.md)。 您必须首先，创建资源帐户，然后将其向自动助理相关联。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

在**Microsoft 团队管理中心**中，单击**语音** > **自动助理**，然后单击 **+ 新建**：

#### <a name="general-info-page"></a>一般信息页

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![第一](media/sfbcallout1.png)

**名称**输入自动助理的描述性的显示名称。 此名称为必填字段，最多可以包含 64 个字符，其中包括空格。 此名称将显示在" **自动助理**"选项卡的" **名称**"列中。

* * *

![第二](media/sfbcallout2.png)

**资源帐户**单击此按钮以选择要连接到您新建的自动助理的一个或多个资源帐户。 所有的自动助理都需要有关联的资源帐户。 资源帐户可以具有电话号码关联到帐户，但它也可能不。 顶级自动助理将肯定会有一个资源具有帐户分配的电话号码，但 （用作的第一个级别的自动助理连接到的级别 2 菜单） 辅助自动助理可能轻松不具有电话号码分配给其资源帐户。

* * *

![第三](media/sfbcallout3.png)

**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。每个自动助理可以有不同的时区，为自动助理设置的营业时间将根据你在此处选择的时区进行设置。

* * *

![第四](media/sfbcallout4.png)

**语言** 从列出的可用语言列表中选择自动助理使用的语言。 您在此处设置的语言的自动助理将使用与进行交互到此自动助理，呼叫中的人员并所有系统播放提示时在这种语言的语言。

* * *

![第五](media/sfbcallout5.png)

**接线员** 此为可选字段，无须为自动助理设置。 但是，您可以设置呼叫中能够页符拖出菜单以帮助他们人讲话的人员**运算符**选项。

键 0 自动分配给接线员。

如果您对此进行设置，还需要告知人员谁调用的这是在**营业呼叫处理**页中的**编辑菜单选项**可用选项。 如果您在自动助理上设置运算符，您需要在**呼叫者收听**框中输入相应的提示文本或更改您的音频文件，以包括此选项。 例如，"如需接线员，请按零"。

可以将以下项设置为接线员：

- 拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。

     > [!Note]
     > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010 。

- **呼叫队列**的设置。
- 你可以通过此设置将呼叫者直接转到语音邮件。 若要执行此操作，选择**您的公司的人员**并将此人的呼叫转接至语音邮件直接设置。

* * *

![第六](media/sfbcallout6.png)

**启用语音输入**语音识别时选择此选项才可用。 呼叫中的人员可以使用[语言设置](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中的语音输入。 通过设置其关闭如果您想要仅允许使用其电话小键盘的人员，您可以禁用语音识别。

* * *

在完成时与您的选择，单击**next**。

#### <a name="business-hours-page"></a>营业页

默认情况下，工作时间设置为到下午 5 点，周一到周五上午 9 点。  营业时间以外的所有时间为非营业时间。 您可以单击**选择 24/7**以使所有小时工作时间。 除非您选择**选择 24/7**选项，将使用**后小时呼叫设置**页上配置营业时间之后的自动助理的处理呼叫。

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![第一](media/sfbcallout1.png)

默认情况下，工作时间设置为周一到周五上午 9:00 – 5:00。 选择**清除所有小时**选项，可取消选择日程表中的所有小时时间点。 当您选择**重置为默认**时，工作时间将重置为周一到周五上午 9:00 – 5:00。

* * *

![第二](media/sfbcallout2.png)

要更改营业时间，请使用日历突出显示希望设置的营业时间。 日历允许您在 30 分钟的间隔，选择工作时间和营业时间您在此处选择将会根据设置在**常规信息**页设置的时区。 要设置休息时间（如午餐时间），请取消选择或通过拖动取消选择某段时间。 在工作时间内，您可以设置多个分页符。

* * *

在完成时与您的选择，单击**next**。

#### <a name="business-hours-call-settings"></a>工作时间内呼叫设置

> [!TIP]
> 如果您使用自定义工作时间日程表，还需要设置使用**后小时呼叫处理**页上，这将使您与**营业呼叫设置**相同的选项的营业时间之后的处理的呼叫。

您可以设置问候语和提示，菜单中向贵组织的自动助理电话号码的呼叫将听到工作时间内的人员。

![工作时间内呼叫处理。](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![呼叫处理继续进行的工作时间。](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![第一](media/sfbcallout1.png)

**问候语**营业时间问候语是可选的并且可以设置为**无问候语**。 在这种情况下，呼叫者将听到没有邮件或问候语之前选择的操作的某个处理呼叫。 还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。

- **没有问候语**人员连接到自动助理电话号码时，将播放没有问候语。
- **上载音频文件**如果选择此，录制的问候语，然后上载音频文件 （以.wav、.mp3 或.wma 格式）。
- **键入的问候语消息**如果您选择此选项，输入您希望系统读取 （最多 1000年个字符） 的文本。 例如，可能会输入"欢迎来到 Contoso 。 您的呼叫对我们非常重要。" 在 **呼叫者将听到** 框中。

* * *

![第二](media/sfbcallout2.png)

您可以选择到达工作时间内的呼叫会发生什么情况。 您可以选择执行下列操作：

- **断开连接**如果您选择它，将听到营业时间问候语后断开呼叫的人。
- **重定向呼叫** 这可用来将呼叫自动发送至：
  - 与**电话系统**许可证启用了企业语音或分配调用计划在 Office 365 中的**公司内的人员**。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，选择**公司内的人员**，并设置此人要使其呼叫直接转接到语音邮件。

    > [!Note]
    > **公司中的人员**可联机用户或用户承载的本地业务服务器 2015年或 Lync Server 2013 中使用 Skype。 不支持 Lync Server 2010。

   - 另一个**自动助理**

   您可以使用现有的自动助理创建第二个级别的包含子菜单的菜单选项。 These are called nested auto attendants. 若要将发送到嵌套的自动助理呼叫，请选择**公司内的人员**并分配资源帐户，或者是一个已关联的自动助理或将关联到自动助理完后创建的此自动助理。

- **播放菜单选项**还可让您设置要播放的提示。

* * *

![第三](media/sfbcallout3.png)

**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。 可以在**设置为呼叫者在菜单导航**框中键入提示符处，也可以记录的音频文件和说，例如:"Sales，说按或说 1。 如需服务，请按或报 2。 如需客户支持，请按或报 3。 如需接线员，请按或报 0。 如需重听此菜单，请按星号键或报'重复'。 **键入的问候语消息**如果您选择此，您应输入您希望系统读取 （最多 1000年个字符） 的文本。 **上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。

* * *

![第四](media/sfbcallout4.png)

**菜单选项安装程序**可以添加或删除使用数字小键盘上键按钮的菜单选项。 要添加菜单选项，请按 **+ 分配拨号键**。 下将显示的选项对应的行。 若要删除的菜单选项，只需单击左侧数字小键盘控件上的相应的键，然后单击上面的删除图标上。 将移除按键映射行。

> [!TIP]
> 您将需要更新菜单提示文本或重新添加到删除选项，因为它不会自动完成的现有菜单提示时单独录制音频。  
>
>任何菜单选项可以添加和删除任何顺序和关键映射不必是连续的。 很有可能，例如，使用键 0、 1 和 3 时不使用项 2 映射到选项，创建一个菜单。

> [!NOTE]
> 注册表项\*（时可重复） 和\#（后） 保留由系统和不能重新分配。 如果已启用语音识别，按 * 将"重复"与对应和 # 将对应的"后退"语音命令。

若要设置您菜单选项中，选择拨号密钥后，您将需要：

- 输入**语音命令**的选项。 此地址可以是最多为 64 个字符，并且可以包含多个单词，如"客户服务"或"操作和可能导致。" 如果已启用语音识别，将自动识别名称，并呼叫的人将能够按 3、 说"3，"或者说"客户服务"，选择映射到 3 键选项。
- 选择呼叫旨在发送如果按下了相应的键，或使用语音识别选择选项。 可以将呼叫发送至：

  - **运算符**如果已设置运算符，它会自动映射到键 0，但它还能够删除或重新分配给不同的密钥。 If operator isn't set to any key, then the voice command "Operator" will be disabled too.
  - 拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。 你可以通过此设置将呼叫者直接转到语音邮件。 要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。

    > [!Note]
    > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010。
    - 另一个**自动助理**

       您可以使用现有的自动助理创建第二个级别的包含子菜单的菜单选项。 These are called nested auto attendants. 若要将发送到嵌套的自动助理呼叫，请选择**公司内的人员**并分配资源帐户，或者是一个已关联的自动助理或将关联到自动助理完后创建的此自动助理。

        > [!Note]
        > **工作时间**的嵌套 （或第二层） 自动助理还将使用，包括来自其他已设置的自动助理的呼叫。

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![第五](media/sfbcallout5.png)

**按名称拨号**如果您选择此选项，这将使呼叫中的组织使用目录搜索中的人员搜索的人员。 在 **拨号范围** 页面上设置这些选项便可为“按名称拨号”选择哪些作为可选人列出或者哪些不作为可选人列出。 使用“按名称拨号”可找到任何拥有 **电话系统** 许可证的联机用户或任何使用Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。

> [!WARNING]
> 使用“按名称拨号” **无法联系** 使用 Lync 2010 的本地托管用户。

* * *

在完成时与您的选择，单击**next**。

#### <a name="holiday-call-settings"></a>假日呼叫设置

可以为每个自动助理添加最多 20 个计划假日。

> [!TIP]
> 您可以在**组织范围的设置**屏幕 > **假日**创建假日，也可以创建其作为创建新的呼叫处理程序的一部分。

![在自动助理中设置假日](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![第一](media/sfbcallout1.png)

如果您已经创建了其他自动助理，您可能会看到一个选项，您可以使用或编辑到您在此列表的需要。 如果没有，您需要创建一个新的呼叫处理程序。

要添加新的呼叫处理程序，请单击 **+ 新建呼叫处理程序**。

* * *

![假日设置在自动助理 （续）](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![第一](media/sfbcallout1.png)

在新窗口中，输入新的呼叫处理程序，在屏幕顶部的名称。

![第二](media/sfbcallout2.png)

如果名称已在假日的**假日**的下拉列表中存在，则可以使用它。 如果尚不存在所需的假日名称，选择**创建新的假日**接的下拉列表和分配一个名称并在出现的新屏幕中新的假日的日期。 单击**保存**，准备好后。

假日名称可以包含最多 64 个字符，并且在同一自动助理中必须是唯一的。 例如，不能在同一自动助理中具有两个名为"感恩节"的假日。

![第三](media/sfbcallout3.png)

**问候语**问候语是可选的并且可以设置为**无问候语**。 在此情况下，在所选选项处理呼叫之前，呼叫者听不到消息或者问候语。 还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。

- **没有问候语**人员连接到自动助理电话号码时，将播放没有问候语。
- **上载音频文件**如果选择此，记录假日问候，然后将上载音频文件 （以.wav、.mp3 或.wma 格式）
- **键入的问候语消息**如果您选择此选项，输入您希望系统读取 （最多 1000年个字符） 的文本。 例如，可以输入"新年快乐！ 我们的办事处当前未营业。" 在**问候语消息类型**框中。

![第四](media/sfbcallout4.png)

**操作**您可以选择在该假日期间到达的呼叫会发生什么情况。 可以从以下选项中进行选择：

- **断开连接** 呼叫者听到假日问候语以后被断开连接。
- **重定向呼叫** 这可用来将呼叫自动发送至：
  - 拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员 **。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。

    > [!Note]
    > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010。

  - **呼叫队列**将呼叫转接到您已设置现有呼叫队列。
  - 另一个**自动助理**创建第二个级别的包含子菜单的菜单选项。 These are called nested auto attendants.

    > [!Note]
    > 默认方式，将假日期间到达的所有呼叫设置为听到问候语（如果有）后断开连接，所以如果希望有不同的反应，则必须指定重定向。

#### <a name="select-dial-scope-page"></a>"选择拨叫范围"页面

在此页上，您可以设置您的组织中哪些用户将您的目录中列出和可用拨号按当某人向您的组织调用的名称。

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![1 号](media/sfbcallout1.png)使用**包括**选项，您有两个选项：

- **所有在线用户** 使用此选项可以将组织中的所有人包含在目录搜索中。 将列出拥有 **电话系统** 许可证的所有联机用户，以及使用 Skype for Business Server 2015 或者 Lync Server 2013 ，并在 Office 365 中拥有呼叫计划的本地托管用户。
- **自定义用户组**如果您使用此选项，您可以搜索 Office 365 组、 通讯组列表或已在组织中的安全组的人员添加到此 Office 365 组、 通讯组列表或安全组属于任一**Online 用户电话系统许可证**或内部托管使用 Skype 业务服务器 2015年或 Lync Server 2013。 您可以添加多个 Office 365 组、 通讯组列表和安全组。

  > [!Caution]
  > 从 Lync Server 2010 的部署的内部部署用户不会按名称时某人搜索目录使用拨号列出。

* * *

![第二](media/sfbcallout2.png)

使用**排除**选项时，有两种：

- **无** 使用此选项表示不会将任何在线用户从目录搜索中排除。
- **自定义用户组**如果您使用此选项，您可以搜索 Office 365 组、 通讯组列表或安全组已在组织中创建和所有人员都添加到此 Office 365 组通讯组列表，或将从目录搜索中排除安全组。 您可以添加多个 Office 365 组、 通讯组列表和安全组。

  > [!Caution]
  > 从 Lync Server 2010 的部署的内部部署用户不会按名称时某人搜索目录使用拨号列出。

> [!NOTE]
> 可能需要 36 小时的时间的新用户具有其目录中列出当有人使用拨号按名称语音识别的名称。

在输入所有必填的字段，并设置呼叫处理菜单和选项后，单击**提交**。

## <a name="editing-and-testing-auto-attendants"></a>编辑和测试自动助理

保存自动助理后，自动助理将在" **自动助理**"页面列出。 这将使您可以快速查看一些设置，包括名称、 电话号码、 语言和状态的选项。

如果您想要更改的自动助理，选择自动助理，，然后单击在操作窗格中的**编辑**。

在操作窗格中，使用**测试**按钮，可以还快速发出测试呼叫自动助理。

## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置自动助理。

### <a name="auto-attendant-cmdlets"></a>自动助理 cmdlet

以下是管理自动助理时需要使用的 cmdlet。

|||
|---  |---  |
| [New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx) | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx) |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx) | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx) |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx) | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx) | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx) |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx) | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx) |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx) |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx) | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx) | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx) | |

### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，您可以管理 Office 365 和 Microsoft 团队使用单点管理，可以简化您的日常工作，如果您有多个要执行的任务。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [为什么要使用 Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：

  - [管理 Office 365 PowerShell 与 Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相关主题

[以下是 Office 365 中的电话系统功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[获取服务电话号码](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[什么是电话系统自动助理？](what-are-phone-system-auto-attendants.md)

[小型企业示例-设置的自动助理](/skypeforbusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)  