---
title: 发布拓扑选择 CMS 页面
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 发布已使用拓扑生成器配置的拓扑。 要求您从将承担中央管理存储角色的前端服务器或前端池列表中选择该列表。 在任何给定时间，只有一个前端服务器或前端池可以保留此角色。
ms.openlocfilehash: 4f4658b13a634d5f1d231d4e8fe7683b3fc38b8f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860559"
---
# <a name="publish-topology-select-cms-page"></a>发布拓扑选择 CMS 页面
 
发布已使用拓扑生成器配置的拓扑。 要求您从将承担中央管理存储角色的前端服务器或前端池列表中选择该列表。 在任何给定时间，只有一个前端服务器或前端池可以保留此角色。 
  
### <a name="about-the-central-management-server"></a>关于中央管理服务器
中央管理服务器是单一主副本/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。 拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）在 SQL Server 数据库 (（默认情况下名为 RTCLOC) AL）中具有中央管理存储数据的只读副本，该副本在安装和部署过程中安装在该计算机上。 本地数据库通过作为服务在所有计算机上运行的 Lync Server 副本复制程序代理接收副本更新。 中央管理服务器上实际数据库和本地副本的名称为 XDS，它由 xds.mdf 和 xds.ldf 文件决定。 主数据库位置由 Active Directory 域服务 (SCP) 服务控制点引用。 使用中央管理服务器管理和配置 Lync Server 的所有工具都使用 SCP 查找中央管理存储。
  
## <a name="see-also"></a>另请参阅

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)