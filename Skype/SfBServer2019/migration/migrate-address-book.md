---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通常情况下，通讯簿与拓扑的其余部分一起迁移。 但是，如果您在旧版环境中自定义以下迁移步骤，则可能需要执行某些迁移后步骤：
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752834"
---
# <a name="migrate-address-book"></a><span data-ttu-id="69619-104">迁移通讯簿</span><span class="sxs-lookup"><span data-stu-id="69619-104">Migrate Address Book</span></span>

<span data-ttu-id="69619-105">通常情况下，通讯簿与拓扑的其余部分一起迁移。</span><span class="sxs-lookup"><span data-stu-id="69619-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="69619-106">但是，如果您在旧版环境中自定义以下迁移步骤，则可能需要执行某些迁移后步骤：</span><span class="sxs-lookup"><span data-stu-id="69619-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="69619-107">自定义了通讯簿规范化规则。</span><span class="sxs-lookup"><span data-stu-id="69619-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="69619-108">将**UseNormalizationRules**参数的默认值更改为 False。</span><span class="sxs-lookup"><span data-stu-id="69619-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="69619-109">**通讯簿规范化规则**</span><span class="sxs-lookup"><span data-stu-id="69619-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="69619-110">如果您在旧版环境中自定义了通讯簿规范化规则，则必须将自定义规则迁移到您的引导池。</span><span class="sxs-lookup"><span data-stu-id="69619-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="69619-111">如果未自定义通讯簿规范化规则，则通讯簿服务没有要迁移的内容。</span><span class="sxs-lookup"><span data-stu-id="69619-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="69619-112">Skype for business Server 2019 的默认规范化规则与旧安装的默认规则相同。</span><span class="sxs-lookup"><span data-stu-id="69619-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="69619-113">按照本节后面的过程操作，迁移自定义的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="69619-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="69619-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span><span class="sxs-lookup"><span data-stu-id="69619-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="69619-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span><span class="sxs-lookup"><span data-stu-id="69619-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="69619-116">**UseNormalizationRules 设置为 False**</span><span class="sxs-lookup"><span data-stu-id="69619-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="69619-117">如果将**UseNormalizationRules**的值设置为 False，以便用户可以使用在 Active Directory 域服务中定义的电话号码，而无需使用 Skype For business Server 2019 应用规范化规则，则需要将**UseNormalizationRules**和**IgnoreGenericRules**参数设置为 True。</span><span class="sxs-lookup"><span data-stu-id="69619-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="69619-118">按照本节后面的过程操作，将这些参数设置为 True。</span><span class="sxs-lookup"><span data-stu-id="69619-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="69619-119">迁移通讯簿自定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="69619-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="69619-120">在通讯簿共享文件夹的根目录中查找 Company_Phone_Number_Normalization_Rules.txt 文件，并将其复制到 Skype for Business Server 2019 试行版池中的通讯簿共享文件夹的根目录中。</span><span class="sxs-lookup"><span data-stu-id="69619-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69619-121">示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。</span><span class="sxs-lookup"><span data-stu-id="69619-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="69619-122">路径为 **$installedDriveLetter： \Program Files\Microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**。</span><span class="sxs-lookup"><span data-stu-id="69619-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="69619-123">可以将此文件作为**Company_Phone_Number_Normalization_Rules.txt**复制和重命名为通讯簿共享文件夹的根目录。</span><span class="sxs-lookup"><span data-stu-id="69619-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="69619-124">例如， **$serverX**中共享的通讯簿，该路径将类似于： \*\* \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*。</span><span class="sxs-lookup"><span data-stu-id="69619-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="69619-125">使用文本编辑器（如“记事本”）打开 Company_Phone_Number_Normalization_Rules.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="69619-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="69619-126">在 Skype for business Server 2019 中，某些类型的条目将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="69619-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="69619-127">请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="69619-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="69619-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span><span class="sxs-lookup"><span data-stu-id="69619-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="69619-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span><span class="sxs-lookup"><span data-stu-id="69619-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="69619-130">For example, the following string would cause the normalization rule to fail:</span><span class="sxs-lookup"><span data-stu-id="69619-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="69619-131">以下字符串不会导致规范化规则失败：</span><span class="sxs-lookup"><span data-stu-id="69619-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="69619-132">将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true</span><span class="sxs-lookup"><span data-stu-id="69619-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="69619-133">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="69619-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="69619-134">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="69619-134">Do one of the following:</span></span>

   - <span data-ttu-id="69619-135">如果您的部署仅包括 Skype for Business Server 2019，请在全局级别运行以下 cmdlet，以将**UseNormalizationRules**和**IgnoreGenericRules**的值更改为 True：</span><span class="sxs-lookup"><span data-stu-id="69619-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="69619-136">如果您的部署包含 Skype for business Server 2019 和旧安装的组合，请运行以下 cmdlet，并将其分配给拓扑中的每个 Skype for Business Server 2019 池：</span><span class="sxs-lookup"><span data-stu-id="69619-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="69619-137">等待中央管理存储复制在所有池上进行。</span><span class="sxs-lookup"><span data-stu-id="69619-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="69619-138">修改电话规范化规则文件 "Company_Phone_Number_Normalization_Rules.txt"，以供您的部署清除内容。</span><span class="sxs-lookup"><span data-stu-id="69619-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="69619-139">文件位于每个 Skype for Business Server 2019 池的文件共享中。</span><span class="sxs-lookup"><span data-stu-id="69619-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="69619-140">如果文件不存在，则创建一个名为 "Company_Phone_Number_Normalization_Rules.txt" 的空文件。</span><span class="sxs-lookup"><span data-stu-id="69619-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="69619-141">等待几分钟，让所有前端池都能读取新文件。</span><span class="sxs-lookup"><span data-stu-id="69619-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="69619-142">在部署中的每个 Skype for Business Server 2019 池中运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="69619-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


