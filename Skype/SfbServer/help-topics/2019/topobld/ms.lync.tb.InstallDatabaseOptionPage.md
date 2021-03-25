---
title: 安装数据库选项页
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 配置数据库和日志文件在数据库和日志文件上的位置的高级SQL Server。 可用的选项有：
ms.openlocfilehash: 4b4323f2b0e953ff24a458a2f28f75f52d4f0149
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121640"
---
# <a name="install-database-options-page"></a><span data-ttu-id="56856-104">安装数据库选项页</span><span class="sxs-lookup"><span data-stu-id="56856-104">Install Database Options Page</span></span>

<span data-ttu-id="56856-105">配置数据库和日志文件在数据库和日志文件上的位置的高级SQL Server。</span><span class="sxs-lookup"><span data-stu-id="56856-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="56856-106">可用的选项有：</span><span class="sxs-lookup"><span data-stu-id="56856-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56856-107">选择最符合与数据和策略相关的要求和策略的选项，日志文件计算机上SQL Server位置。</span><span class="sxs-lookup"><span data-stu-id="56856-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="56856-108">**自动确定数据库文件位置**：默认选项使用一种算法来确定数据库SQL Server并分发数据库和日志文件以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="56856-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="56856-109">**Use SQL Server instance defaults**： Select this option to place database file and log files based on the instance settings at SQL Server.</span><span class="sxs-lookup"><span data-stu-id="56856-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="56856-110">这些选项通常由数据库管理员管理和配置。</span><span class="sxs-lookup"><span data-stu-id="56856-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="56856-111">目标数据库上的这些 **路径** SQL Server：通过键入要放置数据库和日志文件的驱动器和文件夹的完整路径，选择此选项可定义你自己的 SQL Server 数据库和日志文件路径。</span><span class="sxs-lookup"><span data-stu-id="56856-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56856-112">输入的路径可能会根据安装中的性能优化算法进行修改。</span><span class="sxs-lookup"><span data-stu-id="56856-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="56856-113">有关详细信息，请参阅[Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)。</span><span class="sxs-lookup"><span data-stu-id="56856-113">For details, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span></span>

 <span data-ttu-id="56856-114">**确定**：单击“确定”按钮以应用更改。</span><span class="sxs-lookup"><span data-stu-id="56856-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="56856-115">**取消**：单击“取消”以放弃所有更改并返回到“安装数据库”屏幕。</span><span class="sxs-lookup"><span data-stu-id="56856-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="56856-116">**帮助**：单击“帮助”按钮以访问此帮助页面。</span><span class="sxs-lookup"><span data-stu-id="56856-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="56856-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56856-117">See also</span></span>

[<span data-ttu-id="56856-118">SQL Server 数据和日志文件放置</span><span class="sxs-lookup"><span data-stu-id="56856-118">SQL Server Data and Log File Placement</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)