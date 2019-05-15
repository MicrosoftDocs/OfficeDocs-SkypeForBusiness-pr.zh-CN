---
title: 业务服务器中 Skype 测试的灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 为业务服务器池服务器 Skype 测试您的记录的灾难恢复过程中执行系统恢复
ms.openlocfilehash: 55398b95be1cf5cec2cafa3a91a36536df92200e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924813"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="9d8ae-103">业务服务器中 Skype 测试的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="9d8ae-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="9d8ae-104">为业务服务器池服务器 Skype 测试您的记录的灾难恢复过程中执行系统恢复。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="9d8ae-105">此测试将模拟一台服务器的完整的硬件故障，有助于保证可用于恢复资源、 计划和数据。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="9d8ae-106">请尝试每月轮转测试焦点，以便您的组织每次测试不同服务器或其他设备的故障。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="9d8ae-p102">请注意，组织执行灾难恢复测试时所遵循的计划将有所不同。非常重要的是，不得忽略灾难恢复测试。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="9d8ae-109">将您的企业服务器拓扑、 策略和配置设置的 Skype 导出到文件。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="9d8ae-110">在升级、硬件故障或一些其他问题导致数据丢失后，此文件的功能之一是可用于将该信息恢复到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="9d8ae-111">导入您的企业服务器拓扑、 策略和配置设置的 Skype 到中央管理存储或本地计算机示以下命令：</span><span class="sxs-lookup"><span data-stu-id="9d8ae-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="9d8ae-112">若要备份生产数据：</span><span class="sxs-lookup"><span data-stu-id="9d8ae-112">To back up production data:</span></span>

- <span data-ttu-id="9d8ae-113">备份 RTC 和 LCSLog 数据库使用标准的 SQL Server 备份过程能够转储文件或磁带转储设备的数据库。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="9d8ae-114">使用第三方备份应用程序将数据备份到文件或磁带。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="9d8ae-115">使用 Export-CsUserData cmdlet 创建整个 RTC 数据库的 XML 导出。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="9d8ae-116">使用文件系统备份或第三方备份 to back up 会议内容和合规性日志。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="9d8ae-117">使用 Export-csconfiguration 命令行工具备份 Skype 的业务服务器设置。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="9d8ae-118">故障转移过程的第一个步骤包括强制性地将用户从生产池移动到灾难恢复池。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="9d8ae-119">之所以称为强制性移动是因为生产池并不接受用户重新定位。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="9d8ae-120">业务服务器移动用户进程的 Skype 实际上是对除了上的 RTC SQL 数据库的记录更新此用户帐户对象的属性的更改。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="9d8ae-121">可以还原此数据从原始备份转储设备从生产使用标准的 SQL Server 还原进程，或使用第三方 SQL Server 备份/还原实用程序。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="9d8ae-122">在还原此数据后，用户可以有效地连接到灾难恢复池，并像往常一样运行。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="9d8ae-123">若要使用户能够连接到灾难恢复池，还将需要的 DNS 记录的更改。</span><span class="sxs-lookup"><span data-stu-id="9d8ae-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="9d8ae-124">生产 Skype 业务池将使用客户端自动配置和 DNS SRV 记录的引用：</span><span class="sxs-lookup"><span data-stu-id="9d8ae-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="9d8ae-125">SRV: _sip._tls。\<domain> /CNAME: SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="9d8ae-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="9d8ae-126">CNAME: SIP。\<domain> /cvc-pool-1。\<domain></span><span class="sxs-lookup"><span data-stu-id="9d8ae-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="9d8ae-127">为促进故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="9d8ae-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="9d8ae-128">CNAME: SIP。<domain></span><span class="sxs-lookup"><span data-stu-id="9d8ae-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="9d8ae-129">/ DROCSPool。\<domain></span><span class="sxs-lookup"><span data-stu-id="9d8ae-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="9d8ae-130">Sip。\<domain></span><span class="sxs-lookup"><span data-stu-id="9d8ae-130">Sip.\<domain></span></span>
- <span data-ttu-id="9d8ae-131">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="9d8ae-131">AV.\<domain></span></span>
- <span data-ttu-id="9d8ae-132">webconf。\<domain></span><span class="sxs-lookup"><span data-stu-id="9d8ae-132">webconf.\<domain></span></span>
