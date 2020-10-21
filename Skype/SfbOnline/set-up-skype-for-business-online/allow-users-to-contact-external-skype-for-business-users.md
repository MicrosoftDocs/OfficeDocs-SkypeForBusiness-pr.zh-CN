---
title: 允许用户联系外部 Skype for Business 用户
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: '了解如何配置 Skype for Business，让用户与其他组织中的用户交谈，或者让外部联系人与他们交谈。 '
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625048"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="a2340-103">允许用户联系外部 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="a2340-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="a2340-104">在下列情况下，请按照本文的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="a2340-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="a2340-p101">你的用户在企业内的不同域中。例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="a2340-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="a2340-107">希望你组织的人员使用 Skype for Business 联系你组织外特定企业中的人员。</span><span class="sxs-lookup"><span data-stu-id="a2340-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="a2340-p102">您希望世界任何使用 Skype for Business 的其他人都能够使用您的电子邮件地址找到并与您联系。如果您和他们使用默认的 Skype for Business 设置，这将自动工作。如果不是这样，则他们需要确保其配置未阻止您的域。</span><span class="sxs-lookup"><span data-stu-id="a2340-p102">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address. If you and they use the default Skype for Business settings, this will work automatically. If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="a2340-111">为你的用户启用企业到企业通信</span><span class="sxs-lookup"><span data-stu-id="a2340-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="a2340-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a2340-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="a2340-113">您必须在两个组织中的 Microsoft 365 或 Office 365 中具有 [管理员权限](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 才能执行此通信。</span><span class="sxs-lookup"><span data-stu-id="a2340-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="a2340-114">![](../images/teams-logo-30x30.png)**使用团队管理中心**显示 Microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="a2340-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="a2340-115">通过 Microsoft 365 或 Office 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a2340-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="a2340-116">在管理中心，转到 "**管理中心**"  >  **团队**。</span><span class="sxs-lookup"><span data-stu-id="a2340-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![选择 "团队管理员"。](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="a2340-118">在 "**团队中心**" 中，选择 " **Skype** > **旧版门户** 
  ![ " 选择 "SfB 旧版门户"。](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="a2340-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="a2340-119">在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。</span><span class="sxs-lookup"><span data-stu-id="a2340-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="a2340-120">要设置与特定企业或另一个域中的用户之间的通信，在下拉框中选择“**打开(仅针对被允许的域)**”。</span><span class="sxs-lookup"><span data-stu-id="a2340-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="a2340-p103">或者，你希望能够与世界各地采用公开的 Skype for Business 策略的所有其他人通信，请选择" **打开(被阻止的域除外)**"。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a2340-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>

6. <span data-ttu-id="a2340-123">在 " **被阻止或允许的域**" 下，选择 **+** 并添加您要允许的域的名称。</span><span class="sxs-lookup"><span data-stu-id="a2340-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="a2340-124">请确保其他组织中的管理员在其 **Skype For business 管理中心**中执行这些相同步骤。</span><span class="sxs-lookup"><span data-stu-id="a2340-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="a2340-125">例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。</span><span class="sxs-lookup"><span data-stu-id="a2340-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="a2340-126">如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。</span><span class="sxs-lookup"><span data-stu-id="a2340-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="a2340-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="a2340-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="a2340-128">这可能需要将 fqdn 添加到防火墙或代理基础结构配置： \*\* \* api.skype.com**、 \* **users.storage.live.com**和**graph.skype.com\*\*中的出站允许列表。</span><span class="sxs-lookup"><span data-stu-id="a2340-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="a2340-129">有关如何在防火墙中打开这些端口的说明，请查看它附带的文档。</span><span class="sxs-lookup"><span data-stu-id="a2340-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="a2340-130">有关需要打开的所有端口的列表，请参阅 [Office 365 url 和 IP 地址范围](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="a2340-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="a2340-131">请确保组织中的管理员也已按照这些步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a2340-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="a2340-132">**测试最长需要等待 24 小时** 。</span><span class="sxs-lookup"><span data-stu-id="a2340-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="a2340-133">更改外部通信设置时，可能需要长达24小时才能让更改在所有数据中心内填充。</span><span class="sxs-lookup"><span data-stu-id="a2340-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="a2340-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 现在，你可以允许你的用户搜索使用 Skype 这一免费应用的任何人并与其进行即时消息通信！</span><span class="sxs-lookup"><span data-stu-id="a2340-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="a2340-135">若要了解详细信息，请参阅 [让 skype For business 用户添加 skype 联系人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="a2340-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="a2340-136">测试和故障排除</span><span class="sxs-lookup"><span data-stu-id="a2340-136">Test and troubleshoot</span></span>

<span data-ttu-id="a2340-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a2340-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="a2340-138">**人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。**</span><span class="sxs-lookup"><span data-stu-id="a2340-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="a2340-139">要测试你的设置，你需要 Skype for Business 上不受你公司的防火墙保护的联系人。</span><span class="sxs-lookup"><span data-stu-id="a2340-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="a2340-140">在更改外部通信设置后， **直到等待 24 小时后再进行测试** 。</span><span class="sxs-lookup"><span data-stu-id="a2340-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="a2340-141">在 Skype for Business 中，搜索你的 Skype for Business 联系人，然后发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="a2340-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="a2340-142">如果收到一条消息，指出由于公司策略无法发送邮件，您需要仔细检查您的 [Office 365 url 和 IP 地址范围](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="a2340-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="a2340-p108">要求你的 Skype for Business 联系人向你发送聊天请求。如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="a2340-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="a2340-145">测试问题是否是你的防火墙的另一种方法是转到不在防火墙后面的 wifi 位置，例如咖啡店。</span><span class="sxs-lookup"><span data-stu-id="a2340-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="a2340-146">使用 Skype for Business 将请求发送给您的联系人进行聊天。</span><span class="sxs-lookup"><span data-stu-id="a2340-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="a2340-147">如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="a2340-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="a2340-148">在与其他企业连接时如何查找其他人以及如何被找到</span><span class="sxs-lookup"><span data-stu-id="a2340-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="a2340-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a2340-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="a2340-150">启用与其他 Skype for Business 用户的外部通信后，你的用户可以通过搜索其登录名找到联合 Skype for business 用户。</span><span class="sxs-lookup"><span data-stu-id="a2340-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="a2340-151">一个示例是 Rob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a2340-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="a2340-152">然后，他们需要将此人添加到联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="a2340-152">Then they will need to add the person to their list of contacts.</span></span>
  
![若要查找联合企业中的用户，必须搜索其电子邮件地址 (这通常也是他们的登录名称) 。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="a2340-154">设置联盟企业通信的提示</span><span class="sxs-lookup"><span data-stu-id="a2340-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="a2340-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a2340-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="a2340-156">若要配置 Skype for Business 2015 和 Skype for business Online 之间的联盟，请参阅本文： [配置与 Skype for Business online 的联盟](https://technet.microsoft.com/library/jj205126.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2340-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>

- <span data-ttu-id="a2340-157">要配置 Lync 与 Skype for business Online 之间的联盟，请参阅本文： [为 Lync Online 客户配置联合身份验证支持](https://technet.microsoft.com/library/hh202193.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2340-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>

- <span data-ttu-id="a2340-158">当 Microsoft 365 或 Office 365 中的两个 Skype for Business 用户在单独的域上互相通信时，他们只能使用 Skype for Business 功能 (例如，在两个组织中打开的视频对话或桌面共享) 。</span><span class="sxs-lookup"><span data-stu-id="a2340-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="a2340-159">如果组织中的 Skype for Business 用户已加入 In-Place 或诉讼封存，则该用户和其他 Skype for business 或 Skype 用户之间的任何 IM 对话都将保存在其邮箱中的 **可恢复项目** 中。</span><span class="sxs-lookup"><span data-stu-id="a2340-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="a2340-160">这些对话将不保存在其邮箱中的" **对话历史记录**"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a2340-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="a2340-161">关闭特定个人的外部通信</span><span class="sxs-lookup"><span data-stu-id="a2340-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="a2340-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a2340-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="a2340-163">为你的整个企业启用外部通信后，你可以仅为特定的个人关闭它。</span><span class="sxs-lookup"><span data-stu-id="a2340-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="a2340-164">通过 Microsoft 365 或 Office 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a2340-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="a2340-165">在管理中心中，转到 "**用户**  >  **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="a2340-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="a2340-166">在用户列表中，选择用户，然后在" **其他设置**"下单击" **编辑 Skype for Business 属性**"。</span><span class="sxs-lookup"><span data-stu-id="a2340-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="a2340-168">在 **Skype For business 管理中心**，选择 " **外部通信**"。</span><span class="sxs-lookup"><span data-stu-id="a2340-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="a2340-169">在 " **选项** " 页面上，将选中所有选项。</span><span class="sxs-lookup"><span data-stu-id="a2340-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="a2340-170">清除要禁用的通信。</span><span class="sxs-lookup"><span data-stu-id="a2340-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="a2340-171">下图显示了 Jakob 能够与其他可信企业中的人员通信，但是无法与其他 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="a2340-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="a2340-173">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="a2340-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a2340-174">[!注释] 你可能必须等待长达 24 小时，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="a2340-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="a2340-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="a2340-175">Related topics</span></span>

<span data-ttu-id="a2340-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a2340-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="a2340-177">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a2340-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="a2340-178">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="a2340-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  