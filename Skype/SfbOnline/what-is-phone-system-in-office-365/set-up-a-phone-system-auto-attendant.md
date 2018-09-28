---
title: 设置电话系统自动助理
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解如何设置和测试高效处理您的组织的呼叫的电话系统 (云 PBX) 自动助理。 '
ms.openlocfilehash: bceda290adc10e806249cbd0938305ffa321d91f
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347263"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>设置电话系统自动助理

自动助理让人们呼叫您的组织和导航菜单系统，以使其向右部门、 队列、 人员或运算符呼叫。 使用适用于业务管理中心 Skype，可以为组织创建自动助理。 To create a new auto attendant, go to **Call routing** in the left navigation, and then select **Auto attendants** > **Add new**.
  
如果您想要了解有关自动助理的详细信息，请参阅[电话系统自动助理是什么？](/microsoftteams/what-are-phone-system-auto-attendants)
  
## <a name="step-1---getting-started"></a>第 1 步 - 开始

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. 获得收费电话或免费电话服务号码后，它们将显示在**业务管理中心的 Skype** > **语音** > **电话号码**页。 若要获取服务号码，请查看[的业务和 Microsoft 团队的 Skype 获取服务电话号码](getting-service-phone-numbers.md)，或如果您希望进行传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](/microsoftteams/transfer-phone-numbers-to-office-365)。 **User (subscriber)** numbers can't be assigned to auto attendants. 如果您在美国以外，您无法使用业务管理中心的 Skype 获取服务号码;转[此处](/microsoftteams/manage-phone-numbers-for-your-organization)相反。

    > [!CAUTION]
    > 若要获取并使用免费电话号码，则需要设置通信点数。 若要执行此操作，请参阅 [通信点数是什么？](/microsoftteams/what-are-communications-credits) 和 [为组织设置通信点数](/microsoftteams/set-up-communications-credits-for-your-organization) 。
  
- 企业版 E3 以及**电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低要求）。 已分配的**电话系统**用户许可证数量影响的可用于自动助理服务号码数。 取决于您的组织中分配的号码**电话系统**和**音频会议**许可证的自动助理可以具有的数字。 若要了解有关授权的详细信息转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
    > [!TIP]
    > 要重定向呼叫的运算符或联机用户与**电话系统**许可证的菜单选项，您将需要启用企业语音或分配给它们的调用计划在 Office 365 中。 请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 你还可以使用 Windows PowerShell。 例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>第 2 步 - 创建新的自动助理

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**


在 **Skype for Business 管理中心** 内，单击 **呼叫路由** > **自动助理** ，然后单击 **添加新的** ：
  
### <a name="edit-general-info-page"></a>"编辑常规信息"页面
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**名称**输入自动助理的描述性的显示名称。 此名称为必填字段，最多可以包含 64 个字符，其中包括空格。 此名称将显示在" **自动助理**"选项卡的" **名称**"列中。
***

![第二](../images/sfbcallout2.png)<br/>**电话号码** 此设置为可选项。 如果愿意，为自动助理选择一个电话号码。 您可以选择任何可用的服务或已为您的组织的免费电话号码。 如果没有列出任何电话号码，则需要获取收费或免费服务电话号码。 转至 [此处](getting-service-phone-numbers.md) 来获取它们。 <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![第三](../images/sfbcallout3.png)<br/>**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。每个自动助理可以有不同的时区，为自动助理设置的营业时间将根据你在此处选择的时区进行设置。
***
![14](../images/sfbcallout4.png)<br/>**语言** 从列出的可用语言列表中选择自动助理使用的语言。 您在此处设置的语言的自动助理将使用与进行交互到此自动助理，呼叫中的人员并所有系统播放提示时在这种语言的语言。
***
![第五](../images/sfbcallout5.png)<br/>**语音识别**语音识别可用，如果选择此选项。 呼叫中的人员可以使用语音输入中所设置的语言。 如果您想要仅允许使用其电话小键盘的人员清除它，您可以禁用语音识别。
***
![第六](../images/sfbcallout6.png)<br/>**接线员** 此为可选字段，无须为自动助理设置。 但是，您可以设置呼叫中能够页符拖出菜单以帮助他们人讲话的人员**运算符**选项。 <br/> <br/> 键 0 自动分配给接线员。 <br/> <br/> 如果您对此进行设置，还需要告知人员谁调用的这是在**营业呼叫处理**页中的**编辑菜单选项**可用选项。 如果您在自动助理上设置运算符，您需要在**呼叫者收听**框中输入相应的提示文本或更改您的音频文件，以包括此选项。 例如，"如需接线员，请按零"。 <br/><br/>  可以将以下项设置为接线员： 
*    拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。 <br/>

        > [!Note] 
        > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010 。 <br/> 

