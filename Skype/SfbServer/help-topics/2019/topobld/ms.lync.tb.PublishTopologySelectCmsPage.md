---
title: 发布拓扑选择 CMS 页面
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 发布已配置使用拓扑生成器的拓扑。 您需要从前端服务器或前端池，则假定按住中央管理存储的角色的列表中选择。 只有一个前端服务器或前端池可以在任何给定时间保留此角色。
ms.openlocfilehash: 0c80fa30721fe47fc3bc4725ca4f50f8a75f7009
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201691"
---
# <a name="publish-topology-select-cms-page"></a>发布拓扑选择 CMS 页面
 
发布已配置使用拓扑生成器的拓扑。 您需要从前端服务器或前端池，则假定按住中央管理存储的角色的列表中选择。 只有一个前端服务器或前端池可以在任何给定时间保留此角色。 
  
### <a name="about-the-central-management-server"></a>有关中央管理服务器
中央管理服务器是单个母版/多副本系统，数据库的读/写副本由前端服务器包含中央管理服务器。 在拓扑中，包括前端服务器包含中央管理服务器，每台计算机都安装过程中的计算机上安装 SQL Server 数据库 （名为默认情况下 RTCLOCAL） 中的中央管理存储数据的只读副本和部署。 本地数据库接收通过作为服务的所有计算机运行 Lync Server 副本复制程序代理的副本更新。 在中央管理服务器和的本地副本的实际数据库的名称为 XDS，组成 xds.mdf 和 xds.ldf 文件。 服务控制点 (SCP) Active Directory 域服务中被引用的主数据库位置。 中央管理服务器用于管理和配置 Lync Server 的所有工具都使用 SCP 查找中央管理存储。
  
## <a name="see-also"></a>另请参阅

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
