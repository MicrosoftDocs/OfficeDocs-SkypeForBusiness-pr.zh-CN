---
title: 安装数据库选项页
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 配置用于将数据库和日志文件放置到数据库和日志文件的高级SQL Server。 可用的选项有：
ms.openlocfilehash: f9c2553fb0a4fa8f538a70a2ce496eaf054a0dc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806912"
---
# <a name="install-database-options-page"></a><span data-ttu-id="396b5-104">安装数据库选项页</span><span class="sxs-lookup"><span data-stu-id="396b5-104">Install Database Options Page</span></span>

<span data-ttu-id="396b5-105">配置用于将数据库和日志文件放置到数据库和日志文件的高级SQL Server。</span><span class="sxs-lookup"><span data-stu-id="396b5-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="396b5-106">可用的选项有：</span><span class="sxs-lookup"><span data-stu-id="396b5-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="396b5-107">选择最符合你有关数据的要求和策略的选项，日志文件和SQL Server位置。</span><span class="sxs-lookup"><span data-stu-id="396b5-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="396b5-108">**自动确定数据库文件位置**：默认选项使用一种算法来确定数据库上的可用空间SQL Server并分发数据库和日志文件以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="396b5-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="396b5-109">**使用SQL Server** 默认值：选择此选项可基于实例设置将数据库文件和日志文件放在SQL Server。</span><span class="sxs-lookup"><span data-stu-id="396b5-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="396b5-110">这些选项通常由数据库管理员管理和配置。</span><span class="sxs-lookup"><span data-stu-id="396b5-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="396b5-111">目标 SQL Server 上的这些路径：选择此选项，通过键入要放置数据库和日志文件的驱动器和文件夹的完整路径来定义您自己的 SQL Server 数据库和日志文件路径。</span><span class="sxs-lookup"><span data-stu-id="396b5-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="396b5-112">输入的路径可能会根据安装中的性能优化算法进行修改。</span><span class="sxs-lookup"><span data-stu-id="396b5-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="396b5-113">有关详细信息，请参阅[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="396b5-113">For details, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span></span>

 <span data-ttu-id="396b5-114">**确定**：单击“确定”按钮以应用更改。</span><span class="sxs-lookup"><span data-stu-id="396b5-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="396b5-115">**取消**：单击“取消”以放弃所有更改并返回到“安装数据库”屏幕。</span><span class="sxs-lookup"><span data-stu-id="396b5-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="396b5-116">**帮助**：单击“帮助”按钮以访问此帮助页面。</span><span class="sxs-lookup"><span data-stu-id="396b5-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="396b5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="396b5-117">See also</span></span>

[<span data-ttu-id="396b5-118">SQL Server 数据和日志文件放置</span><span class="sxs-lookup"><span data-stu-id="396b5-118">SQL Server Data and Log File Placement</span></span>](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