*    A **Call Queue** that you have set up. 
*    你可以通过此设置将呼叫者直接转到语音邮件。 若要执行此操作，选择**您的公司的人员**并将此人的呼叫转接至语音邮件直接设置。 
   
### <a name="select-hours-of-operation-page"></a>"选择营业时间"页面

默认情况下，工作时间设置为 24 小时、 一周 7 天，因此所有小时被都视为营业时间。 营业时间以外的所有时间为非营业时间。 如果您选择**自定义**选项，并将设置您的工作时间，然后将您可在其中配置营业时间之后的自动助理的处理呼叫添加新页面**小时呼叫处理之后**调用。
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![第一](../images/sfbcallout1.png)<br/>选择" **自定义**"选项可在日历中选择特定的营业时间。选择" **自定义**"后，默认情况下将营业时间设置为周一至周五，上午 9:00 - 下午 5:00。
***
![第二](../images/sfbcallout2.png)<br/>要更改营业时间，请使用日历突出显示希望设置的营业时间。 日历允许您在 30 分钟的间隔，选择工作时间和营业时间您在此处选择将会根据设置在**常规信息**页设置的时区。 要设置休息时间（如午餐时间），请取消选择或通过拖动取消选择某段时间。 在工作时间内，您可以设置多个分页符。 
   
### <a name="select-business-hours-call-handling-page"></a>选择营业时间呼叫处理页面

> [!TIP]
> [!提示] 如果使用自定义营业时间表，则还需要设置非营业时间的呼叫处理方式。将增加一个" **非营业时间呼叫处理**"页面以便你配置这些选项，此页面提供的选项与设置" **营业时间呼叫处理**"的选项相同。 
  
您可以设置问候语和提示，菜单中向贵组织的自动助理电话号码的呼叫将听到工作时间内的人员。
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**公司问候语** 营业时间问候语是可选项，可设置为 **无** 。 在此情况下，在所选选项处理呼叫之前，呼叫者听不到消息或者问候语。 还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。
*    **无** 在有人呼叫自动助理电话号码时，将不播放问候语。
*    **创建自定义问候语**如果您选择此选项，输入您希望系统读取 （最多 1000年个字符） 的文本。 例如，可能会输入"欢迎来到 Contoso 。 您的呼叫对我们非常重要。" 在 **呼叫者将听到** 框中。
*    **上载音频文件**如果选择此，录制的问候语，然后上载音频文件 （以.wav、.mp3 或.wma 格式）。
***
![第二](../images/sfbcallout2.png)<br/>您可以选择到达工作时间内的呼叫会发生什么情况。 可以从以下选项中进行选择：
*    **断开连接**如果您选择它，将听到营业时间问候语后断开呼叫的人。
*    **重定向呼叫** 这可用来将呼叫自动发送至：
     *    拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。 你可以通过此设置将呼叫者直接转到语音邮件。 要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。 <br/><br/>   
        > [!Note]
        > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010。 <br/><br/>

     *    **呼叫队列**使用呼叫的队列使呼叫转接到您已设置的现有调用队列。
     *    另一个**自动助理**可以使用现有自动助理创建第二个级别的包含子菜单的菜单选项。 These are called nested auto attendants.
*    **Play menu options prompt** These can also be used to let you set up a prompt you want played.
***
![第三](../images/sfbcallout3.png)<br/>**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。可以在 **呼叫者将听到**框中输入提示或录制音频文件并播报，例如"如需销售，请按或报 1。如需服务，请按或报 2。如需客户支持，请按或报 3。如需接线员，请按或报 0。如需重听此菜单，请按星号键或报'重复'。" **创建自定义提示** 如果选择此选项，应输入希望系统播报的文本（最多 1000 个字符）。 **上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。
***
![第四](../images/sfbcallout4.png)<br/>**按名称拨号**如果您选择此选项，这将使呼叫中的组织使用目录搜索中的人员搜索的人员。 在 **拨号范围** 页面上设置这些选项便可为“按名称拨号”选择哪些作为可选人列出或者哪些不作为可选人列出。 使用“按名称拨号”可找到任何拥有 **电话系统** 许可证的联机用户或任何使用Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。<br/><br/>  

