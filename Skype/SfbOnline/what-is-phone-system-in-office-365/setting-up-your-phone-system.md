---
title: 设置您的组织中的电话系统
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
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
description: '了解如何为组织设置电话系统 (云 PBX)。 '
ms.openlocfilehash: 26ffa60322c4b3f37b8f524c43efdf9a74cb1305
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501037"
---
# <a name="setting-up-phone-system-in-your-organization"></a>设置您的组织中的电话系统

下面是用于设置 Office 365 中的电话系统的分步指南。 其他详细信息的链接，可从每个步骤结束。  

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>步骤 1： 请确保您的国家或地区可用使用电话系统

1.  首先转到[音频会议和调用计划国家和地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)，并从页面顶部列表中选择您的国家或地区。 
2.  在**电话系统**，下查看的功能和详细信息的列表。 
3.  如果可用电话系统，转到步骤 2。 

**若要了解有关电话系统和音频会议的区域可用性的详细信息，请参阅[国家和地区音频会议和调用计划的可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>步骤 2： 购买和分配电话系统和调用规划许可证

若要将电话系统和调用规划许可证分配给单个用户的步骤是相同分配 Office 365 许可证。 请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 如果您想要分配批量的多个用户，请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步骤 3： 为用户获取电话号码

您可以设置用户在发起和接收电话呼叫贵组织中之前，必须获得这些电话号码。 

必须为用户获取号码的三种方法： 
- 使用 Skype for Business 管理中心获得新号码。
- 获取在业务管理中心的 Skype 中不可用的新号码。
- 端口或将您的现有号码从您的当前服务提供商或电话运营商转移到 Office 365。

必须使用**添加新用户号码**页上，请参阅、 搜索、 获取，并保留这些号码。 您可以通过国家/地区、 状态和市/县搜索，然后输入电话号码，您将需要为您的用户数。 

### <a name="get-new-user-phone-numbers"></a>获取新用户电话号码 
 
![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**

 
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在左侧导航窗格中转到**语音** > **电话号码**，单击**添加新号码**![添加按钮](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)，然后单击**新的用户数量**。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>获取在业务管理中心的 Skype 中不可用的新号码
  
有时 （根据您的国家/地区） 您将无法获取您的业务管理中心使用 Skype 的新号码。 在这种情况下，您需要下载窗体，并将其发送给我们。 请参阅[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，以了解如何请求新的用户数。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- 如果您的用户需要 999 或更少的电话号码，您可以业务管理中心的 Skype 中使用**新建本地号码端口次序**向导。 按照[传输到 Office 365 的电话号码](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)，以将您的电话号码，通过业务 online 转移到 Skype 中找到的步骤。
    
- 如果您需要端口超过 999 电话号码，请参阅[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)提交的端口顺序服务请求或顺序获取所有移植转移到 Office 365 这些电话号码。 

**有关获取新电话号码或转接现有号码的详细信息，请参阅[管理您的组织的电话号码](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md)。**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 4： 获取服务电话号码 （音频会议呼叫的队列，自动助理）

除了从 Office 365 用户获取电话号码，您可以搜索并获取收费电话或音频会议 （会议网桥）、 自动助理等呼叫队列 （也称为服务号码） 服务的免费电话号码。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，服务号码可以处理数百个呼叫同时，而用户的电话号码只能同时处理几个呼叫。

### <a name="get-new-service-numbers"></a>获取新服务号码

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**


1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在左侧导航窗格中转到**语音** > **电话号码** > **添加新号码**，然后单击**新服务号码**。
    
    > [!IMPORTANT] 
    > 要查看的左侧导航中的业务管理中心 Skype 中的**语音**选项，您必须先购买一个**电话系统**加载项许可证或一个**音频会议**加载项许可证至少一个**企业 E5 许可证**。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>获取在业务管理中心的 Skype 中不可用的新号码
  
有时 （根据您的国家/地区） 您将无法获取您的业务管理中心使用 Skype 的新号码。 在这种情况下，您需要下载窗体，并将其发送给我们。 请参阅[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，以了解如何请求新号码。 

### <a name="port-or-transfer-existing-service-numbers"></a>转网或转移现有服务号码

如果要转移来自当前服务提供商或运营商的服务号码，需要向 Microsoft 手动提交转网订单。 您必须提交单独端口订单将使用授权字母 (LOA) 转接您每种类型的服务号码 （收费和免费电话）。 在信函的授权 (LOA)，您必须选择了正确的服务号码类型。 当联系 Microsoft 支持，请确保您指定的传输服务号 （数字*和非用户或订阅者数字*），或并发呼叫容量可能无法足以处理呼叫量。 如果您想要转接电话号码，或执行其他操作与您的电话号码，请参阅[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>步骤 5： 如果您想要设置调用计划

如果您已关注了上述步骤，您已购买并分配电话系统和许可证和调用计划 （第 2 步） 并且收购的电话号码为用户 （第 3 步），因此您调用计划部分设置。 按照下面以完成安装您调用规划的三个过程。

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>添加紧急地址和您的组织的位置

1. 在**语音**页上选择**紧急位置** > **添加新地址**。
    
2. 在" **新址**"窗格中，输入你的地址名称，然后填写剩余框。
    
     ![When you enter a new emergency address, the formatting of the street name might cause an error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > [!提示] 对于英语客户，如果街道名称是数字，请务必在结尾加上"st"或"th"，如上图所示。 
  
3. 选择" **验证**"。
    
    如果需要，系统将提示你对地址进行更改。 
    
    > [!CAUTION]
    > [!警告] 验证街道或市镇地址涉及确保该地址是合法的并且格式设置正确。 则可能的部分正确的紧急地址，例如，如果您输入正确市/县的名称可能仍通过验证。 即使拼写错误并通过验证，拼错的城市名称和地址的其他正确部分相结合也足以将呼叫路由到合适的紧急派遣中心。 
  
    > [!TIP]
    > [!提示] 如果地址需要更正才能处理紧急响应，系统将显示一个绿色横幅，通知你地址已更新。 
  
4. 验证地址之后，请选择" **保存**"。
    
### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>为用户分配电话号码和紧急地址

> [!TIP]
> [!提示] 如果在执行此步骤前刚刚向企业添加了更多人员，这些人员可能需要 **几小时** 才会显示在" **语音用户**"页面。 系统存在延迟。
  
1. 在**语音用户**页中，选择要分配电话号码和紧急地址的人员。
    
2. 在"操作"窗格中，单击" **分配号码**"。
    
3. 在**分配号码**页上，在**选择要分配的号码**列表中，选择用户的电话号码。
    
4. 要选择的紧急地址，请在框中输入市/县的名称，并选择**搜索**。
    
    > [!IMPORTANT]
    > 如果您在美国以外，您的号码已有的紧急地址，但您可以立即更改。 请参阅[为用户分配或更改紧急地址](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md)。 
  
5. 在分配电话号码和紧急地址之后，选择" **保存**"。
    
### <a name="tell-your-users-about-their-new-phone-numbers"></a>有关其新的电话号码告知您的用户


我们建议通过发送邮件或使用企业的首选通信方式，将新电话号码告知用户。 

下面是如何能够看到其**Skype 的业务**应用程序中的电话号码：
  
1. 登录到桌面上的 Skype for Business。
    
2. Choose **Settings** > **Tools** > **Options**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 然后，选择" **电话**"。 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
在**Microsoft 团队**中，用户可以看到他们的电话号码，通过单击左侧导航窗格中的**呼叫**。 拨号盘上方显示的电话号码。

![通过单击左侧导航窗格中的呼叫，用户可以看到中的 Microsoft 团队其号码。](../images/teams-phone-number.png)

**有关所有设置调用规划所涉及的步骤的详细信息，请参阅[Set up 调用计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)。**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>步骤 6： 如果您想要设置音频会议

有时，组织中的用户需要使用电话拨入会议。 商业和 Microsoft 团队的 Skype 包括刚这种情况下的音频会议功能 ！ 人员可以呼叫 Skype 使用电话，而不使用 Skype 为移动设备或 PC 上的业务或 Microsoft 团队应用程序的业务或 Microsoft 小组会议。 
  
您只需为建立音频会议计划安排或潜在顾客会议的人员。 拨入会议与会者不需要任何许可证分配给他们或其他设置。
  
有关音频会议的常见问题进行了问题，请参阅[音频会议的常见问题](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md)。
    
1. 如果您购买**音频会议**加载项许可证和 Communications 字幕式许可证，请将其过分配。 有关说明，请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

    音频会议提供商决定。 音频会议提供商提供音频会议桥。 会议桥设置您的电话拨入电话号码、 Pin 和会议的会议 Id。 决定是否使用 Microsoft 或第三方音频会议提供商： 

    > [!NOTE]
    > Microsoft 团队用户不能用户第三方音频会议提供商。 
  
    - **Microsoft 作为您的音频会议提供商**： 如果您希望为音频会议的最简单的解决方案，选择 Microsoft 作为您的音频会议提供商。
    
    - **第三方音频会议提供商作为**： 如果您在其中不可用的 Office 365 中的音频会议、 服务质量不好由于其位置，或您具有现有合同国家/地区，请选择第三方音频会议提供商。 要查找的提供程序，请转到[Microsoft 可以准确找到](http://go.microsoft.com/fwlink/?LinkId=797530)。
 
2.  将音频会议提供商分配给领导或安排会议的人员。 请参阅[分配 Microsoft 作为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。

3. 设置会议邀请。 以下步骤是可选的但大量 admins 要执行这些操作： 
  
    1. [自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。 为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。 但是，您可以添加您自己的帮助和法律链接、 短信和小公司图形。
    
    2. [音频会议的电话号码的会议组织者的都包含在邀请的设置](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)。 这是将显示在由用户安排的会议的电话号码。
    
    3. [设置为音频会议自动助理语言](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)的音频会议自动助理使用问候时它们拨入音频会议电话号码的呼叫者。 此步骤仅适用如果您使用 Microsoft 作为您的音频提供商。
    
    4. [设置音频会议的 PIN 长度](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md)。
    
    > [!NOTE]
    > 此功能尚不适用于客户由在中国 21Vianet 使用的 Office 365 操作。 若要了解详细信息，请参阅[了解 Office 365 由 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)。 

**有关音频会议的详细信息，请参阅[设置音频会议](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)。**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>步骤 7： 如果您想要设置电话系统呼叫队列

队列包括问候语有人呼叫您的组织、 能够自动将呼叫置于保持状态，和搜索处理该呼叫的人员时的下一个可用呼叫代理的功能电话号码时所使用的电话系统呼叫者保留音乐侦听呼叫。 您可以为组织创建单个或多个呼叫的队列。

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. 获得收费电话或免费电话服务电话号码后，他们会显示在**业务管理中心的 Skype** > **语音** > **电话号码**，并列出**Service-作为免费电话**号码类型**列出将**. 若要获取服务号码，请参阅[Getting 服务电话号码的业务和 Microsoft 团队的 Skype](getting-service-phone-numbers.md)或如果您希望进行传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您在美国以外，您无法使用业务管理中心的 Skype 获取服务号码。 转到[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)而是以了解如何执行从美国的外部。

若要创建新的呼叫队列，**业务管理中心的 Skype**中，单击**呼叫**路由 > **呼叫队列**，请单击**添加新**，然后按照在**步骤 3**中[创建电话系统呼叫队列]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue)的说明。

**有关呼叫队列的详细信息，请参阅[创建电话系统呼叫队列](create-a-phone-system-call-queue.md)。**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>步骤 8： 如果您想要设置电话系统自动助理

自动助理让人们呼叫您的组织和导航菜单系统，以使其向右部门、 队列、 人员或运算符呼叫。 使用适用于业务管理中心 Skype，可以为组织创建自动助理。 

若要创建新的自动助理，业务管理中心的 Skype 中，单击**呼叫**路由 > **自动助理**，单击**添加新**，然后按照的电话系统自动设置的[设置的**步骤 2**中每一页的说明attendant](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant)。

**有关电话系统自动助理的详细信息，请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 9： 分配服务电话号码 （音频会议呼叫的队列，自动助理）

从**上面的步骤 4**您服务号码后，您需要将其分配给每种类型的所需的服务。 例如，如果您希望专用的服务电话号码 (收费电话或免费)，您将需要分配的会议桥的数量。

- 音频会议，您可以分配专用的号码的会议桥，转到**Office 365 管理中心** > **管理中心** > **for Business 的 Skype** > **音频会议**和单击会议桥或通过查看[更改的收费电话或音频会议网桥上的免费电话号码](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

- 自动助理，您可以分配专用的号码到自动助理，转到**Office 365 管理中心** > **管理中心** > **for Business 的 Skype** > **呼叫路由** > **自动助理**，单击的自动助理。 在**常规**页已将**电话号码**中列出的服务号码下拉列表中。 有关详细信息，请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。

- 对于呼叫的队列，您可以分配专用的号码呼叫队列，转到**Office 365 管理中心** > **管理中心** > **for Business 的 Skype** > **呼叫路由** > **呼叫队列**，并单击呼叫队列中。 在**常规**页已将**电话号码**中列出的服务号码下拉列表中。 有关详细信息，请参阅[创建电话系统呼叫队列](create-a-phone-system-call-queue.md)。

**有关获取新服务号码和移植现有服务号码的详细信息，请参阅[Getting 服务电话号码](getting-service-phone-numbers.md)。**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>步骤 10： 为您的组织的通信字幕式设置

您需要设置 Communications 字幕式，如果您想要使用 Skype 业务和 Microsoft 团队免费电话号码。 此外，我们建议您设置 Communications 字幕式调用计划 （国内或国际） 和音频会议用户需要拨出**任何目标**的能力。 多个国家/地区内包括在内，但某些目标不能包含在您调用规划或音频会议的订阅。 如果您不会设置 Communications 字幕式帐单且将**Communications 字幕式**许可证分配给用户，并且您运行出分钟，以便您的组织 （具体取决于您调用计划或音频会议中计划国家/地区），这些用户将无法发起呼叫或从音频会议拨出。 您可以获取详细信息，请通过读取资金数量，包括建议[Communications 字幕式是什么？](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> 若要找出如何它的价格，[请参阅下面的速率](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。 

### <a name="to-set-up-communications-credits"></a>若要设置 Communications 字幕式 

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在 Office 365 管理中心的左侧导航窗格中，转到**帐单** > **订阅** > **加载项** > **购买加载项**，然后选择**Communications 字幕式** > **立即购买**。
    
3. 在**Communications 字幕式**订阅页中，填写您的信息，然后单击**下一步**。
        
4. 输入您的付款信息并单击**下订单**。
    >[!IMPORTANT]
    >如果您是批量许可客户，您可以选择付款您企业协议的编号。 如果您有多个企业协议号码，您将能够选择您希望用于付款的企业协议。 您还将提供指定要将与企业协议编号 （如果适用） 相关联的采购订单号码机会。
    
**有关 Communications 字幕式设置的详细信息，请参阅[设置为您的组织的通信字幕式](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。**
  
### <a name="assign-a-communications-credits-license-to-users"></a>将通信字幕式许可证分配给用户

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在 Office 365 管理中心的左侧导航窗格中，转到**用户** > **活动用户**，然后从列表中选择一个用户。
    
3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。
    
4. 在**产品许可证**页上，切换到**在上**分配此许可证， **Communications 字幕式**，然后单击**保存**。
    
    > [!NOTE]
    > 即使已经分配一个**企业 E5**许可证的用户，仍建议您这样做。

**若要了解有关分配 Communications 字幕式许可证的详细信息，请参阅[设置为您的组织的通信字幕式](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。**

## <a name="related-topics"></a>相关主题
[Office 365 中的电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 