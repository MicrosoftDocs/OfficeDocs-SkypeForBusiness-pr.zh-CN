---
title: 规划 Skype for Business 中的新式身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 适用于 Skype for Business 服务器的身份验证和授权的计划主题，包括与其他产品的集成
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815840"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="64651-103">在 Skype for Business 中讨论身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="64651-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="64651-104">身份验证和授权是相关的概念，但为你执行不同的工作（尽管这两者都是必需的）。</span><span class="sxs-lookup"><span data-stu-id="64651-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="64651-105">放入简单的术语中，authenciation （AuthN）仅依赖于机密用户知道或拥有的有效用户，并且可以是密码、代码、指纹、证书、声明有关用户的情况的组合，或者结合使用这些内容。</span><span class="sxs-lookup"><span data-stu-id="64651-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="64651-106">AuthN 是一种证明你所说的人的过程。</span><span class="sxs-lookup"><span data-stu-id="64651-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="64651-107">授权（AuthZ）在您验证您的身份后，与您有权访问的内容相关。</span><span class="sxs-lookup"><span data-stu-id="64651-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="64651-108">它确定您允许查看、编辑和以其他方式访问的内容。</span><span class="sxs-lookup"><span data-stu-id="64651-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="64651-109">例如，你可能拥有 SharePoint Online 的功能强大的网站集管理员访问权限，但是如果你切换到另一个联机工作负载（如 Skype for Business Online），你可能有权解决用户问题，而不是更改配置服务器或服务器。</span><span class="sxs-lookup"><span data-stu-id="64651-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="64651-110">在第三个工作负荷（如 Exchange Online）中，你可能只有一般用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="64651-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="64651-111">AuthZ 检查你对服务/worloads、应用程序、文件和其他数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="64651-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="64651-112">我们的示例涉及 SharePoint 和 Exchange online 等联机属性，但 AuthN 和 AuthZ 的流程在本地以及在混合场所中均以相同的方式工作。</span><span class="sxs-lookup"><span data-stu-id="64651-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="64651-113">最终，诸如 AAD Connect 和 ADFS 之类的工具通过将本地帐户和密码同步到云的广告（即 Office 365 或 Azure 中的 Azure AD）或在 AuthZ 流中 intruding，在 AuthN 和 AuthZ 情景中参与。用户不会经常收到其凭据的提示，例如，当在云中的工作负载之间切换时，创建单一登录方案。</span><span class="sxs-lookup"><span data-stu-id="64651-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD in the case of either Office 365 or Azure), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="64651-114">但它们本身并不是责任的 AuthN 或 AuthZ，只是这种机制的一部分。</span><span class="sxs-lookup"><span data-stu-id="64651-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="64651-115">如今，许多技术将这些流程（AuthN 和 AuthZ）视为一种机制，并且你将听到许多对身份验证过程的引用，其中还包括授权。</span><span class="sxs-lookup"><span data-stu-id="64651-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="64651-116">请务必记住，用户访问中的第一步是 AuthN，证明你是你所说的人员，并且该 AuthZ 使用用户的知识来确定他或她有权访问的内容（如你将通过开放授权或 OAuth 看到的那样）。</span><span class="sxs-lookup"><span data-stu-id="64651-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="64651-117">身份验证和授权计划主题</span><span class="sxs-lookup"><span data-stu-id="64651-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="64651-118">How to use Modern Authentication (ADAL) with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="64651-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="64651-119">Skype for Business topologies supported with Modern Authentication</span><span class="sxs-lookup"><span data-stu-id="64651-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="64651-120">计划在内部和外部关闭旧版身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="64651-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