> [!WARNING]
> 使用“按名称拨号” **无法联系** 使用 Lync 2010 的本地托管用户。
***

![第五](../images/sfbcallout5.png)<br/>**Edit menu options** Menu options can be added or removed by using key buttons on the keypad. 若要添加菜单选项，按下键盘上相应的按键。 The keys in use will change in color and the corresponding row of options will appear below. 若要删除的菜单选项，只需单击键盘控件以取消选择此项上的相应项。 将移除按键映射行。<br/><br/>  **提示：** 您将需要更新菜单提示文本或重新添加到删除选项，因为它不会自动完成的现有菜单提示时单独录制音频。  <br/><br/>  任何菜单选项可以添加和删除任何顺序和关键映射不必是连续的。 很有可能，例如，使用键 0、 1 和 3 时不使用项 2 映射到选项，创建一个菜单。<br/><br/> 

> [!NOTE]
> 按键 * （重复）和 # （回格）由系统保留，不能再分配。 如果已启用语音识别，按 * 将"重复"与对应和 # 将对应的"后退"语音命令。


若要设置菜单选项，选择按键后，将需要： 
- **输入的选项名称**此地址可以是最多为 64 个字符，并且可以包含多个单词，如"客户服务"或"操作和可能导致。" 如果已启用语音识别，将自动识别名称，并呼叫的人将能够按 3、 说"3，"或者说"客户服务"，选择映射到 3 键选项。 
- 下一步是如果按下了相应的按键，选择将呼叫发送至何处，或使用语音识别选择选项。 可以将呼叫发送至： 
    - **运算符**如果已设置运算符，它会自动映射到键 0，但它还能够删除或重新分配给不同的密钥。 If operator isn't set to any key, then the voice command "Operator" will be disabled too. 
    - 拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。 你可以通过此设置将呼叫者直接转到语音邮件。 要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。<br/><br/> 
    
        > [!Note] 
        > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010。 <br/><br/>

    - **呼叫队列**通过呼叫队列选项可以呼叫转接到您已设置现有呼叫队列。 
    - **Auto Attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.<br/><br/>
    
        > [!Note]
        > **工作时间**的嵌套 （或第二层） 自动助理还将使用，包括来自其他已设置的自动助理的呼叫。         
   
### <a name="select-holidays-page"></a>选择假日页面 

可以为每个自动助理添加最多 20 个计划假日。
  
