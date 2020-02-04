---
title: Lync Server 2013：为智能卡身份验证配置企业 CA
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44df62031e679c641b4c7dbe6b5c205e1ae899e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="19156-102">在 Lync Server 2013 中配置用于智能卡身份验证的企业 CA</span><span class="sxs-lookup"><span data-stu-id="19156-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19156-103">_**主题上次修改时间：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="19156-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="19156-104">以下部分介绍了如何配置企业根证书颁发机构（CA）以支持智能卡身份验证。</span><span class="sxs-lookup"><span data-stu-id="19156-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="19156-105">有关如何安装企业根 CA 的详细信息，请参阅在以下位置[http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)安装企业根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="19156-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="19156-106">配置企业根证书颁发机构以支持智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="19156-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="19156-107">以下步骤介绍如何配置企业根 CA 以支持智能卡身份验证：</span><span class="sxs-lookup"><span data-stu-id="19156-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="19156-108">使用域管理员帐户登录到企业 CA 计算机。</span><span class="sxs-lookup"><span data-stu-id="19156-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="19156-109">启动系统管理器，并验证是否已安装“证书颁发机构 Web 注册”角色。</span><span class="sxs-lookup"><span data-stu-id="19156-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="19156-110">从“管理工具”\*\*\*\* 菜单中，打开“证书颁发机构”\*\*\*\* 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="19156-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="19156-111">在导航窗格中，展开“证书颁发机构”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19156-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="19156-112">右键单击“证书模板”\*\*\*\*，选择“新建”\*\*\*\*，然后选择“要颁发的证书模板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19156-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="19156-113">选择“注册代理”\*\*\*\*、“智能卡用户”\*\*\*\* 和“智能卡登录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19156-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="19156-114">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="19156-114">Click **OK**.</span></span>

8.  <span data-ttu-id="19156-115">右键单击“证书模板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19156-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="19156-116">选择“管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19156-116">Select **Manage**.</span></span>

10. <span data-ttu-id="19156-117">打开智能卡用户模板的属性。</span><span class="sxs-lookup"><span data-stu-id="19156-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="19156-118">单击“安全”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="19156-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="19156-119">更改权限，如下所示：</span><span class="sxs-lookup"><span data-stu-id="19156-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="19156-120">添加具有读取/注册（允许）权限的各个用户 AD 帐户，或者</span><span class="sxs-lookup"><span data-stu-id="19156-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="19156-121">添加具有读取/注册（允许）权限且包含智能卡用户的安全组，或者</span><span class="sxs-lookup"><span data-stu-id="19156-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="19156-122">添加具有读取/注册（允许）权限的域用户组</span><span class="sxs-lookup"><span data-stu-id="19156-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

