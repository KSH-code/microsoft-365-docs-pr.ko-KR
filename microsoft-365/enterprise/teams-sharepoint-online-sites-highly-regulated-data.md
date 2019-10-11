---
title: 높은 규제 대상 데이터를 위한 SharePoint 사이트
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 가장 중요하고 민감한 파일을 저장할 수 있도록 안전한 SharePoint 팀 사이트를 만듭니다.
ms.openlocfilehash: dc604870826075cee645dd466b82f908e1571339
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403191"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="d4902-103">높은 규제 대상 데이터를 위한 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="d4902-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="d4902-104">*이 시나리오는 Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d4902-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d4902-p101">Microsoft 365 Enterprise에는 파일에 저장된 높은 규제 대상 데이터를 만들고, 저장하며, 보안을 설정할 수 있도록 하기 위해 전체 클라우드 기반 서비스 제품군이 포함되어 있습니다. 여기에는 다음과 같은 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="d4902-107">지역 규제를 받는 데이터</span><span class="sxs-lookup"><span data-stu-id="d4902-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="d4902-108">영업 비밀, 재무 또는 인사 관련 정보와 조직의 전략과 같이 조직에서 가장 중요한 데이터</span><span class="sxs-lookup"><span data-stu-id="d4902-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="d4902-109">이러한 비즈니스 요구를 충족하는 Microsoft 365 Enterprise 클라우드 기반 시나리오에서는 다음을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-109">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="d4902-110">SharePoint 팀 사이트에 파일(문서, 슬라이드 데크, 스프레드시트 등)을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the Files tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="d4902-111">다음 사항을 방지하기 위해 사이트를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-111">Lock down the site or team to prevent:</span></span>
  - <span data-ttu-id="d4902-112">해당 사이트에 대한 Office 365 그룹의 구성원이 아닌 사용자에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-112">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="d4902-113">사이트의 멤버가 다른 사람에게 액세스 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-113">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="d4902-114">사이트의 멤버 이외의 사용자가 다른 사람에게 액세스 권한을 요청할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="d4902-115">사용자가 조직 외부에서 파일을 보내지 못하도록 차단하기 위한 기본적인 방법으로 SharePoint 사이트에 맞게 Office 365 보존 레이블을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-115">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="d4902-116">파일을 이동하는 암호화를 사용하여 사이트에서 가장 중요한 파일을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-116">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="d4902-117">가장 중요한 파일이 사이트 외부에서 공유되더라도 파일을 열려면 권한이 있는 사용자 계정의 유효한 자격 증명이 필요하도록 해당 파일에 권한을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-117">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="d4902-118">다음 표에서는 이러한 시나리오의 요구 사항과 해당하는 Microsoft 365 Enterprise의 기능을 연결해서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-118">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="d4902-119">**요구 사항**</span><span class="sxs-lookup"><span data-stu-id="d4902-119">**Requirement**</span></span> | <span data-ttu-id="d4902-120">**Microsoft 365 Enterprise 기능**</span><span class="sxs-lookup"><span data-stu-id="d4902-120">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="d4902-121">파일 저장</span><span class="sxs-lookup"><span data-stu-id="d4902-121">Store files</span></span> | <span data-ttu-id="d4902-122">SharePoint 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="d4902-122">Sensitive SharePoint Online team sites</span></span> |
| <span data-ttu-id="d4902-123">사이트 잠그기</span><span class="sxs-lookup"><span data-stu-id="d4902-123">Lock down the site</span></span> | <span data-ttu-id="d4902-124">Azure Active Directory(Azure AD) 그룹 및 SharePoint 팀 사이트 권한</span><span class="sxs-lookup"><span data-stu-id="d4902-124">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="d4902-125">사이트 파일의 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="d4902-125">Label the digital assets of the site</span></span> | <span data-ttu-id="d4902-126">Office 365 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="d4902-126">Office 365 retention labels</span></span> |
| <span data-ttu-id="d4902-127">사용자가 조직 외부로 파일을 보내지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="d4902-127">Block users when sending files outside the organization</span></span> | <span data-ttu-id="d4902-128">Office 365의 DLP(데이터 손실 방지) 정책</span><span class="sxs-lookup"><span data-stu-id="d4902-128">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="d4902-129">사이트의 파일 모두 암호화</span><span class="sxs-lookup"><span data-stu-id="d4902-129">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="d4902-130">Office 365 민감도 하위 레이블</span><span class="sxs-lookup"><span data-stu-id="d4902-130">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="d4902-131">사이트의 파일에 권한 추가</span><span class="sxs-lookup"><span data-stu-id="d4902-131">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="d4902-132">Office 365 민감도 하위 레이블</span><span class="sxs-lookup"><span data-stu-id="d4902-132">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="d4902-133">다음은 보안 SharePoint 사이트의 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-133">Here is the configuration for a SharePoint Online site.</span></span>

