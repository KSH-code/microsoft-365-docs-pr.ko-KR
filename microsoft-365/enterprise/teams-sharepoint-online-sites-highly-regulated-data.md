---
title: 높은 규제 대상 데이터에 대한 Microsoft Teams 및 SharePoint Online 사이트
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 보안 SharePoint Online 팀 사이트 및 Microsoft Teams 팀을 만들어 가장 소중하고 중요한 디지털 자산을 저장합니다.
ms.openlocfilehash: 04984be44ddb2cc1aabc2032970f92e71899b268
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047345"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a><span data-ttu-id="56bd5-103">높은 규제 대상 데이터에 대한 Microsoft Teams 및 SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="56bd5-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="56bd5-104">*이 시나리오는 Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="56bd5-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="56bd5-p101">Microsoft 365 Enterprise에는 높은 규제 대상 데이터를 만들고, 저장하고, 보안을 유지할 수 있도록 하기 위해 전체 클라우드 기반 서비스 제품군이 포함되어 있습니다. 여기에는 다음과 같은 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="56bd5-107">지역 규제를 받는 데이터</span><span class="sxs-lookup"><span data-stu-id="56bd5-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="56bd5-108">영업 비밀, 재무 또는 인사 관련 정보와 조직의 전략과 같이 조직에서 가장 중요한 데이터</span><span class="sxs-lookup"><span data-stu-id="56bd5-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="56bd5-109">이러한 비즈니스 요구를 충족하는 Microsoft 365 Enterprise 클라우드 기반 시나리오에서는 다음을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-109">A Microsoft 365 Enterprise cloud-based solution that meets this business need requires that you:</span></span>

- <span data-ttu-id="56bd5-110">디지털 자산(문서, 슬라이드 데크, 스프레드시트 등)을 SharePoint Online 팀 사이트 또는 Microsoft Teams 팀의 **파일** 탭에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the **Files** tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="56bd5-111">사이트 또는 팀의 다음 작업이 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-111">Lock down the site or team to prevent:</span></span>
   - <span data-ttu-id="56bd5-112">그룹 멤버 자격을 통해 특정 사용자 계정 집합에만 액세스할 수 있습니다. 특정 사용자 계정 집합에는 임의 권한 수준에서 SharePoint Online 팀 사이트에 액세스할 수 있는 사용자 계정 및 해당 사이트를 관리할 수 있는 사용자 계정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-112">Access to only a specific set of user accounts through group membership, which includes those who can access the SharePoint Online team site and at what level of permission, and those who can administer it.</span></span>
   - <span data-ttu-id="56bd5-113">사이트의 멤버가 다른 사람에게 액세스 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-113">Members of the site from granting access to others.</span></span>
   - <span data-ttu-id="56bd5-114">사이트의 멤버 이외의 사용자가 다른 사람에게 액세스 권한을 요청할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="56bd5-115">SharePoint Online 사이트 또는 팀에 대한 Office 365 보존 레이블을 사이트 또는 팀에 있는 문서에 대한 보존 정책을 정의하는 기본 방법으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-115">Configure an Office 365 retention label for your SharePoint Online sites or teams as a default way to define retention policies on the documents in the site or team.</span></span>
