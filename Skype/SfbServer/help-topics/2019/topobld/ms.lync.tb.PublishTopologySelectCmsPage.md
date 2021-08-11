---
title: 发布拓扑选择 CMS 页面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 发布已使用拓扑生成器配置的拓扑。 要求您从将承担中央管理存储角色的前端服务器或前端池列表中选择该列表。 在任何给定时间，只有一个前端服务器或前端池可以保留此角色。
ms.openlocfilehash: aba80733c215d9de1eab58be7054ad68519123a9f23f131f389b50754ac0dc73
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307543"
---
# <a name="publish-topology-select-cms-page"></a>发布拓扑选择 CMS 页面
 
发布已使用拓扑生成器配置的拓扑。 要求您从将承担中央管理存储角色的前端服务器或前端池列表中选择该列表。 在任何给定时间，只有一个前端服务器或前端池可以保留此角色。 
  
### <a name="about-the-central-management-server"></a>关于中央管理服务器
中央管理服务器是单一主副本/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。 拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）在 SQL Server 数据库 (（默认情况下名为 RTCLOC) AL）中具有中央管理存储数据的只读副本，该副本在安装和部署过程中安装在该计算机上。 本地数据库通过作为服务在所有计算机上运行的 Lync Server 副本复制程序代理接收副本更新。 中央管理服务器上实际数据库和本地副本的名称为 XDS，它由 xds.mdf 和 xds.ldf 文件决定。 主数据库位置由 Active Directory 域服务中 SCP (服务) 引用。 使用中央管理服务器管理和配置 Lync Server 的所有工具都使用 SCP 查找中央管理存储。
  
## <a name="see-also"></a>另请参阅

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)