![높은 규제 대상 데이터를 위한 SharePoint 사이트 시나리오](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="d4902-135">이 시나리오를 사용하려면 다음을 배포했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-135">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="d4902-136">기본 인프라의 [ID](identity-infrastructure.md) 단계 및 [정보 보호](infoprotect-infrastructure.md) 단계의 1-2단계</span><span class="sxs-lookup"><span data-stu-id="d4902-136">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="d4902-137">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="d4902-137">SharePoint</span></span>

<span data-ttu-id="d4902-138">다음 단계에서는 높은 규제 대상 데이터를 위한 SharePoint 사이트의 디자인 및 구성 작업과 채택을 유도하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-138">The following phases step you through designing, configuring, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="d4902-139">가상의 대표적인 다국적 기업인 Contoso Corporation에서 연구팀을 위해 SharePoint 사이트를 설계한 방법을 보려면 이 [예제 구성](contoso-sharepoint-online-site-for-highly-confidential-assets.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4902-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="d4902-140">ID 및 장치 액세스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d4902-140">Identity and device access prerequisites</span></span>

<span data-ttu-id="d4902-141">SharePoint 사이트에 대한 액세스를 보호하려면 [ID 및 장치 액세스 정책](identity-access-policies.md) 및 [권장 SharePoint 액세스 정책](sharepoint-file-access-policies.md)을 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-141">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="d4902-142">1단계: 디자인</span><span class="sxs-lookup"><span data-stu-id="d4902-142">Phase 1: Design</span></span>

<span data-ttu-id="d4902-143">높은 규제 대상 데이터에 적합한 SharePoint 사이트를 만들려면 먼저 해당 용도를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-143">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="d4902-144">예를 들어, 제조 조직의 연구 및 개발 부서에는 기존 제품에 대해 현재 설계 사양을 저장할 수 있는 SharePoint 사이트와 새 제품에 대해 공동 작업할 수 있는 장소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-144">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span> <span data-ttu-id="d4902-145">연구 & 개발 부서의 구성원과 선택된 임원만 해당 사이트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-145">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="d4902-146">그 용도는 다음과 같은 필수 구성 항목을 파악하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-146">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="d4902-147">사이트의 문서 부분에 할당할 Office 365 보존 레이블 및 해당 레이블의 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="d4902-147">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="d4902-148">사이트에 저장된 중요한 파일에 적용하는 Office 365 민감도 하위 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="d4902-148">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="d4902-149">일단 결정이 끝나면 이러한 설정을 사용하여 두 번째 작업 단계에서 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-149">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="d4902-150">1단계: Office 365 보존 레이블 및 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="d4902-150">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="d4902-151">SharePoint 팀 사이트의 문서 부분에 적용된 Office 365 보존 레이블은 사이트에 저장된 모든 파일에 대한 기본 분류 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-151">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="d4902-152">높은 규제 대상 데이터를 위한 SharePoint 사이트에서는 사용할 Office 보존 365 레이블을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-152">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="d4902-153">Office 365 레이블의 디자인 고려 사항에 대해서는 [Office 365 분류 및 레이블](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4902-153">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="d4902-p103">중요한 정보를 보호하고 우발적이거나 의도적인 노출을 방지하려면 DLP 정책을 사용합니다. 자세한 내용은 이 [개요](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4902-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="d4902-156">SharePoint 사이트의 경우, 사용자가 외부 사용자와 파일을 공유하려고 할 때 사용자를 차단하도록 사이트에 할당된 Office 365 보존 레이블에 대한 DLP 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-156">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="d4902-157">2단계: Office 365 민감도 하위 레이블</span><span class="sxs-lookup"><span data-stu-id="d4902-157">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="d4902-158">가장 중요한 파일에 암호화 및 권한 집합을 사용하려면 Office 365 민감도 하위 레이블을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-158">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="d4902-159">하위 레이블은 기존 레이블 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-159">A sublabel exists under an existing label.</span></span> <span data-ttu-id="d4902-160">예를 들어, 높은 규제 대상 레이블 아래에 연구 및 개발 하위 레이블을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-160">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="d4902-161">높은 규제 대상 데이터를 위한 SharePoint 사이트의 경우, 사이트 구성원만 해당 레이블이 지정된 파일을 열고 변경할 수 있도록 권한을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-161">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="d4902-162">적용된 하위 레이블은 파일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-162">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="d4902-163">파일이 사이트 외부로 누출되는 경우에도 권한이 있는 인증된 사용자 계정만 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-163">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="d4902-164">디자인 결과</span><span class="sxs-lookup"><span data-stu-id="d4902-164">Design results</span></span>

<span data-ttu-id="d4902-165">다음 사항이 결정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-165">You have determined the following:</span></span>

- <span data-ttu-id="d4902-166">해당 Office 365 보존 레이블 및 레이블과 연결된 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="d4902-166">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="d4902-167">암호화 및 사용 권한을 포함하는 Office 365 민감도 하위 레이블의 설정</span><span class="sxs-lookup"><span data-stu-id="d4902-167">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="d4902-168">2단계: 구성</span><span class="sxs-lookup"><span data-stu-id="d4902-168">Phase 2: Configure</span></span>

<span data-ttu-id="d4902-169">두 번째 작업 단계에서는 첫 번째 작업 단계에서 결정한 설정을 구현하여 높은 규제 대상 데이터에 대한 SharePoint 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-169">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="d4902-170">1단계: 해당하는 Office 365 그룹의 소유자와 구성원과 함께 개인용 SharePoint 팀 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="d4902-170">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="d4902-171">개인용 SharePoint 팀 사이트를 만들려면 [이 지침]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-171">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="d4902-172">2단계: SharePoint 팀 사이트에 대한 추가 사용 권한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="d4902-172">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="d4902-173">SharePoint 사이트에서 사용 권한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-173">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="d4902-174">도구 모음에서 설정 아이콘을 클릭한 다음, **사이트 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-174">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="d4902-175">**사이트 권한** 창에서 **고급 권한 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="d4902-176">브라우저의 새 **권한** 탭에서 **액세스 요청 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-176">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="d4902-177">**액세스 요청 설정** 대화 상자에서 **구성원이 사이트와 개별 파일 및 폴더를 공유할 수 있도록 허용합니다.** 및 **액세스 요청 허용**(3개의 확인란이 모두 선택 취소됨)을 선택 취소하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-177">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="d4902-178">이 설정을 사용하는 경우, 사이트 그룹 구성원이 다른 구성원과 사이트를 공유하거나 구성원이 아닌 사용자가 해당 사이트의 액세스를 요청할 수 있는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-178">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="d4902-179">3단계: Office 365 보존 레이블에 맞게 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="d4902-179">Step 2: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="d4902-180">[Office 365 레이블 및 DLP를 사용하여 SharePoint 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)의 지침에 따라 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-180">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="d4902-181">필요한 경우, 높은 규제 대상 데이터에 대한 보존 레이블을 만들고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-181">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="d4902-182">1단계에서 만든 보존 레이블에 맞게 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-182">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="d4902-183">2단계에서 만든 보존 레이블을 사용하고 사용자가 조직 외부에서 파일을 전송하지 못하도록 높은 규제 대상 데이터에 대한 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-183">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="d4902-184">4단계: 사이트의 Office 365 민감도 하위 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="d4902-184">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="d4902-185">모든 사용자가 모든 파일에 적용할 수 있는 높은 규제 대상 데이터의 민감도 레이블과 달리, 하위 레이블이 지정된 파일이 다음을 수행하려면 보안 사이트에 고유한 레이블이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-185">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="d4902-186">암호화되고 해당 암호화가 파일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-186">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="d4902-187">사이트 그룹의 구성원만 파일을 열 수 있도록 사용자 지정 권한을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-187">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="d4902-188">사이트에 저장된 파일에 보안 수준을 추가적으로 설정하려면, 높은 규제 대상 파일에 대한 일반적인 레이블의 하위 레이블인 새 민감도 레이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-188">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="d4902-189">사이트의 그룹 구성원만 높은 규제 대상 레이블의 하위 레이블 목록에서 이 레이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-189">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="d4902-190">[여기](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)에 있는 지침을 참조하여 높은 규제 대상 데이터에 사용할 레이블의 하위 레이블을 다음과 같은 설정으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-190">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="d4902-191">파일에 하위 레이블을 지정할 때 쉽게 연상할 수 있도록 하위 레이블 이름에 사이트 이름을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-191">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="d4902-192">암호화가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-192">Encryption is enabled.</span></span>
- <span data-ttu-id="d4902-193">사이트 그룹에 공동 작성자 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-193">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="d4902-194">구성 결과</span><span class="sxs-lookup"><span data-stu-id="d4902-194">Configuration results</span></span>

<span data-ttu-id="d4902-195">구성한 항목</span><span class="sxs-lookup"><span data-stu-id="d4902-195">You have configured the following:</span></span>

- <span data-ttu-id="d4902-196">SharePoint 사이트에 더 제한적인 사용 권한 설정</span><span class="sxs-lookup"><span data-stu-id="d4902-196">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="d4902-197">SharePoint 사이트의 문서 부분에 할당된 Office 365 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="d4902-197">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="d4902-198">Office 365 보존 레이블에 대한 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="d4902-198">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="d4902-199">파일을 암호화하고 팀 사이트 그룹의 구성원만 공동 작성자 액세스 권한이 있는 사이트에 저장된 가장 중요한 파일에 적용할 수 있는 Office 365 하위 레이블</span><span class="sxs-lookup"><span data-stu-id="d4902-199">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="d4902-200">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-200">Here is the resulting configuration.</span></span>

![높은 규제 대상 데이터를 위한 SharePoint 사이트 시나리오](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="d4902-202">다음은 해당 사이트에 저장된 파일에 민감도 하위 레이블을 적용한 사용자의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-202">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![높은 규제 대상 데이터를 위한 SharePoint 사이트 시나리오](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="d4902-204">3단계: 사용자 채택 주도</span><span class="sxs-lookup"><span data-stu-id="d4902-204">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="d4902-205">중요한 파일을 저장하고 액세스하는 데 지속적으로 사용되는 경우 높은 규제 대상 데이터의 SharePoint 사이트에서 해당 데이터만 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-205">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> <span data-ttu-id="d4902-206">사용자가 습관과 선호 사항을 변경해야 하므로 가장 어려운 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-206">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="d4902-207">예를 들어, 중요한 파일을 USB 드라이브나 개인 클라우드 기반 스토리지 솔루션에 저장하는 데 익숙한 직원이 이제는 높은 규제 대상 데이터에 적합한 SharePoint 사이트에만 해당 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-207">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="d4902-208">1단계: 사용자 교육</span><span class="sxs-lookup"><span data-stu-id="d4902-208">Step 1: Train your users</span></span>

<span data-ttu-id="d4902-209">구성을 완료한 후 사이트 액세스 그룹의 구성원인 사용자 집합에게 다음을 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-209">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="d4902-210">새 사이트를 사용하여 중요한 파일을 보호해야 하는 중요성 및 높은 규제 대상 데이터 누출 결과(예: 법적 영향, 규제 벌금, 랜섬웨어 또는 경쟁적 우위 박탈)</span><span class="sxs-lookup"><span data-stu-id="d4902-210">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="d4902-211">사이트 및 해당 파일에 액세스하는 방법</span><span class="sxs-lookup"><span data-stu-id="d4902-211">How to access the site and its assets.</span></span>
- <span data-ttu-id="d4902-212">사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="d4902-212">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="d4902-213">DLP 정책으로 외부에서 파일을 공유하지 못하도록 차단하는 방법</span><span class="sxs-lookup"><span data-stu-id="d4902-213">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="d4902-214">사이트의 하위 레이블을 사용하여 가장 중요한 파일의 레이블을 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="d4902-214">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="d4902-215">파일이 사이트 외부로 누출된 경우에도 하위 레이블이 파일을 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="d4902-215">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="d4902-216">이 교육에는 사용자가 이러한 작업 및 해당 결과를 경험해볼 수 있도록 하기 위해 실무 위주의 연습이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-216">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="d4902-217">2단계: 정기적으로 사용 현황 및 파일 검토 수행</span><span class="sxs-lookup"><span data-stu-id="d4902-217">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="d4902-218">교육이 진행되고 몇 주 후에 SharePoint 사이트의 SharePoint 관리자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-218">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="d4902-219">사이트의 사용 현황을 분석하고 예상 사용 현황과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="d4902-220">매우 중요한 파일의 레이블이 민감도 하위 레이블로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="d4902-221">필요에 따라 사용자를 재교육합니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-221">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="d4902-222">사용자 채택 계획</span><span class="sxs-lookup"><span data-stu-id="d4902-222">User adoption results</span></span>

<span data-ttu-id="d4902-223">높은 규제 대상 파일이 높은 규제 대상 데이터를 위한 SharePoint 사이트에만 저장되고 가장 중요한 파일에 해당 사이트의 민감도 하위 레이블이 적용되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-223">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="d4902-224">Contoso Corporation에서 Microsoft 365 Enterprise를 배포한 방식</span><span class="sxs-lookup"><span data-stu-id="d4902-224">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d4902-225">Contoso 기업은 프랑스 파리에 본사를 둔 가상의 대표적인 글로벌 제조 대기업입니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-225">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="d4902-226">Contoso가 파리, 모스크바, 뉴욕, 베이징, 방갈로르의 연구 팀을 위해 [보안 SharePoint 사이트](contoso-sharepoint-online-site-for-highly-confidential-assets.md)를 설계 및 구성한 다음 채택을 촉진하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d4902-226">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="d4902-227">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4902-227">See also</span></span>

[<span data-ttu-id="d4902-228">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="d4902-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d4902-229">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="d4902-229">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

