---
title: "管理员 Skype 业务联机登录错误疑难解答"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "了解常见原因为 Skype 的在线业务的符号错误和工作通过解决这些问题。 "
ms.openlocfilehash: 55ef2775ecc2f04fe9ce89dc8691c9186512a0e0
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a><span data-ttu-id="81ca8-103">管理员 Skype 业务联机登录错误疑难解答</span><span class="sxs-lookup"><span data-stu-id="81ca8-103">Troubleshooting Skype for Business Online sign-in errors for administrators</span></span>

<span data-ttu-id="81ca8-104">为了解决 Skype 业务联机登录错误，请首先消除登录困难的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="81ca8-104">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty.</span></span> <span data-ttu-id="81ca8-105">如有必要，您可以按照特定的分辨率根据错误类型的步骤。</span><span class="sxs-lookup"><span data-stu-id="81ca8-105">If necessary, you can then follow specific resolution steps based on the type of error.</span></span> <span data-ttu-id="81ca8-106">如果用户仍然不能登录，收集的其他信息，然后再寻求更多帮助。</span><span class="sxs-lookup"><span data-stu-id="81ca8-106">If the user still cannot sign in, collect additional information, and then seek additional help.</span></span> 
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="81ca8-107">你要做什么？</span><span class="sxs-lookup"><span data-stu-id="81ca8-107">What do you want to do?</span></span>
<span data-ttu-id="81ca8-108"><a name="top"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-108"></span></span>

