---
title: 规划 Skype for Business 中的新式验证
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 规划 Skype for Business Server 的身份验证和授权主题，包括与其他产品的集成
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816242"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="bf6b5-103">讨论 Skype for Business 中的身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="bf6b5-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="bf6b5-104">身份验证和授权是相关的概念，但是，虽然这两个概念 (执行不同的) 。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="bf6b5-105">简单地说，身份验证 (AuthN) 仅依赖于有效用户知道或拥有的密码，它可以是密码、代码、指纹、证书、有关用户的真实声明的组合，或结合使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="bf6b5-106">AuthN 是一个过程，可以证明你是谁。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="bf6b5-107">授权 (AuthZ) 在证明你是谁后，你有权访问什么。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="bf6b5-108">它确定允许查看、编辑或以其他方式访问哪些内容。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="bf6b5-109">例如，你可能具有对 SharePoint Online 的强大网站集管理员访问权限，但如果切换到其他联机工作负载（如 Skype for Business Online），你可能有权排查用户问题，而不是更改服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="bf6b5-110">第三个工作负载（如 Exchange Online）可能只具有平均用户访问权。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="bf6b5-111">AuthZ 检查对服务/worloads、应用程序、文件和其他数据具有哪些访问权限以及访问量。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="bf6b5-112">我们的示例涉及 SharePoint 和 Exchange Online 等联机属性，但 AuthN 和 AuthZ 的过程在本地和混合内部部署中同样工作。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="bf6b5-113">最后，AAD Connect 和 ADFS 等工具通过将本地帐户和密码同步到云的 AD (（即 Azure AD) ）或插入 AuthZ 流来涉及 AuthN 和 AuthZ 情景，以便用户不会经常提示输入其凭据，例如，在云中的工作负载之间切换时，创建单个 Sign-On 方案。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="bf6b5-114">但它们本身不是负责的 AuthN 或 AuthZ，只是机制的一部分。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="bf6b5-115">如今，许多技术认为这些 (AuthN 和 AuthZ) 是一种机制，并且你将听到许多对身份验证过程的引用，这些过程也包含授权。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="bf6b5-116">必须记住，用户访问的第一步是 AuthN，证明您就是您说出的用户，并且 AuthZ 使用用户确定有权访问 (的用户的知识，就像使用 Open Authorization 或 OAuth) 一样。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="bf6b5-117">身份验证和授权规划主题</span><span class="sxs-lookup"><span data-stu-id="bf6b5-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="bf6b5-118">如何将新式验证 (ADAL) Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bf6b5-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="bf6b5-119">新式验证支持的 Skype for Business 拓扑</span><span class="sxs-lookup"><span data-stu-id="bf6b5-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="bf6b5-120">计划在网络和外部关闭旧版身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="bf6b5-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

