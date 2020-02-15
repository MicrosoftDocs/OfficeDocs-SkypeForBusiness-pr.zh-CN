---
title: Lync Server 2013：使用 Lync-Skype 连接作为最终用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df22148fae23e0872fc9f33a54792590b634f46d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="019bf-102">在 Lync Server 2013 中使用 Lync Skype 连接作为最终用户</span><span class="sxs-lookup"><span data-stu-id="019bf-102">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="019bf-103">_**上次修改的主题：** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="019bf-103">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="019bf-104">Lync-Skype 连接使 Skype 用户和 Lync 用户能够将彼此添加为联系人、exchange 即时消息并进行音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="019bf-104">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="019bf-105">当 Skype 用户添加 Lync 用户时，Skype 用户将在 Skype 中创建一个联系人，其中包含 Lync 用户的会话初始协议（SIP）统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="019bf-105">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="019bf-106">相反，当 Lync 用户添加 Skype 联系人时，Lync 用户将在 Lync 中创建一个联系人，该联系人将包含 Skype 用户的 Microsoft 帐户（MSA），而不是 Skype 用户名称。</span><span class="sxs-lookup"><span data-stu-id="019bf-106">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="019bf-107">**什么是 MSA？**</span><span class="sxs-lookup"><span data-stu-id="019bf-107">**What is an MSA?**</span></span> <span data-ttu-id="019bf-108">Skype 用户必须使用 Microsoft 帐户（以前称为 Windows Live ID）登录 Skype，才能与 Lync 联系人通信。</span><span class="sxs-lookup"><span data-stu-id="019bf-108">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="019bf-109">Microsoft 帐户包含电子邮件地址和密码的组合，也可用于登录服务，例如 Microsoft OneDrive 存储技术、Windows Phone、Microsoft Xbox LIVE online 游戏服务和 Microsoft Outlook 消息传递和协作客户端（以及以前，基于 Microsoft Hotmail web 的电子邮件服务或 Windows Live Messenger）。</span><span class="sxs-lookup"><span data-stu-id="019bf-109"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="019bf-110">如果您使用电子邮件地址和密码登录到这些或其他服务，则您已经有一个 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="019bf-110"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="019bf-111">有关创建 Microsoft 帐户的详细信息，请参阅上[https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)的 microsoft 帐户注册页。</span><span class="sxs-lookup"><span data-stu-id="019bf-111"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="019bf-112">您可以跨各种应用程序和服务将现有 Skype 帐户与 Microsoft 帐户合并，以实现单一登录。</span><span class="sxs-lookup"><span data-stu-id="019bf-112">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="019bf-113">帐户合并后，Skype 用户可以向 Lync 用户发送联系人请求。</span><span class="sxs-lookup"><span data-stu-id="019bf-113">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="019bf-114">为了使 Lync 和 Skype 用户完全相互通信，必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="019bf-114">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="019bf-115">Skype 用户必须使用 Microsoft 帐户（MSA）登录到其 Skype 客户端。</span><span class="sxs-lookup"><span data-stu-id="019bf-115">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="019bf-116">必须由 lync 管理员启用 lync 用户的公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="019bf-116">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="019bf-117">当 Skype 用户添加 Lync 联系人时，请验证 word Lync 是否显示在联系人姓名的下方。</span><span class="sxs-lookup"><span data-stu-id="019bf-117">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="019bf-118">这表示已找到 Lync URI。</span><span class="sxs-lookup"><span data-stu-id="019bf-118">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="019bf-119">当 Skype 用户添加 Lync 联系人和零搜索结果时，将返回该 Lync 域，PIC 设置过程可能尚未完成，或者 Lync 域尚未设置。</span><span class="sxs-lookup"><span data-stu-id="019bf-119">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="019bf-120">根据 Lync 和 Skype 用户的隐私设置，即时消息、视频和状态可能在每个用户接受新联系人之前不起作用。</span><span class="sxs-lookup"><span data-stu-id="019bf-120">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="019bf-121">**将 Skype 联系人添加到 Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="019bf-121">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="019bf-122">从 Lync，单击 "**添加联系人"，添加 "我的组织" 中没有的联系人**。</span><span class="sxs-lookup"><span data-stu-id="019bf-122">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="019bf-123">从可用联系人提供程序列表中，选择 " **Skype**"。</span><span class="sxs-lookup"><span data-stu-id="019bf-123">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="019bf-124">在 " **IM 地址**" 字段中，输入 Skype 用户的 Microsoft 帐户（MSA）。</span><span class="sxs-lookup"><span data-stu-id="019bf-124">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="019bf-125">在 "**添加到联系人组**" 下拉框中，选择要向其添加用户的联系人组。</span><span class="sxs-lookup"><span data-stu-id="019bf-125">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="019bf-126">在 "**设置隐私关系**" 下拉列表框中，选择适当的联系人设置，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="019bf-126">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="019bf-127">此时，用户将在 Lync 中显示为联系人。</span><span class="sxs-lookup"><span data-stu-id="019bf-127">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="019bf-128">选择用户，右键单击该用户名，然后单击 "**请参阅联系人卡片**" 以查看用户属性。</span><span class="sxs-lookup"><span data-stu-id="019bf-128">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="019bf-129">现在，你可以使用新添加的 Skype 用户建立音频或视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="019bf-129">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="019bf-130">有关对联系人的支持的其他信息，请参阅[在 Lync 中添加联系人](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)。</span><span class="sxs-lookup"><span data-stu-id="019bf-130">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="019bf-131">当 Skype 用户的 Microsoft 帐户使用自定义域名（如<strong>bob@contoso.com</strong> ）时，Lync 用户可以通过以下两种方式将该 Microsoft 帐户添加到 Lync：</span><span class="sxs-lookup"><span data-stu-id="019bf-131">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="019bf-132">使用 "**添加联系人**" 图标或</span><span class="sxs-lookup"><span data-stu-id="019bf-132">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="019bf-133">使用 "**查找某人" 或 "会议室"，或 "拨打号码**" 字段。</span><span class="sxs-lookup"><span data-stu-id="019bf-133">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="019bf-134">在每个实例中，Lync 用户必须按以下格式输入 Skype 用户的电子邮件： <strong>user （域名） @msn .com</strong> 。</span><span class="sxs-lookup"><span data-stu-id="019bf-134">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="019bf-135">对于使用以下域名的 Microsoft 帐户，不需要执行此步骤： <STRONG>@live .com、@hotmail .com 或 @outlook .com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="019bf-135">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="019bf-136">有关受支持的自定义域名称的详细信息，请参阅<A href="https://support.microsoft.com/kb/897567">受支持的公共 IM 域</A>。</span><span class="sxs-lookup"><span data-stu-id="019bf-136">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="019bf-137">**使用自定义域名称时将 Skype 联系人添加到 Lync**</span><span class="sxs-lookup"><span data-stu-id="019bf-137">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="019bf-138">从 Lync，单击 "**添加联系人"，添加 "我的组织" 中没有的联系人**。</span><span class="sxs-lookup"><span data-stu-id="019bf-138">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="019bf-139">从可用联系人提供程序列表中，选择 " **Skype**"。</span><span class="sxs-lookup"><span data-stu-id="019bf-139">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="019bf-140">在 " **IM 地址**" 字段中，输入格式为<strong>user （域名） @msn .Com</strong>中的 Skype 用户的 Microsoft 帐户（MSA）。</span><span class="sxs-lookup"><span data-stu-id="019bf-140">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="019bf-141">因此，对于用户 bob@contoso.com，此条目为<strong>小明（contoso） @msn .com<strong> 。</span><span class="sxs-lookup"><span data-stu-id="019bf-141">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="019bf-142">在 "**添加到联系人组**" 下拉列表框中，选择要向其中添加用户的联系人组。</span><span class="sxs-lookup"><span data-stu-id="019bf-142">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="019bf-143">在 "**设置私人关系**" 下拉列表框中，选择相应的 "联系人" 设置，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="019bf-143">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="019bf-144">Lync 用户还可以使用 "**查找某人或会议室"，或者**在 Lync 中拨打号码域，并添加与以下<strong>用户（域名） @msn .com</strong>类似的地址。</span><span class="sxs-lookup"><span data-stu-id="019bf-144">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="019bf-145">因此，对于 bob@contoso.com Microsoft 帐户，该条目将为<strong>小明（contoso） @msn .com</strong> 。</span><span class="sxs-lookup"><span data-stu-id="019bf-145">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="019bf-146">按照此过程前面的步骤4和步骤5将联系人添加到联系人组，并选择相应的隐私关系。</span><span class="sxs-lookup"><span data-stu-id="019bf-146">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="019bf-147">**将 Lync 联系人添加到 Skype 联系人**</span><span class="sxs-lookup"><span data-stu-id="019bf-147">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="019bf-148">登录 Skype。</span><span class="sxs-lookup"><span data-stu-id="019bf-148">Sign in to Skype.</span></span> <span data-ttu-id="019bf-149">Skype 用户必须使用 Microsoft 帐户（MSA）登录到其 Skype 客户端。</span><span class="sxs-lookup"><span data-stu-id="019bf-149">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="019bf-150">选择 "添加联系人" 图标。</span><span class="sxs-lookup"><span data-stu-id="019bf-150">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="019bf-151">输入 Lync 用户的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="019bf-151">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="019bf-152">例如，bob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="019bf-152">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="019bf-153">当 Skype 在搜索结果中找到匹配项时，请在 Lync 用户的名称下方查找 word **lync** 。</span><span class="sxs-lookup"><span data-stu-id="019bf-153">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="019bf-154">这表明 Skype 已成功找到 Lync 客户端的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="019bf-154">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="019bf-155">单击该名称。</span><span class="sxs-lookup"><span data-stu-id="019bf-155">Click the name.</span></span>

