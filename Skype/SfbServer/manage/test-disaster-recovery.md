---
title: Skype for Business Server 中的灾难恢复测试
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 对 Skype for Business Server 池服务器执行系统恢复以测试记录灾难恢复过程
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832812"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="abff7-103">Skype for Business Server 中的灾难恢复测试</span><span class="sxs-lookup"><span data-stu-id="abff7-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="abff7-104">对 Skype for Business Server 池服务器执行系统恢复，以测试记录灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="abff7-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="abff7-105">此测试将模拟一台服务器的完整硬件故障，并帮助保证资源、计划和数据可用于恢复。</span><span class="sxs-lookup"><span data-stu-id="abff7-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="abff7-106">尝试每月轮换测试的焦点，以便组织每次测试不同服务器或其他设备的故障。</span><span class="sxs-lookup"><span data-stu-id="abff7-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="abff7-107">请注意，组织执行灾难恢复测试的计划将有所不同。</span><span class="sxs-lookup"><span data-stu-id="abff7-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="abff7-108">不要忽略或忽略灾难恢复测试，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="abff7-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="abff7-109">将 Skype for Business Server 拓扑、策略和配置设置导出到文件中。</span><span class="sxs-lookup"><span data-stu-id="abff7-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="abff7-110">此外，此文件还可用于在升级、硬件故障或其他导致数据丢失的问题后将此信息还原到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="abff7-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="abff7-111">将 Skype for Business Server 拓扑、策略和配置设置导入中央管理存储或本地计算机，如以下命令所示：</span><span class="sxs-lookup"><span data-stu-id="abff7-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="abff7-112">备份生产数据：</span><span class="sxs-lookup"><span data-stu-id="abff7-112">To back up production data:</span></span>

- <span data-ttu-id="abff7-113">使用标准备份过程备份 RTC 和 LCSLog 数据库SQL Server将数据库转储到文件或磁带转储设备。</span><span class="sxs-lookup"><span data-stu-id="abff7-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="abff7-114">使用第三方备份应用程序将数据备份到文件或磁带。</span><span class="sxs-lookup"><span data-stu-id="abff7-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="abff7-115">使用 Export-CsUserData cmdlet 创建整个 RTC 数据库的 XML 导出。</span><span class="sxs-lookup"><span data-stu-id="abff7-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="abff7-116">使用文件系统备份或第三方备份来备份会议内容和合规性日志。</span><span class="sxs-lookup"><span data-stu-id="abff7-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="abff7-117">使用 Export-CsConfiguration 命令行工具来备份 Skype for Business Server 设置。</span><span class="sxs-lookup"><span data-stu-id="abff7-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="abff7-118">故障转移过程中的第一步包括强制将用户从生产池移动到灾难恢复池。</span><span class="sxs-lookup"><span data-stu-id="abff7-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="abff7-119">这是强制移动，因为生产池将不能接受用户重定位。</span><span class="sxs-lookup"><span data-stu-id="abff7-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="abff7-120">除了 RTC 数据库上的记录更新之外，Skype for Business Server 移动用户过程实际上是对用户帐户对象上的SQL更改。</span><span class="sxs-lookup"><span data-stu-id="abff7-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="abff7-121">可以使用标准 SQL Server SQL Server 还原过程，或者使用第三方备份/还原实用工具从生产环境中从原始备份转储设备还原此数据。</span><span class="sxs-lookup"><span data-stu-id="abff7-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="abff7-122">还原此数据后，用户可以有效地连接到灾难恢复池，并像往常一样运行。</span><span class="sxs-lookup"><span data-stu-id="abff7-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="abff7-123">若要使用户能够连接到灾难恢复池，需要更改 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="abff7-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="abff7-124">使用自动配置和 DNS SRV 记录的客户端将引用生产 Skype for Business 池：</span><span class="sxs-lookup"><span data-stu-id="abff7-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="abff7-125">SRV：_sip._tls。\<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-125">SRV: _sip._tls.\<domain></span></span> <span data-ttu-id="abff7-126">/CNAME：SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-126">/CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="abff7-127">CNAME：SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-127">CNAME: SIP.\<domain></span></span> <span data-ttu-id="abff7-128">/cvc-pool-1.\<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-128">/cvc-pool-1.\<domain></span></span>

<span data-ttu-id="abff7-129">为了便于进行故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="abff7-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="abff7-130">CNAME：SIP。<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-130">CNAME: SIP.<domain></span></span> <span data-ttu-id="abff7-131">/DROCSPool。\<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-131">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="abff7-132">Sip。\<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-132">Sip.\<domain></span></span>
- <span data-ttu-id="abff7-133">AV。\<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-133">AV.\<domain></span></span>
- <span data-ttu-id="abff7-134">webconf。\<domain></span><span class="sxs-lookup"><span data-stu-id="abff7-134">webconf.\<domain></span></span>
