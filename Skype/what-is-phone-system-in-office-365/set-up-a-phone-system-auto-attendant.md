---
title: "设置电话系统自动助理"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "了解如何设置和测试有效的呼叫处理您的组织的电话系统 (云 PBX) 自动助理。 "
ms.openlocfilehash: 294a91ec723d8234e2dbfec8da79441080263c30
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-a-phone-system-auto-attendant"></a>设置电话系统自动助理

自动助理让人们对您的组织和导航菜单系统，让他们到正确的部门、 呼叫队列、 人员或运算符。 通过 Skype 业务管理中心，可以为您的组织创建的自动助理。 若要创建新的自动助理，在左边的导航，请转到**呼叫路由**，然后选择**自动助理** > **新加**。
  
如果您想要了解有关自动助理的详细信息，请参阅[电话系统自动助理是什么？](what-are-phone-system-auto-attendants.md)
  
## <a name="step-1---getting-started"></a>第 1 步 - 开始

- 您可以创建和设置自动助理之前，您需要获取或转移您的现有收费或免费的服务编号。 获取的收费或免费的服务编号后，它们将显示在**业务管理中心的 Skype** > **语音** > 页**的电话号码**。 若要获得服务号码，看到[Skype 业务和 Microsoft 团队的前服务电话号码](getting-service-phone-numbers.md)，或者如果要传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。 不能将**用户 （订户）**编号分配给自动助理。 如果您不在美国境内，不能使用业务管理中心为 Skype 来获得服务号码;转[这里](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)相反。
    
    > [!CAUTION]
    > 要获取和使用免费电话号码，您需要设置通信贷。 为此请参阅[通信片尾是什么？](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)并[设置为您的组织的通信贷](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。 
  
- 企业 E3 以及**电话系统**许可证或企业 E5 许可证，您的组织必须有 （最低要求）。 分配的**电话系统**用户许可证的数量会影响服务号可用于自动助理的数目。 您可以自动助理的数字是取决于您的组织中分配的数字**电话系统**和**音频会议**许可证。 若要了解有关许可、 转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
    > [!TIP]
    > 要重定向调用的运算符或使用**电话系统**许可证在线用户的菜单选项，将需要企业语音允许它们或将 Office 365 中调用计划分配给它们。 请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 您还可以使用 Windows PowerShell。 例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>第 2 步 - 创建新的自动助理

在**Skype 的业务管理中心**，单击**呼叫路由** > **自动助理**，然后单击**添加新**：
  
### <a name="edit-general-info-page"></a>"编辑常规信息"页面
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>**名称**输入描述性的显示名称自动助理。 该名称是必需的并且可以包含最多 64 个字符，包括空格。 它将**自动助理**选项卡上的**名称**列中列出。
***

![2 号](../images/sfbcallout2.png)<br/>**电话号码**此设置是可选的。 如果需要，选择一个电话号码的自动助理。 您可以选择任何可用的服务收费或免费电话号码，您必须为您的组织。 如果没有列出的电话号码，您需要获取服务收费或免费电话号码。 转[这里](getting-service-phone-numbers.md)来获取它们。 <br/> <br/>

    > [!Note]
    > **User (subscriber)** numbers can't be assigned to auto attendants.
***
![数字 3](../images/sfbcallout3.png)<br/>**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。每个自动助理可以有不同的时区，为自动助理设置的营业时间将根据你在此处选择的时区进行设置。
***
![14](../images/sfbcallout4.png)<br/>**语言**选择您想要为您自动助理是从列出的可用语言使用的语言。 您在此处设置的语言是自动助理将用于交互与连接到此自动助理的人，所有系统提示将都播放以这种语言的语言。
***
![数字 5](../images/sfbcallout5.png)<br/>**语音识别**语音识别是可用，如果选择此选项。 调用中的人可以使用您设置的语言中的语音输入。 通过清除它，如果您希望只允许人们使用其电话键盘，您可以禁用语音识别。
***
![数字 6](../images/sfbcallout6.png)<br/>**运算符**这是可选的并不需要将设置为自动助理。 但是，您可以设置**运算符**选项调用中能够跳出菜单以讲话给人以帮助他们的人。 <br/> <br/> 键 0 自动分配给接线员。 <br/> <br/> 如果您对此进行设置，您还需要告诉人们谁调用，因为这是**营业时间呼叫处理**页上可用选项在**编辑菜单上的选项**。 如果您设置自动助理运算符，将需要在**呼叫者将听到**框中输入相应的提示文本，或更改您的音频文件，以包括此选项。 例如，"对的运算符，请按零。" <br/><br/>  可以将以下项设置为接线员： 
*    与已启用的企业语音或分配调用计划 Office 365 中的**电话系统**许可证**您公司中的人**。 <br/>

        > [!Note] 
        > **在您的公司的人**可以是在线的用户或用户托管内部使用 Skype 业务服务器 2015年或 Lync Server 2013。 Lync Server 2010 中不受支持。 <br/> 

*    您已经设置了**呼叫队列**。 
*    您可以设置它来使呼叫的人将被发送到语音邮件。 这样做，请选择**您的公司中的人**并设置此人的电话，直接向语音邮件转发。 
   
### <a name="select-hours-of-operation-page"></a>"选择营业时间"页面

默认情况下，营业时间设置为每天 24 小时、 一周 7 天，因此所有时间被都视为营业时间。 所有未包括在工作时间以外的时间被认为是在营业时间后。 如果您选择**自定义**选项，并设置您的营业时间，则会在那里可以配置的呼叫处理在营业时间后自动助理的添加新页面**后小时呼叫处理**调用。
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![1 号](../images/sfbcallout1.png)<br/>选择" **自定义**"选项可在日历中选择特定的营业时间。选择" **自定义**"后，默认情况下将营业时间设置为周一至周五，上午 9:00 - 下午 5:00。
***
![2 号](../images/sfbcallout2.png)<br/>若要更改营业时间，突出显示您想要使用日历设置营业时间。 日历允许您在 30 分钟的间隔，选择营业，营业时间您在此处选择将基于设置在**常规信息**页设置的时区。 若要设置断点 （例如，午餐休息），请取消选择或拖动以取消选择日历上的时间。 在营业时间内，您可以设置多个断点。 
   
### <a name="select-business-hours-call-handling-page"></a>选择工作时间呼叫处理页面

> [!TIP]
> [!提示] 如果使用自定义营业时间表，则还需要设置非营业时间的呼叫处理方式。将增加一个" **非营业时间呼叫处理**"页面以便你配置这些选项，此页面提供的选项与设置" **营业时间呼叫处理**"的选项相同。 
  
您可以设置问候语、 提示和菜单中对您的组织的自动助理的电话号码将听到在工作时间内的人员。
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>**公司问候**营业时间问候语是可选的可以设置为**无**。 在这种情况下，调用方会听到任何消息或问候之前调用由您选择的选项之一。 此外可以上载音频文件 （以.wav、 mp3 或.wma 格式），或创建自定义问候语使用文字到语音功能。
*    **无**当人们连接到自动助理的电话号码时，会播放没有问候语。
*    **创建自定义问候语**如果您选择此选项时，输入您希望系统 （最多为 1000年个字符） 读取的文本。 例如，可以输入"欢迎 Contoso。 您的电话对我们很重要。" 在**呼叫者将听到**框中。
*    **将音频文件上载**如果您选择此选项，录制问候语，然后上载音频文件 （以.wav、.mp3 或.wma 格式）。
***
![2 号](../images/sfbcallout2.png)<br/>您可以选择呼叫到达上班期间会发生什么情况。 您可以从以下选项中进行选择：
*    **断开连接**如果选择它，将营业时间问候语听到后断开呼叫的人。
*    **将呼叫重定向**这可以用于自动发送到调用：
     *    与已启用的企业语音或分配调用计划 Office 365 中的**电话系统**许可证**您公司中的人**。 您可以设置它来使调用程序中的用户可以发送到语音邮件。 这样做，请选择**您的公司中的人**并设置此人让其将直接转发至语音邮件的电话。 <br/><br/>   
        > [!Note]
        > **在您的公司的人**可以是在线的用户或用户托管内部使用 Skype 业务服务器 2015年或 Lync Server 2013。 Lync Server 2010 中不受支持。 <br/><br/>

     *    使用调用队列**调用队列**允许呼叫转移到您已设置的现有调用队列。
     *    您可以使用现有的另一个**自动助理**自动助理创建包含子菜单的菜单选项的第二个级别。 这些被称为嵌套的自动助理。
*    **播放菜单选项提示**这些也可以用于允许您设置要播放的提示。
***
![数字 3](../images/sfbcallout3.png)<br/>**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。可以在 **呼叫者将听到**框中输入提示或录制音频文件并播报，例如"如需销售，请按或报 1。如需服务，请按或报 2。如需客户支持，请按或报 3。如需接线员，请按或报 0。如需重听此菜单，请按星号键或报'重复'。" **创建自定义提示** 如果选择此选项，应输入希望系统播报的文本（最多 1000 个字符）。 **上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。
***
![数字 4](../images/sfbcallout4.png)<br/>**按名称拨号**如果您选择此选项，这将使调用中要搜索的目录搜索使用您组织中的人的人。 您可以选择哪些人将被列为可用或不可用拨号的按名称通过设置**拨号范围**页上的这些选项。 使用**电话系统**许可证，任何在线用户或所有用户承载内部使用 Skype 业务服务器 2015年或 Lync Server 2013，找不到具有拨号的名称。<br/><br/>  **注意：**用户承载内部使用 Lync 2010**不能达到**按名称拨号。
***

![数字 5](../images/sfbcallout5.png)<br/>**编辑菜单选项**可以添加或删除使用数字小键盘上键按钮菜单选项。 若要添加一个菜单选项，请在键盘上按对应的键。 中使用的键将更改颜色和对应的行的选项将显示下方。 若要删除一个菜单选项，只需单击相应的键键盘控件将其取消选择此项。 将删除键映射行。<br/><br/>  **提示：**您将需要更新菜单提示文本或重新添加到删除选项，因为它不会自动完成现有菜单提示时分别录制音频。  <br/><br/>  任何菜单选项可以添加并删除任何顺序，不必是连续的键映射。 很可能，例如，用 0、 1 和 3 对应的选项，而不使用密钥 2 键创建菜单。<br/><br/> 

    > [!Note] 
    > The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands. <br/><br/>

若要设置您的菜单选项，选择将密钥后，您将需要： 
- **输入的选项的名称**这可以是最多 64 个字符，并且可以包含多个词，如"客户服务"或"操作和土方。 如果启用语音识别，则名称将自动识别，并呼叫的人将能够按 3、 说"三，"或者说"客户服务"以选择映射到键 3 选项。 
- 下一步是选择调用将发送如果按相应的键，或使用语音识别选中的选项。 可以将该调用发送到： 
    - **运算符**如果已设置运算符，它会自动映射到键 0，但还可以被删除或重新分派给不同的密钥。 如果运算符不设置为任意键，然后将太禁用语音命令"运算符"。 
    - 与已启用的企业语音或分配调用计划 Office 365 中的**电话系统**许可证**您公司中的人**。 您可以设置它来使调用程序中的用户可以发送到语音邮件。 这样做，请选择**您的公司中的人**并设置此人让其将直接转发至语音邮件的电话。<br/><br/> 
    
        > [!Note] 
        > **在您的公司的人**可以是在线的用户或用户托管内部使用 Skype 业务服务器 2015年或 Lync Server 2013。 Lync Server 2010 中不受支持。 <br/><br/>

    - **调用队列**使用调用队列选项允许呼叫转移到您已经设置了某个现有呼叫队列。 
    - **自动助理**可以使用现有的自动助理创建包含子菜单的菜单选项的第二个级别。 这些被称为嵌套的自动助理。<br/><br/>
    
        > [!Note]
        > **营业时间**的嵌套 （或第二层） 自动助理还将使用，包括用于从已设置其他自动助理发送调用。         
   
### <a name="select-holidays-page"></a>选择假日页 

您可以添加最多 20 个计划的假日到每个自动助理。
  
![设置假日的自动助理](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>**添加假日**在**假日名称**字段中输入您新的节日的名称。<br/><br/> 节日名称可能包含最多 64 个字符，并且必须是唯一的相同的自动助理。 例如，不能有两个相同的自动助理中名为"感恩节"的节日。  
***
![2 号](../images/sfbcallout2.png)<br/>**节日问候**节日问候是可选的可以设置为**无**。 在这种情况下，调用方会听到任何消息或问候之前调用由您选择的选项之一。 此外可以上载音频文件 （以.wav、 mp3 或.wma 格式），或创建自定义问候语使用文字到语音功能。
*    **无**当人们连接到自动助理的电话号码时，会播放没有问候语。
*    **创建自定义问候语**如果您选择此选项时，输入您希望系统 （最多为 1000年个字符） 读取的文本。 例如，您可以输入"新年快乐 ！ 我们的办事处当前已关闭。" 在**呼叫者将听到**框中。
*    **将音频文件上载**如果您选择此选项，记录节日问候，然后上载音频文件 （以.wav、.mp3 或.wma 格式）。  
***
![数字 3](../images/sfbcallout3.png)<br/>**怎样对呼叫后问候？** 您可以选择在此节日期间到达该调用会发生什么情况。 您可以从以下选项中进行选择：
*    **断开连接**听到节日问候后，调用程序中的用户将被断开。
*    **将呼叫重定向**这可以用于自动发送到调用：
     *    与已启用的企业语音或分配调用计划 Office 365 中的**电话系统**许可证**您公司中的人**。 您可以设置它来使调用程序中的用户可以发送到语音邮件。 这样做，请选择**您的公司中的人**，并设置此人让其将直接转发至语音邮件的电话。 <br/><br/> 
     
         > [!Note] 
         > **在您的公司的人**可以是在线的用户或用户托管内部使用 Skype 业务服务器 2015年或 Lync Server 2013。 Lync Server 2010 中不受支持。<br/><br/>

     *    将呼叫转给您已设置的现有调用队列**调用队列**。
     *    另一个**自动助理**，以创建包含子菜单的菜单选项的第二个级别。 这些被称为嵌套的自动助理。 <br/><br/>
     
         > [!Note]
         > 默认情况下，在节日期间收到的所有调用都设置断开后 （如果有的话） 的问候语，所以您必须指定一个重定向链接，如果需要不同的行为。

***
![数字 4](../images/sfbcallout4.png)<br/>**您希望何时开始和结束的假日？** 以 dd/mm/yyyy 格式输入您假期的开始日期，然后选择开始时间、 结束日期和结束时间，在日期范围表中的提示。<br/><br/>您可以指定假日最多 10 个不同的日期范围。 例如，可以添加的长达 10 年的新年前夕假期的日期范围。 假期可以跨多天。<br/><br/>若要添加其他假日日期范围 （例如，用于下一年度），单击**添加另一个**，然后输入一组新的假日的开始和结束日期。<br/><br/>此外支持嵌套的假日。 例如，可以嵌套多个节日一个"假日休息"的时间段内： 
*    **月 3 日至 12 月 24:**"快乐的假日 ！ 我们的办事处当前已关闭。 我们将会重新打开在 1 月 4 日上。"
*    **12 月 25 日：**"圣诞快乐 ！ 我们的办事处当前已关闭。 我们将会重新打开在 1 月 4 日上。"
*    **月 1 日：**"新年快乐 ！ 我们的办事处当前已关闭。 我们将会重新打开在 1 月 4 日上。"
   
保存自动助理后，假日将出现在**假日**选项卡，在其中可以编辑、 添加或修改节日设置。
  
### <a name="select-dial-scope-page"></a>"选择拨叫范围"页面

在此页上，您可以设置您的组织中哪些用户将列出您的目录中，供拨按名称时调用您的组织的人员。
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>使用" **包括**"选项时，可以从两个选项中选择：
*    **所有在线的用户**使用此选项允许所有人组织中要包括在目录搜索。 与**电话系统**许可证，以及用户的所有在线用户承载内部使用 Skype 业务服务器 2015年或 Lync Server 2013 Office 365 中拥有调用计划将被列出。 
*    **自定义**如果使用此选项，您可以搜索 Office 365 组、 通讯组列表或已在您的组织创建的安全组的人员添加到此 Office 365 组、 通讯组列表或安全组是任何一个**与联机用户电话系统许可证**或内部部署承载的业务服务器 2015年或 Lync Server 2013 使用 Skype。 您可以添加多个 Office 365 组、 通讯组和安全组。 <br/><br/> 

    > [!Caution]
    > 内部部署 Lync Server 2010 中的用户不会被当有人搜索目录使用拨号按名称列出。 
***
![2 号](../images/sfbcallout2.png)<br/>使用**排除**选项，您有两个选项：
*    **无** 使用此选项表示不会将任何在线用户从目录搜索中排除。 
*    **自定义**如果使用此选项，您可以搜索 Office 365 组、 通讯组列表或已在您的组织创建的安全组和所有人都添加到通讯组列表，此 Office 365 组或安全组将从目录搜索中排除。 您可以添加多个 Office 365 组、 通讯组和安全组。 <br/><br/> 

    > [!Caution]
    > 内部部署 Lync Server 2010 中的用户不会被当有人搜索目录使用拨号按名称列出。          
   
> [!NOTE]
> 可能需要 36 小时的时间让他们的姓名列在目录中有人使用拨号时按名称使用语音识别的新用户。 
  
在输入所有必填的字段并设置呼叫处理菜单和选项后，单击**保存**。
  
## <a name="editing-and-testing-auto-attendants"></a>编辑和测试自动助理

保存自动助理后，它将出现在页上**自动助理**。 这将允许您快速查看一些已设置，包括名称、 电话号码、 语言及状态的选项。
  
如果您想要更改自动助理，选择自动助理，，然后在操作窗格中单击**编辑**。
  
通过操作窗格中的**测试**按钮，可以快速放置测试调用自动助理。
  
## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置自动助理。
  
### <a name="auto-attendant-cmdlets"></a>自动助理 cmdlet

以下是管理自动助理时需要使用的 cmdlet。
  
||| 
|---|---|
[新 CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx)                                                                      | [新 CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx)                                                              |
| [一组 CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx)                                                                      | [新 CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx)                                                           |
| [获得 CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx)                                                                      | [获得 CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [删除 CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx)                                                                   | [新 CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx)                                                                                 | [新 CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx)                                                              |
| [导出 CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [新 CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx)                                                                                  |
| [新 CsOnlineDateTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [新 CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx)                                                                                   |
| [获得 CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/en-us/library/mt796483.aspx)                                                     | [新 CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx)                                               |
| [获得 CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx)                                                     | [导入 CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [新 CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[以下是您所获得的与 Office 365 中的电话系统](here-s-what-you-get-with-phone-system.md)

[业务和 Microsoft 小组获得 Skype 服务电话号码](getting-service-phone-numbers.md)

[音频会议和调用计划的国家和地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    

