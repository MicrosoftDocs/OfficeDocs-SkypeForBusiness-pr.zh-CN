---
title: 设置电话系统自动助理
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: '了解如何设置并测试电话系统（ 云 PBX ）自动助理，使组织的呼叫处理更加高效。 '
ms.openlocfilehash: fb35e36e7d59a3d47584fd15e592f68dd3ac4ae5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780460"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>设置电话系统自动助理

自动助理允许人们呼叫组织并使用菜单系统导航，将他们引导至正确的部门、呼叫列队、人员或者操作员。可以使用 Skype for Business 管理中心为组织创建一个自动助理。若要创建新的自动助理，请转至左侧导航中的 **呼叫路由** ，然后选择 **自动助理** > **添加新的** 。
  
如果想要了解有关自动助理的详细信息，请参阅 [电话系统自动助理是什么？](/microsoftteams/what-are-phone-system-auto-attendants)
  
## <a name="step-1---getting-started"></a>第 1 步 - 开始

- 创建和设置自动助理之前，需要获取或转移现有收费电话或免费电话服务号码。获得收费电话或免费电话服务号码后，它们将显示在 **Skype for Business 管理中心** > **语音** > **电话号码** 页面上。若要获取服务号码，请参阅 [获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)，或者，如果希望转移一个现有服务号码，请参阅 [将电话号码转移至 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) 。不能将 **用户 （订阅服务器）** 号码分配给自动助理。如果身处美国以外，则会无法使用 Skype for Business 管理中心获取服务号码；这时应转至 [此处](/microsoftteams/manage-phone-numbers-for-your-organization) 。
    
    > [!CAUTION]
    > 若要获取并使用免费电话号码，则需要设置通信点数。 若要执行此操作，请参阅 [通信点数是什么？](/microsoftteams/what-are-communications-credits) 和 [为组织设置通信点数](/microsoftteams/set-up-communications-credits-for-your-organization) 。 
  
