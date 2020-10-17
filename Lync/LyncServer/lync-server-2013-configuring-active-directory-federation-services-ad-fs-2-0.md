---
title: 'Lync Server 2013：配置 Active Directory 联合身份验证服务 (AD FS 2.0) '
description: Lync Server 2013：将 Active Directory 联合身份验证服务配置 (AD FS 2.0) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc21500273d8576f54f6110783e61764ec9723a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567838"
---
# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="49dd0-103">为 Lync Server 2013 配置 Active Directory 联合身份验证服务 (AD FS 2.0) </span><span class="sxs-lookup"><span data-stu-id="49dd0-103">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49dd0-104">_**上次修改的主题：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="49dd0-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="49dd0-105">下一节介绍如何配置 Active Directory 联合身份验证服务 (AD FS 2.0) 以支持多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="49dd0-105">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="49dd0-106">有关如何安装 AD FS 2.0 的信息，请参阅 AD FS 2.0 分步和操作方法指南 [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374) 。</span><span class="sxs-lookup"><span data-stu-id="49dd0-106">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="49dd0-107">安装 AD FS 2.0 时，请勿使用 Windows Server 管理器添加 Active Directory 联合身份验证服务角色。</span><span class="sxs-lookup"><span data-stu-id="49dd0-107">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="49dd0-108">请改为在上下载并安装 Active Directory 联合身份验证服务 2.0 RTW 包 <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A> 。</span><span class="sxs-lookup"><span data-stu-id="49dd0-108">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="49dd0-109">**将 AD FS 配置为进行双重身份验证**</span><span class="sxs-lookup"><span data-stu-id="49dd0-109">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="49dd0-110">使用域管理员帐户登录到 AD FS 2.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="49dd0-110">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="49dd0-111">启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="49dd0-111">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="49dd0-112">从 Windows PowerShell 命令行中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="49dd0-112">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="49dd0-113">使用 Lync Server 2013 的累积更新建立与每个 Lync Server 2013 的合作关系：7月 2013 Director、Enterprise Pool 和 Standard Edition Server，可通过运行以下命令替换特定于您的部署的服务器名称来启用被动身份验证：</span><span class="sxs-lookup"><span data-stu-id="49dd0-113">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="49dd0-114">从 "管理工具" 菜单中，启动 AD FS 2.0 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="49dd0-114">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="49dd0-115">展开 " **信任关系**" \> **信赖方信任**。</span><span class="sxs-lookup"><span data-stu-id="49dd0-115">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="49dd0-116">验证是否已为你的 Lync Server 2013 创建了新的信任，并具有 Lync Server 2013 的累积更新：7月 2013 Enterprise Pool 或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="49dd0-116">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="49dd0-117">通过运行以下命令为您使用 Windows PowerShell 的信赖方信任创建并分配发布授权规则：</span><span class="sxs-lookup"><span data-stu-id="49dd0-117">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="49dd0-118">通过运行以下命令为您使用 Windows PowerShell 的信赖方信任创建并分配一个颁发转换规则：</span><span class="sxs-lookup"><span data-stu-id="49dd0-118">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="49dd0-119">从 AD FS 2.0 管理控制台中，右键单击您的信赖方信任，然后选择 " **编辑声明规则**"。</span><span class="sxs-lookup"><span data-stu-id="49dd0-119">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="49dd0-120">选择 " **颁发授权规则** " 选项卡，并验证是否已成功创建新的授权规则。</span><span class="sxs-lookup"><span data-stu-id="49dd0-120">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="49dd0-121">选择 " **颁发转换规则** " 选项卡，并验证是否已成功创建新的转换规则。</span><span class="sxs-lookup"><span data-stu-id="49dd0-121">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