- <span data-ttu-id="56bd5-116">사용자가 조직 외부로 파일을 보내지 못하도록 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-116">Block users from sending files outside the organization.</span></span>
- <span data-ttu-id="56bd5-117">사이트 또는 팀의 가장 중요한 디지털 자산을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-117">Encrypt the most sensitive digital assets of the site or team.</span></span>
- <span data-ttu-id="56bd5-118">사이트 외부에서 공유되더라도 자산을 열기 위해서는 권한이 있는 사용자 계정의 유효한 자격 증명을 요구하도록 가장 중요한 디지털 자산에 대한 권한을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-118">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="56bd5-119">다음 표에서는 이러한 시나리오의 요구 사항과 해당하는 Microsoft 365 Enterprise의 기능을 연결해서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-119">The following table maps the requirements of this solution to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="56bd5-120">**요구 사항**</span><span class="sxs-lookup"><span data-stu-id="56bd5-120">**Requirement**</span></span> | <span data-ttu-id="56bd5-121">**Microsoft 365 Enterprise 기능**</span><span class="sxs-lookup"><span data-stu-id="56bd5-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="56bd5-122">디지털 자산 저장</span><span class="sxs-lookup"><span data-stu-id="56bd5-122">Store digital assets</span></span> | <span data-ttu-id="56bd5-123">SharePoint Online 팀 사이트 및 Office 365의 팀</span><span class="sxs-lookup"><span data-stu-id="56bd5-123">SharePoint Online team sites and teams in Office 365</span></span> |
| <span data-ttu-id="56bd5-124">사이트 잠그기</span><span class="sxs-lookup"><span data-stu-id="56bd5-124">Lock down the site</span></span> | <span data-ttu-id="56bd5-125">Azure AD 그룹 및 SharePoint Online 팀 사이트 사용 권한</span><span class="sxs-lookup"><span data-stu-id="56bd5-125">Azure AD groups and SharePoint Online team site permissions</span></span> |
| <span data-ttu-id="56bd5-126">사이트의 디지털 자산에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="56bd5-126">Label the digital assets of the site</span></span> | <span data-ttu-id="56bd5-127">Office 365 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="56bd5-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="56bd5-128">사용자가 조직 외부로 파일을 보내지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="56bd5-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="56bd5-129">Office 365의 DLP(데이터 손실 방지) 정책</span><span class="sxs-lookup"><span data-stu-id="56bd5-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="56bd5-130">사이트의 모든 디지털 자산 암호화</span><span class="sxs-lookup"><span data-stu-id="56bd5-130">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="56bd5-131">EMS(Enterprise Mobility + Security)의 Azure Information Protection 하위 레이블</span><span class="sxs-lookup"><span data-stu-id="56bd5-131">Azure Information Protection sub-labels in Enterprise Mobility + Security (EMS)</span></span> |
| <span data-ttu-id="56bd5-132">사이트의 디지털 자산에 대한 권한 추가</span><span class="sxs-lookup"><span data-stu-id="56bd5-132">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="56bd5-133">EMS의 Azure Information Protection 하위 레이블</span><span class="sxs-lookup"><span data-stu-id="56bd5-133">Azure Information Protection sub-labels in EMS</span></span> |
|||

<span data-ttu-id="56bd5-134">다음은 SharePoint Online 사이트의 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-134">Here is the configuration for a SharePoint Online site.</span></span>

