---
title: 管理员 Skype 业务 Online 登录错误疑难解答
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: '了解常见原因的 Skype 业务 Online 登录错误和工作通过解决这些问题。 '
ms.openlocfilehash: 88ff25ab4603810d41e92e25a62bfecb3c376246
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255784"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a><span data-ttu-id="e6bf1-103">管理员 Skype 业务 Online 登录错误疑难解答</span><span class="sxs-lookup"><span data-stu-id="e6bf1-103">Troubleshooting Skype for Business Online sign-in errors for administrators</span></span>

<span data-ttu-id="e6bf1-104">若要解决的业务 Online 登录错误 Skype，启动通过消除登录难度的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-104">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty.</span></span> <span data-ttu-id="e6bf1-105">如有必要，则可以按照步骤基于类型的错误的特定解决方案。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-105">If necessary, you can then follow specific resolution steps based on the type of error.</span></span> <span data-ttu-id="e6bf1-106">如果用户仍然不能登录，收集的其他信息，然后 seek 获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-106">If the user still cannot sign in, collect additional information, and then seek additional help.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="e6bf1-107">你要做什么？</span><span class="sxs-lookup"><span data-stu-id="e6bf1-107">What do you want to do?</span></span>
<span data-ttu-id="e6bf1-108"><a name="top"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-108"></span></span>

> [<span data-ttu-id="e6bf1-109">检查的 Skype 业务 Online 登录错误的常见原因</span><span class="sxs-lookup"><span data-stu-id="e6bf1-109">Check for common causes of Skype for Business Online sign-in errors</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc323194094)

> [<span data-ttu-id="e6bf1-110">按照相应解决步骤特定错误 （仅适用于企业）</span><span class="sxs-lookup"><span data-stu-id="e6bf1-110">Follow resolution steps for a specific error (Enterprise only)</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc325626440)

> [<span data-ttu-id="e6bf1-111">将 msoidsvc.exe 防火墙条目添加到您的代理服务器</span><span class="sxs-lookup"><span data-stu-id="e6bf1-111">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)

> [<span data-ttu-id="e6bf1-112">更新 DNS 设置</span><span class="sxs-lookup"><span data-stu-id="e6bf1-112">Update DNS settings</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)

> [<span data-ttu-id="e6bf1-113">在您的 ADFS 服务器上安装第三方 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="e6bf1-113">Install a third-party SSL certificate on your ADFS server</span></span>](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)

> [<span data-ttu-id="e6bf1-114">更新安全凭据</span><span class="sxs-lookup"><span data-stu-id="e6bf1-114">Update security credentials</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)

> [<span data-ttu-id="e6bf1-115">修改 TrustModelData 注册表项</span><span class="sxs-lookup"><span data-stu-id="e6bf1-115">Modify TrustModelData registry keys</span></span>](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)

> [<span data-ttu-id="e6bf1-116">更新 Active Directory 中的用户设置</span><span class="sxs-lookup"><span data-stu-id="e6bf1-116">Update user settings in Active Directory</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)

