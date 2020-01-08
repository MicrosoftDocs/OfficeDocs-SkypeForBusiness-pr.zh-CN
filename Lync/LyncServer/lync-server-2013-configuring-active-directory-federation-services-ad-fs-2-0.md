---
title: Lync Server 2013：配置 Active Directory 联合身份验证服务（AD FS 2.0）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a88fb9db7109bdd2a2938f8f9624b4fd0f369fd9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="b9b69-102">为 Lync Server 2013 配置 Active Directory 联合身份验证服务（AD FS 2.0）</span><span class="sxs-lookup"><span data-stu-id="b9b69-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9b69-103">_**主题上次修改时间：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="b9b69-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="b9b69-104">下面一节介绍如何配置 Active Directory 联合身份验证服务 (AD FS 2.0) 来支持多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="b9b69-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="b9b69-105">有关如何安装 AD FS 2.0 的信息，请参阅广告 FS 2.0 分步介绍和操作指南[http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)。</span><span class="sxs-lookup"><span data-stu-id="b9b69-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b9b69-106">安装 AD FS 2.0 时，请勿使用 Windows Server Manager 添加联合身份验证服务角色。</span><span class="sxs-lookup"><span data-stu-id="b9b69-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="b9b69-107">请改为在<A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>RTW 下载并安装 Active Directory 联合身份验证服务2.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="b9b69-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="b9b69-108">**针对双重身份验证配置 AD FS**</span><span class="sxs-lookup"><span data-stu-id="b9b69-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="b9b69-109">使用域管理员帐户登录到 AD FS 2.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="b9b69-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="b9b69-110">启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b9b69-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="b9b69-111">从 Windows PowerShell 命令行，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b9b69-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="b9b69-112">使用 Lync Server 2013 的累积更新建立与每个 Lync Server 2013 的合作关系：7月 2013 Director、Enterprise Pool 和标准版服务器，通过运行以下命令来启用被动身份验证，并替换特定于你的部署的服务器名称：</span><span class="sxs-lookup"><span data-stu-id="b9b69-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="b9b69-113">从“管理工具”菜单中，启动 AD FS 2.0 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b9b69-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="b9b69-114">展开 "**信任关系** \> "**信赖方信任**。</span><span class="sxs-lookup"><span data-stu-id="b9b69-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="b9b69-115">验证是否已为 Lync Server 2013 创建了新信任，其中包含 Lync Server 2013 的累积更新：7月2013企业版池或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="b9b69-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="b9b69-116">使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发授权规则：</span><span class="sxs-lookup"><span data-stu-id="b9b69-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="b9b69-117">使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发转换规则：</span><span class="sxs-lookup"><span data-stu-id="b9b69-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="b9b69-118">从 AD FS 2.0 管理控制台中，右键单击您的依赖方信任并选择“编辑声明规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9b69-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="b9b69-119">选择“颁发授权规则”\*\*\*\* 选项卡，并验证是否已成功创建新的授权规则。</span><span class="sxs-lookup"><span data-stu-id="b9b69-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="b9b69-120">选择“颁发转换规则”\*\*\*\* 选项卡，并验证是否已成功创建新的转换规则。</span><span class="sxs-lookup"><span data-stu-id="b9b69-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