5.  <span data-ttu-id="019bf-156">在窗口的右上角，单击 "添加到联系人"。</span><span class="sxs-lookup"><span data-stu-id="019bf-156">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="019bf-157">新联系人现在已添加到您的联系人列表中，但在接受你的请求之前，你将看到问号而不是其状态图标。</span><span class="sxs-lookup"><span data-stu-id="019bf-157">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="019bf-158">当新联系人接受你的请求时，你将能够查看他们何时联机、启动 IM 对话以及进行音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="019bf-158">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="019bf-159">Lync Server 管理员必须将 Lync 用户的策略设置配置为允许传入的请求。</span><span class="sxs-lookup"><span data-stu-id="019bf-159">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="019bf-160">如果不是，Lync 用户将不会收到来自 Skype 用户的联系人请求。</span><span class="sxs-lookup"><span data-stu-id="019bf-160">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="019bf-161">根据 Lync 用户的策略设置的配置，添加 Skype 用户的请求将显示在 Lync 客户端的 "<STRONG>新建</STRONG>" 选项卡上。若要开始与 Skype 用户进行通信，Lync 用户必须将 Skype 用户添加到收藏夹列表或联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="019bf-161">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="019bf-162">下图显示了<STRONG>新</STRONG>选项卡在 Lync 客户端中的位置。</span><span class="sxs-lookup"><span data-stu-id="019bf-162">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="019bf-163">Lync 用户必须配置 Lync 警报，以确保从 Skype 用户发送的请求显示，并且由 Lync 用户发现。</span><span class="sxs-lookup"><span data-stu-id="019bf-163">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="019bf-164">若要配置 Lync 警报，请完成下面的过程。</span><span class="sxs-lookup"><span data-stu-id="019bf-164">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="019bf-165">**配置 Lync 警报**</span><span class="sxs-lookup"><span data-stu-id="019bf-165">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="019bf-166">在 Lync 客户端中，单击 "**选项**" 图标。</span><span class="sxs-lookup"><span data-stu-id="019bf-166">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="019bf-167">选择 "**通知**"。</span><span class="sxs-lookup"><span data-stu-id="019bf-167">Select **Alerts**.</span></span>

3.  <span data-ttu-id="019bf-168">在 "**常规通知**" 下，选中 "**当某人将我添加到其联系人列表中时通知我**"。</span><span class="sxs-lookup"><span data-stu-id="019bf-168">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="019bf-169">在 "**未使用 Lync 的联系人**" 下，选择 "**允许邀请但阻止所有其他通信**"。</span><span class="sxs-lookup"><span data-stu-id="019bf-169">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="019bf-170">单击 **"确定"** 关闭 "选项" 窗口。</span><span class="sxs-lookup"><span data-stu-id="019bf-170">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