> [<span data-ttu-id="e6bf1-117">使用故障排除指南的 Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="e6bf1-117">Use the Microsoft Support troubleshooting guide</span></span>](troubleshooting-sign-in-errors-for-admins.md#toc325626447)

> [<span data-ttu-id="e6bf1-118">收集的详细信息和 seek 获取其他帮助</span><span class="sxs-lookup"><span data-stu-id="e6bf1-118">Collect more information and seek additional help </span></span>](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a><span data-ttu-id="e6bf1-119">检查的 Skype 业务 Online 登录错误的常见原因</span><span class="sxs-lookup"><span data-stu-id="e6bf1-119">Check for common causes of Skype for Business Online sign-in errors</span></span>
<span data-ttu-id="e6bf1-120"><a name="toc323194094"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-120"></span></span>

<span data-ttu-id="e6bf1-121">大多数登录问题可以追溯到少量的原因，以及其中的许多易于更正。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-121">Most sign-in issues can be traced to a small number of causes, and many of these are easy to correct.</span></span> <span data-ttu-id="e6bf1-122">下表列出了一些常见登录错误的原因和一些您或用户可以采取的步骤来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-122">The table below lists some common causes of sign-in errors and some steps you or the users can take to resolve them.</span></span>

|<span data-ttu-id="e6bf1-123">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-123">**Possible Cause**</span></span>|<span data-ttu-id="e6bf1-124">**解决方案**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-124">**Resolution**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6bf1-125">登录过程中，出现一个对话框，其中包含以下短语：**无法验证服务器是否为您的登录地址受信任。仍然连接？**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-125">During sign-in, a dialog box appears that contains the following phrase: **cannot verify that the server is trusted for your sign-in address. Connect anyway?**</span></span> <br/> |<span data-ttu-id="e6bf1-126">确认对话框中的域名称是您组织中的受信任的服务器 — 例如， **domainName.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-126">Verify that the domain name in the dialog box is a trusted server in your organization—for example, **domainName.contoso.com**.</span></span> <span data-ttu-id="e6bf1-127">让用户选择**始终信任此服务器**复选框，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-127">Ask the user to select the **Always trust this server** check box, and then click **Connect**.</span></span> <br/> <span data-ttu-id="e6bf1-128">企业客户可以阻止此消息显示当用户登录首次通过修改每个用户的计算机上的 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-128">Enterprise customers can prevent this message from appearing when a user signs in for the first time by modifying the Windows registry on each user's computer.</span></span> <span data-ttu-id="e6bf1-129">有关详细信息，请参阅[修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-129">For details, see [Modify TrustModelData registry keys](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).</span></span><br/> |
|<span data-ttu-id="e6bf1-130">键入错误登录地址、 用户名或密码</span><span class="sxs-lookup"><span data-stu-id="e6bf1-130">Mistyped sign-in address, user name, or password</span></span>  <br/> | <span data-ttu-id="e6bf1-131">确认用户的登录名和密码正确。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-131">Confirm that the user's sign-in name and password are correct.</span></span> <br/>  <span data-ttu-id="e6bf1-132">验证用户的登录名格式，如下所示： **bobk@contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-132">Verify that the user's sign-in name is formatted as follows: **bobk@contoso.com**.</span></span> <span data-ttu-id="e6bf1-133">这可能不同于您用于登录到贵组织的网络的格式。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-133">This may be different from the format you use to sign in to your organization's network.</span></span>  <br/>  <span data-ttu-id="e6bf1-134">询问用户尝试再次登录。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-134">Ask the user to try signing in again.</span></span> <br/> |
|<span data-ttu-id="e6bf1-135">忘记的密码</span><span class="sxs-lookup"><span data-stu-id="e6bf1-135">Forgotten password</span></span>  <br/> |<span data-ttu-id="e6bf1-136">重置用户的密码并通知他或她的新的临时密码。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-136">Reset the user's password and notify him or her of the new temporary password.</span></span>  <br/> |
|<span data-ttu-id="e6bf1-137">没有为业务 Online 使用 Skype 授权</span><span class="sxs-lookup"><span data-stu-id="e6bf1-137">Not licensed to use Skype for Business Online</span></span>  <br/> |<span data-ttu-id="e6bf1-138">确认用户注册为 Skype 业务联机用户。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-138">Confirm that the user is registered as a Skype for Business Online user.</span></span> <span data-ttu-id="e6bf1-139">如果没有，注册用户，并询问他或她再次登录。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-139">If not, register the user, and then ask him or her to sign in again.</span></span>  <br/> |
|<span data-ttu-id="e6bf1-140">Skype 业务 online 安装的版本不正确</span><span class="sxs-lookup"><span data-stu-id="e6bf1-140">Wrong version of Skype for Business Online installed</span></span>  <br/> |<span data-ttu-id="e6bf1-141">此问题是通常与包含以下错误消息：**身份验证服务可能与此版本的程序不兼容**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-141">This issue is usually associated with an error message that contains the following phrase: **the authentication service may be incompatible with this version of the program**.</span></span>  <br/> <span data-ttu-id="e6bf1-142">要求用户要卸载并重新 Skype 安装从 Office 365 门户业务 online。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-142">Ask the user to uninstall and reinstall Skype for Business Online from the Office 365 Portal.</span></span>  <br/> |
|<span data-ttu-id="e6bf1-143">获取个人证书所需登录问题</span><span class="sxs-lookup"><span data-stu-id="e6bf1-143">Problem acquiring a personal certificate that is required to sign in</span></span>  <br/> |<span data-ttu-id="e6bf1-144">如果最近已更改用户的登录地址，它们可能需要删除缓存登录数据。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-144">If the user's sign-in address has recently changed, they may need to delete cached sign-in data.</span></span> <span data-ttu-id="e6bf1-145">要求用户注销，请单击的删除我的登录信息链接上的登录屏幕中，然后再试。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-145">Ask users to sign out, click the Delete my sign-in info link on the sign-in screen, and then try again.</span></span>  <br/> |
|<span data-ttu-id="e6bf1-146">设置自定义域名，并不可能通过系统传播完成所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-146">You set up a custom domain name, and the changes may not have finished propagating through the system.</span></span>  <br/> |<span data-ttu-id="e6bf1-147">首先，确保您已修改的域服务 (DNS) 记录，以反映的更改。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-147">First, ensure that you have modified the Domain Name Service (DNS) records to reflect the change.</span></span>  <br/> <span data-ttu-id="e6bf1-148">如果您已指定的所需的 DNS 更改，告知用户尝试登录更高版本。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-148">If you have already made the necessary DNS changes, advise the user to try logging in later.</span></span> <span data-ttu-id="e6bf1-149">DNS 更改可能需要 72 小时才能反映在整个系统。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-149">DNS changes can take up to 72 hours to be reflected throughout the system.</span></span>  <br/> |
|<span data-ttu-id="e6bf1-150">与服务器时钟不同步的系统时钟</span><span class="sxs-lookup"><span data-stu-id="e6bf1-150">System clock out of sync with server clock</span></span>  <br/> |<span data-ttu-id="e6bf1-151">确保您的网络域控制器与可靠的外部时间源同步。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-151">Ensure that your network domain controller is synchronizing with a reliable external time source.</span></span> <span data-ttu-id="e6bf1-152">有关详细信息，请参阅 Microsoft 知识库文章 816042，[如何配置在 Windows Server 权威时间服务器](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-152">For details, see the Microsoft Knowledge Base article 816042, [How to configure an authoritative time server in Windows Server](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).</span></span><br/> |

<span data-ttu-id="e6bf1-153">若要解决的业务 Online 登录错误 Skype，启动通过消除登录难度的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-153">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty.</span></span> <span data-ttu-id="e6bf1-154">如有必要，则可以按照步骤基于类型的错误的特定解决方案。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-154">If necessary, you can then follow specific resolution steps based on the type of error.</span></span> <span data-ttu-id="e6bf1-155">如果用户仍然不能登录，收集的其他信息，然后 seek 获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-155">If the user still cannot sign in, collect additional information, and then seek additional help.</span></span>

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a><span data-ttu-id="e6bf1-156">按照相应解决步骤特定错误 （仅适用于企业）</span><span class="sxs-lookup"><span data-stu-id="e6bf1-156">Follow resolution steps for a specific error (Enterprise only)</span></span>
<span data-ttu-id="e6bf1-157"><a name="toc325626440"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-157"></span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e6bf1-158">这些说明是主要适用于 Microsoft Office 365 计划 E 客户。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-158">These instructions are intended primarily for Microsoft Office 365 Plan E customers.</span></span> <span data-ttu-id="e6bf1-159">如果您是 Office 365 计划 P 客户，继续下一节，[收集的详细信息和 seek 获取其他帮助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-159">If you are an Office 365 Plan P customer, continue to the following section,[Collect more information and seek additional help ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).</span></span>

<span data-ttu-id="e6bf1-160">如果您试图在未在上一节中的建议后，用户不能登录，您可以执行基于错误类型的其他故障排除。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-160">If the user cannot sign in after you have tried the suggestions in the previous section, then you can do additional troubleshooting based on the type of error.</span></span> <span data-ttu-id="e6bf1-161">下表列出的最常见的错误消息和可能的原因。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-161">The table below lists the most common error messages and possible causes.</span></span> <span data-ttu-id="e6bf1-162">下表是为了解决每个问题的详细的过程。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-162">Following the table are detailed procedures to address each issue.</span></span>

|<span data-ttu-id="e6bf1-163">**错误消息**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-163">**Error message**</span></span>|<span data-ttu-id="e6bf1-164">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-164">**Possible cause**</span></span>|<span data-ttu-id="e6bf1-165">**解决方案**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-165">**Resolution**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6bf1-166">找不到的登录地址</span><span class="sxs-lookup"><span data-stu-id="e6bf1-166">Sign-in address not found</span></span>  <br/> |<span data-ttu-id="e6bf1-167">通过外部防火墙或代理服务器，将不会从 Microsoft Online Services 登录助手 (msoidsvc.exe) 登录请求。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-167">Sign-in requests from the Microsoft Online Services Sign-On Assistant (msoidsvc.exe) are not going through your external firewall, or proxy server.</span></span>  <br/> |[<span data-ttu-id="e6bf1-168">将 msoidsvc.exe 防火墙条目添加到您的代理服务器</span><span class="sxs-lookup"><span data-stu-id="e6bf1-168">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|<span data-ttu-id="e6bf1-169">服务器是暂时不可用</span><span class="sxs-lookup"><span data-stu-id="e6bf1-169">Server is temporarily unavailable</span></span>  <br/> |<span data-ttu-id="e6bf1-170">如果贵组织拥有的自定义域名，缺失或错误可能是必要的域名系统 (DNS) 设置。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-170">If your organization has a custom domain, the necessary Domain Name System (DNS) settings may be missing or incorrect.</span></span>  <br/> |[<span data-ttu-id="e6bf1-171">更新 DNS 设置</span><span class="sxs-lookup"><span data-stu-id="e6bf1-171">Update DNS settings</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|<span data-ttu-id="e6bf1-172">服务器是暂时不可用</span><span class="sxs-lookup"><span data-stu-id="e6bf1-172">Server is temporarily unavailable</span></span>  <br/> |<span data-ttu-id="e6bf1-173">如果您的组织使用单一登录与 Active Directory 联合身份验证服务 (ADFS)，您可能使用的是自签名的安全套接字层 (SSL) 证书，而不是从第三方证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-173">If your organization is using single sign-on with Active Directory Federation Services (ADFS), you may have used a self-signed Secure Socket Layer (SSL) certificate rather than one from a third-party certification authority.</span></span>  <br/> |[<span data-ttu-id="e6bf1-174">在您的 ADFS 服务器上安装第三方 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="e6bf1-174">Install a third-party SSL certificate on your ADFS server</span></span>](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|<span data-ttu-id="e6bf1-175">获取个人证书所需登录问题</span><span class="sxs-lookup"><span data-stu-id="e6bf1-175">Problem acquiring a personal certificate that is required to sign in</span></span>  <br/> |<span data-ttu-id="e6bf1-176">如果已删除缓存的服务器数据用于登录和继续出现错误，、 用户的安全凭据可能已损坏，或可能阻止身份验证的用户的计算机上的 RSA 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-176">If you've already removed the cached server data used to sign in and the error continues to appear, the user's security credentials may be corrupted, or an RSA folder on the user's computer may be blocking authentication.</span></span>  <br/> |[<span data-ttu-id="e6bf1-177">更新安全凭据</span><span class="sxs-lookup"><span data-stu-id="e6bf1-177">Update security credentials</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|<span data-ttu-id="e6bf1-178">用户首次登录时，将出现一个证书信任对话框。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-178">A certificate trust dialog box appears when a user signs in for the first time.</span></span>  <br/> |<span data-ttu-id="e6bf1-179">如果您的业务服务器 Skype 未列出**TrustModelData**注册表项中，将显示此对话框。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-179">This dialog box appears if your Skype for Business server is not yet listed in the **TrustModelData** registry key.</span></span> <br/> |[<span data-ttu-id="e6bf1-180">修改 TrustModelData 注册表项</span><span class="sxs-lookup"><span data-stu-id="e6bf1-180">Modify TrustModelData registry keys</span></span>](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|<span data-ttu-id="e6bf1-181">用户不是启用 SIP</span><span class="sxs-lookup"><span data-stu-id="e6bf1-181">User is not SIP enabled</span></span>  <br/> |<span data-ttu-id="e6bf1-182">如果您的组织具有以前安装的 Microsoft Office Communications Server 或 Microsoft Lync Server 2010，您可能不删除用户从服务器之前停用它。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-182">If your organization had a previous installation of Microsoft Office Communications Server or Microsoft Lync Server 2010, you may not have deleted your users from the server before decommissioning it.</span></span> <span data-ttu-id="e6bf1-183">因此， **Msrtcsip-userenabled**属性仍然设置为**FALSE** Active Directory 域服务中。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-183">As a result, the **msRTCSIP-UserEnabled** attribute is still set to **FALSE** in Active Directory Domain Services.</span></span> <br/> |[<span data-ttu-id="e6bf1-184">更新 Active Directory 中的用户设置</span><span class="sxs-lookup"><span data-stu-id="e6bf1-184">Update user settings in Active Directory</span></span>](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a><span data-ttu-id="e6bf1-185">将 msoidsvc.exe 防火墙条目添加到您的代理服务器</span><span class="sxs-lookup"><span data-stu-id="e6bf1-185">Add a firewall entry for msoidsvc.exe to your proxy server</span></span>
<span data-ttu-id="e6bf1-186"><a name="add-a-firewall"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-186"></span></span>

<span data-ttu-id="e6bf1-187">此过程是可能的修复程序的以下错误消息：**未找到的登录地址**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-187">This procedure is a possible fix for the following error message: **Sign-in address not found**.</span></span>

> [!NOTE]
> <span data-ttu-id="e6bf1-188">下面的步骤假定您使用 Microsoft Forefront Threat Management Gateway (TMG) 2010年。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-188">The following steps assume you are using Microsoft Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="e6bf1-189">如果您具有不同的 web 网关解决方案，使用下面的步骤 4 中所述的设置。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-189">If you have a different web gateway solution, use the settings described in step 4 below.</span></span>


<span data-ttu-id="e6bf1-190">要为 Msoidsvc.exe 在 Forefront TMG 2010 中创建的应用程序条目，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-190">To create an application entry for Msoidsvc.exe in Forefront TMG 2010, follow these steps:</span></span>

1. <span data-ttu-id="e6bf1-191">在 Forefront 的左窗格中，单击**网络**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-191">In the Forefront left pane, click **Networking**.</span></span>

2. <span data-ttu-id="e6bf1-192">单击**网络**选项卡。在右窗格中的**任务**选项卡上，单击**配置 Forefront TMG 客户端设置**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-192">Click the **Network** tab. Under the **Tasks** tab in the right pane, click **Configure Forefront TMG Client Settings**.</span></span>

3. <span data-ttu-id="e6bf1-193">在**Forefront TMG 客户端设置**对话框中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-193">In the **Forefront TMG Client Settings** dialog box, click **New**.</span></span>

4. <span data-ttu-id="e6bf1-194">在**应用程序项目设置**对话框中，配置以下规则：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-194">In the **Application Entry Setting** dialog box, configure the following rules:</span></span>

|<span data-ttu-id="e6bf1-195">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-195">**Application**</span></span>|<span data-ttu-id="e6bf1-196">**关键字**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-196">**Key**</span></span>|<span data-ttu-id="e6bf1-197">**值**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-197">**Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6bf1-198">**msoidsvc**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-198">**msoidsvc**</span></span> <br/> |<span data-ttu-id="e6bf1-199">禁用</span><span class="sxs-lookup"><span data-stu-id="e6bf1-199">Disable</span></span>  <br/> |<span data-ttu-id="e6bf1-200">0</span><span class="sxs-lookup"><span data-stu-id="e6bf1-200">0</span></span>  <br/> |
|<span data-ttu-id="e6bf1-201">**msoidsvc**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-201">**msoidsvc**</span></span> <br/> |<span data-ttu-id="e6bf1-202">DisableEx</span><span class="sxs-lookup"><span data-stu-id="e6bf1-202">DisableEx</span></span>  <br/> |<span data-ttu-id="e6bf1-203">0</span><span class="sxs-lookup"><span data-stu-id="e6bf1-203">0</span></span>  <br/> |

<span data-ttu-id="e6bf1-204">有关详细信息，请参阅 Microsoft 知识库文章 2409256，[因为本地防火墙阻止连接，无法连接到业务 online Skype](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-204">For details, see the Microsoft Knowledge Base article 2409256, [You cannot connect to Skype for Business Online because an on-premises firewall blocks the connection](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).</span></span>

### <a name="update-dns-settings"></a><span data-ttu-id="e6bf1-205">更新 DNS 设置</span><span class="sxs-lookup"><span data-stu-id="e6bf1-205">Update DNS settings</span></span>
<span data-ttu-id="e6bf1-206"><a name="update-dns-service"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-206"></span></span>

<span data-ttu-id="e6bf1-207">如果您的组织具有自定义域，此过程是以下错误消息可能修复：**服务器是暂时不可用**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-207">If your organization has a custom domain, this procedure is a possible fix for the following error message: **Server is temporarily unavailable**.</span></span>

- <span data-ttu-id="e6bf1-208">有关如何将下面的 CNAME 记录添加到您的域的信息，请联系您域名注册机构：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-208">Contact your domain name registrar for information on how to add the following CNAME record to your domain:</span></span>

  - <span data-ttu-id="e6bf1-209">**DNS 记录类型**： CNAME</span><span class="sxs-lookup"><span data-stu-id="e6bf1-209">**DNS record type**: CNAME</span></span>

  - <span data-ttu-id="e6bf1-210">**名称**： sip</span><span class="sxs-lookup"><span data-stu-id="e6bf1-210">**Name**: sip</span></span>

  - <span data-ttu-id="e6bf1-211">**值/目的地**： sipdir.online.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e6bf1-211">**Value/Destination**: sipdir.online.microsoft.com</span></span>

<span data-ttu-id="e6bf1-212">有关详细信息，请参阅 Microsoft 知识库文章 2566790， [Office 365 中的业务联机 DNS 配置问题的疑难解答 Skype](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-212">For details, see the Microsoft Knowledge Base article 2566790, [Troubleshooting Skype for Business Online DNS configuration issues in Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).</span></span>

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a><span data-ttu-id="e6bf1-213">在您的 ADFS 服务器上安装第三方 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="e6bf1-213">Install a third-party SSL certificate on your ADFS server</span></span>
<span data-ttu-id="e6bf1-214"><a name="verify-upn-and"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-214"></span></span>

<span data-ttu-id="e6bf1-215">若要在您的活动域联合身份验证服务 (ADFS) 服务器上安装第三方 SSL 证书，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-215">To install a third-party SSL certificate on your Active Domain Federation Services (ADFS) server, follow these steps:</span></span>

1. <span data-ttu-id="e6bf1-216">从如 VeriSign 或 Thawte 第三方证书颁发机构获取 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-216">Obtain an SSL certificate from a third-party certification authority such as VeriSign or Thawte.</span></span>

2. <span data-ttu-id="e6bf1-217">使用 ADFS 管理控制台中，在您的 ADFS 服务器上安装证书。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-217">Install the certificate on your ADFS server by using the ADFS management console.</span></span>

### <a name="update-security-credentials"></a><span data-ttu-id="e6bf1-218">更新安全凭据</span><span class="sxs-lookup"><span data-stu-id="e6bf1-218">Update security credentials</span></span>
<span data-ttu-id="e6bf1-219"><a name="update-security-credentials"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-219"></span></span>

<span data-ttu-id="e6bf1-220">此过程是可能的修复**问题获取个人证书需要登录**的错误消息。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-220">This procedure is a possible fix for the error message **Problem acquiring a personal certificate required to sign in**.</span></span>

<span data-ttu-id="e6bf1-221">若要消除可能的证书或凭据问题，请首先续订 Windows 证书管理器中的用户的证书。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-221">To eliminate possible certificate or credential problems, first renew the user's certificate in Windows Certificate Manager.</span></span> <span data-ttu-id="e6bf1-222">若要执行此操作，请按照以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-222">To do this, follow these steps:</span></span>

1. <span data-ttu-id="e6bf1-223">打开 Windows 证书管理器。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-223">Open Windows Certificate Manager.</span></span> <span data-ttu-id="e6bf1-224">若要执行此操作，单击**开始**，单击**运行**，键入**certmgr.msc**，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-224">To do this, click **Start**, click **Run**, type **certmgr.msc**, and then click **OK**.</span></span>

2. <span data-ttu-id="e6bf1-225">双击**个人**，然后双击**证书**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-225">Double-click **Personal**, and then double-click **Certificates**.</span></span>

3. <span data-ttu-id="e6bf1-226">排序依据的**颁发者**列和 Communications server 颁发的证书，然后外观。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-226">Sort by the **Issued By** column, and then look for a certificate that is issued by Communications Server.</span></span>

4. <span data-ttu-id="e6bf1-227">右键单击该证书，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-227">Right-click the certificate, and then click **Delete**.</span></span>

<span data-ttu-id="e6bf1-228">接下来，如果用户正在运行 Windows 7，删除其存储的凭据 Windows 凭据管理器中。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-228">Next, if the user is running Windows 7, remove their stored credentials in Windows Credential Manager.</span></span> <span data-ttu-id="e6bf1-229">若要执行此操作，请按照以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-229">To do this, follow these steps:</span></span>

1. <span data-ttu-id="e6bf1-230">单击**开始**，单击**控制面板**，，然后单击**凭据管理器**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-230">Click **Start**, click **Control Panel**, and then click **Credential Manager**.</span></span>

2. <span data-ttu-id="e6bf1-231">找到用于连接到 Skype 业务 online 凭据集。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-231">Locate the set of credentials that is used to connect to Skype for Business Online.</span></span>

3. <span data-ttu-id="e6bf1-232">展开的一组凭据，，，然后单击**存储库中删除**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-232">Expand the set of credentials, and then click **Remove from Vault**.</span></span>

4. <span data-ttu-id="e6bf1-233">再次登录，然后重新键入用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-233">Sign in again and reenter the user's credentials.</span></span>

<span data-ttu-id="e6bf1-234">最后，如果用户仍然不能登录已更新其凭据后，请尝试删除用户的计算机上的 RSA 文件夹因为可能会阻止用户身份验证过程完成：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-234">Finally, if the user still cannot sign in after you've updated their credentials, try deleting the RSA folder on the user's computer, because it could be blocking completion of the user authentication process:</span></span>

1. <span data-ttu-id="e6bf1-235">登录到使用管理员帐户的用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-235">Sign in to the user's computer using an administrator account.</span></span>

2. <span data-ttu-id="e6bf1-236">如有必要，打开**显示隐藏的文件**文件夹视图选项。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-236">If necessary, turn on the folder view option **Show hidden files**.</span></span>

3. <span data-ttu-id="e6bf1-237">键入以下内容到在地址栏中的文件资源管理器： **c:\\Documents and Settings\\UserName\\应用程序数据\\Microsoft\\加密\\RSA**，其中***UserName***是您 Windows 登录名。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-237">Type the following into the address bar of File Explorer: **C:\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**, where ***UserName*** is your Windows sign-in name.</span></span>

4. <span data-ttu-id="e6bf1-238">删除名称开头的任何文件夹**S-1-5-21-** 跟包含数字的字符串。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-238">Delete any folder that begins with the name **S-1-5-21-** followed by a string of numbers.</span></span>

### <a name="modify-trustmodeldata-registry-keys"></a><span data-ttu-id="e6bf1-239">修改 TrustModelData 注册表项</span><span class="sxs-lookup"><span data-stu-id="e6bf1-239">Modify TrustModelData registry keys</span></span>
<span data-ttu-id="e6bf1-240"><a name="modify-trustmodeldata-registry"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-240"></span></span>

<span data-ttu-id="e6bf1-241">当用户首次使用登录时，它们可能会收到一个对话框，包含与下面类似：**无法验证服务器是否为您的登录地址受信任。仍然连接？**</span><span class="sxs-lookup"><span data-stu-id="e6bf1-241">When a user signs in for the first time, they may receive a dialog box that contains something like the following: **Cannot verify that the server is trusted for your sign-in address. Connect anyway?**</span></span> <span data-ttu-id="e6bf1-242">这是一项安全功能，而不是错误。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-242">This is a security feature, and not an error.</span></span> <span data-ttu-id="e6bf1-243">但是，可以阻止对话框中显示通过使用组策略对象 (GPO) 之前用户首次登录您的域名与更新用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-243">However, you can prevent the dialog box from appearing by using a Group Policy Object (GPO) to update users' machines with your domain name before they sign in for the first time.</span></span> <span data-ttu-id="e6bf1-244">若要实现此目的，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-244">To accomplish this, do the following:</span></span>

- <span data-ttu-id="e6bf1-245">创建和部署附加业务域名您 Skype GPO — 例如，domainName.contoso.com—to HKEY_LOCAL_MACHINE 的当前值\\软件\\策略\\Microsoft\\Communicator\\TrustModelData。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-245">Create and deploy a GPO that appends your Skype for Business domain name—for example, domainName.contoso.com—to the current value of HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e6bf1-246">您必须*追加*到现有的值您的域名，不是简单地将其替换。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-246">You must *append*  your domain name to the existing value, not simply replace it.</span></span>

<span data-ttu-id="e6bf1-247">有关详细信息，请参阅 Microsoft 知识库文章 2531068， [Skype for Business (Lync) 无法验证服务器为您的登录地址受信任](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-247">For details, see the Microsoft Knowledge Base article 2531068, [Skype for Business (Lync) cannot verify that the server is trusted for your sign-in address](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).</span></span>

### <a name="update-user-settings-in-active-directory"></a><span data-ttu-id="e6bf1-248">更新 Active Directory 中的用户设置</span><span class="sxs-lookup"><span data-stu-id="e6bf1-248">Update user settings in Active Directory</span></span>
<span data-ttu-id="e6bf1-249"><a name="update-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-249"></span></span>

<span data-ttu-id="e6bf1-250">如果您的组织具有以前安装的 Microsoft Office Communications Server 或 Microsoft Lync Server 2010，您可能不删除用户从服务器之前停用它。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-250">If your organization had a previous installation of Microsoft Office Communications Server or Microsoft Lync Server 2010, you may not have deleted your users from the server before decommissioning it.</span></span> <span data-ttu-id="e6bf1-251">因此， **Msrtcsip-userenabled**属性仍然设置为**FALSE** Active Directory 域服务中。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-251">As a result, the **msRTCSIP-UserEnabled** attribute is still set to **FALSE** in Active Directory Domain Services.</span></span>

<span data-ttu-id="e6bf1-252">若要解决此问题，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-252">To fix this issue, follow these steps:</span></span>

1. <span data-ttu-id="e6bf1-253">更新所有受影响的用户的**Msrtcsip-userenabled**属性为**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-253">Update the **msRTCSIP-UserEnabled** attribute for all affected users to **TRUE**.</span></span>

2. <span data-ttu-id="e6bf1-254">重新运行 Microsoft Online Services 目录同步工具 (DirSync)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-254">Rerun the Microsoft Online Services Directory Synchronization Tool (DirSync).</span></span> <span data-ttu-id="e6bf1-255">有关详细信息，请参阅[Azure Active Directory AIntegrate 本地目录](https://technet.microsoft.com/en-us/library/hh967642.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-255">For details, see [AIntegrate your on-premises directories with Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).</span></span>

<span data-ttu-id="e6bf1-256">若要解决的业务 Online 登录错误 Skype，启动通过消除登录难度的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-256">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty.</span></span> <span data-ttu-id="e6bf1-257">如有必要，则可以按照步骤基于类型的错误的特定解决方案。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-257">If necessary, you can then follow specific resolution steps based on the type of error.</span></span> <span data-ttu-id="e6bf1-258">如果用户仍然不能登录，收集的其他信息，然后 seek 获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-258">If the user still cannot sign in, collect additional information, and then seek additional help.</span></span>
## <a name="use-the-microsoft-support-troubleshooting-guide"></a><span data-ttu-id="e6bf1-259">使用故障排除指南的 Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="e6bf1-259">Use the Microsoft Support troubleshooting guide</span></span>
<span data-ttu-id="e6bf1-260"><a name="toc325626447"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-260"></span></span>

<span data-ttu-id="e6bf1-261">如果仍无法解决用户的登录问题，请查看 Microsoft 知识库文章 2541980，[如何解决登录问题中 Skype 业务 online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)中的建议。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-261">If you're still not able to resolve the user's sign-in problems, review the suggestions in Microsoft Knowledge Base article 2541980, [How to troubleshoot sign-in issues in Skype for Business Online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).</span></span>

## <a name="collect-more-information-and-seek-additional-help"></a><span data-ttu-id="e6bf1-262">收集的详细信息和 seek 获取其他帮助</span><span class="sxs-lookup"><span data-stu-id="e6bf1-262">Collect more information and seek additional help</span></span>
<span data-ttu-id="e6bf1-263"><a name="collect-more-information"> </a></span><span class="sxs-lookup"><span data-stu-id="e6bf1-263"></span></span>

<span data-ttu-id="e6bf1-264">如果您已关注上面的指南并仍无法解决登录问题，您必须收集的其他信息并与技术支持联系。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-264">If you've followed the guidance above and still can't resolve your sign-in issues, you must collect additional information and contact technical support.</span></span> <span data-ttu-id="e6bf1-265">若要执行此操作，请按照以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e6bf1-265">To do this, follow these steps:</span></span>

1. <span data-ttu-id="e6bf1-266">从用户的计算机中获取的日志文件和 Windows 事件日志的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-266">Obtain the log files and Windows Event log details from the user's machine.</span></span> <span data-ttu-id="e6bf1-267">有关分步说明，请参阅[启用 Lync 中的错误日志](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)最终用户帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-267">For step-by-step instructions, see the end-user help topic [Turn on error logs in Lync](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).</span></span>

2. <span data-ttu-id="e6bf1-268">将日志文件和有关错误的详细的信息发送到 Microsoft 技术支持。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-268">Send the log files and detailed information about the error to Microsoft technical support.</span></span>

<span data-ttu-id="e6bf1-269">可能要求您通过受影响的用户的计算机上安装 Microsoft Online Services 诊断和日志记录 (MOSDAL) 支持工具包提供附加诊断信息。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-269">You may be asked to supply additional diagnostic information by installing the Microsoft Online Services Diagnostic and Logging (MOSDAL) Support Toolkit on the affected user's machine.</span></span> <span data-ttu-id="e6bf1-270">有关详细信息，请参阅[使用 MOSDAL 支持工具包](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-270">For details, see [Using the MOSDAL Support Toolkit](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).</span></span>

<span data-ttu-id="e6bf1-271">若要解决的业务 Online 登录错误 Skype，启动通过消除登录难度的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-271">To troubleshoot Skype for Business Online sign-in errors, start by eliminating the most common causes of sign-in difficulty.</span></span> <span data-ttu-id="e6bf1-272">如有必要，则可以按照步骤基于类型的错误的特定解决方案。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-272">If necessary, you can then follow specific resolution steps based on the type of error.</span></span> <span data-ttu-id="e6bf1-273">如果用户仍然不能登录，收集的其他信息，然后 seek 获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="e6bf1-273">If the user still cannot sign in, collect additional information, and then seek additional help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6bf1-274">相关主题</span><span class="sxs-lookup"><span data-stu-id="e6bf1-274">Related topics</span></span>
[<span data-ttu-id="e6bf1-275">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e6bf1-275">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e6bf1-276">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="e6bf1-276">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