![在自动助理中设置假日](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**添加假日** 在 **假日名称** 字段中输入新假日的名称。<br/><br/> 假日名称可以包含最多 64 个字符，并且在同一自动助理中必须是唯一的。 例如，不能在同一自动助理中具有两个名为"感恩节"的假日。  
***
![第二](../images/sfbcallout2.png)<br/>**假日问候** 假日问候是可选项，可以设置为 **无** 。 在此情况下，在所选选项处理呼叫之前，呼叫者听不到消息或者问候语。 还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。
*    **无** 在有人呼叫自动助理电话号码时，将不播放问候语。
*    **创建自定义问候语**如果您选择此选项，输入您希望系统读取 （最多 1000年个字符） 的文本。 例如，可以输入"新年快乐！ 我们的办事处当前未营业。" 在 **呼叫者将听到** 框中。
*    **上载音频文件**如果选择此，记录假日问候，然后上载音频文件 （以.wav、.mp3 或.wma 格式）。  
***
![第三](../images/sfbcallout3.png)<br/>**问候语之后对呼叫做些什么？** 您可以选择在该假日期间到达的呼叫会发生什么情况。 可以从以下选项中进行选择：
*    **断开连接** 呼叫者听到假日问候语以后被断开连接。
*    **重定向呼叫** 这可用来将呼叫自动发送至：
     *    拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员 **。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。 <br/><br/> 
     
         > [!Note] 
         > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010。<br/><br/>

     *    将呼叫转接到您已设置的现有调用队列**呼叫的队列**。
     *    另一个**自动助理**创建第二个级别的包含子菜单的菜单选项。 These are called nested auto attendants. <br/><br/>
     
         > [!Note]
         > 默认方式，将假日期间到达的所有呼叫设置为听到问候语（如果有）后断开连接，所以如果希望有不同的反应，则必须指定重定向。

***
![第四](../images/sfbcallout4.png)<br/>**希望假日何时开始和结束？** 以 dd/mm/yyyy 格式，输入假日的开始日期，然后选择开始时间、结束日期和结束时间，如日期范围表中所提示。<br/><br/>可以为假日指定最多 10 个不同的日期范围。 例如，可以添加最多 10 年的除夕假日的日期范围。 假日可以有多天。<br/><br/>若要添加其他假日日期范围 （例如，下一年），单击 **添加另一个** ，然后输入一组新的假日起止日期。<br/><br/>亦支持嵌套假日。 例如，可以在一个“假日假期”时间段内嵌套多个假日： 
*    **12 月 24 日至 1 月 3 日：** “假日快乐！ 我们的办事处当前未营业。 我们将于 1 月 4 日恢复营业。"
*    **12 月 25:** "圣诞快乐！ 我们的办事处当前未营业。 我们将于 1 月 4 日恢复营业。"
*    **1 月 1:** "新年快乐！ 我们的办事处当前未营业。 我们将于 1 月 4 日恢复营业。"
   
保存自动助理后，假日出现在 **假日** 选项卡上，可在此编辑、添加或修改假日设置。
  
### <a name="select-dial-scope-page"></a>"选择拨叫范围"页面

在此页上，您可以设置您的组织中哪些用户将您的目录中列出和可用拨号按当某人向您的组织调用的名称。
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![第一](../images/sfbcallout1.png)<br/>使用" **包括**"选项时，可以从两个选项中选择：
*    **所有在线用户** 使用此选项可以将组织中的所有人包含在目录搜索中。 将列出拥有 **电话系统** 许可证的所有联机用户，以及使用 Skype for Business Server 2015 或者 Lync Server 2013 ，并在 Office 365 中拥有呼叫计划的本地托管用户。 
*    **自定义** 如果使用此选项，可以搜索 Office 365 组、通讯组列表或已在组织中创建的安全组，以及添加至此 Office 365 组、通讯组列表或安全组的人员，他们可能是 **拥有电话系统许可证的联机用户** 或者是使用 Skype for Business Server 2015 或 Lync Server 2013 的本地托管用户。 您可以添加多个 Office 365 组、 通讯组列表和安全组。 <br/><br/> 

    > [!Caution]
    > 从 Lync Server 2010 的部署的内部部署用户不会按名称时某人搜索目录使用拨号列出。 
***
![第二](../images/sfbcallout2.png)<br/>使用**排除**选项时，有两种：
*    **无** 使用此选项表示不会将任何在线用户从目录搜索中排除。 
*    **自定义**如果您使用此选项，您可以搜索 Office 365 组、 通讯组列表或安全组已在组织中创建和所有人员都添加到此 Office 365 组通讯组列表，或将从目录搜索中排除安全组。 您可以添加多个 Office 365 组、 通讯组列表和安全组。 <br/><br/> 

    > [!Caution]
    > 从 Lync Server 2010 的部署的内部部署用户不会按名称时某人搜索目录使用拨号列出。          
   
> [!NOTE]
> 可能需要 36 小时的时间的新用户具有其目录中列出当有人使用拨号按名称语音识别的名称。 
  
在输入所有必填的字段，并设置呼叫处理菜单和选项后，单击**保存**。
  
## <a name="editing-and-testing-auto-attendants"></a>编辑和测试自动助理

保存自动助理后，自动助理将在" **自动助理**"页面列出。 这将使您可以快速查看一些设置，包括名称、 电话号码、 语言和状态的选项。
  
如果您想要更改的自动助理，选择自动助理，，然后单击在操作窗格中的**编辑**。
  
在操作窗格中，使用**测试**按钮，可以还快速发出测试呼叫自动助理。
  
## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置自动助理。
  
### <a name="auto-attendant-cmdlets"></a>自动助理 cmdlet

以下是管理自动助理时需要使用的 cmdlet。
  
||| 
|---|---|
[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                                                      | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                                              |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                                                      | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                                                   | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                                                                 | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                                              |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                                                                  |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                                                     | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                                                     | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[Office 365 中的电话系统的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[什么是电话系统自动助理？](/MicrosoftTeams/what-are-phone-system-auto-attendants.md)

[小型企业示例-设置的自动助理](tutorial-org-aa.yml)  