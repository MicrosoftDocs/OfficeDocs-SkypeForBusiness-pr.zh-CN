---
title: "设置电话系统自动助理"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c

description: "Learn how to set up and test Phone System (Cloud PBX) auto attendents for efficient call handling for your organization. "
---

# 设置电话系统自动助理

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](6fc2687c-0abf-43b8-aa54-7c3b2a84b67c.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/6fc2687c-0abf-43b8-aa54-7c3b2a84b67c) 中查找本文的英文版本以便参考。
  
自动助理让呼叫进入您的组织和导航菜单系统以向右部门获得它们，请致电队列、 人员或运算符的人员。通过使用 for Business 管理中心中的 Skype，您可以为您的组织创建自动助理。若要创建新的自动助理，在左侧导航中，转到 **呼叫路由**，选择 **自动助理**> **添加新**。
  
如果您想要了解有关自动助理的详细信息，请参阅[电话系统自动助理是什么？](what-are-phone-system-auto-attendants.md)。
  
## 第 1 步 - 开始

- 您可以创建和设置自动助理之前，您需要获取或将现有收费或免费服务传输数字。熟悉收费或免费服务编号之后，它们将显示在 **Skype for Business 管理中心**> **语音**> **电话号码**的页面。以获取您的服务号码，请参阅[获取 Skype for Business 服务电话号码](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)，或如果您希望的传输和现有服务号码，请参阅[将电话号码转移到 Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。无法将 **用户 （订阅服务器）** 号码分配给自动助理。如果您是在美国以外，您不能使用 Skype for Business 管理中心获取服务编号;转[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)相反。
    
    > [!CAUTION]
    > 若要获取并使用免费电话号码，您需要设置通信贷项。若要执行此，请参阅[什么是通信贷项？](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)和[为您的组织设置通信贷项](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。 
  
- 企业版 E3 与 **电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低）。 将被分配的 **电话系统**的用户许可证数影响的服务号码可用于自动助理。您可以自动助理的数字，取决于您的组织中分配的数字 **电话系统**和 **音频会议**许可证。若要了解有关许可，转[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
    > [!TIP]
    > 要重定向呼叫转接到的运算符或联机用户与 **电话系统**许可证的菜单选项，您将需要启用企业语音或为其分配致电 Office 365 中计划。请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。您还可以使用 Windows PowerShell。例如运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`。 
  
## 第 2 步 - 创建新的自动助理

在 **Skype for Business 管理中心**，单击" **呼叫路由**">" **自动助理**"，然后单击" **新增**"：
  
### "编辑常规信息"页面

在 **编辑常规信息**页上：
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
|||
|:-----|:-----|
|**1** <br/> |**名称**输入自动助理的描述性的显示名称。该名称是必需的并且可以包含多达 64 个字符，包括空格。它将在 **自动助理**选项卡上的 **名称**列中列出。  <br/> |
|**2** <br/> |**电话号码**此设置是可选的。如果您愿意，选择自动助理的电话号码。您可以选择任何可用的服务收费电话或您拥有您的组织的免费电话号码。如果没有列出的电话号码，您将需要获取服务收费或免费电话号码。转[获取 Skype for Business 服务电话号码](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)可以获得它们。  <br/> > [!NOTE]> **用户（订阅者）** 的号码不能分配给自动助理。          |
|**3** <br/> |**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。每个自动助理可以有不同的时区，为自动助理设置的营业时间将根据你在此处选择的时区进行设置。 <br/> |
|**4** <br/> |**语言**选择要用于从任何可用语言列出您自动助理的语言。在此处设置的语言是自动助理将使用与进行交互此自动助理，拨入的人员和所有系统提示将都播放该语言的语言。  <br/> |
|**5** <br/> |**语音识别**语音识别器可用，如果选择此选项。拨入的人员可以在您设置的语言使用语音输入。您可以通过清除如果您希望仅允许用户使用其电话键盘禁用语音识别。  <br/> |
|**6** <br/> |**运算符**这是可选的不需要设置为自动助理。但是，您可以设置拨入用户能够利用菜单以对某位人员以帮助他们说话中断的人员的 **运算符**选项。  <br/>  键 0 自动分配给接线员。 <br/>  如果您对此进行设置，您还需要告诉人们谁呼叫，因为这是 **营业时间呼叫处理**页面上的可用选项中 **编辑菜单选项**。如果您设置自动助理运算符，您将需要的 **呼叫者将听到**框中输入相应的提示文本或更改您的音频文件，以包含此选项。例如，"为运算符，按零。"  <br/>  可以将以下项设置为接线员： <br/>  与 **电话系统**许可证已启用企业语音或分配致电 Office 365 中计划 **您所在公司的人员**。  <br/> > [!NOTE]> **您所在公司的人员**可以联机用户或用户托管本地使用 Skype for Business Server 2015 或 Lync Server 2013。不支持 Lync Server 2010。            已设置的 **呼叫队列**。  <br/>  您可以设置它以便呼叫的人将被发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，然后设置此人的呼叫转移直接向语音邮件。  <br/> |
   
### "选择营业时间"页面

默认情况下，营业时间是设置为每周 7 天的 24 小时，以便所有小时被都视为营业时间。所有的小时数不包括的营业时间被视为后营业时间。如果您选择的 **自定义**选项并设置营业时间，然后将您可以在其中配置的呼叫处理业务小时后的自动助理添加新页面 **后小时呼叫处理**调用。
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)
  
|||
|:-----|:-----|
|**1** <br/> |选择" **自定义**"选项可在日历中选择特定的营业时间。选择" **自定义**"后，默认情况下将营业时间设置为周一至周五，上午 9:00 - 下午 5:00。  <br/> |
|**2** <br/> |若要更改工作时间，突出显示营业时间您想要使用日历设置。日历允许您选择在 30 分钟的时间间隔，营业时间并营业时间您在此处选择将设置基于您在 **常规信息**页设置的时区上。若要设置分页符 （例如，午餐符），请取消选中，或拖动以取消选中日历上的时间。业务小时内，您可以设置多个分页符。  <br/> |
   
### 选择营业时间呼叫处理页面

> [!TIP]
> 如果使用自定义营业时间表，则还需要设置非营业时间的呼叫处理方式。将增加一个" **非营业时间呼叫处理**"页面以便你配置这些选项，此页面提供的选项与设置" **营业时间呼叫处理**"的选项相同。 
  
您可以设置问候语、 提示和菜单在您的组织的自动助理的电话号码的呼叫将听到在工作时间内的人员。
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
|||
|:-----|:-----|
|**1**|**公司问候语** 营业时间问候语是一项可选设置，可以设置为" **无**"。在这种情况下，在所选择的某个选项对呼叫进行处理之前，呼叫者不会听到任何消息或问候语。你也可以上载音频文件（.wav, .mp3 或 .wma 格式）或使用文本到语音转换创建自定义问候语。 **无**当用户呼叫进入的自动助理的电话号码，则将播放没有问候语。 **创建自定义问候语**如果您选择此选项，输入所需的系统 （最多 1000年个字符） 阅读的文本。例如，您可以输入"欢迎康浦。您的呼叫对我们很重要。"的 **呼叫者将听到**框中。 **上载音频文件**如果选择此，录制问候语，然后上载您音频 （.wav, .mp3 或.wma 文件格式的文件）。 |
|**2**| 您可以选择在工作时间内收到的呼叫会发生什么情况。您可以从以下选项中进行选择： **断开连接** 如果选择此选项，呼叫者将在听到营业时间问候语之后断开连接。 **重定向呼叫** 此选项可用于将呼叫自动发送到： 与 **电话系统**许可证已启用企业语音或分配致电 Office 365 中计划 **您所在公司的人员**。您可以设置它以便呼叫的人发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，然后设置其呼叫转接到语音邮件直接此人。 > [!NOTE]> **您所在公司的人员**可以联机用户或用户托管本地使用 Skype for Business Server 2015 或 Lync Server 2013。不支持 Lync Server 2010。           **呼叫队列** 使用"呼叫队列"可以将呼叫转接给已设置好的现有呼叫队列 其他 **自动助理** 可以使用现有自动助理来创建包含子菜单的二级菜单选项。这称为嵌入式自动助理。 **播放菜单选项提示** 可用于设置你希望播放的提示。|
|**3**|**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。可以在 **呼叫者将听到**框中输入提示或录制音频文件并播报，例如"如需销售，请按或报 1。如需服务，请按或报 2。如需客户支持，请按或报 3。如需接线员，请按或报 0。如需重听此菜单，请按星号键或报'重复'。" **创建自定义提示** 如果选择此选项，应输入希望系统播报的文本（最多 1000 个字符）。 **上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。|
|**4**|**按名称拨号**如果您选择此选项，这将使呼叫中搜索的人员使用目录搜索您组织中的人员。您可以选择哪些人将列为可用或不可用的拨号按名称通过设置 **以拨打范围**页面上的这些选项。任何 online 用户与 **电话系统**许可证或任何用户托管本地使用 Skype for Business Server 2015 或 Lync Server 2013，可以找到与拨按名称。> [!CAUTION]> 用户托管本地拨按名称与使用 Lync 2010 **不能访问** 。          |
|**5**|**编辑菜单选项**可以添加或删除通过使用键盘上的关键按钮菜单选项。要添加一个菜单选项，请按键盘上的对应的键。使用中的键将更改的颜色和选项的对应行下方将显示。若要删除的菜单选项，只需单击键盘控件将其取消选中此项对应的键。将删除密钥映射行。> [!TIP]> 您必须更新菜单提示文本或重新添加到删除选项，因为它不会自动完成的现有菜单提示时单独录制音频。           可以添加和删除任何顺序任何菜单选项和键映射不必是连续。很可能，例如，若要使用键 0、 1 和 3 而不使用密钥 2 映射选项，请创建一个菜单。> [!NOTE]> 键 * （重复） 和 # （后退） 由系统保留和不能重新分配。如果已启用语音识别，按 * 将对应的"重复"，并且 # 将对应的"重回"语音命令。           |
|| 要设置菜单选项，选择键后，需要： **输入选项的名称** 这可以是最多 64 个字符，并可以包含多个字词，例如"客户服务"或"操作以及可能导致。"如果已启用语音识别，该名称会自动识别，和拨入的人员将能够按 3、 假设"3，"或者说"客户服务"，选择映射到键 3 选项。 下一步是选择在按下相应的键后或使用语音识别选中选项后，将呼叫发送到的目的地。可以将呼叫发送到： **运算符**如果已设置运算符，它会自动映射到键 0，但还可以将被删除或重新分配给不同的密钥。如果运算符未设置为任何键，然后将太禁用"运算符"中的语音命令。  与 **电话系统**许可证已启用企业语音或分配调用规划 Office 365 中 **您所在公司的人员**。您可以设置它以便呼叫的人发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，然后设置其呼叫转接到语音邮件直接此人。 > [!NOTE]> **您所在公司的人员**可以联机用户或用户托管本地使用 Skype for Business Server 2015 或 Lync Server 2013。不支持 Lync Server 2010。           **呼叫队列**使用呼叫队列选项允许呼叫转移到已经设置了现有呼叫队列。 **自动助理** 可以使用现有自动助理来创建包含子菜单的二级菜单选项。这称为嵌入式自动助理。> [!NOTE]>  嵌套 （或第二级） 自动助理 **营业时间**还将使用，包括从已设置其他自动助理发送呼叫。           |
   
### 选择假日页面 （适用于仅预览客户）

您可以将最多 20 的计划的假日添加到每个自动助理。
  
![Setting up Holidays in auto attendant](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
|||
|:-----|:-----|
|**1**|**添加假日** **假日名称**字段中输入新的假日的名称。假日名称可能包括最多 64 个字符，并且必须是唯一的相同的自动助理。例如，不能具有相同的自动助理中名为"感恩节"的两个假日。|
|**2**|**问候语假日**节日问候语是可选的可以设置为 **无**。在这种情况下，呼叫者将听到任何邮件或问候语之前呼叫由您选择的选项之一。您也可以上载音频文件 （在.wav、 mp3 或.wma 格式） 或创建自定义问候语使用文本到语音转换。 **无**当用户呼叫进入的自动助理的电话号码，则将播放没有问候语。 **创建自定义问候语**如果您选择此选项，输入所需的系统 （最多 1000年个字符） 阅读的文本。例如，您可以输入"新年 ！我们办公室当前已关闭。" **呼叫者将听到**框中。 **上载音频文件**如果选择此，录制假日问候语，然后上载您音频 （.wav, .mp3 或.wma 文件格式的文件）。 |
|**3**|**问候语之后对呼叫有何影响？**您可以选择此假日期间到达呼叫会发生什么情况。您可以从以下选项中进行选择： **断开连接**呼叫的人将听到节日问候后断开连接。 **重定向呼叫** 此选项可用于将呼叫自动发送到： 与 **电话系统**许可证已启用企业语音或分配致电 Office 365 中计划 **您所在公司的人员**。您可以设置它以便呼叫的人发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，并设置其呼叫转接到语音邮件直接此人。 > [!NOTE]> **您所在公司的人员**可以联机用户或用户托管本地使用 Skype for Business Server 2015 或 Lync Server 2013。不支持 Lync Server 2010。            若要将呼叫转接到您已经建立的现有呼叫队列 **呼叫队列** 其他 **自动助理**，若要创建第二个级别的包含子菜单的菜单选项。这些称为嵌套的自动助理。 > [!NOTE]>  默认情况下，设置抵达节假日期间的所有电话如果需要不同的行为，必须指定重定向，以便断开连接后的问候语 （如果有）。          |
|**4**|**执行所需的假日开始和结束？**Dd/mm/yyyy 格式，输入您的假日开始日期，然后选择开始时间、 结束日期和结束时间日期范围表中的提示。为假日，您可以指定最多 10 个不同的日期范围。例如，您可能最多为 10 年除夕节假日添加日期范围。 节日可以跨多天。若要添加其他假日日期范围 （例如下, 一年） 的单击 **添加另一个**，然后输入一组新的假日的开始和结束日期。嵌套的假日也受支持。例如，可以嵌套在一个"假日分页符"时间段内的多个假日： **·通过月 3 日 12 月 24:** "快乐假日 ！我们办公室当前已关闭。我们将重新打开上年 1 月 4 日。" **·12 月 25:** "圣诞 ！我们办公室当前已关闭。我们将重新打开上年 1 月 4 日。" **·1 月 1 日：** "新年 ！我们办公室当前已关闭。我们将重新打开上年 1 月 4 日。"|
   
保存您的自动助理后，您的假日将显示 **假日**选项卡，在其中编辑、 添加或修改假日设置。
  
### "选择拨叫范围"页面

在此页面上，您可以设置您的组织中的用户将列出您的目录中且可用于拨按时向您的组织呼叫的人员的名称。
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
|||
|:-----|:-----|
|**1** <br/> | 使用" **包括**"选项时，可以从两个选项中选择：  <br/> **所有联机用户**使用此选项允许所有人在您的组织，包括在目录搜索。与 **电话系统**许可证，以及用户的所有联机用户托管本地使用 Skype for Business Server 2015 或 Lync Server 2013 拥有调用计划在 Office 365 中，将会列出。  <br/> **自定义**如果您使用此选项，您可以搜索 Office 365 组、 通讯组列表或已创建您的组织中的安全组的人员添加到此 Office 365 组、 通讯组列表或安全组处于任一 **Online 用户与 电话系统许可证** 或托管的本地使用 Skype for Business Server 2015 或 Lync Server 2013。您可以添加多个 Office 365 组、 通讯组列表和安全组。 <br/> > [!CAUTION]>  部署 Lync Server 2010 的本地用户不会按名称如果某人搜索目录中使用拨列出。          |
|**2** <br/> | 使用" **排除**"选项时，可以从两个选项中选择：  <br/> **无** 使用此选项表示不会将任何在线用户从目录搜索中排除。 <br/> **自定义**如果您使用此选项，您可以搜索 Office 365 组、 通讯组列表或已创建您的组织中的安全组和所有人都添加到 Office 365 该组，通讯组列表，或将从目录搜索中排除的安全组。您可以添加多个 Office 365 组、 通讯组列表和安全组。  <br/> > [!CAUTION]>  部署 Lync Server 2010 的本地用户不会按名称如果某人搜索目录中使用拨列出。          |
   
> [!NOTE]
> 可能需要多达 36 小时，为新用户具有其目录中列出用户使用拨号时按名称语音识别的名称。 
  
输入所有必需的字段并设置呼叫处理菜单和选项后，单击 **保存**。
  
## 编辑和测试自动助理

保存您的自动助理后，它将 **自动助理**页面上列出。这样，您可以快速查看一些您已经设置了，包括名称、 电话号码、 语言和状态的选项。
  
如果您想要更改为自动助理，选择自动助理，，然后单击在操作窗格中的 **编辑**。
  
通过使用操作窗格中的 **测试**按钮，您可以快速将自动助理测试呼叫。
  
## 希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置自动助理。
  
### 自动助理 cmdlet

以下是管理自动助理时需要使用的 cmdlet。
  
||||
|:-----|:-----|:-----|
|[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedTimeZone]( https://technet.microsoft.com/en-us/library/mt796483.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx ) <br/> |
|[Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx) <br/> |[New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx) <br/> |
|[Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx) <br/> |[New-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx ) <br/> |
|[Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx) <br/> |[New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx ) <br/> |[New-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx) <br/> |
|[New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx ) <br/> |
|[导出 CsOrganizationalAutoAttendantHolidays （仅适用于预览客户）](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[获取 CsOrganizationalAutoAttendantHolidays （仅适用于预览客户）](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[导入 CsOrganizationalAutoAttendantHolidays （仅适用于预览客户）](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) <br/> |
|[新建 CsOnlineDateTimeRange （仅适用于预览客户）](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) <br/> |||
   
### 有关 Windows PowerShell 的详细信息

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