- 组织必须拥有（至少） Enterprise E3 plus **电话系统** 许可证或 Enterprise E5 许可证。 已分配的 **电话系统** 用户许可证数量会影响可供自动助理使用的服务号码数量。 能够拥有的自动助理的号码数取决于组织中分配的 **电话系统** 和 **音频会议** 许可证数量。 若要了解有关授权的详细信息，请转至 [此处](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 。
    
    > [!TIP]
    > 若要将呼叫重定向至属于持有 **电话系统** 许可证的联机用户的操作员或者菜单选项，将需要启用他们的企业语音或在 Office 365 中给他们分配呼叫计划。 请参阅 [分配 Skype for Business 和 Microsoft Teams 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 。 还可以使用 Windows PowerShell 。 例如，运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>第 2 步 - 创建新的自动助理

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**


在 **Skype for Business 管理中心** 内，单击 **呼叫路由** > **自动助理** ，然后单击 **添加新的** ：
  
### <a name="edit-general-info-page"></a>编辑常规信息页面
  
![新自动助理页面 1 。](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**名称** 为自动助理输入描述性显示名称。 此名称为必填字段，最多可以包含 64 个字符，其中包括空格。 此名称将在 **自动助理** 选项卡的 **名称** 列中列出。
***

![第二](../images/sfbcallout2.png)<br/>**电话号码** 此设置为可选项。 如果愿意，为自动助理选择一个电话号码。 可以为组织选择任何可用的收费或者免费服务电话号码。 如果没有列出任何电话号码，则需要获取收费或免费服务电话号码。 转至 [此处](getting-service-phone-numbers.md) 来获取它们。 <br/> <br/>

> [!NOTE]
> **用户（订阅服务器）** 号码可以分配给自动助理。
    
***
![第三](../images/sfbcallout3.png)<br/>**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。每个自动助理可以有不同的时区，为自动助理设置的营业时间将根据你在此处选择的时区进行设置。
***
![14](../images/sfbcallout4.png)<br/>**语言** 从列出的可用语言列表中选择自动助理使用的语言。此处设置的语言即为自动助理与呼入此自动助理的呼叫者交互时使用的语言，所有系统提示均使用此语言。
***
![第五](../images/sfbcallout5.png)<br/>**语音识别** 可以使用语音识别，如果选中此选项。呼叫者可以使用设置的语言进行语音输入。如果希望用户只能使用其电话键盘，可以通过取消选中此选项来禁用语音识别。
***
![第六](../images/sfbcallout6.png)<br/>**操作员** 此项 为可选，自动助理无须设置。 但是，可以通过设置 **接线员** 选项，使呼叫者能够跳出菜单与真人对话，从而获得帮助。 <br/> <br/> 按键 0 自动分配给操作员。 <br/> <br/> 如果设置此选项，还需要通过 **营业时间呼叫处理** 页面上的 **编辑菜单选项** ，告诉呼叫者此为可用选项。 如果为自动助理设置接线员，需要在 **呼叫者将听到** 框中输入相应的提示文本，或更改语音文件以包含此选项。 例如，“如需操作员，请按零。” <br/><br/>  可以将以下项中的一种设置为操作员： 
*    拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。 <br/>

        > [!Note] 
        > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010 。 <br/> 

*    已设置的 **呼叫列队** 。 
*    可以通过此设置将呼叫发送至语音邮件。 为此，请选择 **公司人员** ，并将此人的呼叫设置为直接转到语音邮件。 
   
### <a name="select-hours-of-operation-page"></a>选择营业时间页面

默认方式，将营业时间设置为每周 7 天，每天 24 小时，因此所有时间均视为营业时间。 营业时间以外的所有时间为非营业时间。 如果选择 **自定义** 选项并设置营业时间，将会添加一个名为 **非营业时间呼叫处理** 的新页面，可在此为自动助理配置非营业时间的呼叫处理。
  
![新的自动助理营业时间。](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![第一](../images/sfbcallout1.png)<br/>选择" **自定义**"选项可在日历中选择特定的营业时间。选择" **自定义**"后，默认情况下将营业时间设置为周一至周五，上午 9:00 - 下午 5:00。
***
![第二](../images/sfbcallout2.png)<br/>若要更改营业时间，请使用日历突出显示希望设置的营业时间。 日历允许以 30 分钟的间隔来选择营业时间，此处选择的营业时间将根据 **常规信息** 页面上设置的时区来设置。 若要设置休息时间（如午餐时间），请在日历上取消选择或拖动取消选择时间。 可在营业时间内设置多个休息时间。 
   
### <a name="select-business-hours-call-handling-page"></a>选择营业时间呼叫处理页面

> [!TIP]
> [!提示] 如果使用自定义营业时间表，则还需要设置非营业时间的呼叫处理方式。将增加一个" **非营业时间呼叫处理**"页面以便你配置这些选项，此页面提供的选项与设置" **营业时间呼叫处理**"的选项相同。 
  
可以设置在营业时间内呼叫组织自动助理电话号码的呼叫者将听到的问候语、提示和菜单。
  
![营业时间呼叫处理。](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**公司问候语** 营业时间问候语是可选项，可设置为 **无** 。 在此情况下，在所选选项处理呼叫之前，呼叫者听不到消息或者问候语。 还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。
*    **无** 在有人呼叫自动助理电话号码时，将不播放问候语。
*    **创建自定义问候语** 如果选择此选项，输入希望系统朗读的文本 （最多 1000 个字符）。 例如，可能会输入"欢迎来到 Contoso 。 您的呼叫对我们非常重要。" 在 **呼叫者将听到** 框中。
*    **上传音频文件** 如果选择此选项，则需要录制问候语并上传音频文件（ .wav、 .mp3 或 .wma 格式）。
***
![第二](../images/sfbcallout2.png)<br/>可选择对在营业时间呼入的呼叫做些什么。 可以从以下选项中进行选择：
*    **断开连接** 如果选择它，则呼叫人在听到营业时间问候语后被断开链接。
*    **重定向呼叫** 这可用来将呼叫自动发送至：
     *    拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。 可以通过此设置将呼叫发送至语音邮件。 为此，请选择 **公司人员** ，并将此人的呼叫设置为直接转到语音邮件。 <br/><br/>   
        > [!Note]
        > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010。 <br/><br/>

     *    **呼叫列队** 使用呼叫列队允许将呼叫传输至已设置好的现有呼叫列队。
     *    另一个 **自动助理** 可以使用现有自动助理创建一个包含子菜单的二级菜单选项。 称其为嵌套自动助理。
*    **播放菜单选项提示** 亦可用来设置希望播放的提示。
***
![第三](../images/sfbcallout3.png)<br/>**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。可以在 **呼叫者将听到**框中输入提示或录制音频文件并播报，例如"如需销售，请按或报 1。如需服务，请按或报 2。如需客户支持，请按或报 3。如需接线员，请按或报 0。如需重听此菜单，请按星号键或报'重复'。" **创建自定义提示** 如果选择此选项，应输入希望系统播报的文本（最多 1000 个字符）。 **上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。
***
![第四](../images/sfbcallout4.png)<br/>**按名称拨号** 如果选择此选项，将允许呼叫者使用目录搜索，搜索组织内的人员。 在 **拨号范围** 页面上设置这些选项便可为“按名称拨号”选择哪些作为可选人列出或者哪些不作为可选人列出。 使用“按名称拨号”可找到任何拥有 **电话系统** 许可证的联机用户或任何使用Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。<br/><br/>  

> [!WARNING]
> 使用“按名称拨号” **无法联系** 使用 Lync 2010 的本地托管用户。
***

![第五](../images/sfbcallout5.png)<br/>**编辑菜单选项** 使用键盘上的按键可以添加或者移除菜单选项。 若要添加菜单选项，按下键盘上相应的按键。 使用中的按键会改变颜色，下面会出现相应选项的行。 若要删除菜单选项，只需单击键盘上相应的按键，取消选择该按键。 将移除按键映射行。<br/><br/>  **提示：** 添加和移除选项时，需要单独更新菜单提示文本或重新录制音频文件，因为它不会自动更新现有菜单提示。  <br/><br/>  可以任何顺序添加和移除任何菜单选项，按键映射不必连续。 例如，可能创建一个将按键 0、 1 和 3 映射至选项的菜单，而没有使用按键 2 。<br/><br/> 

> [!NOTE]
> 按键 * （重复）和 # （回格）由系统保留，不能再分配。 如果已启用语音识别，按 * 将与语音命令“重复”对应，而按 # 则对应的是"后退"语音命令。


若要设置菜单选项，选择按键后，将需要： 
- **输入选项名称** 此字段最多可为 64 个字符，并且可以包含多个单词，如"客户服务"或"运营和土方"。 如果已启用语音识别，将自动识别名称，呼叫者将能够按 3、 即“三”，或者说"客户服务"，选择映射至 3 键的选项。 
- 下一步是如果按下了相应的按键，选择将呼叫发送至何处，或使用语音识别选择选项。 可以将呼叫发送至： 
    - **操作员** 如果已设置了操作员，它会自动映射至按键 0 ，但也可以将其删除或重新分配给不同的按键。 如果操作员没有设置给任何按键，语音命令“操作员”也将被禁止。 
    - 拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。 可以通过此设置将呼叫发送至语音邮件。 为此，请选择 **公司人员** ，并将此人的呼叫设置为直接转到语音邮件。<br/><br/> 
    
        > [!Note] 
        > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010。 <br/><br/>

    - **呼叫列队** 使用呼叫列队允许将呼叫传输至已设置好的现有呼叫列队。 
    - **自动助理** 可以使用现有自动助理创建一个包含子菜单的二级菜单选项。 称其为嵌套自动助理。<br/><br/>
    
        > [!Note]
        > 还将使用嵌套 （或二级）自动助理的 **营业时间** ，包括来自其他已设置自动助理的呼叫。         
   
### <a name="select-holidays-page"></a>选择假日页面 

可以为每个自动助理添加最多 20 个计划假日。
  
![在自动助理中设置假日](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**添加假日** 在 **假日名称** 字段中输入新假日的名称。<br/><br/> 假日名称可以包含最多 64 个字符，并且在同一自动助理中必须是唯一的。 例如，不能在同一自动助理中具有两个名为"感恩节"的假日。  
***
![第二](../images/sfbcallout2.png)<br/>**假日问候** 假日问候是可选项，可以设置为 **无** 。 在此情况下，在所选选项处理呼叫之前，呼叫者听不到消息或者问候语。 还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。
*    **无** 在有人呼叫自动助理电话号码时，将不播放问候语。
*    **创建自定义问候语** 如果选择此选项，输入希望系统朗读的文本 （最多 1000 个字符）。 例如，可以输入"新年快乐！ 我们的办事处当前未营业。" 在 **呼叫者将听到** 框中。
*    **上传音频文件** 如果选择此选项，则需要录制假日问候语并上传音频文件（ .wav、 .mp3 或 .wma 格式）。  
***
![第三](../images/sfbcallout3.png)<br/>**问候语之后对呼叫做些什么？** 可以选择对该假日期间到达的呼叫做些什么。 可以从以下选项中进行选择：
*    **断开连接** 呼叫者听到假日问候语以后被断开连接。
*    **重定向呼叫** 这可用来将呼叫自动发送至：
     *    拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员 **。 可以通过此设置将呼叫发送至语音邮件。 为此，请选择 **公司人员** ，并将此人的呼叫设置为直接转到语音邮件。 <br/><br/> 
     
         > [!Note] 
         > **公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。 不支持 Lync Server 2010。<br/><br/>

     *    **呼叫队列** 将呼叫传输至已设置的现有呼叫列队。
     *    另一个 **自动助理** ，创建一个包含子菜单的二级菜单选项。 称其为嵌套自动助理。 <br/><br/>
     
         > [!Note]
         > 默认方式，将假日期间到达的所有呼叫设置为听到问候语（如果有）后断开连接，所以如果希望有不同的反应，则必须指定重定向。

***
![第四](../images/sfbcallout4.png)<br/>**希望假日何时开始和结束？** 以 dd/mm/yyyy 格式，输入假日的开始日期，然后选择开始时间、结束日期和结束时间，如日期范围表中所提示。<br/><br/>可以为假日指定最多 10 个不同的日期范围。 例如，可以添加最多 10 年的除夕假日的日期范围。 假日可以有多天。<br/><br/>若要添加其他假日日期范围 （例如，下一年），单击 **添加另一个** ，然后输入一组新的假日起止日期。<br/><br/>亦支持嵌套假日。 例如，可以在一个“假日假期”时间段内嵌套多个假日： 
*    **12 月 24 日至 1 月 3 日：** “假日快乐！ 我们的办事处当前未营业。 我们将于 1 月 4 日恢复营业。"
*    **12 月 25:** "圣诞快乐！ 我们的办事处当前未营业。 我们将于 1 月 4 日恢复营业。"
*    **1 月 1:** "新年快乐！ 我们的办事处当前未营业。 我们将于 1 月 4 日恢复营业。"
   
保存自动助理后，假日出现在 **假日** 选项卡上，可在此编辑、添加或修改假日设置。
  
### <a name="select-dial-scope-page"></a>选择拨号范围页面

在此页面上，可以设置组织中的哪个用户将被列入目录，以及在有人呼叫组织时，组织中的哪个用户适合于“按名称拨号”。
  
![按名称拨号搜索的拨号范围。](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![第一](../images/sfbcallout1.png)<br/>使用 **包括** 选项，可以有两种选择：
*    **所有联机用户** 使用此选项允许将组织中的所有人包含在目录搜索中。 将列出拥有 **电话系统** 许可证的所有联机用户，以及使用 Skype for Business Server 2015 或者 Lync Server 2013 ，并在 Office 365 中拥有呼叫计划的本地托管用户。 
*    **自定义** 如果使用此选项，可以搜索 Office 365 组、通讯组列表或已在组织中创建的安全组，以及添加至此 Office 365 组、通讯组列表或安全组的人员，他们可能是 **拥有电话系统许可证的联机用户** 或者是使用 Skype for Business Server 2015 或 Lync Server 2013 的本地托管用户。 可以添加多个 Office 365 组、通讯组列表，以及安全组。 <br/><br/> 

    > [!Caution]
    > 当有人搜索使用“按名称拨号”的目录时，来自 Lync Server 2010 部署的本地户将不被列出。 
***
![第二](../images/sfbcallout2.png)<br/>使用 **排除** 选项，可以有两种选择：
*    **无** 使用此选项表示不会将任何联机用户从目录搜索中排除。 
*    **自定义** 如果使用此选项，则可以搜索 Office 365 组、通讯组列表或组织中已创建的安全组，并从目录搜索中排除所有添加至 Office 365 组、通讯组列表以及安全组的人员 可以添加多个 Office 365 组、通讯组列表，以及安全组。 <br/><br/> 

    > [!Caution]
    > 当有人搜索使用“按名称拨号”的目录时，来自 Lync Server 2010 部署的本地户将不被列出。          
   
> [!NOTE]
> 当有人使用语音识别的“按名称拨号”时，新用户的名称最长可能需要经过 36 小时才能在目录中列出。 
  
填写所有必填字段并设置呼叫处理菜单和选项后，单击 **保存** 。
  
## <a name="editing-and-testing-auto-attendants"></a>编辑并测试自动助理

保存自动助理后，自动助理将在 **自动助理** 页面列出。 这样便可以快速查看已经设置的某些选项，包括名称、电话号码、语言和状态。
  
若要对自动助理进行更改，请选择自动助理，然后在操作窗格中单击 **编辑** 。
  
还可以使用操作窗格中的 **测试** 按钮，向自动助理快速发起测试呼叫。
  
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

- Windows PowerShell  完全是关于管理用户内容以及有关哪些用户被允许或不被允许用户执行操作的内容。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
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
    
  
 
