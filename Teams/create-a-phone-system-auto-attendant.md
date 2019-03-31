---
title: 设置电话系统自动助理
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解如何设置和测试高效处理您的组织的呼叫的电话系统 (云 PBX) 自动助理。
ms.openlocfilehash: 32fbf066524ec73b6cfa683a493dc93c58932d7c
ms.sourcegitcommit: 355bcdafa58b6349bb6bc771054f4c9c91387a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013650"
---
# <a name="set-up-a-phone-system-auto-attendant"></a><span data-ttu-id="a7210-103">设置电话系统自动助理</span><span class="sxs-lookup"><span data-stu-id="a7210-103">Set up a Phone System auto attendant</span></span>

<span data-ttu-id="a7210-104">自动助理让人们呼叫您的组织和导航菜单系统，以使其向右部门、 队列、 人员或运算符呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7210-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="a7210-105">通过使用 Microsoft 团队管理中心，您可以为您的组织创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="a7210-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="a7210-106">若要创建新的自动助理，在左侧导航窗格中，转到**语音**，然后选择**自动助理** > **添加新**。</span><span class="sxs-lookup"><span data-stu-id="a7210-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="a7210-107">如果您想要了解有关自动助理的详细信息，请参阅[电话系统自动助理是什么？](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="a7210-107">If you want to learn more about auto attendants, see [What are Phone System auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="a7210-108">本文同时适用于 Microsoft 团队和 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="a7210-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>



## <a name="step-1---get-started"></a><span data-ttu-id="a7210-109">步骤 1-开始</span><span class="sxs-lookup"><span data-stu-id="a7210-109">Step 1 - Get started</span></span>

- <span data-ttu-id="a7210-110">自动助理需要具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="a7210-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="a7210-111">有关资源帐户的详细信息，请参阅[团队中的管理资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="a7210-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="a7210-112">如果您打算分配一个直接路由号，则需要获取并将以下许可证分配给资源帐户\(Office 365 企业版 E1、 E3 或 E5，与电话系统加载项\)。</span><span class="sxs-lookup"><span data-stu-id="a7210-112">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="a7210-113">如果要改用分配 Microsoft 服务号码，您需要获取并将以下许可证分配给资源帐户\(Office 365 企业版 E1、 E3 或 E5，与电话系统加载项调用规划\)。</span><span class="sxs-lookup"><span data-stu-id="a7210-113">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="a7210-114">现在您需要使用用户授权模型，Microsoft 的协作的应用程序云自动助理和呼叫的队列，如适当许可模型中。</span><span class="sxs-lookup"><span data-stu-id="a7210-114">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!CAUTION]
> <span data-ttu-id="a7210-115">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="a7210-115">To get and use toll-free phone numbers, you need to set up Communications Credits.</span></span> <span data-ttu-id="a7210-116">若要执行此操作，请参阅 [通信点数是什么？](what-are-communications-credits.md) 和 [为组织设置通信点数](set-up-communications-credits-for-your-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="a7210-116">To do this see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

> [!TIP]
> <span data-ttu-id="a7210-117">要重定向呼叫的运算符或联机用户与**电话系统**许可证的菜单选项，您将需要启用企业语音或分配给它们的调用计划在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="a7210-117">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them.</span></span> <span data-ttu-id="a7210-118">请参阅[业务许可证分配 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="a7210-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="a7210-119">你还可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a7210-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="a7210-120">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="a7210-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="a7210-121">第 2 步 - 创建新的自动助理</span><span class="sxs-lookup"><span data-stu-id="a7210-121">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7210-122">每个呼叫队列需要具有关联的[资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="a7210-122">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="a7210-123">您必须首先，创建资源帐户，然后将其向自动助理相关联。</span><span class="sxs-lookup"><span data-stu-id="a7210-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a7210-124">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="a7210-124">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a7210-125">在**Microsoft 团队管理中心**中，单击**语音** > **自动助理**，然后单击 **+ 新建**：</span><span class="sxs-lookup"><span data-stu-id="a7210-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="a7210-126">一般信息页</span><span class="sxs-lookup"><span data-stu-id="a7210-126">General info page</span></span>

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![第一](media/sfbcallout1.png)

<span data-ttu-id="a7210-129">**名称**输入自动助理的描述性的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a7210-129">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="a7210-130">此名称为必填字段，最多可以包含 64 个字符，其中包括空格。</span><span class="sxs-lookup"><span data-stu-id="a7210-130">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="a7210-131">此名称将显示在" **自动助理**"选项卡的" **名称**"列中。</span><span class="sxs-lookup"><span data-stu-id="a7210-131">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![第二](media/sfbcallout2.png)

<span data-ttu-id="a7210-133">**资源帐户**单击此按钮以选择要连接到您新建的自动助理的一个或多个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="a7210-133">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="a7210-134">所有的自动助理都需要有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="a7210-134">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="a7210-135">资源帐户可以具有电话号码关联到帐户，但它也可能不。</span><span class="sxs-lookup"><span data-stu-id="a7210-135">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="a7210-136">顶级自动助理将肯定会有一个资源具有帐户分配的电话号码，但 （用作的第一个级别的自动助理连接到的级别 2 菜单） 辅助自动助理可能轻松不具有电话号码分配给其资源帐户。</span><span class="sxs-lookup"><span data-stu-id="a7210-136">A top-level auto attendant would almost certainly would have a resource account with an assigned phone number, but a secondary auto attendant (used as a level 2 menu that the first level auto attendant connects to) might easily not have a phone number assigned to its resource account.</span></span>

* * *

![第三](media/sfbcallout3.png)

<span data-ttu-id="a7210-p108">**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。每个自动助理可以有不同的时区，为自动助理设置的营业时间将根据你在此处选择的时区进行设置。</span><span class="sxs-lookup"><span data-stu-id="a7210-p108">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization. Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![第四](media/sfbcallout4.png)

<span data-ttu-id="a7210-141">**语言** 从列出的可用语言列表中选择自动助理使用的语言。</span><span class="sxs-lookup"><span data-stu-id="a7210-141">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="a7210-142">您在此处设置的语言的自动助理将使用与进行交互到此自动助理，呼叫中的人员并所有系统播放提示时在这种语言的语言。</span><span class="sxs-lookup"><span data-stu-id="a7210-142">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

![第五](media/sfbcallout5.png)

<span data-ttu-id="a7210-144">**接线员** 此为可选字段，无须为自动助理设置。</span><span class="sxs-lookup"><span data-stu-id="a7210-144">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="a7210-145">但是，您可以设置呼叫中能够页符拖出菜单以帮助他们人讲话的人员**运算符**选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-145">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="a7210-146">键 0 自动分配给接线员。</span><span class="sxs-lookup"><span data-stu-id="a7210-146">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="a7210-147">如果您对此进行设置，还需要告知人员谁调用的这是在**营业呼叫处理**页中的**编辑菜单选项**可用选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-147">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="a7210-148">如果您在自动助理上设置运算符，您需要在**呼叫者收听**框中输入相应的提示文本或更改您的音频文件，以包括此选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-148">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="a7210-149">例如，"如需接线员，请按零"。</span><span class="sxs-lookup"><span data-stu-id="a7210-149">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="a7210-150">可以将以下项设置为接线员：</span><span class="sxs-lookup"><span data-stu-id="a7210-150">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="a7210-151">拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。</span><span class="sxs-lookup"><span data-stu-id="a7210-151">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="a7210-152">**公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="a7210-152">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="a7210-153">**呼叫队列**的设置。</span><span class="sxs-lookup"><span data-stu-id="a7210-153">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="a7210-154">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a7210-154">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="a7210-155">若要执行此操作，选择**您的公司的人员**并将此人的呼叫转接至语音邮件直接设置。</span><span class="sxs-lookup"><span data-stu-id="a7210-155">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![第六](media/sfbcallout6.png)

<span data-ttu-id="a7210-157">**启用语音输入**语音识别时选择此选项才可用。</span><span class="sxs-lookup"><span data-stu-id="a7210-157">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="a7210-158">呼叫中的人员可以使用[语言设置](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中的语音输入。</span><span class="sxs-lookup"><span data-stu-id="a7210-158">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="a7210-159">通过设置其关闭如果您想要仅允许使用其电话小键盘的人员，您可以禁用语音识别。</span><span class="sxs-lookup"><span data-stu-id="a7210-159">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="a7210-160">在完成时与您的选择，单击**next**。</span><span class="sxs-lookup"><span data-stu-id="a7210-160">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="a7210-161">营业页</span><span class="sxs-lookup"><span data-stu-id="a7210-161">Business hours page</span></span>

<span data-ttu-id="a7210-162">默认情况下，工作时间设置为到下午 5 点，周一到周五上午 9 点。</span><span class="sxs-lookup"><span data-stu-id="a7210-162">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="a7210-163">营业时间以外的所有时间为非营业时间。</span><span class="sxs-lookup"><span data-stu-id="a7210-163">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="a7210-164">您可以单击**选择 24/7**以使所有小时工作时间。</span><span class="sxs-lookup"><span data-stu-id="a7210-164">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="a7210-165">除非您选择**选择 24/7**选项，将使用**后小时呼叫设置**页上配置营业时间之后的自动助理的处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7210-165">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![第一](media/sfbcallout1.png)

<span data-ttu-id="a7210-168">默认情况下，工作时间设置为周一到周五上午 9:00 – 5:00。</span><span class="sxs-lookup"><span data-stu-id="a7210-168">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="a7210-169">选择**清除所有小时**选项，可取消选择日程表中的所有小时时间点。</span><span class="sxs-lookup"><span data-stu-id="a7210-169">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="a7210-170">当您选择**重置为默认**时，工作时间将重置为周一到周五上午 9:00 – 5:00。</span><span class="sxs-lookup"><span data-stu-id="a7210-170">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![第二](media/sfbcallout2.png)

<span data-ttu-id="a7210-172">要更改营业时间，请使用日历突出显示希望设置的营业时间。</span><span class="sxs-lookup"><span data-stu-id="a7210-172">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="a7210-173">日历允许您在 30 分钟的间隔，选择工作时间和营业时间您在此处选择将会根据设置在**常规信息**页设置的时区。</span><span class="sxs-lookup"><span data-stu-id="a7210-173">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="a7210-174">要设置休息时间（如午餐时间），请取消选择或通过拖动取消选择某段时间。</span><span class="sxs-lookup"><span data-stu-id="a7210-174">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="a7210-175">在工作时间内，您可以设置多个分页符。</span><span class="sxs-lookup"><span data-stu-id="a7210-175">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="a7210-176">在完成时与您的选择，单击**next**。</span><span class="sxs-lookup"><span data-stu-id="a7210-176">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="a7210-177">工作时间内呼叫设置</span><span class="sxs-lookup"><span data-stu-id="a7210-177">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="a7210-178">如果您使用自定义工作时间日程表，还需要设置使用**后小时呼叫处理**页上，这将使您与**营业呼叫设置**相同的选项的营业时间之后的处理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7210-178">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="a7210-179">您可以设置问候语和提示，菜单中向贵组织的自动助理电话号码的呼叫将听到工作时间内的人员。</span><span class="sxs-lookup"><span data-stu-id="a7210-179">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="a7210-180">![工作时间内呼叫处理。](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![呼叫处理继续进行的工作时间。](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="a7210-180">![Business hours call handling.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Business hours call handling continued.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![第一](media/sfbcallout1.png)

<span data-ttu-id="a7210-182">**问候语**营业时间问候语是可选的并且可以设置为**无问候语**。</span><span class="sxs-lookup"><span data-stu-id="a7210-182">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="a7210-183">在这种情况下，呼叫者将听到没有邮件或问候语之前选择的操作的某个处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7210-183">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="a7210-184">还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。</span><span class="sxs-lookup"><span data-stu-id="a7210-184">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="a7210-185">**没有问候语**人员连接到自动助理电话号码时，将播放没有问候语。</span><span class="sxs-lookup"><span data-stu-id="a7210-185">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="a7210-186">**上载音频文件**如果选择此，录制的问候语，然后上载音频文件 （以.wav、.mp3 或.wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="a7210-186">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="a7210-187">**键入的问候语消息**如果您选择此选项，输入您希望系统读取 （最多 1000年个字符） 的文本。</span><span class="sxs-lookup"><span data-stu-id="a7210-187">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="a7210-188">例如，可能会输入"欢迎来到 Contoso 。</span><span class="sxs-lookup"><span data-stu-id="a7210-188">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="a7210-189">您的呼叫对我们非常重要。"</span><span class="sxs-lookup"><span data-stu-id="a7210-189">Your call is important to us."</span></span> <span data-ttu-id="a7210-190">在 **呼叫者将听到** 框中。</span><span class="sxs-lookup"><span data-stu-id="a7210-190">in the **Callers will hear** box.</span></span>

* * *

![第二](media/sfbcallout2.png)

<span data-ttu-id="a7210-192">您可以选择到达工作时间内的呼叫会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="a7210-192">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="a7210-193">您可以选择执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a7210-193">You can chose from the following actions:</span></span>

- <span data-ttu-id="a7210-194">**断开连接**如果您选择它，将听到营业时间问候语后断开呼叫的人。</span><span class="sxs-lookup"><span data-stu-id="a7210-194">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="a7210-195">**重定向呼叫** 这可用来将呼叫自动发送至：</span><span class="sxs-lookup"><span data-stu-id="a7210-195">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="a7210-196">与**电话系统**许可证启用了企业语音或分配调用计划在 Office 365 中的**公司内的人员**。</span><span class="sxs-lookup"><span data-stu-id="a7210-196">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="a7210-197">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a7210-197">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="a7210-198">为此，选择**公司内的人员**，并设置此人要使其呼叫直接转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a7210-198">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="a7210-199">**公司中的人员**可联机用户或用户承载的本地业务服务器 2015年或 Lync Server 2013 中使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="a7210-199">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="a7210-200">另一个**自动助理**</span><span class="sxs-lookup"><span data-stu-id="a7210-200">Another **Auto attendant**</span></span>

   <span data-ttu-id="a7210-201">您可以使用现有的自动助理创建第二个级别的包含子菜单的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-201">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="a7210-202">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="a7210-202">These are called nested auto attendants.</span></span> <span data-ttu-id="a7210-203">若要将发送到嵌套的自动助理呼叫，请选择**公司内的人员**并分配资源帐户，或者是一个已关联的自动助理或将关联到自动助理完后创建的此自动助理。</span><span class="sxs-lookup"><span data-stu-id="a7210-203">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="a7210-204">**播放菜单选项**还可让您设置要播放的提示。</span><span class="sxs-lookup"><span data-stu-id="a7210-204">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![第三](media/sfbcallout3.png)

<span data-ttu-id="a7210-206">**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。</span><span class="sxs-lookup"><span data-stu-id="a7210-206">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="a7210-207">可以在**设置为呼叫者在菜单导航**框中键入提示符处，也可以记录的音频文件和说，例如:"Sales，说按或说 1。</span><span class="sxs-lookup"><span data-stu-id="a7210-207">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="a7210-208">如需服务，请按或报 2。</span><span class="sxs-lookup"><span data-stu-id="a7210-208">For Services, press or say 2.</span></span> <span data-ttu-id="a7210-209">如需客户支持，请按或报 3。</span><span class="sxs-lookup"><span data-stu-id="a7210-209">For Customer Support, press or say 3.</span></span> <span data-ttu-id="a7210-210">如需接线员，请按或报 0。</span><span class="sxs-lookup"><span data-stu-id="a7210-210">For the operator, press or say 0.</span></span> <span data-ttu-id="a7210-211">如需重听此菜单，请按星号键或报'重复'。</span><span class="sxs-lookup"><span data-stu-id="a7210-211">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="a7210-212">**键入的问候语消息**如果您选择此，您应输入您希望系统读取 （最多 1000年个字符） 的文本。</span><span class="sxs-lookup"><span data-stu-id="a7210-212">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="a7210-213">**上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="a7210-213">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![第四](media/sfbcallout4.png)

<span data-ttu-id="a7210-215">**菜单选项安装程序**可以添加或删除使用数字小键盘上键按钮的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-215">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="a7210-216">要添加菜单选项，请按 **+ 分配拨号键**。</span><span class="sxs-lookup"><span data-stu-id="a7210-216">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="a7210-217">下将显示的选项对应的行。</span><span class="sxs-lookup"><span data-stu-id="a7210-217">A corresponding row of options will appear below.</span></span> <span data-ttu-id="a7210-218">若要删除的菜单选项，只需单击左侧数字小键盘控件上的相应的键，然后单击上面的删除图标上。</span><span class="sxs-lookup"><span data-stu-id="a7210-218">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="a7210-219">将移除按键映射行。</span><span class="sxs-lookup"><span data-stu-id="a7210-219">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="a7210-220">您将需要更新菜单提示文本或重新添加到删除选项，因为它不会自动完成的现有菜单提示时单独录制音频。</span><span class="sxs-lookup"><span data-stu-id="a7210-220">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="a7210-221">任何菜单选项可以添加和删除任何顺序和关键映射不必是连续的。</span><span class="sxs-lookup"><span data-stu-id="a7210-221">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="a7210-222">很有可能，例如，使用键 0、 1 和 3 时不使用项 2 映射到选项，创建一个菜单。</span><span class="sxs-lookup"><span data-stu-id="a7210-222">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="a7210-223">注册表项\*（时可重复） 和\#（后） 保留由系统和不能重新分配。</span><span class="sxs-lookup"><span data-stu-id="a7210-223">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="a7210-224">如果已启用语音识别，按 \* 将"重复"与对应和 # 将对应的"后退"语音命令。</span><span class="sxs-lookup"><span data-stu-id="a7210-224">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="a7210-225">若要设置您菜单选项中，选择拨号密钥后，您将需要：</span><span class="sxs-lookup"><span data-stu-id="a7210-225">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="a7210-226">输入**语音命令**的选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-226">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="a7210-227">此地址可以是最多为 64 个字符，并且可以包含多个单词，如"客户服务"或"操作和可能导致。"</span><span class="sxs-lookup"><span data-stu-id="a7210-227">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="a7210-228">如果已启用语音识别，将自动识别名称，并呼叫的人将能够按 3、 说"3，"或者说"客户服务"，选择映射到 3 键选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-228">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="a7210-229">选择呼叫旨在发送如果按下了相应的键，或使用语音识别选择选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-229">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="a7210-230">可以将呼叫发送至：</span><span class="sxs-lookup"><span data-stu-id="a7210-230">The call can be sent to:</span></span>

  - <span data-ttu-id="a7210-231">**运算符**如果已设置运算符，它会自动映射到键 0，但它还能够删除或重新分配给不同的密钥。</span><span class="sxs-lookup"><span data-stu-id="a7210-231">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="a7210-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span><span class="sxs-lookup"><span data-stu-id="a7210-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="a7210-233">拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。</span><span class="sxs-lookup"><span data-stu-id="a7210-233">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="a7210-234">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a7210-234">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="a7210-235">要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a7210-235">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="a7210-236">**公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="a7210-236">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 
    - <span data-ttu-id="a7210-237">另一个**自动助理**</span><span class="sxs-lookup"><span data-stu-id="a7210-237">Another **Auto attendant**</span></span>

       <span data-ttu-id="a7210-238">您可以使用现有的自动助理创建第二个级别的包含子菜单的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-238">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="a7210-239">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="a7210-239">These are called nested auto attendants.</span></span> <span data-ttu-id="a7210-240">若要将发送到嵌套的自动助理呼叫，请选择**公司内的人员**并分配资源帐户，或者是一个已关联的自动助理或将关联到自动助理完后创建的此自动助理。</span><span class="sxs-lookup"><span data-stu-id="a7210-240">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="a7210-241">**工作时间**的嵌套 （或第二层） 自动助理还将使用，包括来自其他已设置的自动助理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7210-241">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![第五](media/sfbcallout5.png)

<span data-ttu-id="a7210-243">**按名称拨号**如果您选择此选项，这将使呼叫中的组织使用目录搜索中的人员搜索的人员。</span><span class="sxs-lookup"><span data-stu-id="a7210-243">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="a7210-244">在 **拨号范围** 页面上设置这些选项便可为“按名称拨号”选择哪些作为可选人列出或者哪些不作为可选人列出。</span><span class="sxs-lookup"><span data-stu-id="a7210-244">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="a7210-245">使用“按名称拨号”可找到任何拥有 **电话系统** 许可证的联机用户或任何使用Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="a7210-245">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.</span></span>


* * *

<span data-ttu-id="a7210-246">在完成时与您的选择，单击**next**。</span><span class="sxs-lookup"><span data-stu-id="a7210-246">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="a7210-247">假日呼叫设置</span><span class="sxs-lookup"><span data-stu-id="a7210-247">Holiday call settings</span></span>

<span data-ttu-id="a7210-248">可以为每个自动助理添加最多 20 个计划假日。</span><span class="sxs-lookup"><span data-stu-id="a7210-248">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="a7210-249">您可以在**组织范围的设置**屏幕 > **假日**创建假日，也可以创建其作为创建新的呼叫处理程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="a7210-249">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![在自动助理中设置假日](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![第一](media/sfbcallout1.png)

<span data-ttu-id="a7210-252">如果您已经创建了其他自动助理，您可能会看到一个选项，您可以使用或编辑到您在此列表的需要。</span><span class="sxs-lookup"><span data-stu-id="a7210-252">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="a7210-253">如果没有，您需要创建一个新的呼叫处理程序。</span><span class="sxs-lookup"><span data-stu-id="a7210-253">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="a7210-254">要添加新的呼叫处理程序，请单击 **+ 新建呼叫处理程序**。</span><span class="sxs-lookup"><span data-stu-id="a7210-254">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![假日设置在自动助理 （续）](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![第一](media/sfbcallout1.png)

<span data-ttu-id="a7210-257">在新窗口中，输入新的呼叫处理程序，在屏幕顶部的名称。</span><span class="sxs-lookup"><span data-stu-id="a7210-257">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![第二](media/sfbcallout2.png)

<span data-ttu-id="a7210-259">如果名称已在假日的**假日**的下拉列表中存在，则可以使用它。</span><span class="sxs-lookup"><span data-stu-id="a7210-259">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="a7210-260">如果尚不存在所需的假日名称，选择**创建新的假日**接的下拉列表和分配一个名称并在出现的新屏幕中新的假日的日期。</span><span class="sxs-lookup"><span data-stu-id="a7210-260">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="a7210-261">单击**保存**，准备好后。</span><span class="sxs-lookup"><span data-stu-id="a7210-261">Click on **Save** when ready.</span></span>

<span data-ttu-id="a7210-262">假日名称可以包含最多 64 个字符，并且在同一自动助理中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a7210-262">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="a7210-263">例如，不能在同一自动助理中具有两个名为"感恩节"的假日。</span><span class="sxs-lookup"><span data-stu-id="a7210-263">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![第三](media/sfbcallout3.png)

<span data-ttu-id="a7210-265">**问候语**问候语是可选的并且可以设置为**无问候语**。</span><span class="sxs-lookup"><span data-stu-id="a7210-265">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="a7210-266">在此情况下，在所选选项处理呼叫之前，呼叫者听不到消息或者问候语。</span><span class="sxs-lookup"><span data-stu-id="a7210-266">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="a7210-267">还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。</span><span class="sxs-lookup"><span data-stu-id="a7210-267">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="a7210-268">**没有问候语**人员连接到自动助理电话号码时，将播放没有问候语。</span><span class="sxs-lookup"><span data-stu-id="a7210-268">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="a7210-269">**上载音频文件**如果选择此，记录假日问候，然后将上载音频文件 （以.wav、.mp3 或.wma 格式）</span><span class="sxs-lookup"><span data-stu-id="a7210-269">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="a7210-270">**键入的问候语消息**如果您选择此选项，输入您希望系统读取 （最多 1000年个字符） 的文本。</span><span class="sxs-lookup"><span data-stu-id="a7210-270">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="a7210-271">例如，可以输入"新年快乐！</span><span class="sxs-lookup"><span data-stu-id="a7210-271">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="a7210-272">我们的办事处当前未营业。"</span><span class="sxs-lookup"><span data-stu-id="a7210-272">Our offices are currently closed."</span></span> <span data-ttu-id="a7210-273">在**问候语消息类型**框中。</span><span class="sxs-lookup"><span data-stu-id="a7210-273">in the **Type a greeting message** box.</span></span>

![第四](media/sfbcallout4.png)

<span data-ttu-id="a7210-275">**操作**您可以选择在该假日期间到达的呼叫会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="a7210-275">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="a7210-276">可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="a7210-276">You can chose from the following options:</span></span>

- <span data-ttu-id="a7210-277">**断开连接** 呼叫者听到假日问候语以后被断开连接。</span><span class="sxs-lookup"><span data-stu-id="a7210-277">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="a7210-278">**重定向呼叫** 这可用来将呼叫自动发送至：</span><span class="sxs-lookup"><span data-stu-id="a7210-278">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="a7210-279">拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 \*\*公司人员 \*\*。</span><span class="sxs-lookup"><span data-stu-id="a7210-279">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="a7210-280">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a7210-280">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="a7210-281">为此，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a7210-281">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="a7210-282">**公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="a7210-282">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 

  - <span data-ttu-id="a7210-283">**呼叫队列**将呼叫转接到您已设置现有呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="a7210-283">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="a7210-284">另一个**自动助理**创建第二个级别的包含子菜单的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-284">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="a7210-285">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="a7210-285">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="a7210-286">默认方式，将假日期间到达的所有呼叫设置为听到问候语（如果有）后断开连接，所以如果希望有不同的反应，则必须指定重定向。</span><span class="sxs-lookup"><span data-stu-id="a7210-286">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="a7210-287">"选择拨叫范围"页面</span><span class="sxs-lookup"><span data-stu-id="a7210-287">Select dial scope page</span></span>

<span data-ttu-id="a7210-288">在此页上，您可以设置您的组织中哪些用户将您的目录中列出和可用拨号按当某人向您的组织调用的名称。</span><span class="sxs-lookup"><span data-stu-id="a7210-288">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="a7210-290">![1 号](media/sfbcallout1.png)使用**包括**选项，您有两个选项：</span><span class="sxs-lookup"><span data-stu-id="a7210-290">![Number 1](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="a7210-291">**所有在线用户** 使用此选项可以将组织中的所有人包含在目录搜索中。</span><span class="sxs-lookup"><span data-stu-id="a7210-291">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="a7210-292">将列出拥有 **电话系统** 许可证的所有联机用户，以及使用 Skype for Business Server 2015 或者 Lync Server 2013 ，并在 Office 365 中拥有呼叫计划的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="a7210-292">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="a7210-293">**自定义用户组**如果您使用此选项，您可以搜索 Office 365 组、 通讯组列表或已在组织中的安全组的人员添加到此 Office 365 组、 通讯组列表或安全组属于任一**Online 用户电话系统许可证**或内部托管使用 Skype 业务服务器 2015年或 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a7210-293">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="a7210-294">您可以添加多个 Office 365 组、 通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="a7210-294">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![第二](media/sfbcallout2.png)

<span data-ttu-id="a7210-296">使用**排除**选项时，有两种：</span><span class="sxs-lookup"><span data-stu-id="a7210-296">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="a7210-297">**无** 使用此选项表示不会将任何在线用户从目录搜索中排除。</span><span class="sxs-lookup"><span data-stu-id="a7210-297">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="a7210-298">**自定义用户组**如果您使用此选项，您可以搜索 Office 365 组、 通讯组列表或安全组已在组织中创建和所有人员都添加到此 Office 365 组通讯组列表，或将从目录搜索中排除安全组。</span><span class="sxs-lookup"><span data-stu-id="a7210-298">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="a7210-299">您可以添加多个 Office 365 组、 通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="a7210-299">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="a7210-300">可能需要 36 小时的时间的新用户具有其目录中列出当有人使用拨号按名称语音识别的名称。</span><span class="sxs-lookup"><span data-stu-id="a7210-300">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="a7210-301">在输入所有必填的字段，并设置呼叫处理菜单和选项后，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="a7210-301">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="a7210-302">编辑和测试自动助理</span><span class="sxs-lookup"><span data-stu-id="a7210-302">Editing and testing auto attendants</span></span>

<span data-ttu-id="a7210-303">保存自动助理后，自动助理将在" **自动助理**"页面列出。</span><span class="sxs-lookup"><span data-stu-id="a7210-303">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="a7210-304">这将使您可以快速查看一些设置，包括名称、 电话号码、 语言和状态的选项。</span><span class="sxs-lookup"><span data-stu-id="a7210-304">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="a7210-305">如果您想要更改的自动助理，选择自动助理，，然后单击在操作窗格中的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a7210-305">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="a7210-306">在操作窗格中，使用**测试**按钮，可以还快速发出测试呼叫自动助理。</span><span class="sxs-lookup"><span data-stu-id="a7210-306">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="want-to-know-more"></a><span data-ttu-id="a7210-307">希望了解更多信息吗？</span><span class="sxs-lookup"><span data-stu-id="a7210-307">Want to know more?</span></span>

<span data-ttu-id="a7210-308">还可以使用 Windows PowerShell 来创建和设置自动助理。</span><span class="sxs-lookup"><span data-stu-id="a7210-308">You can also use Windows PowerShell to create and set up auto attendants.</span></span>

### <a name="auto-attendant-cmdlets"></a><span data-ttu-id="a7210-309">自动助理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="a7210-309">Auto attendant cmdlets</span></span>

<span data-ttu-id="a7210-310">以下是管理自动助理时需要使用的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a7210-310">Here are the cmdlets that you need to manage an auto attendant.</span></span>

- [<span data-ttu-id="a7210-311">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a7210-311">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csOrganizationalautoattendant?view=skype-ps)  
- [<span data-ttu-id="a7210-312">Set-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a7210-312">Set-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csOrganizationalautoattendant?view=skype-ps) 
- [<span data-ttu-id="a7210-313">Get-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a7210-313">Get-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csOrganizationalautoattendant?view=skype-ps) 
- [<span data-ttu-id="a7210-314">Get-CsOrganizationalAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a7210-314">Get-CsOrganizationalAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csOrganizationalautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="a7210-315">Remove-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a7210-315">Remove-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csOrganizationalautoattendant?view=skype-ps) 
- [<span data-ttu-id="a7210-316">New-CsOrganizationalAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="a7210-316">New-CsOrganizationalAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csOrganizationalautoattendantmenu?view=skype-ps) 
- [<span data-ttu-id="a7210-317">新 CsOrganizationalOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="a7210-317">New-CsOrganizationalOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [<span data-ttu-id="a7210-318">New-CsOrganizationalAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="a7210-318">New-CsOrganizationalAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOrganizationalAutoAttendantCallFlow?view=skype-ps) 
- [<span data-ttu-id="a7210-319">Export-CsOrganizationalAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a7210-319">Export-CsOrganizationalAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-Export-CsOrganizationalAutoAttendantHolidays?view=skype-ps) 
- [<span data-ttu-id="a7210-320">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="a7210-320">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [<span data-ttu-id="a7210-321">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="a7210-321">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [<span data-ttu-id="a7210-322">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="a7210-322">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [<span data-ttu-id="a7210-323">Get-CsOrganizationalAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="a7210-323">Get-CsOrganizationalAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsOrganizationalAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="a7210-324">New-CsOrganizationalAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="a7210-324">New-CsOrganizationalAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOrganizationalAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="a7210-325">Get-CsOrganizationalAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="a7210-325">Get-CsOrganizationalAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsOrganizationalAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="a7210-326">Import-CsOrganizationalAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a7210-326">Import-CsOrganizationalAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csOrganizationalautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="a7210-327">New-CsOrganizationalAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="a7210-327">New-CsOrganizationalAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a><span data-ttu-id="a7210-328">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="a7210-328">More about Windows PowerShell</span></span>

- <span data-ttu-id="a7210-329">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="a7210-329">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a7210-330">使用 Windows PowerShell，您可以管理 Office 365 和 Microsoft 团队使用单点管理，可以简化您的日常工作，如果您有多个要执行的任务。</span><span class="sxs-lookup"><span data-stu-id="a7210-330">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="a7210-331">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a7210-331">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="a7210-332">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="a7210-332">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="a7210-333">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7210-333">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="a7210-p145">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="a7210-p145">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="a7210-336">管理 Office 365 PowerShell 与 Office 365</span><span class="sxs-lookup"><span data-stu-id="a7210-336">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="a7210-337">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a7210-337">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="a7210-338">相关主题</span><span class="sxs-lookup"><span data-stu-id="a7210-338">Related topics</span></span>

[<span data-ttu-id="a7210-339">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="a7210-339">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="a7210-340">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="a7210-340">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="a7210-341">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="a7210-341">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="a7210-342">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a7210-342">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="a7210-343">什么是电话系统自动助理？</span><span class="sxs-lookup"><span data-stu-id="a7210-343">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="a7210-344">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="a7210-344">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  
