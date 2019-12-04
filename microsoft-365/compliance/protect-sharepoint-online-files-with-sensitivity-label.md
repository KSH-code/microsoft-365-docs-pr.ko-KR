---
title: 민감도 레이블을 사용하여 SharePoint Online 파일 보호
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: '요약: Azure Information Protection을 적용하여 극비 SharePoint Online 팀 사이트의 파일을 보호합니다.'
ms.openlocfilehash: 51950bd3c9790dedd2801e98234ff16470db6421
ms.sourcegitcommit: 58a7bd70a4bcf52530baf5f82507fd5dc4455fd9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "39668806"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a><span data-ttu-id="03465-103">민감도 레이블을 사용하여 SharePoint Online 파일 보호</span><span class="sxs-lookup"><span data-stu-id="03465-103">Protect SharePoint Online files with sensitivity labels</span></span>

<span data-ttu-id="03465-104">이 문서의 단계를 사용하여 파일에 대한 암호화 및 권한을 제공하도록 Office 365 민감도 레이블을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-104">Use the steps in this article to configure an Office 365 sensitivity label to provide encryption and permissions for files.</span></span> <span data-ttu-id="03465-105">이러한 파일은 극비 보호를 위해 구성된 SharePoint 라이브러리에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-105">These files can be added to a SharePoint library configured for highly confidential protection.</span></span> <span data-ttu-id="03465-106">또는 사이트에서 직접 파일을 열고 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-106">Or, you can open a file directly from the site and apply the label.</span></span> <span data-ttu-id="03465-107">암호와 및 권한 보호는 사이트에서 다운로드할 때에도 파일과 함께 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-107">The encryption and permissions protection travels with a file even when it is downloaded from the site.</span></span> 

<span data-ttu-id="03465-p102">다음 단계는 이러한 사이트 내에서 SharePoint 사이트 및 파일에 대해 극비 보호를 구성하기 위한 보다 큰 솔루션의 일부입니다. 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03465-p102">These steps are part of a larger solution for configuring highly confidential protection for SharePoint sites and the files within these sites. For more information, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span> 

<span data-ttu-id="03465-110">SharePoint Online의 파일에 대해 민감도 레이블을 사용하는 것이 모든 고객에게 권장되는 것은 아니지만 일부 파일에 대해 이러한 수준의 보호가 필요한 고객에게는 적절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-110">Using Azure Information Protection for files in SharePoint Online is not recommended for all customers, but is an option for customers who need this level of protection for a subset of files.</span></span>

<span data-ttu-id="03465-111">이 솔루션에 대한 몇 가지 중요 참고 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-111">Some important notes about this solution:</span></span>
- <span data-ttu-id="03465-112">Office 365에 저장된 파일에 암호화가 적용되어 있으면 이 파일의 내용을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-112">Be aware that when sensitivity label encryption is applied to files stored in Office 365, the service cannot process the contents of these files.</span></span> <span data-ttu-id="03465-113">즉 공동 작성, eDiscovery, 검색, Delve 및 기타 공동 작업 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-113">Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work.</span></span> <span data-ttu-id="03465-114">DLP(데이터 손실 방지) 정책은 메타데이터(Office 365 레이블 포함)에만 작동할 수 있지만 파일의 내용(예: 파일 내의 신용 카드 번호)에는 작동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-114">Data Loss Prevention (DLP) policies can only work with the metadata (including Office 365 labels) but not the contents of these files (such as credit card numbers within files).</span></span>

- <span data-ttu-id="03465-115">이 솔루션을 사용하려면 사용자가 보호를 적용할 레이블을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-115">This solution requires a user to select a label that applies the protection.</span></span> <span data-ttu-id="03465-116">자동 암호화 및 SharePoint에서 파일을 색인화하고 검사하는 기능이 필요한 경우 SharePoint Online에서 IRM (정보 권한 관리)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-116">If you require automatic encryption and the ability for SharePoint to index and inspect the files, consider using Information Rights Management (IRM) in SharePoint Online.</span></span> <span data-ttu-id="03465-117">IRM에 대해 SharePoint 라이브러리를 구성하면 파일은 편집을 위해 다운로드될 때 자동으로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="03465-117">When you configure a SharePoint library for IRM, files are automatically encrypted when they are downloaded for editing.</span></span>  <span data-ttu-id="03465-118">SharePoint IRM에는 결정에 영향을 줄 수 있는 제한 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-118">SharePoint IRM includes limitations that might influence your decision.</span></span> <span data-ttu-id="03465-119">자세한 내용은 [SharePoint 관리 센터의 IRM (정보 권한 관리) 설정](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-119">For more information, see [Set up Information Rights Management (IRM) in SharePoint admin center](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).</span></span>

## <a name="admin-setup"></a><span data-ttu-id="03465-120">관리자 설정</span><span class="sxs-lookup"><span data-stu-id="03465-120">Admin setup</span></span>

