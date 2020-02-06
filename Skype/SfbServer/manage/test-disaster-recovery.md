---
title: Skype for Business 服务器中的灾难恢复测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 为 Skype for business 服务器池服务器执行系统恢复，以测试已记录的灾难恢复过程
ms.openlocfilehash: f3eba25d59c56f085b9bd6d347fcde910f11a00d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817298"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="62a85-103">Skype for Business 服务器中的灾难恢复测试</span><span class="sxs-lookup"><span data-stu-id="62a85-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="62a85-104">为 Skype for business 服务器池服务器执行系统恢复，以测试已记录的灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="62a85-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="62a85-105">此测试将模拟一台服务器的完整硬件故障，并将帮助确保资源、计划和数据可用于恢复。</span><span class="sxs-lookup"><span data-stu-id="62a85-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="62a85-106">请尝试每月轮转测试焦点，以便您的组织每次测试不同服务器或其他设备的故障。</span><span class="sxs-lookup"><span data-stu-id="62a85-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="62a85-p102">请注意，组织执行灾难恢复测试时所遵循的计划将有所不同。非常重要的是，不得忽略灾难恢复测试。</span><span class="sxs-lookup"><span data-stu-id="62a85-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="62a85-109">将 Skype for Business 服务器拓扑、策略和配置设置导出到文件。</span><span class="sxs-lookup"><span data-stu-id="62a85-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="62a85-110">在升级、硬件故障或一些其他问题导致数据丢失后，此文件的功能之一是可用于将该信息恢复到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="62a85-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="62a85-111">将 Skype for Business 服务器拓扑、策略和配置设置导入中央管理存储或本地计算机，如以下命令所示：</span><span class="sxs-lookup"><span data-stu-id="62a85-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="62a85-112">要备份生产数据，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="62a85-112">To back up production data:</span></span>

- <span data-ttu-id="62a85-113">通过使用标准 SQL Server 备份过程来备份 RTC 和 LCSLog 数据库，以将数据库转储到文件或磁带转储设备。</span><span class="sxs-lookup"><span data-stu-id="62a85-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="62a85-114">使用第三方备份应用程序将数据备份到文件或磁带。</span><span class="sxs-lookup"><span data-stu-id="62a85-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="62a85-115">使用 Export-CsUserData cmdlet 创建整个 RTC 数据库的 XML 导出。</span><span class="sxs-lookup"><span data-stu-id="62a85-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="62a85-116">使用文件系统备份或第三方备份备份会议内容和合规性日志。</span><span class="sxs-lookup"><span data-stu-id="62a85-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="62a85-117">使用 Export-CsConfiguration 命令行工具备份 Skype for Business 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="62a85-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="62a85-118">故障转移过程的第一个步骤包括强制性地将用户从生产池移动到灾难恢复池。</span><span class="sxs-lookup"><span data-stu-id="62a85-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="62a85-119">之所以称为强制性移动是因为生产池并不接受用户重新定位。</span><span class="sxs-lookup"><span data-stu-id="62a85-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="62a85-120">除了 RTC SQL 数据库上的记录更新之外，Skype for Business 服务器移动用户进程对用户帐户对象上的属性的更改很有效。</span><span class="sxs-lookup"><span data-stu-id="62a85-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="62a85-121">通过使用标准 SQL Server 还原过程或使用第三方备份/还原实用工具，可以从生产 SQL Server 中的原始备份转储设备还原此数据。</span><span class="sxs-lookup"><span data-stu-id="62a85-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="62a85-122">还原此数据后，用户可以有效地连接到灾难恢复池，并照常运行。</span><span class="sxs-lookup"><span data-stu-id="62a85-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="62a85-123">若要使用户能够连接到灾难恢复池，则需要更改 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="62a85-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="62a85-124">使用以下各项的自动配置和 DNS SRV 记录，客户端将引用生产版 Skype for Business 池：</span><span class="sxs-lookup"><span data-stu-id="62a85-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="62a85-125">SRV： _sip _tls。\<域>/CNAME： SIP。\<域></span><span class="sxs-lookup"><span data-stu-id="62a85-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="62a85-126">CNAME： SIP。\<域>/cvc-pool-1。\<域></span><span class="sxs-lookup"><span data-stu-id="62a85-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="62a85-127">为促进故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="62a85-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="62a85-128">CNAME： SIP。<domain></span><span class="sxs-lookup"><span data-stu-id="62a85-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="62a85-129">/DROCSPool.\<域></span><span class="sxs-lookup"><span data-stu-id="62a85-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="62a85-130">Sip.\<域></span><span class="sxs-lookup"><span data-stu-id="62a85-130">Sip.\<domain></span></span>
- <span data-ttu-id="62a85-131">> 的\<AV 域</span><span class="sxs-lookup"><span data-stu-id="62a85-131">AV.\<domain></span></span>
- <span data-ttu-id="62a85-132">webconf.\<域></span><span class="sxs-lookup"><span data-stu-id="62a85-132">webconf.\<domain></span></span>
