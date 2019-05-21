---
title: 设置 Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: '了解如何为你的组织设置你的域、用户、IM 和状态, 以供你的组织安装 Skype for Business。 另请参阅如何设置音频会议、电话系统和通话计划以及 Skype 会议直播。 '
ms.openlocfilehash: fb31a2affa1507f043244fbe6f1988040cfec4ba
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285251"
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="39ac6-104">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="39ac6-104">Set up Skype for Business Online</span></span>

<span data-ttu-id="39ac6-p102">你必须拥有 Office 365 全局管理员权限才能设置 Skype for Business。如果你有限制访问部分 Web 的防火墙或代理服务器，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你设置 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="39ac6-p102">You must have Office 365 global admin permissions to set up Skype for Business. If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="setting-up-skype"></a><span data-ttu-id="39ac6-107">设置 Skype</span><span class="sxs-lookup"><span data-stu-id="39ac6-107">Setting up Skype</span></span>

<span data-ttu-id="39ac6-108">看来你需要帮助来完成与你的 Office 365 订阅相关的 Skype 设置。</span><span class="sxs-lookup"><span data-stu-id="39ac6-108">Looks like you need help setting up Skype with your Office 365 subscription.</span></span> <span data-ttu-id="39ac6-109">你可以按照本文中的步骤操作来完成设置。</span><span class="sxs-lookup"><span data-stu-id="39ac6-109">You can follow the steps in this article to get your setup completed.</span></span>

## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="39ac6-110">1. Skype for Business 计划</span><span class="sxs-lookup"><span data-stu-id="39ac6-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="39ac6-111">如果有 **[Office 365 商业高级版](https://products.office.com/en-us/business/office-365-business-premium)** 或 **商业协作版** ，则可使用 Skype for Business 拨打联机电话给企业中订阅上的其他人。</span><span class="sxs-lookup"><span data-stu-id="39ac6-111">If you have **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription.</span></span> <span data-ttu-id="39ac6-112">例如, 如果您的企业有10个人, 那么您可以在执行下面的步骤2-6 后, 您可以[开始使用 skype for](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) business 与 skype for business 一起使用 skype for business, 以及使用 skype for business 的 skype For business[会议](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)。</span><span class="sxs-lookup"><span data-stu-id="39ac6-112">For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below.</span></span> <span data-ttu-id="39ac6-113">您也可以[在 Outlook 中将 Skype For business 会议设置](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)为联机会议!</span><span class="sxs-lookup"><span data-stu-id="39ac6-113">And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>

<span data-ttu-id="39ac6-114">如果你想使用 Skype for Business 与组织 **外部** 的用户进行 *通话*  ，则有下列选项：</span><span class="sxs-lookup"><span data-stu-id="39ac6-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>