<span data-ttu-id="03465-121">특정 SharePoint Online 팀 사이트에 저장된 파일에 대한 보안 수준을 추가적으로 설정하려면, 고유의 레이블이나 높은 규제 대상 데이터를 위한 일반 레이블의 하위 레이블인 사용자 지정 민감도 레이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-121">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="03465-122">SharePoint Online 팀 사이트의 Office 365 그룹 구성원만 레이블 목록에서 사용자 지정된 레이블 또는 하위 레이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-122">Only members of the Office 365 group for the SharePoint Online team site will see the customized label or sublabel in their list of labels.</span></span>

- <span data-ttu-id="03465-123">전역적인 사용과 개별적 개인 팀에 소수의 레이블이 필요한 경우에는 민감도 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-123">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span>

- <span data-ttu-id="03465-124">다수의 레이블을 보유하고 있거나 극비 파일에 일반 레이블로 극비 팀의 레이블을 구성하려는 경우 민감도 하위 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-124">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="03465-125">[이 지침](encryption-sensitivity-labels.md)을 사용하여 다음의 설정으로 개별 레이블이나 하위 레이블을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-125">[Use these instructions](encryption-sensitivity-labels.md) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="03465-126">레이블 또는 하위 레이블 이름은 팀 사이트 이름을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-126">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="03465-127">암호화를 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="03465-127">Encryption is enabled</span></span>
- <span data-ttu-id="03465-128">팀 사이트의 Office 365 그룹은 공동 작성 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="03465-128">The Office 365 group for the team site has Co-Author permissions</span></span>

<span data-ttu-id="03465-129">작성한 후에는 사용자를 위해 새 레이블이나 하위 레이블을 게시합니다. 사용자는 레이블을 팀에 업로드하기 전에 로컬에서 파일에 적용하거나 파일이 팀에 저장된 후에 파일에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-129">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>
 
<span data-ttu-id="03465-130">사용자가 Microsoft Word, Excel 및 PowerPoint의 **홈** 리본에 있는 **민감도** 옵션에서 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-130">Once your uses can select the sensitivity label from the **Sensitivity** option from the **Home** ribbon in Microsoft Word, Excel, and PowerPoint.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03465-131">극비 SharePoint Online 팀 사이트가 여러 개인 경우 여러 개의 민감도 레이블을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-131">If you have multiple highly sensitive SharePoint Online team sites, you should create multiple sensitivity labels.</span></span> 
  
## <a name="adding-permissions-for-external-users"></a><span data-ttu-id="03465-132">외부 사용자에 대한 권한 추가</span><span class="sxs-lookup"><span data-stu-id="03465-132">Adding permissions for external users</span></span>
<span data-ttu-id="03465-133">민감도 레이블로 보호된 파일에 대한 액세스 권한을 외부 사용자에게 부여할 수 있는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-133">There are two ways you can grant external users access to files protected with a sensitivity label.</span></span> <span data-ttu-id="03465-134">두 경우 모두 외부 사용자에게 Azure AD 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-134">In both these cases, external users must have an Azure AD account.</span></span> <span data-ttu-id="03465-135">외부 사용자가 Azure AD를 사용하는 조직의 구성원이 아닌 경우 [https://aka.ms/aip-signup](https://aka.ms/aip-signup) 등록 페이지를 사용하여 Azure AD 계정을 개별로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-135">If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this sign-up page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>

 - <span data-ttu-id="03465-136">팀 사이트의 Office 365 그룹에 외부 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-136">Add external users to the Office 365 group for the team site.</span></span> <span data-ttu-id="03465-137">먼저 디렉터리에 계정을 B2B 사용자로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-137">You'll need to first add the account as a B2B user in your directory.</span></span> <span data-ttu-id="03465-138">[Azure Rights Management에서 그룹 구성원 자격을 캐시](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection)하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-138">It can take a couple of hours for [group membership caching by Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).</span></span>  
 - <span data-ttu-id="03465-139">직접 외부 사용자 계정을 레이블 구성에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03465-139">Add external user accounts directly to the label configuration.</span></span> <span data-ttu-id="03465-140">조직의 모든 사용자 (예: Fabrikam.com), Office 365 그룹(조직 내의 재무 그룹 등) 또는 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-140">Add external users directly to the label protection. You can add all users from an organization (e.g. Fabrikam.com), an Azure AD group (such as a finance group within an organization), or user. For example, you can add an external team of regulators to the protection for a label.</span></span> <span data-ttu-id="03465-141">예를 들어 민감도 레이블의 권한에 외부 규제자 팀을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03465-141">For example, you can add an external team of regulators to the permissions of your sensitivity label.</span></span>

## <a name="see-also"></a><span data-ttu-id="03465-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03465-142">See Also</span></span>

[<span data-ttu-id="03465-143">SharePoint Online 사이트 및 파일 보호</span><span class="sxs-lookup"><span data-stu-id="03465-143">Secure SharePoint Online sites and files</span></span>](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="03465-144">정치적 캠페인, 비영리 조직 및 기타 기밀 조직을 위한 Microsoft 보안 지침</span><span class="sxs-lookup"><span data-stu-id="03465-144">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="03465-145">클라우드 도입 및 하이브리드 솔루션</span><span class="sxs-lookup"><span data-stu-id="03465-145">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
