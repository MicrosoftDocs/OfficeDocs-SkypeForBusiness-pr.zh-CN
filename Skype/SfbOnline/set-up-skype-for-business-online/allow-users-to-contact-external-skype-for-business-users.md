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
description: '了解如何配置 Skype for Business，让用户与另一组织的用户交谈，或让外部联系人与用户交谈。 '
ms.openlocfilehash: 8acab73fec7337ee70cd8b5059b00df42e836e62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093506"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="d6898-103">允许用户联系外部 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="d6898-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="d6898-104">在下列情况下，请按照本文的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="d6898-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="d6898-p101">你的用户在企业内的不同域中。例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="d6898-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="d6898-107">希望你组织的人员使用 Skype for Business 联系你组织外特定企业中的人员。</span><span class="sxs-lookup"><span data-stu-id="d6898-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="d6898-108">希望世界上使用 Skype for Business 的其他人能够使用你的电子邮件地址找到你并联系你。</span><span class="sxs-lookup"><span data-stu-id="d6898-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="d6898-109">如果你和他们都使用默认的 Skype for Business 设置，此功能会自动运行。</span><span class="sxs-lookup"><span data-stu-id="d6898-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="d6898-110">如果他们更改了默认设置，他们需要确认其配置没有阻止你的域。</span><span class="sxs-lookup"><span data-stu-id="d6898-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="d6898-111">为你的用户启用企业到企业通信</span><span class="sxs-lookup"><span data-stu-id="d6898-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="d6898-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="d6898-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="d6898-113">您必须在 [Microsoft](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 365 或 Office 365 这两个组织中具有管理员权限才能进行此通信。</span><span class="sxs-lookup"><span data-stu-id="d6898-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="d6898-114">![使用 Teams 管理中心显示 Microsoft Teams 徽标 ](../images/teams-logo-30x30.png) **的图标**</span><span class="sxs-lookup"><span data-stu-id="d6898-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="d6898-115">使用 Microsoft 365 或 Office 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d6898-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="d6898-116">在管理中心中，转到"**管理中心**  >  **Teams"。**</span><span class="sxs-lookup"><span data-stu-id="d6898-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![选择"Teams 管理员"。](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="d6898-118">在 **Teams 中心，选择\*\*\*\*"Skype** > **旧版门户** 
  ![ "选择 SfB 旧版门户。](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="d6898-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="d6898-119">在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。</span><span class="sxs-lookup"><span data-stu-id="d6898-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="d6898-120">要设置与特定企业或另一个域中的用户之间的通信，在下拉框中选择“**打开(仅针对被允许的域)**”。</span><span class="sxs-lookup"><span data-stu-id="d6898-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="d6898-p103">或者，你希望能够与世界各地采用公开的 Skype for Business 策略的所有其他人通信，请选择" **打开(被阻止的域除外)**"。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d6898-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>

6. <span data-ttu-id="d6898-123">在 **"阻止或允许的域**"下，选择并添加 **+** 要允许的域的名称。</span><span class="sxs-lookup"><span data-stu-id="d6898-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="d6898-124">请确保另一组织的管理员在 Skype for Business 管理中心中执行 **这些相同的步骤**。</span><span class="sxs-lookup"><span data-stu-id="d6898-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="d6898-125">例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。</span><span class="sxs-lookup"><span data-stu-id="d6898-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="d6898-126">如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。</span><span class="sxs-lookup"><span data-stu-id="d6898-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="d6898-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="d6898-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="d6898-128">这可能需要将 FQNS 添加到防火墙或代理基础结构配置中的出站允许列表 **\* ：.api.skype.com、.users.storage.live.com** \* \*\*\*\*和 graph.skype.com。\*\*</span><span class="sxs-lookup"><span data-stu-id="d6898-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \**_.users.storage.live.com_*, and **graph.skype.com**.</span></span> <span data-ttu-id="d6898-129">有关如何在防火墙中打开这些端口的说明，请查看它提供的文档。</span><span class="sxs-lookup"><span data-stu-id="d6898-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="d6898-130">有关需要打开的所有端口的列表，请参阅 [Office 365 URL 和 IP 地址范围](/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="d6898-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="d6898-131">确保组织的管理员也遵循了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d6898-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="d6898-132">**测试最长需要等待 24 小时** 。</span><span class="sxs-lookup"><span data-stu-id="d6898-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="d6898-133">更改外部通信设置时，可能需要 24 小时才能在所有数据中心填充更改。</span><span class="sxs-lookup"><span data-stu-id="d6898-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="d6898-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 现在，你可以允许你的用户搜索使用 Skype 这一免费应用的任何人并与其进行即时消息通信！</span><span class="sxs-lookup"><span data-stu-id="d6898-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="d6898-135">有关详细信息，请参阅允许 [Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="d6898-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="d6898-136">测试和故障排除</span><span class="sxs-lookup"><span data-stu-id="d6898-136">Test and troubleshoot</span></span>

<span data-ttu-id="d6898-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="d6898-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="d6898-138">**人们在设置企业到企业通信时遇到的最常见的问题是正确完成 [Office 365 URL 和 IP 地址范围](/microsoftteams/office-365-urls-ip-address-ranges)。**</span><span class="sxs-lookup"><span data-stu-id="d6898-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="d6898-139">要测试你的设置，你需要 Skype for Business 上不受你公司的防火墙保护的联系人。</span><span class="sxs-lookup"><span data-stu-id="d6898-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="d6898-140">在更改外部通信设置后， **直到等待 24 小时后再进行测试** 。</span><span class="sxs-lookup"><span data-stu-id="d6898-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="d6898-141">在 Skype for Business 中，搜索你的 Skype for Business 联系人，然后发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="d6898-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="d6898-142">如果收到由于公司策略无法发送的消息，则需要仔细检查 [Office 365 URL](/microsoftteams/office-365-urls-ip-address-ranges)和 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="d6898-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="d6898-p108">要求你的 Skype for Business 联系人向你发送聊天请求。如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="d6898-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="d6898-145">测试问题是否出在防火墙的另一种方式是转到不在防火墙后面的 wifi 位置，例如咖啡店。</span><span class="sxs-lookup"><span data-stu-id="d6898-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="d6898-146">使用 Skype for Business 向联系人发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="d6898-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="d6898-147">如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="d6898-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="d6898-148">在与其他企业连接时如何查找其他人以及如何被找到</span><span class="sxs-lookup"><span data-stu-id="d6898-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="d6898-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="d6898-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="d6898-150">启用与其他 Skype for Business 用户的外部通信后，你的用户可以通过搜索其登录名来查找联合 Skype for Business 用户。</span><span class="sxs-lookup"><span data-stu-id="d6898-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="d6898-151">例如，Rob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="d6898-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="d6898-152">然后，他们需要将此人添加到联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="d6898-152">Then they will need to add the person to their list of contacts.</span></span>
  
![若要在联合企业中查找用户，必须搜索其电子邮件地址 (这通常也是其登录名) 。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="d6898-154">设置联盟企业通信的提示</span><span class="sxs-lookup"><span data-stu-id="d6898-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="d6898-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="d6898-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="d6898-156">若要在 Skype for Business 2015 和 Skype for Business Online 之间配置联合，请参阅此文章： [配置与 Skype for Business Online 的联盟](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="d6898-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>

- <span data-ttu-id="d6898-157">若要在 Lync 和 Skype for Business Online 之间配置联合，请参阅此文章：为 Lync Online 客户 [配置联合支持](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)。</span><span class="sxs-lookup"><span data-stu-id="d6898-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span></span>

- <span data-ttu-id="d6898-158">当 Microsoft 365 或 Office 365 中的两个 Skype for Business 用户在单独的域上相互通信时，他们只能使用 Skype for Business 功能 (例如，在两个组织中启用的视频对话或桌面共享) 。</span><span class="sxs-lookup"><span data-stu-id="d6898-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="d6898-159">如果贵组织的 Skype for Business 用户被置于 In-Place 或诉讼保留，该用户与其他 Skype for Business 或 Skype 用户之间的任何 IM对话都将保存在其邮箱中的可恢复项目中。</span><span class="sxs-lookup"><span data-stu-id="d6898-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="d6898-160">这些对话将不保存在其邮箱中的" **对话历史记录**"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d6898-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="d6898-161">关闭特定个人的外部通信</span><span class="sxs-lookup"><span data-stu-id="d6898-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="d6898-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="d6898-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="d6898-163">为你的整个企业启用外部通信后，你可以仅为特定的个人关闭它。</span><span class="sxs-lookup"><span data-stu-id="d6898-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="d6898-164">使用 Microsoft 365 或 Office 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d6898-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="d6898-165">在管理中心，**转到"用户**  >  **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="d6898-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="d6898-166">在用户列表中，选择用户，然后在" **其他设置**"下单击" **编辑 Skype for Business 属性**"。</span><span class="sxs-lookup"><span data-stu-id="d6898-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="d6898-168">在 **Skype for Business 管理中心中，选择**"**外部通信"。**</span><span class="sxs-lookup"><span data-stu-id="d6898-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="d6898-169">在" **选项** "页上，将选择所有选项。</span><span class="sxs-lookup"><span data-stu-id="d6898-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="d6898-170">清除要禁用的通信。</span><span class="sxs-lookup"><span data-stu-id="d6898-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="d6898-171">下图显示了 Jakob 能够与其他可信企业中的人员通信，但是无法与其他 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="d6898-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="d6898-173">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="d6898-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d6898-174">[!注释] 你可能必须等待长达 24 小时，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="d6898-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="d6898-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="d6898-175">Related topics</span></span>

<span data-ttu-id="d6898-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="d6898-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="d6898-177">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d6898-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="d6898-178">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="d6898-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