> [<span data-ttu-id="81ca8-109">检查的 Skype 业务联机登录错误的常见原因</span><span class="sxs-lookup"><span data-stu-id="81ca8-109">Check for common causes of Skype for Business Online sign-in errors</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
    
> [<span data-ttu-id="81ca8-110">按照一个特定的错误 （仅适用于企业） 的解决方法步骤</span><span class="sxs-lookup"><span data-stu-id="81ca8-110">Follow resolution steps for a specific error (Enterprise only)</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
    
> [<span data-ttu-id="81ca8-111">将 msoidsvc.exe 防火墙项添加到您的代理服务器</span><span class="sxs-lookup"><span data-stu-id="81ca8-111">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
    
> [<span data-ttu-id="81ca8-112">更新 DNS 设置</span><span class="sxs-lookup"><span data-stu-id="81ca8-112">Update DNS settings</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
    
> [<span data-ttu-id="81ca8-113">ADFS 在服务器上安装一个第三方的 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="81ca8-113">Install a third-party SSL certificate on your ADFS server</span></span>](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
    
> [<span data-ttu-id="81ca8-114">更新的安全凭据</span><span class="sxs-lookup"><span data-stu-id="81ca8-114">Update security credentials</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
    
> [<span data-ttu-id="81ca8-115">修改 TrustModelData 注册表项</span><span class="sxs-lookup"><span data-stu-id="81ca8-115">Modify TrustModelData registry keys</span></span>](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
    
> [<span data-ttu-id="81ca8-116">更新在 Active Directory 中的用户设置</span><span class="sxs-lookup"><span data-stu-id="81ca8-116">Update user settings in Active Directory</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
    
> [<span data-ttu-id="81ca8-117">使用 Microsoft 支持故障排除指南</span><span class="sxs-lookup"><span data-stu-id="81ca8-117">Use the Microsoft Support troubleshooting guide</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
    
> [<span data-ttu-id="81ca8-118">收集的详细信息，并寻求额外的帮助</span><span class="sxs-lookup"><span data-stu-id="81ca8-118">Collect more information and seek additional help </span></span>](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)
    
## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a><span data-ttu-id="81ca8-119">检查的 Skype 业务联机登录错误的常见原因</span><span class="sxs-lookup"><span data-stu-id="81ca8-119">Check for common causes of Skype for Business Online sign-in errors</span></span>
<span data-ttu-id="81ca8-120"><a name="toc323194094"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-120"></span></span>

<span data-ttu-id="81ca8-121">符号中的大多数问题可以归因为对数目较少的原因，和许多种可以很容易地更正。</span><span class="sxs-lookup"><span data-stu-id="81ca8-121">Most sign-in issues can be traced to a small number of causes, and many of these are easy to correct.</span></span> <span data-ttu-id="81ca8-122">下表列出了登录错误的某些常见原因和一些您或用户可以采取的措施来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="81ca8-122">The table below lists some common causes of sign-in errors and some steps you or the users can take to resolve them.</span></span>
  
|<span data-ttu-id="81ca8-123">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="81ca8-123">**Possible Cause**</span></span>|<span data-ttu-id="81ca8-124">**解析**</span><span class="sxs-lookup"><span data-stu-id="81ca8-124">**Resolution**</span></span>|
|:-----|:-----|
|<span data-ttu-id="81ca8-125">在签入期间会出现一个对话框，其中包含下列文字：**不能验证服务器是否信任您的登录地址。是否仍要连接？**</span><span class="sxs-lookup"><span data-stu-id="81ca8-125">During sign-in, a dialog box appears that contains the following phrase: **cannot verify that the server is trusted for your sign-in address. Connect anyway?**</span></span> <br/> |<span data-ttu-id="81ca8-126">验证是否在对话框中的域名是您的组织中受信任的服务器 — — 例如， **domainName.contoso.com**。要求用户选中**始终信任此服务器**复选框，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-126">Verify that the domain name in the dialog box is a trusted server in your organization—for example, **domainName.contoso.com**. Ask the user to select the **Always trust this server** check box, and then click **Connect**.</span></span> <br/> <span data-ttu-id="81ca8-127">企业客户可以防止用户签署第一次通过修改每个用户的计算机上的 Windows 注册表时出现此消息。</span><span class="sxs-lookup"><span data-stu-id="81ca8-127">Enterprise customers can prevent this message from appearing when a user signs in for the first time by modifying the Windows registry on each user's computer.</span></span> <span data-ttu-id="81ca8-128">有关详细信息，请参阅[修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)。</span><span class="sxs-lookup"><span data-stu-id="81ca8-128">For details, see [Modify TrustModelData registry keys](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).</span></span><br/> |
|<span data-ttu-id="81ca8-129">键入登录地址、 用户名或密码</span><span class="sxs-lookup"><span data-stu-id="81ca8-129">Mistyped sign-in address, user name, or password</span></span>  <br/> | <span data-ttu-id="81ca8-130">确认用户的登录名和密码正确。</span><span class="sxs-lookup"><span data-stu-id="81ca8-130">Confirm that the user's sign-in name and password are correct.</span></span> <br/>  <span data-ttu-id="81ca8-131">验证用户的登录名的格式如下： **bobk@contoso.com**。这可能不同于您用于登录到您的组织的网络的格式。</span><span class="sxs-lookup"><span data-stu-id="81ca8-131">Verify that the user's sign-in name is formatted as follows: **bobk@contoso.com**. This may be different from the format you use to sign in to your organization's network.</span></span>  <br/>  <span data-ttu-id="81ca8-132">要求用户再次尝试登录。</span><span class="sxs-lookup"><span data-stu-id="81ca8-132">Ask the user to try signing in again.</span></span> <br/> |
|<span data-ttu-id="81ca8-133">忘记的密码</span><span class="sxs-lookup"><span data-stu-id="81ca8-133">Forgotten password</span></span>  <br/> |<span data-ttu-id="81ca8-134">重置用户的密码并通知他 （或她） 的新的临时密码。</span><span class="sxs-lookup"><span data-stu-id="81ca8-134">Reset the user's password and notify him or her of the new temporary password.</span></span>  <br/> |
|<span data-ttu-id="81ca8-135">未被授权用于 Skype 在线业务</span><span class="sxs-lookup"><span data-stu-id="81ca8-135">Not licensed to use Skype for Business Online</span></span>  <br/> |<span data-ttu-id="81ca8-136">请确认该用户被视为业务在线用户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="81ca8-136">Confirm that the user is registered as a Skype for Business Online user.</span></span> <span data-ttu-id="81ca8-137">如果不是，注册用户，并询问他或她再次登录。</span><span class="sxs-lookup"><span data-stu-id="81ca8-137">If not, register the user, and then ask him or her to sign in again.</span></span>  <br/> |
|<span data-ttu-id="81ca8-138">Skype 业务在线安装的版本不正确</span><span class="sxs-lookup"><span data-stu-id="81ca8-138">Wrong version of Skype for Business Online installed</span></span>  <br/> |<span data-ttu-id="81ca8-139">此问题是通常与错误消息包含下面的短语：**可能是身份验证服务与程序的当前版本不兼容**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-139">This issue is usually associated with an error message that contains the following phrase: **the authentication service may be incompatible with this version of the program**.</span></span>  <br/> <span data-ttu-id="81ca8-140">要求用户卸载并重新安装 Office 365 门户在线业务的 Skype。</span><span class="sxs-lookup"><span data-stu-id="81ca8-140">Ask the user to uninstall and reinstall Skype for Business Online from the Office 365 Portal.</span></span>  <br/> |
|<span data-ttu-id="81ca8-141">获得个人证书所需登录问题</span><span class="sxs-lookup"><span data-stu-id="81ca8-141">Problem acquiring a personal certificate that is required to sign in</span></span>  <br/> |<span data-ttu-id="81ca8-142">如果最近更改了用户的登录地址，它们可能需要删除缓存的登录数据。</span><span class="sxs-lookup"><span data-stu-id="81ca8-142">If the user's sign-in address has recently changed, they may need to delete cached sign-in data.</span></span> <span data-ttu-id="81ca8-143">询问用户注销，请单击的删除我的登录信息链接在登录屏幕上，并再试一次。</span><span class="sxs-lookup"><span data-stu-id="81ca8-143">Ask users to sign out, click the Delete my sign-in info link on the sign-in screen, and then try again.</span></span>  <br/> |
|<span data-ttu-id="81ca8-144">设置自定义的域名，并不可能传播通过系统完成所做的更改。</span><span class="sxs-lookup"><span data-stu-id="81ca8-144">You set up a custom domain name, and the changes may not have finished propagating through the system.</span></span>  <br/> |<span data-ttu-id="81ca8-145">首先，确保您已修改了域名服务 (DNS) 记录以反映此更改。</span><span class="sxs-lookup"><span data-stu-id="81ca8-145">First, ensure that you have modified the Domain Name Service (DNS) records to reflect the change.</span></span>  <br/> <span data-ttu-id="81ca8-146">如果您已进行必要的 DNS 更改，建议用户尝试登录以后。</span><span class="sxs-lookup"><span data-stu-id="81ca8-146">If you have already made the necessary DNS changes, advise the user to try logging in later.</span></span> <span data-ttu-id="81ca8-147">DNS 更改可能需要 72 小时可以反映整个系统。</span><span class="sxs-lookup"><span data-stu-id="81ca8-147">DNS changes can take up to 72 hours to be reflected throughout the system.</span></span>  <br/> |
|<span data-ttu-id="81ca8-148">系统同步的服务器时钟的时钟</span><span class="sxs-lookup"><span data-stu-id="81ca8-148">System clock out of sync with server clock</span></span>  <br/> |<span data-ttu-id="81ca8-149">确保您网络的域控制器与可靠的外部时间源同步。</span><span class="sxs-lookup"><span data-stu-id="81ca8-149">Ensure that your network domain controller is synchronizing with a reliable external time source.</span></span> <span data-ttu-id="81ca8-150">有关详细信息，请参阅 Microsoft 知识库文章 816042，[如何配置 Windows 服务器的权威时间服务器](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)。</span><span class="sxs-lookup"><span data-stu-id="81ca8-150">For details, see the Microsoft Knowledge Base article 816042, [How to configure an authoritative time server in Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).</span></span><br/> |
   
<span data-ttu-id="81ca8-151">为了解决 Skype 业务联机登录错误，请首先消除登录困难的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="81ca8-151">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty.</span></span> <span data-ttu-id="81ca8-152">如有必要，您可以按照特定的分辨率根据错误类型的步骤。</span><span class="sxs-lookup"><span data-stu-id="81ca8-152">If necessary, you can then follow specific resolution steps based on the type of error.</span></span> <span data-ttu-id="81ca8-153">如果用户仍然不能登录，收集的其他信息，然后再寻求更多帮助。</span><span class="sxs-lookup"><span data-stu-id="81ca8-153">If the user still cannot sign in, collect additional information, and then seek additional help.</span></span> 
  
## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a><span data-ttu-id="81ca8-154">按照一个特定的错误 （仅适用于企业） 的解决方法步骤</span><span class="sxs-lookup"><span data-stu-id="81ca8-154">Follow resolution steps for a specific error (Enterprise only)</span></span>
<span data-ttu-id="81ca8-155"><a name="toc325626440"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-155"></span></span>

> [!IMPORTANT]
>  <span data-ttu-id="81ca8-156">这些说明是主要适用于 Microsoft Office 365 计划电子客户。</span><span class="sxs-lookup"><span data-stu-id="81ca8-156">These instructions are intended primarily for Microsoft Office 365 Plan E customers.</span></span> <span data-ttu-id="81ca8-157">如果您是 Office 365 计划 P 客户，继续下一节，[收集更多的信息，并寻求额外的帮助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)。</span><span class="sxs-lookup"><span data-stu-id="81ca8-157">If you are an Office 365 Plan P customer, continue to the following section,[Collect more information and seek additional help ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).</span></span> 
  
<span data-ttu-id="81ca8-158">如果您已经尝试了上一节中的建议之后，用户无法登录，则可以执行根据错误类型的其它故障诊断。</span><span class="sxs-lookup"><span data-stu-id="81ca8-158">If the user cannot sign in after you have tried the suggestions in the previous section, then you can do additional troubleshooting based on the type of error.</span></span> <span data-ttu-id="81ca8-159">下表列出了最常见的错误消息和可能的原因。</span><span class="sxs-lookup"><span data-stu-id="81ca8-159">The table below lists the most common error messages and possible causes.</span></span> <span data-ttu-id="81ca8-160">下表是以解决每个问题的详细的过程。</span><span class="sxs-lookup"><span data-stu-id="81ca8-160">Following the table are detailed procedures to address each issue.</span></span>
  
|<span data-ttu-id="81ca8-161">**错误消息**</span><span class="sxs-lookup"><span data-stu-id="81ca8-161">**Error message**</span></span>|<span data-ttu-id="81ca8-162">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="81ca8-162">**Possible cause**</span></span>|<span data-ttu-id="81ca8-163">**解析**</span><span class="sxs-lookup"><span data-stu-id="81ca8-163">**Resolution**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="81ca8-164">找不到的登录地址</span><span class="sxs-lookup"><span data-stu-id="81ca8-164">Sign-in address not found</span></span>  <br/> |<span data-ttu-id="81ca8-165">从 Microsoft 联机服务登录助手 (msoidsvc.exe) 的登录请求将不会通过外部的防火墙或代理服务器。</span><span class="sxs-lookup"><span data-stu-id="81ca8-165">Sign-in requests from the Microsoft Online Services Sign-On Assistant (msoidsvc.exe) are not going through your external firewall, or proxy server.</span></span>  <br/> |[<span data-ttu-id="81ca8-166">将 msoidsvc.exe 防火墙项添加到您的代理服务器</span><span class="sxs-lookup"><span data-stu-id="81ca8-166">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|<span data-ttu-id="81ca8-167">服务器当前不可用</span><span class="sxs-lookup"><span data-stu-id="81ca8-167">Server is temporarily unavailable</span></span>  <br/> |<span data-ttu-id="81ca8-168">如果您的组织自定义的域，则必要的域名系统 (DNS) 设置可能会丢失或不正确。</span><span class="sxs-lookup"><span data-stu-id="81ca8-168">If your organization has a custom domain, the necessary Domain Name System (DNS) settings may be missing or incorrect.</span></span>  <br/> |[<span data-ttu-id="81ca8-169">更新 DNS 设置</span><span class="sxs-lookup"><span data-stu-id="81ca8-169">Update DNS settings</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|<span data-ttu-id="81ca8-170">服务器当前不可用</span><span class="sxs-lookup"><span data-stu-id="81ca8-170">Server is temporarily unavailable</span></span>  <br/> |<span data-ttu-id="81ca8-171">如果您的组织与活动目录联合身份验证服务 (ADF) 使用单一登录，您可能使用的是自签名的安全套接字层 (SSL) 证书，而不是从第三方证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="81ca8-171">If your organization is using single sign-on with Active Directory Federation Services (ADFS), you may have used a self-signed Secure Socket Layer (SSL) certificate rather than one from a third-party certification authority.</span></span>  <br/> |[<span data-ttu-id="81ca8-172">ADFS 在服务器上安装一个第三方的 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="81ca8-172">Install a third-party SSL certificate on your ADFS server</span></span>](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|<span data-ttu-id="81ca8-173">获得个人证书所需登录问题</span><span class="sxs-lookup"><span data-stu-id="81ca8-173">Problem acquiring a personal certificate that is required to sign in</span></span>  <br/> |<span data-ttu-id="81ca8-174">如果您已经删除了已缓存的服务器数据用于登录错误继续出现，可能损坏用户的安全凭据，或 RSA 文件夹在用户的计算机上可能会阻止身份验证。</span><span class="sxs-lookup"><span data-stu-id="81ca8-174">If you've already removed the cached server data used to sign in and the error continues to appear, the user's security credentials may be corrupted, or an RSA folder on the user's computer may be blocking authentication.</span></span>  <br/> |[<span data-ttu-id="81ca8-175">更新的安全凭据</span><span class="sxs-lookup"><span data-stu-id="81ca8-175">Update security credentials</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|<span data-ttu-id="81ca8-176">当用户首次登录时，会出现证书信任对话框。</span><span class="sxs-lookup"><span data-stu-id="81ca8-176">A certificate trust dialog box appears when a user signs in for the first time.</span></span>  <br/> |<span data-ttu-id="81ca8-177">如果您 Skype 业务服务器未列出的**TrustModelData**注册表项中，将出现此对话框。</span><span class="sxs-lookup"><span data-stu-id="81ca8-177">This dialog box appears if your Skype for Business server is not yet listed in the **TrustModelData** registry key.</span></span> <br/> |[<span data-ttu-id="81ca8-178">修改 TrustModelData 注册表项</span><span class="sxs-lookup"><span data-stu-id="81ca8-178">Modify TrustModelData registry keys</span></span>](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|<span data-ttu-id="81ca8-179">不启用了 SIP 用户。</span><span class="sxs-lookup"><span data-stu-id="81ca8-179">User is not SIP enabled</span></span>  <br/> |<span data-ttu-id="81ca8-180">如果您的组织具有以前安装的 Microsoft Office 通信服务器或 Microsoft Lync Server 2010 中，您可能不具有您的用户从服务器上删除在停止使用它之前。</span><span class="sxs-lookup"><span data-stu-id="81ca8-180">If your organization had a previous installation of Microsoft Office Communications Server or Microsoft Lync Server 2010, you may not have deleted your users from the server before decommissioning it.</span></span> <span data-ttu-id="81ca8-181">因此， **msRTCSIP UserEnabled**属性仍设置为**FALSE**在 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="81ca8-181">As a result, the **msRTCSIP-UserEnabled** attribute is still set to **FALSE** in Active Directory Domain Services.</span></span> <br/> |[<span data-ttu-id="81ca8-182">更新在 Active Directory 中的用户设置</span><span class="sxs-lookup"><span data-stu-id="81ca8-182">Update user settings in Active Directory</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |
   
### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a><span data-ttu-id="81ca8-183">将 msoidsvc.exe 防火墙项添加到您的代理服务器</span><span class="sxs-lookup"><span data-stu-id="81ca8-183">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>
<span data-ttu-id="81ca8-184"><a name="add-a-firewall"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-184"></span></span>

<span data-ttu-id="81ca8-185">此过程是下面的错误消息的可能解决方法：**找不到的登录地址**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-185">This procedure is a possible fix for the following error message: **Sign-in address not found**.</span></span>
  
 <span data-ttu-id="81ca8-186">**注意**： 以下步骤假定您使用的 Microsoft 最前沿威胁管理网关 (TMG) 2010年。</span><span class="sxs-lookup"><span data-stu-id="81ca8-186">**NOTE**: The following steps assume you are using Microsoft Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="81ca8-187">如果您有另一个站点的网关解决方案，使用下面的步骤 4 中所述的设置。</span><span class="sxs-lookup"><span data-stu-id="81ca8-187">If you have a different web gateway solution, use the settings described in step 4 below.</span></span>
  
<span data-ttu-id="81ca8-188">要为在前沿 TMG 2010 Msoidsvc.exe 创建一个应用程序项目，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="81ca8-188">To create an application entry for Msoidsvc.exe in Forefront TMG 2010, follow these steps:</span></span>
  
1. <span data-ttu-id="81ca8-189">在最前沿的左窗格中，单击**网络**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-189">In the Forefront left pane, click **Networking**.</span></span>
    
2. <span data-ttu-id="81ca8-190">单击**网络**选项卡。在右窗格中的**任务**选项卡上，单击**配置 Forefront TMG 客户端设置**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-190">Click the **Network** tab. Under the **Tasks** tab in the right pane, click **Configure Forefront TMG Client Settings**.</span></span>
    
3. <span data-ttu-id="81ca8-191">在**最前沿 TMG 客户端设置**对话框中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-191">In the **Forefront TMG Client Settings** dialog box, click **New**.</span></span>
    
4. <span data-ttu-id="81ca8-192">在**应用程序项目设置**对话框中，配置以下规则：</span><span class="sxs-lookup"><span data-stu-id="81ca8-192">In the **Application Entry Setting** dialog box, configure the following rules:</span></span>
    
|<span data-ttu-id="81ca8-193">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="81ca8-193">**Application**</span></span>|<span data-ttu-id="81ca8-194">**密钥**</span><span class="sxs-lookup"><span data-stu-id="81ca8-194">**Key**</span></span>|<span data-ttu-id="81ca8-195">**值**</span><span class="sxs-lookup"><span data-stu-id="81ca8-195">**Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="81ca8-196">**msoidsvc**</span><span class="sxs-lookup"><span data-stu-id="81ca8-196">**msoidsvc**</span></span> <br/> |<span data-ttu-id="81ca8-197">禁用</span><span class="sxs-lookup"><span data-stu-id="81ca8-197">Disable</span></span>  <br/> |<span data-ttu-id="81ca8-198">0</span><span class="sxs-lookup"><span data-stu-id="81ca8-198">0</span></span>  <br/> |
|<span data-ttu-id="81ca8-199">**msoidsvc**</span><span class="sxs-lookup"><span data-stu-id="81ca8-199">**msoidsvc**</span></span> <br/> |<span data-ttu-id="81ca8-200">DisableEx</span><span class="sxs-lookup"><span data-stu-id="81ca8-200">DisableEx</span></span>  <br/> |<span data-ttu-id="81ca8-201">0</span><span class="sxs-lookup"><span data-stu-id="81ca8-201">0</span></span>  <br/> |
   
<span data-ttu-id="81ca8-202">有关详细信息，请参阅 Microsoft 知识库文章 2409256，[由于内部防火墙会阻止该连接无法连接到 Skype 的在线业务](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)。</span><span class="sxs-lookup"><span data-stu-id="81ca8-202">For details, see the Microsoft Knowledge Base article 2409256, [You cannot connect to Skype for Business Online because an on-premises firewall blocks the connection](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).</span></span>
  
### <a name="update-dns-settings"></a><span data-ttu-id="81ca8-203">更新 DNS 设置</span><span class="sxs-lookup"><span data-stu-id="81ca8-203">Update DNS settings</span></span>
<span data-ttu-id="81ca8-204"><a name="update-dns-service"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-204"></span></span>

<span data-ttu-id="81ca8-205">如果您的组织自定义的域，此过程是下面的错误消息的可能解决方法：**服务器当前不可用**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-205">If your organization has a custom domain, this procedure is a possible fix for the following error message: **Server is temporarily unavailable**.</span></span>
  
- <span data-ttu-id="81ca8-206">有关如何将以下的 CNAME 记录添加到您的域的信息联系您的域名称注册：</span><span class="sxs-lookup"><span data-stu-id="81ca8-206">Contact your domain name registrar for information on how to add the following CNAME record to your domain:</span></span>
    
  - <span data-ttu-id="81ca8-207">**DNS 记录类型**： CNAME</span><span class="sxs-lookup"><span data-stu-id="81ca8-207">**DNS record type**: CNAME</span></span> 
    
  - <span data-ttu-id="81ca8-208">**名称**： sip</span><span class="sxs-lookup"><span data-stu-id="81ca8-208">**Name**: sip</span></span>
    
  - <span data-ttu-id="81ca8-209">**值/目标**： sipdir.online.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="81ca8-209">**Value/Destination**: sipdir.online.microsoft.com</span></span>
    
<span data-ttu-id="81ca8-210">有关详细信息，请参阅 Microsoft 知识库文章 2566790， [Office 365 中的业务在线 DNS 配置问题的故障排除 Skype](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)。</span><span class="sxs-lookup"><span data-stu-id="81ca8-210">For details, see the Microsoft Knowledge Base article 2566790, [Troubleshooting Skype for Business Online DNS configuration issues in Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).</span></span>
  
### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a><span data-ttu-id="81ca8-211">ADFS 在服务器上安装一个第三方的 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="81ca8-211">Install a third-party SSL certificate on your ADFS server</span></span>
<span data-ttu-id="81ca8-212"><a name="verify-upn-and"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-212"></span></span>

<span data-ttu-id="81ca8-213">以活动域联合身份验证服务 (ADF) 在服务器上安装一个第三方的 SSL 证书，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="81ca8-213">To install a third-party SSL certificate on your Active Domain Federation Services (ADFS) server, follow these steps:</span></span>
  
1. <span data-ttu-id="81ca8-214">从第三方证书颁发机构如 VeriSign 或 Thawte 获取 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="81ca8-214">Obtain an SSL certificate from a third-party certification authority such as VeriSign or Thawte.</span></span>
    
2. <span data-ttu-id="81ca8-215">使用 ADFS 管理控制台在 ADFS 服务器上安装证书。</span><span class="sxs-lookup"><span data-stu-id="81ca8-215">Install the certificate on your ADFS server by using the ADFS management console.</span></span> 
    
### <a name="update-security-credentials"></a><span data-ttu-id="81ca8-216">更新的安全凭据</span><span class="sxs-lookup"><span data-stu-id="81ca8-216">Update security credentials</span></span>
<span data-ttu-id="81ca8-217"><a name="update-security-credentials"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-217"></span></span>

<span data-ttu-id="81ca8-218">此过程是可能的修复**问题获得个人证书登录所需**的错误消息。</span><span class="sxs-lookup"><span data-stu-id="81ca8-218">This procedure is a possible fix for the error message **Problem acquiring a personal certificate required to sign in**.</span></span>
  
<span data-ttu-id="81ca8-219">若要消除可能的证书或凭据问题，第一次续订的证书用户的 Windows 证书管理器中。</span><span class="sxs-lookup"><span data-stu-id="81ca8-219">To eliminate possible certificate or credential problems, first renew the user's certificate in Windows Certificate Manager.</span></span> <span data-ttu-id="81ca8-220">若要执行此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="81ca8-220">To do this, follow these steps:</span></span>
  
1. <span data-ttu-id="81ca8-221">打开 Windows 证书管理器。</span><span class="sxs-lookup"><span data-stu-id="81ca8-221">Open Windows Certificate Manager.</span></span> <span data-ttu-id="81ca8-222">若要执行此操作，单击**开始**，单击**运行**，键入**certmgr.msc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-222">To do this, click **Start**, click **Run**, type **certmgr.msc**, and then click **OK**.</span></span> 
    
2. <span data-ttu-id="81ca8-223">双击**个人**，然后双击**证书**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-223">Double-click **Personal**, and then double-click **Certificates**.</span></span> 
    
3. <span data-ttu-id="81ca8-224">通信服务器颁发的证书，然后查找与**颁发者**列进行排序。</span><span class="sxs-lookup"><span data-stu-id="81ca8-224">Sort by the **Issued By** column, and then look for a certificate that is issued by Communications Server.</span></span>
    
4. <span data-ttu-id="81ca8-225">用鼠标右键单击证书，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-225">Right-click the certificate, and then click **Delete**.</span></span> 
    
<span data-ttu-id="81ca8-226">接下来，如果用户在运行 Windows 7，删除它们存储的凭据 Windows 凭据管理器中。</span><span class="sxs-lookup"><span data-stu-id="81ca8-226">Next, if the user is running Windows 7, remove their stored credentials in Windows Credential Manager.</span></span> <span data-ttu-id="81ca8-227">若要执行此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="81ca8-227">To do this, follow these steps:</span></span>
  
1. <span data-ttu-id="81ca8-228">单击**开始**，单击**控制面板**，然后单击**凭据管理器**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-228">Click **Start**, click **Control Panel**, and then click **Credential Manager**.</span></span> 
    
2. <span data-ttu-id="81ca8-229">找到一的组凭据用来连接到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="81ca8-229">Locate the set of credentials that is used to connect to Skype for Business Online.</span></span> 
    
3. <span data-ttu-id="81ca8-230">展开的一组凭据，，然后单击**删除存储库中**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-230">Expand the set of credentials, and then click **Remove from Vault**.</span></span> 
    
4. <span data-ttu-id="81ca8-231">重新登录并重新输入用户凭据。</span><span class="sxs-lookup"><span data-stu-id="81ca8-231">Sign in again and reenter the user's credentials.</span></span>
    
<span data-ttu-id="81ca8-232">最后，如果用户仍然不能登录后您已经更新其凭据，请尝试删除 RSA 文件夹在用户的计算机上，因为它可能会阻止用户身份验证过程的完成：</span><span class="sxs-lookup"><span data-stu-id="81ca8-232">Finally, if the user still cannot sign in after you've updated their credentials, try deleting the RSA folder on the user's computer, because it could be blocking completion of the user authentication process:</span></span>
  
1. <span data-ttu-id="81ca8-233">登录到用户的计算机使用的是管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="81ca8-233">Sign in to the user's computer using an administrator account.</span></span>
    
2. <span data-ttu-id="81ca8-234">如果有必要，请打开**显示隐藏的文件**文件夹视图选项。</span><span class="sxs-lookup"><span data-stu-id="81ca8-234">If necessary, turn on the folder view option **Show hidden files**.</span></span> 
    
3. <span data-ttu-id="81ca8-235">到地址栏的文件资源管理器中键入以下内容： **c:\\文档和设置\\用户名\\应用程序数据\\Microsoft\\加密\\RSA**，其中***用户名***是您的 Windows 登录名。</span><span class="sxs-lookup"><span data-stu-id="81ca8-235">Type the following into the address bar of File Explorer: **C:\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**, where ***UserName*** is your Windows sign-in name.</span></span>
    
4. <span data-ttu-id="81ca8-236">删除名称开头的任何文件夹**S-1-5-21-**跟的一串数字。</span><span class="sxs-lookup"><span data-stu-id="81ca8-236">Delete any folder that begins with the name **S-1-5-21-** followed by a string of numbers.</span></span>
    
### <a name="modify-trustmodeldata-registry-keys"></a><span data-ttu-id="81ca8-237">修改 TrustModelData 注册表项</span><span class="sxs-lookup"><span data-stu-id="81ca8-237">Modify TrustModelData registry keys</span></span>
<span data-ttu-id="81ca8-238"><a name="modify-trustmodeldata-registry"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-238"></span></span>

<span data-ttu-id="81ca8-239">当第一次登录的用户时，他们可能会收到一个对话框，其中包含类似下面的内容：**不能验证服务器是否信任您的登录地址。是否仍要连接？**</span><span class="sxs-lookup"><span data-stu-id="81ca8-239">When a user signs in for the first time, they may receive a dialog box that contains something like the following: **Cannot verify that the server is trusted for your sign-in address. Connect anyway?**</span></span> <span data-ttu-id="81ca8-240">这是一种安全功能，而不是错误。</span><span class="sxs-lookup"><span data-stu-id="81ca8-240">This is a security feature, and not an error.</span></span> <span data-ttu-id="81ca8-241">但是，可以防止对话框中显示通过使用组策略对象 (GPO) 前他们第一次登录与您的域名更新用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="81ca8-241">However, you can prevent the dialog box from appearing by using a Group Policy Object (GPO) to update users' machines with your domain name before they sign in for the first time.</span></span> <span data-ttu-id="81ca8-242">若要完成此任务，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81ca8-242">To accomplish this, do the following:</span></span>
  
- <span data-ttu-id="81ca8-243">创建和部署 GPO 附加您的 Skype 的业务域的名称 — — 例如，domainName.contoso.com—to 置此变量的当前值\\软件\\策略\\Microsoft\\Communicator\\TrustModelData。</span><span class="sxs-lookup"><span data-stu-id="81ca8-243">Create and deploy a GPO that appends your Skype for Business domain name—for example, domainName.contoso.com—to the current value of HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="81ca8-244">必须*追加*的现有值与您的域名，不是简单地将其替换。</span><span class="sxs-lookup"><span data-stu-id="81ca8-244">You must *append*  your domain name to the existing value, not simply replace it.</span></span>
  
<span data-ttu-id="81ca8-245">有关详细信息，请参阅 Microsoft 知识库文章 2531068， [Skype 业务 (Lync) 无法验证服务器信任您的登录地址](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)。</span><span class="sxs-lookup"><span data-stu-id="81ca8-245">For details, see the Microsoft Knowledge Base article 2531068, [Skype for Business (Lync) cannot verify that the server is trusted for your sign-in address](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).</span></span>
  
### <a name="update-user-settings-in-active-directory"></a><span data-ttu-id="81ca8-246">更新 Active Directory 中的用户设置</span><span class="sxs-lookup"><span data-stu-id="81ca8-246">Update user settings in Active Directory</span></span>
<span data-ttu-id="81ca8-247"><a name="update-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-247"></span></span>

<span data-ttu-id="81ca8-248">如果您的组织具有以前安装的 Microsoft Office 通信服务器或 Microsoft Lync Server 2010 中，您可能不具有您的用户从服务器上删除在停止使用它之前。</span><span class="sxs-lookup"><span data-stu-id="81ca8-248">If your organization had a previous installation of Microsoft Office Communications Server or Microsoft Lync Server 2010, you may not have deleted your users from the server before decommissioning it.</span></span> <span data-ttu-id="81ca8-249">因此， **msRTCSIP UserEnabled**属性仍设置为**FALSE**在 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="81ca8-249">As a result, the **msRTCSIP-UserEnabled** attribute is still set to **FALSE** in Active Directory Domain Services.</span></span>
  
<span data-ttu-id="81ca8-250">若要解决此问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="81ca8-250">To fix this issue, follow these steps:</span></span>
  
1. <span data-ttu-id="81ca8-251">更新所有受影响的用户的**msRTCSIP UserEnabled**属性设**为 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="81ca8-251">Update the **msRTCSIP-UserEnabled** attribute for all affected users to **TRUE**.</span></span>
    
2. <span data-ttu-id="81ca8-252">重新运行 Microsoft Online Services 目录同步工具 （目录同步）。</span><span class="sxs-lookup"><span data-stu-id="81ca8-252">Rerun the Microsoft Online Services Directory Synchronization Tool (DirSync).</span></span> <span data-ttu-id="81ca8-253">有关详细信息，请参阅[使用 Azure 活动目录的 AIntegrate 您的内部目录](https://technet.microsoft.com/en-us/library/hh967642.aspx)。</span><span class="sxs-lookup"><span data-stu-id="81ca8-253">For details, see [AIntegrate your on-premises directories with Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).</span></span> 
    
<span data-ttu-id="81ca8-254">为了解决 Skype 业务联机登录错误，请首先消除登录困难的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="81ca8-254">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty.</span></span> <span data-ttu-id="81ca8-255">如有必要，您可以按照特定的分辨率根据错误类型的步骤。</span><span class="sxs-lookup"><span data-stu-id="81ca8-255">If necessary, you can then follow specific resolution steps based on the type of error.</span></span> <span data-ttu-id="81ca8-256">如果用户仍然不能登录，收集的其他信息，然后再寻求更多帮助。</span><span class="sxs-lookup"><span data-stu-id="81ca8-256">If the user still cannot sign in, collect additional information, and then seek additional help.</span></span> 
## <a name="use-the-microsoft-support-troubleshooting-guide"></a><span data-ttu-id="81ca8-257">使用 Microsoft 支持故障排除指南</span><span class="sxs-lookup"><span data-stu-id="81ca8-257">Use the Microsoft Support troubleshooting guide</span></span>
<span data-ttu-id="81ca8-258"><a name="toc325626447"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-258"></span></span>

<span data-ttu-id="81ca8-259">如果你仍然不能解决用户的登录问题，查看 Microsoft 知识库文章 2541980，[如何解决登录问题在 Skype 的在线业务](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)中的建议。</span><span class="sxs-lookup"><span data-stu-id="81ca8-259">If you're still not able to resolve the user's sign-in problems, review the suggestions in Microsoft Knowledge Base article 2541980, [How to troubleshoot sign-in issues in Skype for Business Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).</span></span>
  
## <a name="collect-more-information-and-seek-additional-help"></a><span data-ttu-id="81ca8-260">收集的详细信息，并寻求额外的帮助</span><span class="sxs-lookup"><span data-stu-id="81ca8-260">Collect more information and seek additional help</span></span>
<span data-ttu-id="81ca8-261"><a name="collect-more-information"> </a></span><span class="sxs-lookup"><span data-stu-id="81ca8-261"></span></span>

<span data-ttu-id="81ca8-262">如果按照上述指南，仍不能解决登录问题，必须收集的其他信息，请联系技术支持。</span><span class="sxs-lookup"><span data-stu-id="81ca8-262">If you've followed the guidance above and still can't resolve your sign-in issues, you must collect additional information and contact technical support.</span></span> <span data-ttu-id="81ca8-263">若要执行此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="81ca8-263">To do this, follow these steps:</span></span> 
  
1. <span data-ttu-id="81ca8-264">从用户的计算机中获取日志文件和 Windows 事件日志的详细信息。</span><span class="sxs-lookup"><span data-stu-id="81ca8-264">Obtain the log files and Windows Event log details from the user's machine.</span></span> <span data-ttu-id="81ca8-265">有关分步说明，请参阅[打开错误日志中 Lync](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)最终用户帮助主题。</span><span class="sxs-lookup"><span data-stu-id="81ca8-265">For step-by-step instructions, see the end-user help topic [Turn on error logs in Lync](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).</span></span>
    
2. <span data-ttu-id="81ca8-266">将日志文件和错误的详细的信息发送到 Microsoft 技术支持部门。</span><span class="sxs-lookup"><span data-stu-id="81ca8-266">Send the log files and detailed information about the error to Microsoft technical support.</span></span>
    
<span data-ttu-id="81ca8-267">您可能需要通过受影响的用户的计算机上安装的 Microsoft Online Services 诊断和日志记录 (MOSDAL) 支持 Toolkit 提供更多的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="81ca8-267">You may be asked to supply additional diagnostic information by installing the Microsoft Online Services Diagnostic and Logging (MOSDAL) Support Toolkit on the affected user's machine.</span></span> <span data-ttu-id="81ca8-268">有关详细信息，请参阅[使用 MOSDAL 支持 Toolkit](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)。</span><span class="sxs-lookup"><span data-stu-id="81ca8-268">For details, see [Using the MOSDAL Support Toolkit](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).</span></span>
  
<span data-ttu-id="81ca8-269">为了解决 Skype 业务联机登录错误，请首先消除登录困难的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="81ca8-269">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty.</span></span> <span data-ttu-id="81ca8-270">如有必要，您可以按照特定的分辨率根据错误类型的步骤。</span><span class="sxs-lookup"><span data-stu-id="81ca8-270">If necessary, you can then follow specific resolution steps based on the type of error.</span></span> <span data-ttu-id="81ca8-271">如果用户仍然不能登录，收集的其他信息，然后再寻求更多帮助。</span><span class="sxs-lookup"><span data-stu-id="81ca8-271">If the user still cannot sign in, collect additional information, and then seek additional help.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="81ca8-272">相关主题</span><span class="sxs-lookup"><span data-stu-id="81ca8-272">Related topics</span></span>
[<span data-ttu-id="81ca8-273">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="81ca8-273">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="81ca8-274">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="81ca8-274">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