![높은 규제 대상 데이터 시나리오에 대한 Microsoft Teams 및 SharePoint Online 사이트](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="56bd5-136">이 시나리오를 사용하려면 다음을 배포했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-136">This solution requires that you have already deployed:</span></span>

- <span data-ttu-id="56bd5-137">기본 인프라의 [ID](identity-infrastructure.md) 단계 및 [정보 보호](infoprotect-infrastructure.md) 단계의 1-2단계</span><span class="sxs-lookup"><span data-stu-id="56bd5-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="56bd5-138">SharePoint Online 팀 사이트에 있는 높은 규제 대상 데이터의 경우 [SharePoint Online](sharepoint-online-onedrive-workload.md)</span><span class="sxs-lookup"><span data-stu-id="56bd5-138">For highly regulated data in SharePoint Online team sites, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="56bd5-139">Microsoft Teams 팀에 있는 높은 규제 대상 데이터의 경우 [Microsoft Teams](teams-workload.md)</span><span class="sxs-lookup"><span data-stu-id="56bd5-139">For highly regulated data in Microsoft Teams teams, [Microsoft Teams](teams-workload.md).</span></span>

<span data-ttu-id="56bd5-140">다음 단계에서는 높은 규제 대상 데이터에 대한 SharePoint Online 사이트 및 팀의 디자인 및 구성 작업과 채택을 유도하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-140">The following phases step you through the design, configuration, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="56bd5-141">가상의 대표적인 다국적 기업인 Contoso Corporation에서 연구팀을 위해 SharePoint Online 사이트를 설계한 방법을 보려면 이 [예제 구성](contoso-sharepoint-online-site-for-highly-confidential-assets.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56bd5-141">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

<span data-ttu-id="56bd5-p102">높은 규제 대상 데이터에 대한 팀을 사용하려면 먼저 높은 규제 대상 데이터에 대한 SharePoint Online 팀 사이트를 만들어야 합니다. 그런 후 SharePoint Online 팀 사이트의 Office 365 그룹을 사용하는 새 팀을 만듭니다. 자세한 내용은 두 번째 작업 단계, 4단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p102">A team for highly regulated data requires that you first create a SharePoint Online team site for highly regulated data. You then create a new team that uses the Office 365 group of the SharePoint Online team site. See Phase 2, Step 4 for more information.</span></span>

<span data-ttu-id="56bd5-145">다음은 팀을 위한 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-145">Here is the configuration for a team.</span></span>

![높은 규제 대상 데이터 시나리오에 대한 Microsoft Teams 및 SharePoint Online 사이트](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-team.png)


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="56bd5-147">ID 및 장치 액세스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="56bd5-147">Identity and device access prerequisites</span></span>

<span data-ttu-id="56bd5-148">팀 또는 SharePoint Online 사이트에 대한 액세스를 보호하려면 [ID 및 장치 액세스 정책](identity-access-policies.md) 및 [권장 SharePoint Online 액세스 정책](sharepoint-file-access-policies.md)을 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-148">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="56bd5-149">첫 번째 작업 단계: 디자인</span><span class="sxs-lookup"><span data-stu-id="56bd5-149">Phase 1: Design</span></span>

<span data-ttu-id="56bd5-p103">높은 규제 대상 데이터에 대한 SharePoint Online 사이트 또는 팀을 만들려면 먼저 해당 용도를 식별해야 합니다. 예를 들어, 제조 회사의 연구/개발 부서에는 기존 제품의 최신 디자인 사양을 저장하기 위한 SharePoint Online 사이트와 신제품에 대해 공동 작업을 진행할 장소가 필요합니다. 연구/개발 부서의 구성원과 선택한 임원만 해당 사이트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p103">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="56bd5-153">그 용도는 다음과 같은 필수 구성 항목을 파악하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-153">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="56bd5-154">SharePoint Online 권한 집합 및 SharePoint 그룹 집합</span><span class="sxs-lookup"><span data-stu-id="56bd5-154">The set of SharePoint Online permission sets and SharePoint groups</span></span>
- <span data-ttu-id="56bd5-155">액세스 그룹 집합, Azure AD 보안 그룹 및 SharePoint 그룹에 추가할 구성원</span><span class="sxs-lookup"><span data-stu-id="56bd5-155">The set of access groups, the Azure AD security groups and their members to add to the SharePoint groups</span></span>
- <span data-ttu-id="56bd5-156">사이트에 할당할 Office 365 보존 레이블 및 레이블에 대한 DLP 정책 집합</span><span class="sxs-lookup"><span data-stu-id="56bd5-156">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="56bd5-157">사용자가 사이트에 저장된 높은 규제 대상 디지털 자산에 적용하는 Azure Information Protection 하위 레이블에 대한 설정</span><span class="sxs-lookup"><span data-stu-id="56bd5-157">The settings of an Azure Information Protection sub-label that users apply to highly sensitive digital assets stored in the site</span></span>

<span data-ttu-id="56bd5-158">일단 결정이 끝나면 이러한 설정을 사용하여 두 번째 작업 단계에서 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-158">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-an-isolated-sharepoint-online-site"></a><span data-ttu-id="56bd5-159">1단계: 격리된 SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="56bd5-159">Step 1: An isolated SharePoint Online site</span></span>

<span data-ttu-id="56bd5-p104">SharePoint Online 팀 사이트의 잠긴 버전을 격리된 사이트라고 합니다. 비공개 팀 사이트의 기본 설정과 달리, 격리된 사이트는 다음을 방지하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p104">The locked-down version of a SharePoint Online team site is known as an isolated site. Unlike the default settings of private team sites, isolated sites are configured to prevent:</span></span>

- <span data-ttu-id="56bd5-162">지정된 그룹의 구성원이 아닌 사용자에게 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="56bd5-162">Access to those who are not members of specified groups.</span></span>
- <span data-ttu-id="56bd5-163">액세스 요청</span><span class="sxs-lookup"><span data-stu-id="56bd5-163">The requesting of access.</span></span>
- <span data-ttu-id="56bd5-164">지정된 그룹의 현재 구성원이 무단으로 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="56bd5-164">The unauthorized granting of access by current members of specified groups.</span></span>
- <span data-ttu-id="56bd5-165">액세스 그룹 구성원에 의한 사이트 관리</span><span class="sxs-lookup"><span data-stu-id="56bd5-165">Administration of the site by access group members.</span></span>

<span data-ttu-id="56bd5-166">높은 규제 대상 자산을 포함하는 SharePoint Online 팀 사이트의 보안은 사이트의 SharePoint 관리자가 아니면 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-166">The security of SharePoint Online team sites that contain highly regulated assets do not change unless done by a SharePoint administrator for the site.</span></span>

<span data-ttu-id="56bd5-167">권한 수준, SharePoint 그룹, 액세스 그룹 및 그룹 구성원 집합 결정에 대한 자세한 내용은 [격리된 SharePoint Online 팀 사이트 디자인](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56bd5-167">See [Design an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) for the details to determine the set of permission levels, SharePoint groups, access groups, and group members.</span></span>

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="56bd5-168">2단계: Office 365 보존 레이블 및 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="56bd5-168">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="56bd5-169">SharePoint Online 팀 사이트에 적용된 Office 365 보존 레이블은 사이트에 저장된 모든 디지털 자산에 대한 기본 분류 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-169">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="56bd5-170">높은 규제 대상 데이터에 대한 SharePoint Online 사이트에서는 사용할 Office 보존 365 레이블을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-170">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="56bd5-171">Office 365 레이블의 디자인 고려 사항에 대해서는 [Office 365 분류 및 레이블](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56bd5-171">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="56bd5-p105">중요한 정보를 보호하고 우발적이거나 의도적인 노출을 방지하려면 DLP 정책을 사용합니다. 자세한 내용은 이 [개요](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p105">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="56bd5-174">높은 규제 대상 데이터에 대한 SharePoint Online 사이트의 경우, 사용자가 외부 사용자와 디지털 자산을 공유하려고 할 때 사용자를 차단하도록 사이트에 할당된 Office 365 보존 레이블에 대한 DLP 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-174">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-3-your-azure-information-protection-sub-label"></a><span data-ttu-id="56bd5-175">3단계: Azure Information Protection 하위 레이블</span><span class="sxs-lookup"><span data-stu-id="56bd5-175">Step 3: Your Azure Information Protection sub-label</span></span>

<span data-ttu-id="56bd5-p106">가장 중요한 디지털 자산에 암호화 및 권한 집합을 제공하기 위해 사용자는 Azure Information Protection 클라이언트를 사용하여 Azure Information Protection 레이블을 적용해야 합니다. 높은 규제 대상 데이터에 대한 SharePoint Online 사이트에 Azure Information Protection 레이블을 사용하려면 범위가 지정된 정책에서 Azure Information Protection 하위 레이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p106">To provide encryption and a set of permissions to your most sensitive digital assets, users must apply an Azure Information Protection label using the Azure Information Protection client. To use Azure Information Protection labels for SharePoint Online sites for highly regulated data, you must configure an Azure Information Protection sub-label in a scoped policy.</span></span> 

<span data-ttu-id="56bd5-p107">하위 레이블은 기존 레이블 아래에 있습니다. 예를 들어 극비 레이블 아래에는 연구/개발 하위 레이블을 만들 수 있습니다. 범위가 지정된 정책은 사용자 하위 집합에만 적용되는 정책입니다. 높은 규제 대상 데이터에 대한 SharePoint Online 사이트에서는 해당 범위가 사이트의 액세스 그룹 구성원인 사용자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p107">A sub-label exists under an existing label. For example, you can create a Research & Development sub-label under the Highly Confidential label. A scoped policy is one that applies only to a subset of users. For SharePoint Online sites for highly regulated data, the scope is the set of users that are members of the access groups for the site.</span></span>

<span data-ttu-id="56bd5-p108">적용된 하위 레이블 설정은 자산을 따라 이동합니다. 사이트 외부에서 다운로드되고 공유되더라도, 권한이 있는 인증된 사용자 계정만 해당 자산을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p108">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="56bd5-184">디자인 결과</span><span class="sxs-lookup"><span data-stu-id="56bd5-184">Design results</span></span>

<span data-ttu-id="56bd5-185">다음 사항이 결정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-185">You have determined the following:</span></span>

- <span data-ttu-id="56bd5-186">SharePoint 그룹 및 권한 수준 집합</span><span class="sxs-lookup"><span data-stu-id="56bd5-186">The set of SharePoint groups and permission levels</span></span>
- <span data-ttu-id="56bd5-187">액세스 그룹 집합 및 각 권한 수준의 구성원</span><span class="sxs-lookup"><span data-stu-id="56bd5-187">The set of access groups and their members for each permission level</span></span>
- <span data-ttu-id="56bd5-188">해당 Office 365 보존 레이블 및 레이블과 연결된 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="56bd5-188">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="56bd5-189">암호화 및 권한을 포함하는 Azure Information Protection 하위 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="56bd5-189">The settings of the Azure Information Protection sub-label that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="56bd5-190">두 번째 작업 단계: 구성</span><span class="sxs-lookup"><span data-stu-id="56bd5-190">Phase 2: Configure</span></span>

<span data-ttu-id="56bd5-191">두 번째 작업 단계에서는 첫 번째 작업 단계에서 결정한 설정을 구현하여 높은 규제 대상 데이터에 대한 SharePoint Online 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-191">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="56bd5-192">1단계: 격리된 SharePoint Online 팀 사이트 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="56bd5-192">Step 1: Create and configure an isolated SharePoint Online team site</span></span>

<span data-ttu-id="56bd5-193">[격리된 SharePoint Online 팀 사이트 배포](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)의 지침에 따라 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-193">Use the instructions in [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) to:</span></span>

- <span data-ttu-id="56bd5-194">사이트에서 사용되는 각 SharePoint 권한 수준에 대한 액세스 그룹을 만들고 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-194">Create and populate the access groups for each SharePoint permission level used on the site.</span></span>
- <span data-ttu-id="56bd5-195">격리된 팀 사이트를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-195">Create and configure the isolated team site.</span></span>

### <a name="step-2-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="56bd5-196">2단계: Office 365 보존 레이블에 맞게 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="56bd5-196">Step 2: Configure the site for an Office 365 retention label DLP policy</span></span>

<span data-ttu-id="56bd5-197">[Office 365 레이블 및 DLP를 사용하여 SharePoint Online 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)의 지침에 따라 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-197">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

- <span data-ttu-id="56bd5-198">Office 365 보존 레이블을 식별하거나 만든 후 격리된 SharePoint Online 사이트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-198">Identify or create the Office 365 retention label and apply it to your isolated SharePoint Online site.</span></span>
- <span data-ttu-id="56bd5-199">조직 외부의 SharePoint Online 사이트에서 디지털 자산을 공유하려고 할 경우 사용자를 차단하는 DLP 정책을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-199">Create and configure the DLP policy that blocks users when they attempt to share a digital asset on your SharePoint Online site outside the organization.</span></span>

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="56bd5-200">3단계: 사이트에 대한 Azure Information Protection 하위 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="56bd5-200">Step 3: Create an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="56bd5-201">[Azure Information Protection을 사용한 SharePoint Online 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)의 지침에 따라 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-201">Use the instructions in [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) to:</span></span> 

- <span data-ttu-id="56bd5-202">범위가 지정된 정책에서 Azure Information Protection 하위 레이블을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-202">Create and configure an Azure Information Protection sub-label in a scoped policy.</span></span>
- <span data-ttu-id="56bd5-203">사용자 컴퓨터에 Azure Information Protection 클라이언트를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-203">Deploy the Azure Information Protection client to user computers.</span></span>

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a><span data-ttu-id="56bd5-204">4단계(선택 사항): 높은 규제 대상 데이터에 대한 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="56bd5-204">Step 4 (optional): Create a team for the highly regulated data</span></span>

<span data-ttu-id="56bd5-p109">높은 규제 대상 데이터에 대한 팀을 원하는 경우 먼저 높은 규제 대상 데이터에 대한 SharePoint Online 사이트를 만듭니다. 초기 비공개 SharePoint Online 팀 사이트를 만들 때 Office 365 그룹 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p109">If you want a team for highly regulated data, you first create a SharePoint Online site for highly regulated data. When you create the initial private SharePoint Online team site, you specify an Office 365 group name.</span></span>

<span data-ttu-id="56bd5-207">높은 규제 대상 데이터에 대한 SharePoint Online 사이트가 완전히 구성되면 다음 단계에 따라 높은 규제 대상 데이터에 대한 팀으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-207">After the SharePoint Online site for highly regulated data is fully configured, use these steps to convert it into a team for highly regulated data:</span></span>

1. <span data-ttu-id="56bd5-208">Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-208">Sign in to Office 365.</span></span>
2. <span data-ttu-id="56bd5-209">**Microsoft Office 홈** 탭에서 **Teams**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-209">From the **Microsoft Office Home** tab, click **Teams**.</span></span>
3. <span data-ttu-id="56bd5-210">**Microsoft Teams** 탭의 **팀 가입 또는 팀 만들기** 창에서 **팀 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-210">From the **Microsoft Teams** tab, in the **Join or create a team** pane, click **Create team**.</span></span>
4. <span data-ttu-id="56bd5-211">**팀 만들기** 창에서 **기존 Office 365 그룹에서 팀 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-211">In the **Create your team** pane, click **Create a team from an existing Office 365 group**.</span></span>
5. <span data-ttu-id="56bd5-212">Office 365 그룹 목록에서 높은 규제 대상 데이터에 대한 SharePoint Online 사이트에 해당하는 Office 365 그룹의 이름을 선택한 후 **팀 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-212">In the list of Office 365 groups, select the name of the Office 365 group corresponding to the SharePoint Online site for highly regulated data, and then click **Choose team**.</span></span>

<span data-ttu-id="56bd5-p110">새 팀의 **파일** 탭에는 해당 SharePoint Online 사이트의 **문서** 영역에 있는 **일반** 폴더의 내용이 표시됩니다. 팀에 대한 SharePoint Online 사이트의 나머지 리소스를 보려면 줄임표를 클릭하고 **SharePoint에서 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p110">The **Files** tab of the new team lists the contents of the **General** folder of the **Documents** area of the corresponding SharePoint Online site. To see the rest of the resources of the SharePoint Online site for the team, click the ellipsis, and then click **Open in SharePoint**.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="56bd5-215">구성 결과</span><span class="sxs-lookup"><span data-stu-id="56bd5-215">Configuration results</span></span>

<span data-ttu-id="56bd5-216">구성한 항목</span><span class="sxs-lookup"><span data-stu-id="56bd5-216">You have configured the following:</span></span>

- <span data-ttu-id="56bd5-217">격리된 SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="56bd5-217">A SharePoint Online isolated site</span></span>
- <span data-ttu-id="56bd5-218">격리된 SharePoint Online 사이트에 Office 365 보존 레이블 할당</span><span class="sxs-lookup"><span data-stu-id="56bd5-218">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="56bd5-219">Office 365 보존 레이블에 대한 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="56bd5-219">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="56bd5-220">사이트에 저장되어 있으며 자산을 암호화하고 권한을 적용하는 가장 중요한 디지털 자산에 사용자가 적용할 수 있는 범위 지정 정책에 대한 Azure Information Protection 하위 레이블</span><span class="sxs-lookup"><span data-stu-id="56bd5-220">An Azure Information Protection sub-label of a scoped policy that users can apply to the most sensitive digital assets stored in the site that encrypts the asset and enforces permissions</span></span>
- <span data-ttu-id="56bd5-221">필요한 경우, SharePoint Online 사이트를 기준으로 하는 높은 규제 대상 데이터용 팀</span><span class="sxs-lookup"><span data-stu-id="56bd5-221">If needed, a team for highly regulated data based on the SharePoint Online site</span></span>

## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="56bd5-222">3단계: 사용자 채택 주도</span><span class="sxs-lookup"><span data-stu-id="56bd5-222">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="56bd5-p111">높은 규제 대상 데이터에 대한 SharePoint Online 사이트 또는 팀은 중요한 디지털 자산의 저장 및 액세스에 일관되게 사용되는 경우에만 해당 데이터를 보호할 수 있습니다. 이 단계에서는 사용자가 방식을 변경할 수 있으므로 가장 까다로운 단계에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-p111">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> 

<span data-ttu-id="56bd5-225">예를 들어 USB 드라이브 또는 개인 클라우드 기반 저장소 솔루션에 중요한 데이터를 저장하던 임원이 이제는 해당 데이터를 높은 규제 대상 데이터에 대한 SharePoint Online 사이트 또는 팀에만 독점적으로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-225">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="56bd5-226">1단계: 사용자 교육</span><span class="sxs-lookup"><span data-stu-id="56bd5-226">Step 1: Train your users</span></span>

<span data-ttu-id="56bd5-227">구성을 완료한 후 사이트 액세스 그룹의 구성원인 사용자 집합에게 다음을 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-227">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="56bd5-228">새 사이트 또는 팀을 사용한 귀중한 자산 보호의 중요성과 높은 규제 대상 데이터가 누출되었을 때의 결과(예: 법적 효과, 규제 벌금, 랜섬웨어 또는 경쟁적 우위 박탈)</span><span class="sxs-lookup"><span data-stu-id="56bd5-228">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="56bd5-229">사이트 및 해당 자산에 액세스하는 방법</span><span class="sxs-lookup"><span data-stu-id="56bd5-229">How to access the site and its assets.</span></span>
- <span data-ttu-id="56bd5-230">사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="56bd5-230">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="56bd5-231">DLP 정책으로 외부에서 파일을 공유하지 못하도록 차단하는 방법</span><span class="sxs-lookup"><span data-stu-id="56bd5-231">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="56bd5-232">Azure Information Protection 클라이언트를 사용하여 하위 레이블이 구성된 가장 중요한 디지털 자산에 레이블을 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="56bd5-232">How to use the Azure Information Protection client to label the most sensitive digital assets with the configured sub-label.</span></span>
- <span data-ttu-id="56bd5-233">사이트 또는 팀에서 누출된 자산을 Azure Information Protection 하위 레이블을 통해 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="56bd5-233">How the Azure Information Protection sub-label protects an asset even when it is leaked off the site or team.</span></span>

<span data-ttu-id="56bd5-234">이 교육에는 사용자가 이러한 작업 및 해당 결과를 경험해볼 수 있도록 하기 위해 실무 위주의 연습이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-234">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="56bd5-235">2단계: 정기적으로 사용 현황 및 파일 검토 수행</span><span class="sxs-lookup"><span data-stu-id="56bd5-235">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="56bd5-236">교육이 진행되고 몇 주 후에 SharePoint Online 사이트 또는 팀의 SharePoint 관리자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-236">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="56bd5-237">사이트 또는 팀의 사용 현황을 분석하고 예상 사용 현황과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-237">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="56bd5-238">매우 중요한 파일에 Azure Information Protection 하위 레이블이 적절히 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-238">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="56bd5-239">필요에 따라 사용자를 재교육합니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-239">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="56bd5-240">사용자 채택 계획</span><span class="sxs-lookup"><span data-stu-id="56bd5-240">User adoption results</span></span>

<span data-ttu-id="56bd5-241">중요한 디지털 자산은 높은 규제 대상 데이터를 위한 SharePoint Online 사이트 또는 팀에 단독으로 저장되며 가장 중요한 자산은 Azure Information Protection 하위 레이블로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-241">Sensitive digital assets are stored exclusively on SharePoint Online sites or teams for highly regulated data and that the most sensitive assets have the configured Azure Information Protection sub-label applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="56bd5-242">Contoso Corporation에서 Microsoft 365 Enterprise를 배포한 방식</span><span class="sxs-lookup"><span data-stu-id="56bd5-242">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="56bd5-243">Contoso 기업은 프랑스 파리에 본사를 둔 가상의 대표적인 글로벌 제조 대기업입니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-243">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="56bd5-244">Contoso가 파리, 모스크바, 뉴욕, 베이징, 방갈로르의 연구 팀을 위해 [보안 SharePoint Online 사이트](contoso-sharepoint-online-site-for-highly-confidential-assets.md)를 설계 및 구성한 다음 채택을 촉진하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="56bd5-244">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="56bd5-245">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56bd5-245">See also</span></span>

[<span data-ttu-id="56bd5-246">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="56bd5-246">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="56bd5-247">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="56bd5-247">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="56bd5-248">개발/테스트 환경의 보안 SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="56bd5-248">Secure SharePoint Online sites in a dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
