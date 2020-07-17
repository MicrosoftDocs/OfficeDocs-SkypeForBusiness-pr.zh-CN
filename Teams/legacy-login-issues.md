---
title: 在团队中接收消息和旧式系统上的通话时出现问题
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 解决在旧版系统上接收消息和呼叫相关的问题
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af7845b5fd6d50d63be6cd21749cbfedc7669fcf
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085148"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="a68e9-103">在旧式系统上接收消息和通话时出现问题</span><span class="sxs-lookup"><span data-stu-id="a68e9-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="a68e9-104">如果用户使用较早版本的团队或已使用其他应用程序登录，则用户可能会遇到问题，即接收邮件或呼叫。</span><span class="sxs-lookup"><span data-stu-id="a68e9-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="a68e9-105">旧版 ADU 设置</span><span class="sxs-lookup"><span data-stu-id="a68e9-105">Legacy ADU setups</span></span>

 <span data-ttu-id="a68e9-106">如果用户登录到了加入域的计算机，并且你**不希望他们的用户名预填充在 Teams 登录屏幕上**，则管理员可以设置以下 Windows 注册表来关闭用户名预填充 (UPN)：</span><span class="sxs-lookup"><span data-stu-id="a68e9-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="a68e9-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="a68e9-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="a68e9-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="a68e9-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="a68e9-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="a68e9-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="a68e9-110">默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="a68e9-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="a68e9-111">有关详细信息，请参阅[使用新式身份验证登录 Microsoft 团队](sign-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a68e9-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="a68e9-112">Skype 令牌吊销</span><span class="sxs-lookup"><span data-stu-id="a68e9-112">Skype token revocation</span></span>

<span data-ttu-id="a68e9-113">更改/重置密码时，旧客户端将不会收到最长一小时的消息和呼叫。</span><span class="sxs-lookup"><span data-stu-id="a68e9-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="a68e9-114">若要解决此问题，请重新启动应用或移动到较新的客户端。</span><span class="sxs-lookup"><span data-stu-id="a68e9-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a68e9-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="a68e9-115">Related topics</span></span>

[<span data-ttu-id="a68e9-116">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="a68e9-116">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)