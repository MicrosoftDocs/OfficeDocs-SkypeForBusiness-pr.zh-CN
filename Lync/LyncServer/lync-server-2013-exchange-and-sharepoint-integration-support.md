---
title: Lync Server 2013： Exchange 和 SharePoint 集成支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 566af847bb177173f91634b9b46cceae1d9c88ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="2153e-102">Lync Server 2013 中的 Exchange 和 SharePoint 集成支持</span><span class="sxs-lookup"><span data-stu-id="2153e-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2153e-103">_**上次修改的主题：** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="2153e-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="2153e-104">如果集成这些产品，lync Server 2013 和 Lync 2013 可以与其他应用程序和服务器产品（包括 Office 2013、Exchange Server 2013、Exchange Server 2016 和 SharePoint）进行安全和无缝通信。</span><span class="sxs-lookup"><span data-stu-id="2153e-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="2153e-105">集成 Lync Server 2013 和 Office 可为用户提供对即时消息（IM）的上下文中访问权限，并增强了 Lync 的状态、电话服务和会议功能。</span><span class="sxs-lookup"><span data-stu-id="2153e-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="2153e-106">Office 用户可以从 Outlook 2013 消息和协作客户端以及其他 Office 程序或 SharePoint 页面中访问 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="2153e-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="2153e-107">用户还可以在 "Outlook 对话历史记录" 文件夹中查看 Lync 对话的记录。</span><span class="sxs-lookup"><span data-stu-id="2153e-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="2153e-108">当与 Exchange 2013、Exchange 2016 或 Exchange Online 集成时，Lync Server 2013 还支持以下内容：</span><span class="sxs-lookup"><span data-stu-id="2153e-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="2153e-109">统一的联系人存储库，使用户能够在 Exchange 或 Exchange Online 中存储所有联系人信息，以便信息在 Lync 2013、Exchange、Outlook 和 Outlook Web App 中全局可用。</span><span class="sxs-lookup"><span data-stu-id="2153e-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="2153e-110">会话历史记录和 Web 会议历史记录，存储在 Exchange 用户文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2153e-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="2153e-111">Lync 中存档的内容（如 IM 和会议内容）可以存储在 Exchange 存储中。</span><span class="sxs-lookup"><span data-stu-id="2153e-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2153e-112">Lync Server 2013 支持与 Microsoft Exchange Server 和 SharePoint Server 的早期版本集成，但并不是所有这些早期版本都支持的功能，例如，将存档存储与 Microsoft Exchange 集成。</span><span class="sxs-lookup"><span data-stu-id="2153e-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="2153e-113">如果要将用户迁移到 Exchange 2013 或 Exchange 2016，可以在完成迁移的同时，临时使用 Exchange 存储和 Lync Server 存储。</span><span class="sxs-lookup"><span data-stu-id="2153e-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="2153e-114">不支持永久使用 Exchange 和 Lync Server 存储。</span><span class="sxs-lookup"><span data-stu-id="2153e-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="2153e-115">将 Lync Server 2013 与 Exchange Server 和 SharePoint Server 集成需要在运行 Lync Server 2013、Exchange Server 和 SharePoint Server 的服务器之间进行服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="2153e-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="2153e-116">Lync Server 2013 支持用于服务器到服务器身份验证和授权的 OAuth （开放式授权）协议。</span><span class="sxs-lookup"><span data-stu-id="2153e-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="2153e-117">对于在两台 Microsoft 服务器之间进行的本地服务器到服务器身份验证，无需使用第三方令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="2153e-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="2153e-118">Lync Server 2013、Exchange Server 和 SharePoint Server 具有可用于相互进行身份验证的内置令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="2153e-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="2153e-119">例如，Lync Server 2013 本身可以颁发和签名安全令牌，并在与 Exchange 通信时使用该令牌。</span><span class="sxs-lookup"><span data-stu-id="2153e-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="2153e-120">在此情况下，无需使用第三方令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="2153e-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="2153e-121">Lync Server 2013 支持两种服务器到服务器身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="2153e-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="2153e-122">其中包括在以下各项之间配置服务器到服务器身份验证：</span><span class="sxs-lookup"><span data-stu-id="2153e-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="2153e-123">安装了 Lync Server 2013 的本地安装以及 Exchange Server 2013、Exchange Server 2016 和/或 SharePoint Server 的本地安装。</span><span class="sxs-lookup"><span data-stu-id="2153e-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="2153e-124">一对 Office 组件（例如，在 Microsoft Exchange 365 和 Microsoft Lync Server 365 之间，或 Microsoft Lync Server 365 与 Microsoft SharePoint 365 之间）。</span><span class="sxs-lookup"><span data-stu-id="2153e-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2153e-125">在此 Lync Server 2013 版本中不支持在本地服务器和 Office 365 组件之间进行服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="2153e-125">Server-to-server authentication between an on-premises server and an Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="2153e-126">此外，这意味着您不能在本地安装 Lync Server 2013 和 Microsoft Exchange 365 之间设置服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="2153e-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="2153e-127">有关服务器到服务器身份验证的详细信息，请参阅部署文档或操作文档中的在[Lync server 2013 中管理服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="2153e-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

