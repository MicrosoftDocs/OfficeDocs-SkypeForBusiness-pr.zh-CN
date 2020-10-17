---
title: 删除授权主机条目
description: 删除授权主机条目。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95aa8df1745ad3108654fcb9b441b5919d42ec40
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570278"
---
# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="67e94-103">删除授权主机条目</span><span class="sxs-lookup"><span data-stu-id="67e94-103">Remove an authorized host entry</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67e94-104">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="67e94-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="67e94-105">本主题介绍如何删除旧版授权主机条目 (在 Lync Server 2013) 中称为 " *受信任的应用程序" 条目* 。</span><span class="sxs-lookup"><span data-stu-id="67e94-105">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="67e94-106">当您将远程呼叫控制迁移到 Lync Server 2013 部署时，您必须删除 Office 通信服务器 2007 R2 部署中任何 SIP/CSTA 网关的现有授权主机条目。</span><span class="sxs-lookup"><span data-stu-id="67e94-106">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="67e94-107">您必须使用 Office 通信服务器 2007 R2 附带的管理工具删除现有的已授权主机项。</span><span class="sxs-lookup"><span data-stu-id="67e94-107">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="67e94-108">从 Office Communications Server 2007 R2 部署中删除授权主机项</span><span class="sxs-lookup"><span data-stu-id="67e94-108">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="67e94-109">打开 Office 通信服务器 2007 R2 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="67e94-109">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="67e94-110">展开树，并右键单击创建授权主机的池。</span><span class="sxs-lookup"><span data-stu-id="67e94-110">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="67e94-111">单击“属性”\*\*\*\*，然后单击“前端属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67e94-111">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="67e94-112">单击“主机授权”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="67e94-112">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="67e94-113">选择一台服务器，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67e94-113">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="67e94-114">在“属性”\*\*\*\* 中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67e94-114">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

