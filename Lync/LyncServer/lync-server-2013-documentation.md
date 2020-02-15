---
title: Lync Server 2013：文档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb6dd3b632c1eb4ae4b90b68cde7996ca6bf133
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="cee06-102">Lync Server 2013 中的文档</span><span class="sxs-lookup"><span data-stu-id="cee06-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cee06-103">_**上次修改的主题：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="cee06-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="cee06-104">MOF 模型由许多服务管理功能组成。</span><span class="sxs-lookup"><span data-stu-id="cee06-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="cee06-105">有关如何以及何时执行任务的文档可以与同一个团队的成员或其他团队共享。</span><span class="sxs-lookup"><span data-stu-id="cee06-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="cee06-106">存储和共享文档的方法可能因函数类型而异。</span><span class="sxs-lookup"><span data-stu-id="cee06-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="cee06-107">例如，系统管理过程可能存储为 Word 文档，因为它们可能会经常打印和引用。</span><span class="sxs-lookup"><span data-stu-id="cee06-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="cee06-108">配置管理信息可能会自动生成并存储在数据库中，以方便搜索和编制索引。</span><span class="sxs-lookup"><span data-stu-id="cee06-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="cee06-109">有些文档可能是敏感文档，应加以限制。</span><span class="sxs-lookup"><span data-stu-id="cee06-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="cee06-110">文档管理系统</span><span class="sxs-lookup"><span data-stu-id="cee06-110">Document management systems</span></span>

<span data-ttu-id="cee06-111">文档管理系统充当文档的中央存储库，并帮助确保仅提供最新的文档修订。</span><span class="sxs-lookup"><span data-stu-id="cee06-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="cee06-112">您还可以考虑存档文档的旧版本以供参考。</span><span class="sxs-lookup"><span data-stu-id="cee06-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="cee06-113">Lync Server 提供了适用于此任务的功能。</span><span class="sxs-lookup"><span data-stu-id="cee06-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="cee06-114">Databases</span><span class="sxs-lookup"><span data-stu-id="cee06-114">Databases</span></span>

<span data-ttu-id="cee06-115">讨论了几个适用于使用数据库的工具和管理功能。</span><span class="sxs-lookup"><span data-stu-id="cee06-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="cee06-116">配置管理过程可能使用存储大量需要索引和搜索的数据的自动化过程。</span><span class="sxs-lookup"><span data-stu-id="cee06-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="cee06-117">支持人员在对新问题进行故障排除时，可以在数据库中搜索过去的问题和解决方法。</span><span class="sxs-lookup"><span data-stu-id="cee06-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="cee06-118">可能会有不同的数据库用于不同的用途。</span><span class="sxs-lookup"><span data-stu-id="cee06-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="cee06-119">决定是否应链接或组合这些数据库。</span><span class="sxs-lookup"><span data-stu-id="cee06-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="cee06-120">例如，如果服务中心标识了一个常见主题（例如新软件导致特定网络适配器出现问题）的多个问题，则支持人员可以查询配置数据库，以预测可能受影响的计算机数。</span><span class="sxs-lookup"><span data-stu-id="cee06-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

