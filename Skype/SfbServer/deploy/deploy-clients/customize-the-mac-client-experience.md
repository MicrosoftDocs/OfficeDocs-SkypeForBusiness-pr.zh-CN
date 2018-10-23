---
title: 在 Skype for Business 中自定义 Mac 客户端体验
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: PhillipGarding
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: 本文介绍 Mac 客户端上对 Skype for Business 可用的客户端首选项和默认值，以及如何在应用外部对其进行编辑。
ms.openlocfilehash: dd2f9b1d69e24f17cf76f33896804e5f50cd0ad3
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699293"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="6b751-103">在 Skype for Business 中自定义 Mac 客户端体验</span><span class="sxs-lookup"><span data-stu-id="6b751-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="6b751-104">本文介绍 Mac 客户端上对 Skype for Business 可用的客户端首选项和默认值，以及如何在应用外部对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="6b751-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="6b751-105">Mac 客户端上的 Skype for Business 首选项设置</span><span class="sxs-lookup"><span data-stu-id="6b751-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="6b751-106">某些功能和供 Mac 客户端的业务的 Skype 的行为由客户端上的首选项设置确定。</span><span class="sxs-lookup"><span data-stu-id="6b751-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="6b751-107">在 Mac 首选项的业务 Skype 找到文件位于安装业务客户端位于以下路径的 Skype 的 Mac 中：</span><span class="sxs-lookup"><span data-stu-id="6b751-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="6b751-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="6b751-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="6b751-109">若要设置这些首选项，获取客户端的 Mac 上的终端提示符下，并作为需要输入默认值写入 com.microsoft.SkypeForBusiness 关键命令使用下表中所述的首选项键。</span><span class="sxs-lookup"><span data-stu-id="6b751-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="6b751-110">**客户端首选项关键字**</span><span class="sxs-lookup"><span data-stu-id="6b751-110">**Client preference keys**</span></span>


