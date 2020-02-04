---
title: 允许 Skype for Business 用户添加 Skype 联系人
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: '了解如何让使用 Skype for Business 的人员联系你组织外部的 Skype for Business 用户并将其添加到联系人列表。 '
ms.openlocfilehash: d6251e8e86527172e6818d11b1e07da892b4b0ef
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692877"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="4403e-103">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="4403e-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="4403e-p101">通过 Skype for Business，你的用户可以搜索使用 Skype 这一免费应用的任何人并与其进行即时消息通信！本文介绍为使你的用户能够添加 Skype 联系人，你需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4403e-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="4403e-106">必须在 Office 365 中拥有[管理员角色](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4403e-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="4403e-107">![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="4403e-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="4403e-108">使用 Office 365 管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)。</span><span class="sxs-lookup"><span data-stu-id="4403e-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="4403e-109">在管理中心，转到 "**管理中心** > "**Skype for**business。</span><span class="sxs-lookup"><span data-stu-id="4403e-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![选择“Skype for Business 管理中心”。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="4403e-111">在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。</span><span class="sxs-lookup"><span data-stu-id="4403e-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="4403e-112">默认情况下，你的用户可以与世界各地使用 Skype for Business 的所有其他人通信（假设你的防火墙已配置为允许这样）。</span><span class="sxs-lookup"><span data-stu-id="4403e-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![选择允许用户使用 Skype for Business 与 Skype 用户进行通信。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="4403e-p102">如果你希望你的用户与 Skype 用户聊天，但不希望他们与使用 Skype for Business 的其他人聊天，请选择" **打开(仅针对被允许的域)**"。当你允许与 Skype 用户联系时，系统会在后台自动将 skype.com 添加为允许的域。</span><span class="sxs-lookup"><span data-stu-id="4403e-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="4403e-p103">如果你希望允许世界各地使用 Skype for Business 的所有其他企业与你联系，但特定企业除外，请选择" **打开(被阻止的域除外)**"，并选择 **+** 添加那些域。除了那些特定域中的人之外，所有人都将能够与你联系（有些企业可能选择此选项，例如，如果他们处于诉讼状态，并需要确保不与其他企业联系。）</span><span class="sxs-lookup"><span data-stu-id="4403e-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="4403e-119">选择" **让用户能够使用 Skype for Business 与组织外的 Skype 用户进行通信**"。</span><span class="sxs-lookup"><span data-stu-id="4403e-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="4403e-120">如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。</span><span class="sxs-lookup"><span data-stu-id="4403e-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="4403e-p104">如果贵组织使用其他解决方案限制网络中的计算机连接至 Internet，请确保客户端计算机能够访问用于 Skype 连接和 Skype 目录搜索的所有 [IP 地址和 URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。为此，可能需要将其添加到你的防火墙或代理基础结构配置中的出站允许列表内。</span><span class="sxs-lookup"><span data-stu-id="4403e-p104">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search. This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="4403e-p105">**测试最长需要等待 24 小时** 。如果你更改了外部通信设置，最长需要等待 24 小时才能让更改传播到所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="4403e-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="4403e-p106">向你的用户演示如何查找 Skype 联系人并将他们添加到其 Skype for Business 联系人列表。请指示他们查看[在 Skype for Business 中搜索人员](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)。</span><span class="sxs-lookup"><span data-stu-id="4403e-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="4403e-127">测试和故障排除</span><span class="sxs-lookup"><span data-stu-id="4403e-127">Test and troubleshoot</span></span>

<span data-ttu-id="4403e-p107">要测试你的设置，你需要一个不受你公司防火墙保护的 Skype 联系人。他们可以使用 Gmail 帐户、Outlook.com 帐户或其他类型的电子邮件帐户登录 Skype。</span><span class="sxs-lookup"><span data-stu-id="4403e-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="4403e-130">在更改外部通信设置后，**直到等待 24 小时后再进行测试** 。</span><span class="sxs-lookup"><span data-stu-id="4403e-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="4403e-131">注销 Skype for Business，然后重新登录，这样你会看到用于搜索 Skype Directory 的选项。</span><span class="sxs-lookup"><span data-stu-id="4403e-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![当突出显示 Skype 目录时，便可搜索拥有 Skype 帐户的联系人。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="4403e-133">在 Skype for Business 中，搜索你的 Skype 联系人，然后发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="4403e-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="4403e-134">如果收到由于公司策略无法发送的消息，你需要再次检查你的[防火墙设置](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="4403e-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="4403e-135">另一个测试问题是否出自你的防火墙的方法是在不受你的防火墙保护的 WiFi 位置（例如咖啡店）使用 Skype for Business 向你的 Skype 联系人发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="4403e-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="4403e-p108">**如果你向你的 Skype 联系人发送了请求，但他们从未收到** ，请要求他们向你发送聊天请求。如果问题是无法在 Skype 与 Skype for Business 之间建立连接，这样做通常会解决问题。</span><span class="sxs-lookup"><span data-stu-id="4403e-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="4403e-138">此时如果在咖啡店里消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="4403e-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="4403e-139">可以执行的操作和不能执行的操作</span><span class="sxs-lookup"><span data-stu-id="4403e-139">What you can and can't do</span></span>

- <span data-ttu-id="4403e-140">**Skype for Business在 Mac 中** 无法搜索 Skype 联系人并与之通信。</span><span class="sxs-lookup"><span data-stu-id="4403e-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="4403e-141">启用了目录搜索后，你可以搜索并查找 Skype 和 Skype for Business 用户。</span><span class="sxs-lookup"><span data-stu-id="4403e-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="4403e-142">如果由于某种原因，你无法通过搜索目录来查找用户，可以向他们发送联系人请求，然后让他们登录 Skype 并接受你的请求，以便你可以与他们进行即时消息传递。</span><span class="sxs-lookup"><span data-stu-id="4403e-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="4403e-p110">不可能允许与其他 IM 提供商（如 Google 或 Facebook）建立 IM 连接。不能使用 Skype for Business 发送手机短信。</span><span class="sxs-lookup"><span data-stu-id="4403e-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="4403e-145">不能录制 Skype 联系人和 Skype for Business 联系人之间的音频通话或视频通话。</span><span class="sxs-lookup"><span data-stu-id="4403e-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="4403e-146">添加 Skype 联系人时可使用哪些功能？</span><span class="sxs-lookup"><span data-stu-id="4403e-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="4403e-147">使用其 Microsoft 帐户（以前称为 Windows Live ID）登录的 Skype 联系人与 Skype for Business 用户交谈时，可以获得部分功能而非所有功能。</span><span class="sxs-lookup"><span data-stu-id="4403e-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="4403e-148">**对 Skype 联系人可用**</span><span class="sxs-lookup"><span data-stu-id="4403e-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="4403e-149">**对 Skype 联系人不可用**</span><span class="sxs-lookup"><span data-stu-id="4403e-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="4403e-150">视频对话</span><span class="sxs-lookup"><span data-stu-id="4403e-150">Video conversations</span></span> <br/>  <span data-ttu-id="4403e-151">个人对个人的即时消息</span><span class="sxs-lookup"><span data-stu-id="4403e-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="4403e-152">状态</span><span class="sxs-lookup"><span data-stu-id="4403e-152">Presence</span></span> <br/> | <span data-ttu-id="4403e-153">多方 IM 对话</span><span class="sxs-lookup"><span data-stu-id="4403e-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="4403e-154">与三人或多人的音频和视频对话</span><span class="sxs-lookup"><span data-stu-id="4403e-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="4403e-155">桌面和程序共享</span><span class="sxs-lookup"><span data-stu-id="4403e-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="4403e-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="4403e-156">Related topics</span></span>

[<span data-ttu-id="4403e-157">允许用户联系外部 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="4403e-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="4403e-158">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4403e-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