- <span data-ttu-id="39ac6-115">**选项 1。使用免费的 [Skype 应用](https://www.skype.com/)** 。</span><span class="sxs-lookup"><span data-stu-id="39ac6-115">**Option 1. Use the free [Skype app](https://www.skype.com/)**.</span></span> <span data-ttu-id="39ac6-116">如果企业的规模很小（例如，1-2 人），则使用 Skype 应用比较好。</span><span class="sxs-lookup"><span data-stu-id="39ac6-116">If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go.</span></span> <span data-ttu-id="39ac6-117">进行国内和国际呼叫的费用较低。</span><span class="sxs-lookup"><span data-stu-id="39ac6-117">It's less expensive to use for domestic and international calls.</span></span> <span data-ttu-id="39ac6-118">您仍可以举行电话会议、进行视频通话和分享桌面演示文稿。</span><span class="sxs-lookup"><span data-stu-id="39ac6-118">You can still hold conference calls, make video calls, and share your desktop for presentations.</span></span> <span data-ttu-id="39ac6-119">[检查费率和付款选项](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)。</span><span class="sxs-lookup"><span data-stu-id="39ac6-119">[Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>

- <span data-ttu-id="39ac6-120">**选项 2。升级你的计划，并购买 Office 365 的电话系统和呼叫计划** 。</span><span class="sxs-lookup"><span data-stu-id="39ac6-120">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**.</span></span> <span data-ttu-id="39ac6-121">了解这些成本的最简单的方法, 然后进行切换, 即[联系业务产品支持-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)并让他们为您执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="39ac6-121">The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>

<span data-ttu-id="39ac6-122">若要了解详细信息, 请参阅[规划 Office 365 for business 的设置](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。</span><span class="sxs-lookup"><span data-stu-id="39ac6-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>

## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="39ac6-123">2. 登录到 Office 365</span><span class="sxs-lookup"><span data-stu-id="39ac6-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="39ac6-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-124"></span></span>

<span data-ttu-id="39ac6-p107">Skype for Business Online 是 Office 365 服务套件的一部分。要设置 Skype for Business Online，你需要登录到 Office 365。下面介绍了如何操作：</span><span class="sxs-lookup"><span data-stu-id="39ac6-p107">Skype for Business Online is part of the Office 365 suite of services. To set up Skype for Business Online, you need to sign in to Office 365. Here's how you do that:</span></span>

1. <span data-ttu-id="39ac6-p108">查找你的 Office 365 用户 ID（例如， <em>rob@fourthcoffee.com</em>  ）。你收到了来自 Microsoft Online Services 团队的一封电子邮件，其中包含你在购买 Office 365 时创建的 Skype for Business Online 用户 ID。邮件内容如下所示：</span><span class="sxs-lookup"><span data-stu-id="39ac6-p108">Locate your Office 365 user ID (for example,  <em>rob@fourthcoffee.com</em>  ). You received an email from the Microsoft Online Services Team that contains the Office 365 user ID that you created when you purchased Skype for Business Online. The mail looks something like this:</span></span>

    ![在你注册 Skype for Business Online 之后收到的欢迎电子邮件的示例。 它包含你的 Office 365 用户 ID。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. <span data-ttu-id="39ac6-133">登录到 Office 365 管理中心, 然后输入您的 Office 365 用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="39ac6-133">Sign in to the Office 365 admin center and enter your Office 365 user ID and password.</span></span> <span data-ttu-id="39ac6-134">登录后，你将看到 Office 365 管理中心：</span><span class="sxs-lookup"><span data-stu-id="39ac6-134">After you sign in, you'll see the Office 365 admin center:</span></span>

    ![当你有 Skype for Business Online 计划时 Office 365 管理中心的外观的示例。](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)

## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="39ac6-136">3. 设置你的域和用户</span><span class="sxs-lookup"><span data-stu-id="39ac6-136">3. Set up your domain and users</span></span>
<span data-ttu-id="39ac6-137"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-137"></span></span>

<span data-ttu-id="39ac6-138">在登录到 Office 365 之后，你可以将你的域和你的组织中的用户设置为使用 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="39ac6-138">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>

1. <span data-ttu-id="39ac6-139">[将域和用户添加到 office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): 使用 office 365 安装向导设置自定义域 (如*Fourthcoffee.com*) 和 office 365。</span><span class="sxs-lookup"><span data-stu-id="39ac6-139">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365.</span></span> <span data-ttu-id="39ac6-140">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span><span class="sxs-lookup"><span data-stu-id="39ac6-140">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span></span> <span data-ttu-id="39ac6-141">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span><span class="sxs-lookup"><span data-stu-id="39ac6-141">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>

2. <span data-ttu-id="39ac6-p112">[检查你的域和 DNS 连接](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)：使用我们的工具（域疑难解答）检查你的域和 DNS 设置是否正确。执行此操作将发挥较大作用，可帮助解决任何安装问题，因为你可以避免 DNS 设置将来引起问题。</span><span class="sxs-lookup"><span data-stu-id="39ac6-p112">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct. Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>

3. <span data-ttu-id="39ac6-144">[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)：大多数小型企业不需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="39ac6-144">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step.</span></span> <span data-ttu-id="39ac6-145">**但是，如果你有限制访问部分 Web 的防火墙或代理服务器** ，你必须创建规则来允许访问 Skype for Business Online 终结点。</span><span class="sxs-lookup"><span data-stu-id="39ac6-145">**But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints.</span></span> <span data-ttu-id="39ac6-146">这是最好由有配置防火墙和代理服务器经验的人执行的高级步骤。</span><span class="sxs-lookup"><span data-stu-id="39ac6-146">This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers.</span></span> <span data-ttu-id="39ac6-147">如果您之前没有执行此操作, 请考虑聘用[Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为您设置 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="39ac6-147">If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="39ac6-148">4. 在你的组织中设置即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="39ac6-148">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="39ac6-149"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-149"></span></span>

<span data-ttu-id="39ac6-p114">即时消息 (IM) 和状态（[在 Skype for Business 中控制对你状态信息的访问](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)）是 Skype for Business 附带的基本功能。默认情况下，你的企业中的人员可以相互进行 Skype 和即时消息通信。</span><span class="sxs-lookup"><span data-stu-id="39ac6-p114">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business. By default, the people in your business can Skype and IM with each other.</span></span>

1. <span data-ttu-id="39ac6-152">**选择你的 Skype for Business 用户可以进行通信的人员：**</span><span class="sxs-lookup"><span data-stu-id="39ac6-152">**Choose who else your Skype for Business users can communicate with:**</span></span>

   - <span data-ttu-id="39ac6-153">[允许用户联系外部 Skype for Business 用户](allow-users-to-contact-external-skype-for-business-users.md) 你 *和*  其他企业将需要配置你的系统。</span><span class="sxs-lookup"><span data-stu-id="39ac6-153">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>

     <span data-ttu-id="39ac6-154">**重要** ：如果你的企业有两个域，例如 rob@contosowest.com 和 ina@contosoeast.com，你需要执行此操作，让你的所有用户之间都可以通信。</span><span class="sxs-lookup"><span data-stu-id="39ac6-154">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>

   - <span data-ttu-id="39ac6-155">[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="39ac6-155">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>

2. <span data-ttu-id="39ac6-156">**选择哪些人是否可以看到同事是否在线：** 状态功能显示谁处于在线状态及其可用性，例如有空、忙碌、离开或正在演示。</span><span class="sxs-lookup"><span data-stu-id="39ac6-156">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>

    ![An example of a person's online status with a personal message.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    <span data-ttu-id="39ac6-158">你可以为你的企业中的每个人选择默认设置：</span><span class="sxs-lookup"><span data-stu-id="39ac6-158">You can choose the default settings for everyone in your business:</span></span>

   - <span data-ttu-id="39ac6-159">自动向组织中的所有人显示某个用户的联机状态</span><span class="sxs-lookup"><span data-stu-id="39ac6-159">Automatically display a person's online presence to everyone in the organization</span></span>

   - <span data-ttu-id="39ac6-160">仅向某个用户的联系人显示其联机状态</span><span class="sxs-lookup"><span data-stu-id="39ac6-160">Display a person's online presence only to their contacts</span></span>

<span data-ttu-id="39ac6-161">有关说明，请参阅[在 Skype for Business Online 中配置状态](configure-presence-in-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="39ac6-161">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>

## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="39ac6-162">5. 下载并安装 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="39ac6-162">5. Download and install Skype for Business</span></span>
<span data-ttu-id="39ac6-163"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-163"></span></span>

<span data-ttu-id="39ac6-164">要在你的电脑、Mac 或移动设备上使用 Skype for Business，你和你的企业中的其他人必须首先在你的设备上安装 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="39ac6-164">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>

- <span data-ttu-id="39ac6-165">[安装 Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)：有关如何从 Office 365 门户下载该应用并将其安装在你的 PC 或 Mac 上的说明。</span><span class="sxs-lookup"><span data-stu-id="39ac6-165">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Office 365 portal, and install it on your PC or Mac.</span></span>

- <span data-ttu-id="39ac6-166">[在 Office 365 中部署 Skype For business 客户端](deploy-the-skype-for-business-client-in-office-365.md): 在大型企业中部署应用的说明。</span><span class="sxs-lookup"><span data-stu-id="39ac6-166">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>

- <span data-ttu-id="39ac6-167">[安装 Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)：在 Android 设备、iOS 设备和 Windows Phone 上下载、安装和登录 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="39ac6-167">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>

- <span data-ttu-id="39ac6-168">[打开或关闭移动电话通知](turn-on-or-off-mobile-phone-notifications.md): 当你在移动设备上安装了 Skype for business 时, 你和你的企业中的其他人可以接收有关传入和错过的即时消息的通知。</span><span class="sxs-lookup"><span data-stu-id="39ac6-168">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>

## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="39ac6-169">6. 测试以确保所有功能都能正常工作</span><span class="sxs-lookup"><span data-stu-id="39ac6-169">6. Test to make sure everything is working</span></span>
<span data-ttu-id="39ac6-170"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-170"></span></span>

<span data-ttu-id="39ac6-p115">首先，测试你和你的企业中的其他人是否可以[登录和注销 Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)。检查你们是否相互收发即时消息、查看彼此的状态，并尝试召开快速会议。</span><span class="sxs-lookup"><span data-stu-id="39ac6-p115">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451). Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>

<span data-ttu-id="39ac6-p116">有问题？请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="39ac6-p116">Problems? Do the following:</span></span>

- <span data-ttu-id="39ac6-175">[需要帮助登录到 Skype for Business 吗？](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)。</span><span class="sxs-lookup"><span data-stu-id="39ac6-175">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>

- <span data-ttu-id="39ac6-p117">[联系 Office 365 商业版支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。我们随时为你提供帮助！</span><span class="sxs-lookup"><span data-stu-id="39ac6-p117">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span>

## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="39ac6-178">想要设置其他可用的功能？</span><span class="sxs-lookup"><span data-stu-id="39ac6-178">Do you want to set up other available features?</span></span>
<span data-ttu-id="39ac6-179"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-179"></span></span>

<span data-ttu-id="39ac6-180">在设置更多功能之前, 请确保你有许可证。</span><span class="sxs-lookup"><span data-stu-id="39ac6-180">Before setting up more features, make sure you have licenses for them.</span></span> [<span data-ttu-id="39ac6-181">Skype for Business 和 Microsoft Teams 外接程序许可</span><span class="sxs-lookup"><span data-stu-id="39ac6-181">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a><span data-ttu-id="39ac6-182">设置音频会议</span><span class="sxs-lookup"><span data-stu-id="39ac6-182">Set up Audio Conferencing</span></span>

<span data-ttu-id="39ac6-p119">有时组织中的人员会需要使用电话呼入会议。Skype for Business 包含了正是针对此种情况的音频会议功能。人们可以使用电话呼入 Skype for Business 会议，而无需使用移动设备或电脑上的 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="39ac6-p119">Sometimes people in your organization will need to use a phone to call into a meeting. Skype for Business includes the Audio Conferencing feature for just this situation! People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="39ac6-186">在 Office 365 中设置电话系统和呼叫计划</span><span class="sxs-lookup"><span data-stu-id="39ac6-186">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="39ac6-p120">Office 365 中的电话系统功能提供了适用于你的业务的电话系统。呼叫组织中的其他 Skype for Business 人员是免费的，而且你的员工可以互相并从外部呼叫方接收语音邮件。以下是使用电话系统可获得的功能。</span><span class="sxs-lookup"><span data-stu-id="39ac6-p120">The Phone System feature in Office 365 gives you a phone system for your business. Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers. Here's what you get with Phone System.</span></span>

<span data-ttu-id="39ac6-p121">添加呼叫计划服务时，员工会在 Skype for Business 中获得主电话号码。他们可以拨打和接听公司外部的电话。他们可以通过 VolP 电话、电脑和移动设备进行语音呼叫，并且在紧急情况下，他们还可以呼叫 911 求助。</span><span class="sxs-lookup"><span data-stu-id="39ac6-p121">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business. They can make and receive phone calls outside of your business. They can make voice calls across VoIP phones, PCs, and mobile devices. And, in case of emergencies, they can call 911 for help.</span></span>

<span data-ttu-id="39ac6-194">有关分步设置说明，请参阅设置呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="39ac6-194">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="39ac6-195">设置 Skype 会议广播</span><span class="sxs-lookup"><span data-stu-id="39ac6-195">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="39ac6-p122">Skype 会议广播 是一项功能，允许你针对最多 10,000 个与会者制作、主持和直播会议。 **要了解其工作方式的详细信息，请参阅[什么是 Skype 会议直播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span><span class="sxs-lookup"><span data-stu-id="39ac6-p122">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees. **To learn more about how it works, see [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>

<span data-ttu-id="39ac6-198">以下是设置 Skype 会议广播 的步骤概述：</span><span class="sxs-lookup"><span data-stu-id="39ac6-198">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>

1. <span data-ttu-id="39ac6-199">[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)：为将 **主持** 直播会议的每个人分配 **Skype for Business Online** 或 **企业版计划** 许可证。</span><span class="sxs-lookup"><span data-stu-id="39ac6-199">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>

2. <span data-ttu-id="39ac6-200">[启用 Skype 会议直播](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): 默认情况下, 此功能未启用。</span><span class="sxs-lookup"><span data-stu-id="39ac6-200">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled.</span></span> <span data-ttu-id="39ac6-201">在启用该功能后，你的用户将能够与组织中的其他人一起主持直播会议。</span><span class="sxs-lookup"><span data-stu-id="39ac6-201">After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>

3. <span data-ttu-id="39ac6-202">[设置 Skype 会议直播网络](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): 如果要将多人网络研讨会和其他广播托管到组织外部的与会者, 需要配置您的网络。</span><span class="sxs-lookup"><span data-stu-id="39ac6-202">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>

4. <span data-ttu-id="39ac6-203">[安排 Skype 会议直播](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553)并[加入 skype 会议直播](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): 确保在*https://portal.broadcast.skype.com*会议中安排 skype 会议直播, 然后让某人尝试加入会议。</span><span class="sxs-lookup"><span data-stu-id="39ac6-203">[Schedule a Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>

## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="39ac6-204">了解网络连接的要求</span><span class="sxs-lookup"><span data-stu-id="39ac6-204">Learn about network connectivity requirements</span></span>
<span data-ttu-id="39ac6-205"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-205"></span></span>

<span data-ttu-id="39ac6-p124">Skype for Business 中音频、视频和应用程序共享的质量很大程度上受端到端网络连接质量的影响。为获得最佳体验，必须确保公司网络和 Skype for Business Online 间有高质量网络连接。有关网络和优化的信息，请参见 [优化 Skype for Business Online 性能](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。</span><span class="sxs-lookup"><span data-stu-id="39ac6-p124">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity. For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online. For network and tuning information, see [Tune Skype for Business Online performance](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="39ac6-209">全部设置已完成？</span><span class="sxs-lookup"><span data-stu-id="39ac6-209">All done setting up?</span></span> <span data-ttu-id="39ac6-210">开始使用 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="39ac6-210">Getting started using Skype for Business</span></span>
<span data-ttu-id="39ac6-211"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-211"></span></span>

<span data-ttu-id="39ac6-212">[Skype For business 培训](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): 查看此培训主题列表, 帮助您快速入门!</span><span class="sxs-lookup"><span data-stu-id="39ac6-212">[Skype for Business training](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>

[<span data-ttu-id="39ac6-213">开始 Skype for Business 电话会议</span><span class="sxs-lookup"><span data-stu-id="39ac6-213">Start a Skype for Business conference call</span></span>](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[<span data-ttu-id="39ac6-214">在 Skype for Business 中设置视频设备选项</span><span class="sxs-lookup"><span data-stu-id="39ac6-214">Set Video Device options in Skype for Business</span></span>](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[<span data-ttu-id="39ac6-215">使用 Skype for Business 拨打和接听视频呼叫</span><span class="sxs-lookup"><span data-stu-id="39ac6-215">Make and receive a video call using Skype for Business</span></span>](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="39ac6-216">相关主题</span><span class="sxs-lookup"><span data-stu-id="39ac6-216">Related topics</span></span>
<span data-ttu-id="39ac6-217"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="39ac6-217"></span></span>

[<span data-ttu-id="39ac6-218">计划 Skype for Business Server 与 Skype for Business Online 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="39ac6-218">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/p/?linkid=400791)