| <span data-ttu-id="6b751-111">关键字</span><span class="sxs-lookup"><span data-stu-id="6b751-111">Key</span></span> | <span data-ttu-id="6b751-112">类型</span><span class="sxs-lookup"><span data-stu-id="6b751-112">Type</span></span> | <span data-ttu-id="6b751-113">值</span><span class="sxs-lookup"><span data-stu-id="6b751-113">Value</span></span> | <span data-ttu-id="6b751-114">说明</span><span class="sxs-lookup"><span data-stu-id="6b751-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b751-115">AutoDetectAutoDiscoveryURLs</span><span class="sxs-lookup"><span data-stu-id="6b751-115">AutoDetectAutoDiscoveryURLs</span></span>    |<span data-ttu-id="6b751-116">Bool</span><span class="sxs-lookup"><span data-stu-id="6b751-116">Bool</span></span>    |<span data-ttu-id="6b751-117">0 = 手动配置服务器</span><span class="sxs-lookup"><span data-stu-id="6b751-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="6b751-118">1 = 自动检测服务器（默认）</span><span class="sxs-lookup"><span data-stu-id="6b751-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="6b751-119">指定 for Business 的 Skype 识别传输类型和服务器登录过程中使用的方式。</span><span class="sxs-lookup"><span data-stu-id="6b751-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="6b751-120">如果启用此策略设置，则必须指定 **internalAutoDiscoveryURL** 和 **externalAutoDiscoveryURL**。</span><span class="sxs-lookup"><span data-stu-id="6b751-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="6b751-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="6b751-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="6b751-122">字符串</span><span class="sxs-lookup"><span data-stu-id="6b751-122">String</span></span>    |<span data-ttu-id="6b751-123">完全自动发现 URL</span><span class="sxs-lookup"><span data-stu-id="6b751-123">Full autodiscover URL</span></span>    |<span data-ttu-id="6b751-124">内部自动发现 URL</span><span class="sxs-lookup"><span data-stu-id="6b751-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="6b751-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="6b751-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="6b751-126">字符串</span><span class="sxs-lookup"><span data-stu-id="6b751-126">String</span></span>    |<span data-ttu-id="6b751-127">完全自动发现 URL</span><span class="sxs-lookup"><span data-stu-id="6b751-127">Full autodiscover URL</span></span>    |<span data-ttu-id="6b751-128">外部自动发现 URL</span><span class="sxs-lookup"><span data-stu-id="6b751-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="6b751-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="6b751-129">httpProxyDomain</span></span>    |<span data-ttu-id="6b751-130">字符串</span><span class="sxs-lookup"><span data-stu-id="6b751-130">String</span></span>    ||<span data-ttu-id="6b751-131">HTTP 代理域</span><span class="sxs-lookup"><span data-stu-id="6b751-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="6b751-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="6b751-132">httpProxyUserName</span></span>    |<span data-ttu-id="6b751-133">字符串</span><span class="sxs-lookup"><span data-stu-id="6b751-133">String</span></span>    ||<span data-ttu-id="6b751-134">HTTP 代理用户名</span><span class="sxs-lookup"><span data-stu-id="6b751-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="6b751-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="6b751-135">httpProxyPassword</span></span>    |<span data-ttu-id="6b751-136">字符串</span><span class="sxs-lookup"><span data-stu-id="6b751-136">String</span></span>    ||<span data-ttu-id="6b751-137">HTTP 代理密码</span><span class="sxs-lookup"><span data-stu-id="6b751-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="6b751-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="6b751-138">trustedDomainList</span></span>    |<span data-ttu-id="6b751-139">数组</span><span class="sxs-lookup"><span data-stu-id="6b751-139">Array</span></span>    ||<span data-ttu-id="6b751-140">HTTP 重定向的受信任域列表。</span><span class="sxs-lookup"><span data-stu-id="6b751-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="6b751-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="6b751-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="6b751-142">数字</span><span class="sxs-lookup"><span data-stu-id="6b751-142">Number</span></span>    |<span data-ttu-id="6b751-143">300（默认值）</span><span class="sxs-lookup"><span data-stu-id="6b751-143">300 (default)</span></span>    |<span data-ttu-id="6b751-144">无服务器端对话历史记录时，用户的自动接受超时时间。</span><span class="sxs-lookup"><span data-stu-id="6b751-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="6b751-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="6b751-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="6b751-146">Bool</span><span class="sxs-lookup"><span data-stu-id="6b751-146">Bool</span></span>    |<span data-ttu-id="6b751-147">0 = 已禁用</span><span class="sxs-lookup"><span data-stu-id="6b751-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="6b751-148">1 = 已启用</span><span class="sxs-lookup"><span data-stu-id="6b751-148">1 = Enabled</span></span>    |<span data-ttu-id="6b751-149">从未知位置拨打紧急号码时警告用户。</span><span class="sxs-lookup"><span data-stu-id="6b751-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="6b751-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="6b751-150">sipAddress</span></span>    |<span data-ttu-id="6b751-151">字符串</span><span class="sxs-lookup"><span data-stu-id="6b751-151">String</span></span>    ||<span data-ttu-id="6b751-152">SIP 地址 （电子邮件） 用于登录到 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="6b751-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="6b751-153">userName</span><span class="sxs-lookup"><span data-stu-id="6b751-153">userName</span></span>    |<span data-ttu-id="6b751-154">字符串</span><span class="sxs-lookup"><span data-stu-id="6b751-154">String</span></span>    ||<span data-ttu-id="6b751-155">用来登录到 for Business 的 Skype UPN （用户名）。</span><span class="sxs-lookup"><span data-stu-id="6b751-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="6b751-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="6b751-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="6b751-157">Bool</span><span class="sxs-lookup"><span data-stu-id="6b751-157">Bool</span></span>    |<span data-ttu-id="6b751-158">0 = 主要的登录屏幕上和高级属性对话框中显示用户名称字段</span><span class="sxs-lookup"><span data-stu-id="6b751-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="6b751-159">1 = 只在高级属性对话框 （默认值） 显示用户名称字段</span><span class="sxs-lookup"><span data-stu-id="6b751-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="6b751-160">指定用户名字段登录过程中的显示位置。</span><span class="sxs-lookup"><span data-stu-id="6b751-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="6b751-161">使用示例</span><span class="sxs-lookup"><span data-stu-id="6b751-161">Usage examples</span></span>

<span data-ttu-id="6b751-162">若要向受信任的域列表添加单个域 (Contoso.com) 需要使用 trustedDomainList 键，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b751-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="6b751-163">默认值写入 com.microsoft.SkypeForBusiness trustedDomainList-数组-添加"Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="6b751-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="6b751-164">要将多个域添加到受信任域列表，按如下所示使用 trustedDomainList 关键字：</span><span class="sxs-lookup"><span data-stu-id="6b751-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="6b751-165">默认值写入 com.microsoft.SkypeForBusiness trustedDomainList-数组-添加"sfb.com""abc.com""test.org"</span><span class="sxs-lookup"><span data-stu-id="6b751-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="6b751-166">未编辑的设置示例</span><span class="sxs-lookup"><span data-stu-id="6b751-166">Sample unedited settings</span></span>

<span data-ttu-id="6b751-167">如需参考，此处是仅使用默认设置的设置文件示例：</span><span class="sxs-lookup"><span data-stu-id="6b751-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
