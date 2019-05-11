---
title: 规划 Skype for Business 中的新式身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 规划身份验证和授权的 Skype 业务服务器，包括与其他产品集成的主题
ms.openlocfilehash: 1a7f20fe10a757001fb3eb819371b81f24d6901e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907155"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="58ced-103">讨论身份验证和授权的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58ced-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="58ced-104">身份验证和授权是相关的概念，但是 （虽然两者都是必需的） 为您执行不同的工作。</span><span class="sxs-lookup"><span data-stu-id="58ced-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="58ced-105">将简单地说，authenciation （身份验证） 取决于机密仅而有效的用户了解或具有，这可能需要密码、 代码、 指纹、 证书、 为 true，则有关用户声明的组合或结合使用这些操作组合。</span><span class="sxs-lookup"><span data-stu-id="58ced-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="58ced-106">身份验证是一个过程出证明要所说的人。</span><span class="sxs-lookup"><span data-stu-id="58ced-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="58ced-107">使用何种您具有访问权限后经过您的身份验证而言授权 （身份验证）。</span><span class="sxs-lookup"><span data-stu-id="58ced-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="58ced-108">确定什么已被允许您查看、 编辑和否则访问。</span><span class="sxs-lookup"><span data-stu-id="58ced-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="58ced-109">例如，您可以对 SharePoint Online 功能强大的网站集管理员访问，但如果切换到另一个联机工作负荷，如 Skype 业务 online，您可能必须解决用户问题，未更改的配置的权限服务器或服务器。</span><span class="sxs-lookup"><span data-stu-id="58ced-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="58ced-110">在第三个工作负荷，例如 Exchange Online 中，您可能只有平均用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="58ced-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="58ced-111">身份验证检查哪些和多少您对访问服务/worloads、 应用程序、 文件和其他数据。</span><span class="sxs-lookup"><span data-stu-id="58ced-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="58ced-112">我们的示例涉及联机属性像 SharePoint 和 Exchange online，但身份验证和身份验证流程工作内部部署和混合部署中相同的方式。</span><span class="sxs-lookup"><span data-stu-id="58ced-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="58ced-113">最终，工具就像 AAD 连接和 ADFS 成为涉及身份验证和身份验证的文字部分中的同步的本地帐户和密码到云的 AD （这是 Office 365 或 Azure 对于 Azure AD），或 intruding 流中的身份验证，以便的用户不频繁时提示输入凭据，说之间创建单一登录方案，云中的工作负荷切换。</span><span class="sxs-lookup"><span data-stu-id="58ced-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD in the case of either Office 365 or Azure), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="58ced-114">但它们不是本身，负责身份验证或身份验证的机制只一部分。</span><span class="sxs-lookup"><span data-stu-id="58ced-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="58ced-115">如今，许多技术考虑 （身份验证和身份验证） 是一种机制，这些过程，您会听到对身份验证过程许多在其中还包含授权的引用。</span><span class="sxs-lookup"><span data-stu-id="58ced-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="58ced-116">非常重要记住用户访问的第一步是身份验证，证明了您的身份，或者使用用户是谁确定哪些他/她与具有访问权限 （您将看到与 Open Authorization 或 OAuth） 的知识。</span><span class="sxs-lookup"><span data-stu-id="58ced-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="58ced-117">身份验证和授权规划主题</span><span class="sxs-lookup"><span data-stu-id="58ced-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="58ced-118">How to use Modern Authentication (ADAL) with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58ced-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="58ced-119">Skype for Business topologies supported with Modern Authentication</span><span class="sxs-lookup"><span data-stu-id="58ced-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="58ced-120">关闭旧身份验证方法内部和外部到您的网络规划。</span><span class="sxs-lookup"><span data-stu-id="58ced-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

