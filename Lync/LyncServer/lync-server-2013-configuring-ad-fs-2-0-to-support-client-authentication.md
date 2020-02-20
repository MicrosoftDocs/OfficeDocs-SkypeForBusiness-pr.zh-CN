---
title: Lync Server 2013：配置 AD FS 2.0 以支持客户端身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8729ca803f3e3897aa9383f28a486229bf5ce33f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="c3de4-102">在 Lync Server 2013 中配置 AD FS 2.0 以支持客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="c3de4-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3de4-103">_**上次修改的主题：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="c3de4-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="c3de4-104">有两种可能的身份验证类型可配置为允许 AD FS 2.0 支持使用智能卡的身份验证：</span><span class="sxs-lookup"><span data-stu-id="c3de4-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="c3de4-105">基于表单的身份验证（FBA）</span><span class="sxs-lookup"><span data-stu-id="c3de4-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="c3de4-106">传输层安全性客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="c3de4-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="c3de4-107">使用基于表单的身份验证，您可以开发允许用户通过使用其用户名/密码或使用智能卡和 PIN 进行身份验证的网页。</span><span class="sxs-lookup"><span data-stu-id="c3de4-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="c3de4-108">本主题重点介绍如何使用 AD FS 2.0 实施传输层安全性客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="c3de4-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="c3de4-109">有关 AD FS 2.0 身份验证类型的详细信息，请参阅 AD FS 2.0：如何更改本地身份验证类型[https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384)。</span><span class="sxs-lookup"><span data-stu-id="c3de4-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="c3de4-110">**配置 AD FS 2.0 以支持客户端身份验证**</span><span class="sxs-lookup"><span data-stu-id="c3de4-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="c3de4-111">使用域管理员帐户登录到 AD FS 2.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="c3de4-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="c3de4-112">启动 Windows 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="c3de4-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="c3de4-113">浏览到 C：\\inetpub\\adfs\\ls</span><span class="sxs-lookup"><span data-stu-id="c3de4-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="c3de4-114">创建现有 web.config 文件的备份副本。</span><span class="sxs-lookup"><span data-stu-id="c3de4-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="c3de4-115">使用记事本打开现有的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="c3de4-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="c3de4-116">从菜单栏中，选择 "**编辑**"，然后选择 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="c3de4-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="c3de4-117">搜索\*\* \<localAuthenticationTypes\>\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3de4-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="c3de4-118">请注意，每行列出了四种身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c3de4-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="c3de4-119">将包含 TLSClient 身份验证类型的行移到 "" 部分的列表顶部。</span><span class="sxs-lookup"><span data-stu-id="c3de4-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="c3de4-120">保存并关闭 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="c3de4-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="c3de4-121">使用提升的权限启动命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c3de4-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="c3de4-122">通过运行以下命令来重新启动 IIS：</span><span class="sxs-lookup"><span data-stu-id="c3de4-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

