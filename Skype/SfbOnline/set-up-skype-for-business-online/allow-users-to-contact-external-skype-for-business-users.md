---
title: "允许用户联系外部 Skype for Business 用户"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: 570f268427ddac33e8f720230fbb1f6adb2e319b
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="8d0a1-103">允许用户联系外部 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="8d0a1-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="8d0a1-104">Skype 业务联盟到 Office 365 由 21Vianet 和 Office 365 德国组织不可。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="8d0a1-105">在下列情况下，请按照本文的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="8d0a1-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="8d0a1-p101">你的用户在企业内的不同域中。例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="8d0a1-108">希望你组织的人员使用 Skype for Business 联系你组织外特定企业中的人员。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="8d0a1-109">-您想其他任何人在世界中使用 Skype 业务能够找到您并联系您使用您的电子邮件地址的用户。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="8d0a1-110">如果你和他们都使用默认的 Skype for Business 设置，此功能会自动运行。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="8d0a1-111">如果他们更改了默认设置，他们需要确认其配置没有阻止你的域。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="8d0a1-112">为你的用户启用企业到企业通信</span><span class="sxs-lookup"><span data-stu-id="8d0a1-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="8d0a1-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0a1-113"></span></span>

<span data-ttu-id="8d0a1-114">必须在 Office 365 中拥有[管理员角色](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="8d0a1-115">使用您的 Office 365 管理帐户登录。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-115">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="8d0a1-116">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-116">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="8d0a1-118">在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-118">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="8d0a1-119">若要设置通讯与特定业务或用户在另一个域中，在下拉列表框中，选择**上只允许域**。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-119">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="8d0a1-p103">或者，你希望能够与世界各地采用公开的 Skype for Business 策略的所有其他人通信，请选择" **打开(被阻止的域除外)**"。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
5. <span data-ttu-id="8d0a1-122">**阻止或允许的域**，请在下选择**+**并添加您希望允许的域的名称。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-122">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="8d0a1-123">请确保在其他组织中的管理员 does **Skype 业务管理中心的**他们在相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-123">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="8d0a1-124">例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="8d0a1-125">如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-125">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="8d0a1-126">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="8d0a1-126">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="8d0a1-127">这可能需要添加到出站 Fqdn 允许列表中您的防火墙或代理服务器基础结构配置： ** \*。 api.skype.com**， \* **。 users.storage.live.com**，和**graph.skype.com**。有关如何在您的防火墙中打开这些端口，请检查随之附带的文档。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-127">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="8d0a1-128">所有您需要打开的端口的列表，请参阅[Office 365 的 Url 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-128">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
8. <span data-ttu-id="8d0a1-p106">**测试最长需要等待 24 小时** 。如果你更改了外部通信设置，最长需要等待 24 小时才能让更改传播到所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="8d0a1-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 现在，你可以允许你的用户搜索使用 Skype 这一免费应用的任何人并与其进行即时消息通信！</span><span class="sxs-lookup"><span data-stu-id="8d0a1-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="8d0a1-132">若要了解详细信息，请参阅[适用于业务用户让 Skype 将 Skype 联系人添加](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-132">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="8d0a1-133">测试和故障排除</span><span class="sxs-lookup"><span data-stu-id="8d0a1-133">Test and troubleshoot</span></span>
<span data-ttu-id="8d0a1-134"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0a1-134"></span></span>

 <span data-ttu-id="8d0a1-135">**人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。**</span><span class="sxs-lookup"><span data-stu-id="8d0a1-135">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="8d0a1-136">要测试你的设置，你需要 Skype for Business 上不受你公司的防火墙保护的联系人。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-136">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="8d0a1-137">在更改外部通信设置后， **直到等待 24 小时后再进行测试** 。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-137">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="8d0a1-138">在 Skype for Business 中，搜索你的 Skype for Business 联系人，然后发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-138">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="8d0a1-139">如果您收到一条消息，由于公司政策而无法发送它，您需要仔细检查您的[Office 365 的 Url 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-139">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="8d0a1-p108">要求你的 Skype for Business 联系人向你发送聊天请求。如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="8d0a1-p109">另一个测试问题是否出自你的防火墙的方法是在不受你的防火墙保护的 WiFi 位置（例如咖啡店）使用 Skype for Business 向你的 Skype 联系人发送聊天请求。如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="8d0a1-144">在与其他企业连接时如何查找其他人以及如何被找到</span><span class="sxs-lookup"><span data-stu-id="8d0a1-144">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="8d0a1-145"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0a1-145"></span></span>

<span data-ttu-id="8d0a1-146">启用其他适用于业务用户的 Skype 与外部通信后，用户联合的 Skype 适用于业务用户通过搜索可以找到的他们的登录名： 例如，Rob@contoso.com。然后他们将需要将此人添加到他们的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-146">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.</span></span>
  
![联盟企业中查找用户，您必须搜索其电子邮件地址 （这通常也是其登录名）。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="8d0a1-148">设置联盟企业通信的提示</span><span class="sxs-lookup"><span data-stu-id="8d0a1-148">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="8d0a1-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0a1-149"></span></span>

- <span data-ttu-id="8d0a1-150">要配置 Skype for Business 2015 与 Skype for Business Online 之间的联盟，请参阅 TechNet 文章：[配置与 Skype for Business Online 联盟](https://technet.microsoft.com/en-us/library/jj205126.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-150">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="8d0a1-151">要配置 Lync 与 Skype for Business Online 之间的联盟，请参阅 TechNet 文章：[为 Lync Online 客户配置联盟支持](https://technet.microsoft.com/en-us/library/hh202193.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-151">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="8d0a1-152">当 Office 365 中的两个 Skype for Business 用户在单独的域上相互通信时，他们只能使用在两个组织中都启用的 Skype for Business 功能（例如，视频对话或桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-152">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="8d0a1-153">如果您的组织中的业务用户 Skype 放在适当或诉讼封存，将**可恢复项目**在其邮箱中保存该用户和其他有关业务或 Skype 用户的 Skype 之间的 IM 对话。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-153">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="8d0a1-154">这些对话将不保存在其邮箱中的" **对话历史记录**"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-154">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="8d0a1-155">关闭特定个人的外部通信</span><span class="sxs-lookup"><span data-stu-id="8d0a1-155">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="8d0a1-156"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0a1-156"></span></span>

<span data-ttu-id="8d0a1-157">为你的整个企业启用外部通信后，你可以仅为特定的个人关闭它。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-157">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="8d0a1-158">使用您的 Office 365 管理帐户登录。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-158">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="8d0a1-159">在 Office 365 管理中心中，请转到**用户** > **活动的用户**。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-159">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="8d0a1-160">在用户列表中，选择用户，然后在" **其他设置**"下单击" **编辑 Skype for Business 属性**"。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-160">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="8d0a1-162">**Skype 的业务管理中心**，在选择**外部通信**。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-162">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="8d0a1-163">在**选项**页中，将被选中所有选项。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-163">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="8d0a1-164">清除要禁用的通信。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-164">Clear the communications you want to disable.</span></span> <span data-ttu-id="8d0a1-165">下图显示了 Jakob 能够与其他可信企业中的人员通信，但是无法与其他 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-165">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="8d0a1-167">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-167">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8d0a1-168">[!注释] 你可能必须等待长达 24 小时，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-168">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="8d0a1-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="8d0a1-169">Related topics</span></span>
<span data-ttu-id="8d0a1-170"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0a1-170"></span></span>

[<span data-ttu-id="8d0a1-171">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8d0a1-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="8d0a1-172">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="8d0a1-172">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="feedback"></a><span data-ttu-id="8d0a1-173">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="8d0a1-173">Feedback?</span></span>
<span data-ttu-id="8d0a1-174">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-174">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
