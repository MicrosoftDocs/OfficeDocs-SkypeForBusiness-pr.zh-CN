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
ms.openlocfilehash: c7fe9587e85ad300a212e4a8199fa4a8a48d1877
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="ffd69-102">配置 AD FS 2.0 以支持 Lync Server 2013 中的客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="ffd69-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffd69-103">_**主题上次修改时间：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="ffd69-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="ffd69-104">有两种可能的身份验证类型可配置为允许 AD FS 2.0 支持使用智能卡进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="ffd69-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="ffd69-105">基于表单的身份验证 (FBA)</span><span class="sxs-lookup"><span data-stu-id="ffd69-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="ffd69-106">传输层安全性客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="ffd69-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="ffd69-107">使用基于表单的身份验证，您可以开发一个网页以允许用户使用其用户名/密码或使用其智能卡和 PIN 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ffd69-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="ffd69-108">本主题着重介绍如何实施传输层安全性客户端身份验证与 AD FS 2.0。</span><span class="sxs-lookup"><span data-stu-id="ffd69-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="ffd69-109">有关 AD FS 2.0 身份验证类型的详细信息，请参阅广告 FS 2.0：如何更改本地身份验证类型[http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)。</span><span class="sxs-lookup"><span data-stu-id="ffd69-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="ffd69-110">**配置 AD FS 2.0 以支持客户端身份验证**</span><span class="sxs-lookup"><span data-stu-id="ffd69-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="ffd69-111">使用域管理员帐户登录到 AD FS 2.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="ffd69-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="ffd69-112">启动 Windows 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="ffd69-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="ffd69-113">浏览到 C：\\inetpub\\adfs\\ls</span><span class="sxs-lookup"><span data-stu-id="ffd69-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="ffd69-114">创建现有 web.config 文件的备份副本。</span><span class="sxs-lookup"><span data-stu-id="ffd69-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="ffd69-115">使用记事本打开现有 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ffd69-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="ffd69-116">从菜单栏中，选择“编辑”\*\*\*\*，然后选择“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ffd69-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="ffd69-117">搜索\*\* \<localAuthenticationTypes\>\*\*。</span><span class="sxs-lookup"><span data-stu-id="ffd69-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="ffd69-118">请注意，列出了四种身份验证类型，每行一个。</span><span class="sxs-lookup"><span data-stu-id="ffd69-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="ffd69-119">将包含 TLSClient 身份验证类型的行移动到列表顶部。</span><span class="sxs-lookup"><span data-stu-id="ffd69-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="ffd69-120">保存并关闭 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ffd69-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="ffd69-121">使用提升的特权启动命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ffd69-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="ffd69-122">通过运行以下命令来重新启动 IIS：</span><span class="sxs-lookup"><span data-stu-id="ffd69-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

