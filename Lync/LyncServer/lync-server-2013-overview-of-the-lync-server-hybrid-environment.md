---
title: Lync Server 2013： Lync Server 混合环境概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 480e4a097a3faa8dc70d05ff72027fd6e65e5a76
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="b0ba5-102">Lync Server 2013 混合环境概述</span><span class="sxs-lookup"><span data-stu-id="b0ba5-102">Overview of the Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0ba5-103">_**上次修改的主题：** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="b0ba5-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="b0ba5-104">Lync Server 2013 混合环境指的是部署中有一些用户驻留在本地 Lync Server 2013 中，其他用户驻留在 Lync Online 中，但用户共享相同的域，如 user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="b0ba5-105">关于本指南</span><span class="sxs-lookup"><span data-stu-id="b0ba5-105">About this Guide</span></span>

<span data-ttu-id="b0ba5-106">本指南介绍了配置 Lync Server 2013 环境以实现与 Lync Online 的互操作性所需的任务，然后将用户从本地部署迁移到使用 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="b0ba5-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="b0ba5-107">Prerequisites</span></span>

<span data-ttu-id="b0ba5-108">您需要安装以下应用程序和实用程序，才能完成配置混合部署的任务。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="b0ba5-109">这些文件的安装程序位于针对您的部署提供的安装介质上，以及下表提供的链接中。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="b0ba5-110">Active Directory 联合身份验证服务 (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="b0ba5-110">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="b0ba5-111">Microsoft Directory 同步工具9。1</span><span class="sxs-lookup"><span data-stu-id="b0ba5-111">Microsoft Directory Synchronization Tool 9.1</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="b0ba5-112">安装 Windows PowerShell 以使用 AD FS 进行单一登录</span><span class="sxs-lookup"><span data-stu-id="b0ba5-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="b0ba5-113">Microsoft Online Services 登录助手（msoidcli-7.0）包含在 Office 365 的桌面安装程序中，可从 Office 365 管理门户链接到的下载页面获取。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Office 365, which can be obtained from the Downloads page linked to from the Office 365 Admin portal.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="b0ba5-114">管理员凭据</span><span class="sxs-lookup"><span data-stu-id="b0ba5-114">Administrator Credentials</span></span>

<span data-ttu-id="b0ba5-115">当系统询问你是否提供管理员凭据时，请使用适用于 Office 365 租户的管理员帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="b0ba5-116">在将 Active Directory 联合身份验证服务（AD FS）2.0、目录同步、单一登录、联合和移动用户配置为 Lync Online 时，也将使用这些凭据。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="b0ba5-117">连接到 Lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0ba5-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="b0ba5-118">管理员现在能够使用 Windows PowerShell 管理 Lync Online 及其 Lync Online 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="b0ba5-119">若要执行此操作，必须首先从 Microsoft 下载中心（https://go.microsoft.com/fwlink/?LinkId=294688)）下载并安装 Lync Online 连接器模块。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="b0ba5-120">有关下载、安装和使用 Lync Online 连接器模块的详细信息，以及有关使用 Windows PowerShell 管理 Lync Online 的详细信息，请参阅[Using Windows powershell to Manage Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b0ba5-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

