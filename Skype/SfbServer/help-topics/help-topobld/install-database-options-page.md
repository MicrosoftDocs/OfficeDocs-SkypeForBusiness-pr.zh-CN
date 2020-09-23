---
title: 安装数据库选项页
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 您可以为 SQL Server 上的数据库和日志文件的放置配置高级选项。 可用的选项有：
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215303"
---
# <a name="install-database-options-page"></a><span data-ttu-id="a909a-104">安装数据库选项页</span><span class="sxs-lookup"><span data-stu-id="a909a-104">Install Database Options Page</span></span>

<span data-ttu-id="a909a-105">您可以为 SQL Server 上的数据库和日志文件的放置配置高级选项。</span><span class="sxs-lookup"><span data-stu-id="a909a-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="a909a-106">可用的选项有：</span><span class="sxs-lookup"><span data-stu-id="a909a-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a909a-107">选择最适合您的要求和策略的选项，这些要求和策略与 SQL Server 计算机上的数据和日志文件放置相关。</span><span class="sxs-lookup"><span data-stu-id="a909a-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="a909a-108">**自动确定数据库文件位置**：默认选项使用一个算法来确定 SQL Server 上的可用空间，并分发数据库和日志文件以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="a909a-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="a909a-109">**使用 Sql server 实例默认值**：选择此选项可根据 SQL Server 上的实例设置放置数据库文件和日志文件。</span><span class="sxs-lookup"><span data-stu-id="a909a-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="a909a-110">这些选项通常由数据库管理员管理和配置。</span><span class="sxs-lookup"><span data-stu-id="a909a-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="a909a-111">**我们在目标 SQL Server 上的这些路径**：选择此选项可通过键入要放置数据库和日志文件的驱动器和文件夹的完整路径，从而定义您自己的 SQL server 数据库和日志文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a909a-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a909a-112">输入的路径可能会根据安装中的性能优化算法进行修改。</span><span class="sxs-lookup"><span data-stu-id="a909a-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="a909a-113">有关详细信息，请参阅[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a909a-113">For details, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span></span>

 <span data-ttu-id="a909a-114">**确定**：单击“确定”按钮以应用更改。</span><span class="sxs-lookup"><span data-stu-id="a909a-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="a909a-115">**取消**：单击“取消”以放弃所有更改并返回到“安装数据库”屏幕。</span><span class="sxs-lookup"><span data-stu-id="a909a-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="a909a-116">**帮助**：单击“帮助”按钮以访问此帮助页面。</span><span class="sxs-lookup"><span data-stu-id="a909a-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a909a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a909a-117">See also</span></span>

[<span data-ttu-id="a909a-118">SQL Server 数据和日志文件放置</span><span class="sxs-lookup"><span data-stu-id="a909a-118">SQL Server Data and Log File Placement</span></span>](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
