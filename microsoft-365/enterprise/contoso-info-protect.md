---
title: Contoso Corporation의 정보 보호
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso에서 Microsoft 365 Enterprise의 정보 보호 기능을 사용하여 클라우드에서 디지털 자산을 보호하는 방법을 이해합니다.
ms.openlocfilehash: 66ae8f4d3ddd71db593daa7b375348e71afeb2f8
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369599"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="ece05-103">Contoso Corporation의 정보 보호</span><span class="sxs-lookup"><span data-stu-id="ece05-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="ece05-104">**요약:** Contoso에서 Microsoft 365 Enterprise의 정보 보호 기능을 사용하여 클라우드에서 디지털 자산을 보호하는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-104">**Summary:** Understand how Contoso uses information protection features in Microsoft 365 Enterprise to secure their digital assets in the cloud.</span></span>

<span data-ttu-id="ece05-p101">Contoso는 정보 보안 및 보호 문제를 중요하게 생각합니다. 예를 들어, 제품 디자인 및 독점적인 제조 기법을 설명하는 지적 재산권이 누출되거나 손상되면 경쟁력이 떨어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-p101">Contoso is serious about their information security and protection. For example, leakage or destruction of their intellectual property describing product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="ece05-107">따라서 중요하고 가장 가치 있는 디지털 자산을 클라우드로 이동하기 전에, Microsoft 365 Enterprise의 클라우드 기반 서비스에서 온-프레미스 정보 분류 및 보호 요구 사항이 지원되고 구현되는지 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-107">Before moving their sensitive and most valuable digital assets to the cloud, they made sure that their on-premises information classification and protection requirements were supported and implemented in the cloud-based services of Microsoft 365 Enterprise.</span></span>

## <a name="contosos-data-security-classification"></a><span data-ttu-id="ece05-108">Contoso의 데이터 보안 분류</span><span class="sxs-lookup"><span data-stu-id="ece05-108">Contoso's data security classification</span></span>

<span data-ttu-id="ece05-109">Contoso는 데이터를 분석하고 다음과 같은 수준을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-109">Contoso performed an analysis of their data and determined the following levels.</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="ece05-110">**수준 1: 기본 데이터**</span><span class="sxs-lookup"><span data-stu-id="ece05-110">**Level 1: Baseline**</span></span> | <span data-ttu-id="ece05-111">**수준 2: 중요 데이터**</span><span class="sxs-lookup"><span data-stu-id="ece05-111">**Level 2: Sensitive**</span></span> | <span data-ttu-id="ece05-112">**수준 3: 높은 규제 대상 데이터**</span><span class="sxs-lookup"><span data-stu-id="ece05-112">**Level 3: Highly regulated**</span></span> |
| <span data-ttu-id="ece05-113">데이터가 암호화되며 인증된 사용자에게만 제공됨</span><span class="sxs-lookup"><span data-stu-id="ece05-113">Data is encrypted and available only to authenticated users</span></span> <BR> <BR> <span data-ttu-id="ece05-p102">온-프레미스 및 클라우드 기반 저장소와 작업(예: Office 365)에 저장된 모든 데이터에 대해 제공됩니다. 데이터는 서비스에 상주하는 동안, 그리고 서비스 및 클라이언트 장치 간에 전송될 때 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-p102">Provided for all data stored on premises and in cloud-based storage and workloads, such as Office 365. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR> <span data-ttu-id="ece05-116">수준 1 데이터의 예로는 관리/영업/지원 담당자의 파일 및 일반적인 업무 관련 통신 내용(전자 메일)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-116">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="ece05-117">수준 1의 기능과 함께 높은 수준의 인증 및 데이터 손실 방지 기능 제공</span><span class="sxs-lookup"><span data-stu-id="ece05-117">Level 1 plus strong authentication and data loss protection:</span></span> <BR> <BR> <span data-ttu-id="ece05-p103">높은 수준의 인증에는 SMS 유효성 검사를 통한 다단계 인증이 포함됩니다. 데이터 손실 방지 기능을 사용하면 민감하거나 중요한 정보가 온-프레미스 네트워크 외부로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-p103">Strong authentication includes multi-factor authentication with SMS validation. Data loss prevention ensures that sensitive or critical information does not travel outside the on-premises network.</span></span> <BR><BR> <span data-ttu-id="ece05-120">수준 2 데이터의 예로는 신제품 연구 개발 데이터 및 재무/법률 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-120">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="ece05-121">수준 2의 기능과 함께 최고 수준의 암호화, 인증 및 감사 기능 제공</span><span class="sxs-lookup"><span data-stu-id="ece05-121">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span> <BR> <BR>  <span data-ttu-id="ece05-122">미사용 데이터 및 클라우드의 데이터에 대해 지역별 규정을 준수하는 최고 수준의 암호화 기능이 제공되며, 스마트 카드를 사용하는 다단계 인증과 세분화된 감사/경고 기능도 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-122">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with multi-factor authentication with smart cards and granular auditing and alerting.</span></span> <BR> <BR> <span data-ttu-id="ece05-123">수준 3 데이터의 예로는 고객/파트너의 개인 식별이 가능한 정보와 제품 엔지니어링 사양 및 재산적 가치를 가지는 제조 기술 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-123">Examples of Level 3 data are customer and partner personally identifiable information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contosos-information-policies"></a><span data-ttu-id="ece05-124">Contoso의 정보 정책</span><span class="sxs-lookup"><span data-stu-id="ece05-124">Contoso's information policies</span></span>
<span data-ttu-id="ece05-125">다음 표에는 Contoso의 정보 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-125">The following table lists Contoso's information policies.</span></span>

|||||
|:-------|:-----|:-----|:-----|
|  | <span data-ttu-id="ece05-126">**액세스**</span><span class="sxs-lookup"><span data-stu-id="ece05-126">**Access**</span></span> | <span data-ttu-id="ece05-127">**데이터 보존**</span><span class="sxs-lookup"><span data-stu-id="ece05-127">**Data retention**</span></span> | <span data-ttu-id="ece05-128">**정보 보호**</span><span class="sxs-lookup"><span data-stu-id="ece05-128">**Information protection**</span></span> |
| <span data-ttu-id="ece05-129">비즈니스 가치가 낮은 데이터(수준 1: 기본 데이터)</span><span class="sxs-lookup"><span data-stu-id="ece05-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="ece05-130">모든 사용자에 대해 액세스 허용</span><span class="sxs-lookup"><span data-stu-id="ece05-130">Allow access to all</span></span>  | <span data-ttu-id="ece05-131">6개월</span><span class="sxs-lookup"><span data-stu-id="ece05-131">6 months</span></span> | <span data-ttu-id="ece05-132">암호화 사용</span><span class="sxs-lookup"><span data-stu-id="ece05-132">Use encryption</span></span> |
| <span data-ttu-id="ece05-133">비즈니스 가치가 중간 정도인 데이터(수준 2: 중요 데이터)</span><span class="sxs-lookup"><span data-stu-id="ece05-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="ece05-134">Contoso 직원, 하도급업자 및 파트너에 대해 액세스 허용</span><span class="sxs-lookup"><span data-stu-id="ece05-134">Allow access to Contoso employees, subcontractors, and partners</span></span> <BR> <BR> <span data-ttu-id="ece05-135">MFA(Multi-Factor Authentication), TLS(전송 계층 보안) 및 MAM(모바일 응용 프로그램 관리) 사용</span><span class="sxs-lookup"><span data-stu-id="ece05-135">Use multi-factor authentication (MFA), Transport Layer Security (TLS), and Mobile Application Management (MAM)</span></span> | <span data-ttu-id="ece05-136">2년</span><span class="sxs-lookup"><span data-stu-id="ece05-136">2 years</span></span>  | <span data-ttu-id="ece05-137">데이터 무결성을 위해 해시 값 사용</span><span class="sxs-lookup"><span data-stu-id="ece05-137">Use hash values for data integrity</span></span>  |
| <span data-ttu-id="ece05-138">비즈니스 가치가 높은 데이터(수준 3: 높은 규제 대상 데이터)</span><span class="sxs-lookup"><span data-stu-id="ece05-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="ece05-139">엔지니어링/제조 부문 임원과 책임자에 대해 액세스 허용</span><span class="sxs-lookup"><span data-stu-id="ece05-139">Allow access to executives and leads in engineering and manufacturing</span></span> <BR> <BR> <span data-ttu-id="ece05-140">관리되는 네트워크 장치만 있는 RMS(권한 관리 시스템)</span><span class="sxs-lookup"><span data-stu-id="ece05-140">Rights Management System (RMS) with managed network devices only</span></span>  | <span data-ttu-id="ece05-141">7년</span><span class="sxs-lookup"><span data-stu-id="ece05-141">7 years</span></span>  | <span data-ttu-id="ece05-142">거부 없음이 설정된 디지털 서명 사용</span><span class="sxs-lookup"><span data-stu-id="ece05-142">Use digital signatures for non-repudiation</span></span>  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a><span data-ttu-id="ece05-143">Microsoft 365 Enterprise를 사용한 Contoso의 정보 보호 경로</span><span class="sxs-lookup"><span data-stu-id="ece05-143">Contoso’s path to information protection with Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ece05-144">Contoso는 다음 단계를 사용하여 정보 보호 요구에 맞게 Microsoft 365 Enterprise를 준비했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-144">Contoso used the following steps to prepare Microsoft 365 Enterprise for their information protection requirements:</span></span>

1. <span data-ttu-id="ece05-145">보호할 정보 식별</span><span class="sxs-lookup"><span data-stu-id="ece05-145">Identified what information to protect</span></span>

   <span data-ttu-id="ece05-146">Contoso는 온-프레미스 SharePoint 사이트 및 파일 공유에 있는 기존의 디지털 자산을 광범위하게 검토하고 각 자산을 분류했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each one.</span></span>

2. <span data-ttu-id="ece05-147">데이터 수준에 대한 액세스, 보존 및 정보 보호 정책 결정</span><span class="sxs-lookup"><span data-stu-id="ece05-147">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="ece05-148">Contoso는 데이터 수준에 따라, 자세한 정책 요구 사항을 결정했습니다. 이러한 요구 사항은 기존 디지털 자산이 클라우드로 전환될 때 보호하는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="ece05-149">다양한 정보 수준에 대해 민감도 레이블 및 설정 생성</span><span class="sxs-lookup"><span data-stu-id="ece05-149">Created sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="ece05-150">Contoso는 암호화, 사용 권한 및 워터마크를 포함하여 중요 및 높은 규제 대상 레이블을 사용하여 데이터 수준에 맞게 민감도 레이블을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-150">Contoso created sensitivity labels for their data levels, with sensitive and highly regulated label including encryption, permissions, and watermarks.</span></span>

4. <span data-ttu-id="ece05-151">액세스를 잠그는 권한을 사용하여 중요한 데이터 및 높은 규제 대상 데이터에 대해 보호된 SharePoint Online 사이트 생성</span><span class="sxs-lookup"><span data-stu-id="ece05-151">Created protected SharePoint Online sites for sensitive and highly regulated data with permissions that lock down access</span></span>

   <span data-ttu-id="ece05-152">중요 및 높은 규제 대상 사이트 모두 [격리된 사이트](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites)로 구성되었습니다. 이러한 사이트에서는 기본 SharePoint Online 팀 사이트 권한이 Azure AD(Azure Active Directory) 그룹으로 사용자 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-152">Both sensitive and highly regulated sites were configured as [isolated sites](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites), in which the default SharePoint Online team site permissions were customized to Azure Active Directory (Azure AD) groups.</span></span> <span data-ttu-id="ece05-153">또한 중요 및 높은 규제 대상 SharePoint Online 사이트도 해당 보존 레이블로 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-153">Sensitive and highly regulated SharePoint Online sites were also configured with a corrresponding retention label.</span></span> <span data-ttu-id="ece05-154">높은 규제 대상 SharePoint Online 사이트에 저장된 파일은 높은 규제 대상 민감도 레이블로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-154">Files stored in highly regulated SharePoint Online sites are protected with the Highly Regulated sensitivity label.</span></span> <span data-ttu-id="ece05-155">자세한 내용은 [높은 규제 대상 데이터에 대한 Microsoft Teams 및 SharePoint Online 사이트](teams-sharepoint-online-sites-highly-regulated-data.md) 시나리오를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ece05-155">For more information, see the [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md) scenario.</span></span>

5.  <span data-ttu-id="ece05-156">온-프레미스 SharePoint 사이트 및 파일 공유의 데이터를 새 SharePoint Online 사이트로 이동</span><span class="sxs-lookup"><span data-stu-id="ece05-156">Moved data from on-premises SharePoint sites and file shares to their new SharePoint Online sites</span></span>

    <span data-ttu-id="ece05-157">새 SharePoint Online 사이트로 마이그레이션된 파일에는 해당 사이트에 할당된 기본 보존 레이블이 상속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-157">The files migrated to the new SharePoint Online sites inherited the default retention labels assigned to the site.</span></span>

6.  <span data-ttu-id="ece05-158">직원에게 새 문서에 대해 민감도 레이블을 사용하는 방법, 새 SharePoint Online 사이트를 만들 때 Contoso IT와 상호 작용하는 방법을 학습시키고 항상 SharePoint Online 사이트에 디지털 자산을 저장하도록 교육</span><span class="sxs-lookup"><span data-stu-id="ece05-158">Trained employees on how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint Online sites, and to always store digital assets on SharePoint Online sites</span></span>

    <span data-ttu-id="ece05-159">클라우드에 대한 정보 보호 전환에서 가장 어려운 부분을 고려하면서 Contoso IT 및 관리 부서는 조직의 직원들이 나타내는 나쁜 정보 저장 습관을 변경하여 항상 디지털 자산을 클라우드에 저장하고 레이블을 지정하도록 하고 온-프레미스 파일 공유 사용을 자제하며 제3자 클라우드 저장소 서비스 또는 USB 드라이브를 사용하지 않도록 변경해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-159">Considered the hardest part of the information protection transition for the cloud, Contoso IT and management needed to change the bad information storage habits of the organization’s employees to always store and label their digital assets in the cloud, refrain from using on-premises file shares, and never use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="ece05-160">정보 보호에 대한 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="ece05-160">Conditional access policies for information protection</span></span>

<span data-ttu-id="ece05-161">해당 ID 및 모바일 장치 관리 인프라에 따라, Exchange Online 및 SharePoint Online에 대한 롤아웃의 일환으로, Contoso는 다음과 같은 조건부 액세스 정책 집합을 구성하고 해당 Azure AD 그룹에 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-161">In conjunction with their identity and mobile device management infrastructure and as part of their rollout of Exchange Online and SharePoint Online, Contoso configured the following set of conditional access policies and applied them to the appropriate Azure AD groups:</span></span>

- [<span data-ttu-id="ece05-162">장치 정책에 대한 관리 및 비관리 응용 프로그램 액세스</span><span class="sxs-lookup"><span data-stu-id="ece05-162">Managed and unmanaged application access on devices policies</span></span>](identity-access-policies.md)
- [<span data-ttu-id="ece05-163">Exchange Online 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="ece05-163">Exchange Online access policies</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="ece05-164">SharePoint Online 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="ece05-164">SharePoint Online access policies</span></span>](sharepoint-file-access-policies.md)

<span data-ttu-id="ece05-165">그림 1에서는 Contoso의 정보 보호를 위한 정책 결과 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-165">Figure 1 shows Contoso's resulting set of policies for information protection.</span></span>

![장치, Exchange Online 및 SharePoint Online 조건부 액세스 정책](./media/contoso-info-protect/contoso-info-protect-fig1.png)

<span data-ttu-id="ece05-167">**그림 1: 장치, Exchange Online 및 SharePoint Online 조건부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="ece05-167">**Figure 1: Device, Exchange Online, and SharePoint Online conditional access policies**</span></span>
 
>[!Note]
><span data-ttu-id="ece05-p105">또한 Contoso는 ID 및 로그인에 대한 조건부 액세스 정책을 추가로 구성했습니다. [Contoso Corporation ID](contoso-identity.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ece05-p105">Contoso also configured additional conditional access policies for identity and sign-in. See [Identity for the Contoso Corporation](contoso-identity.md).</span></span>
>

<span data-ttu-id="ece05-170">이러한 정책은 다음을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-170">These policies ensure that:</span></span>

- <span data-ttu-id="ece05-171">앱 보호 정책으로 허용되는 앱과 조직 데이터로 수행할 수 있는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-171">Apps are allowed and the actions they can take with your organization data are defined by app protection policies.</span></span>
- <span data-ttu-id="ece05-172">PC 및 모바일 장치는 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-172">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="ece05-173">Exchange Online은 Exchange Online에 대해 Office 365 메시지 암호화를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-173">Exchange Online uses Office 365 message encryption for Exchange Online.</span></span>
- <span data-ttu-id="ece05-174">SharePoint Online은 앱 적용 제한을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-174">SharePoint Online uses app enforced restrictions.</span></span>
- <span data-ttu-id="ece05-175">SharePoint Online은 브라우저 전용 액세스에 대해 액세스 제어 정책을 사용하고 관리되지 않는 장치에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-175">SharePoint Online uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a><span data-ttu-id="ece05-176">Microsoft 365 Enterprise 기능을 Contoso의 데이터 수준에 매핑</span><span class="sxs-lookup"><span data-stu-id="ece05-176">Mapping Microsoft 365 Enterprise features to Contoso's data levels</span></span>

<span data-ttu-id="ece05-177">다음 표에서는 Contoso의 데이터 수준이 Microsoft 365 Enterprise의 정보 보호 기능에 어떻게 매핑되는지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ece05-177">The following table shows the mapping the Contoso's data levels to information protection features in Microsoft 365 Enterprise.</span></span>

|||||
|:-------|:-----|:-----|:-----|
| | <span data-ttu-id="ece05-178">**Office 365**</span><span class="sxs-lookup"><span data-stu-id="ece05-178">**Office 365**</span></span> | <span data-ttu-id="ece05-179">**Windows 10 및 Office 365 ProPlus**</span><span class="sxs-lookup"><span data-stu-id="ece05-179">**Windows 10 and Office 365 ProPlus**</span></span> | <span data-ttu-id="ece05-180">**EMS**</span><span class="sxs-lookup"><span data-stu-id="ece05-180">**EMS**</span></span> |
| <span data-ttu-id="ece05-181">수준 1: 기본 데이터</span><span class="sxs-lookup"><span data-stu-id="ece05-181">Level 1: Baseline</span></span>  | <span data-ttu-id="ece05-182">SharePoint Online 및 Exchange Online 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="ece05-182">SharePoint Online and Exchange Online conditional access policies</span></span> <BR> <span data-ttu-id="ece05-183">SharePoint Online 사이트에 대한 권한</span><span class="sxs-lookup"><span data-stu-id="ece05-183">Permissions on SharePoint Online sites</span></span> | <span data-ttu-id="ece05-184">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ece05-184">Sensitivity labels</span></span> <BR> <span data-ttu-id="ece05-185">BitLocker</span><span class="sxs-lookup"><span data-stu-id="ece05-185">BitLocker</span></span> <BR> <span data-ttu-id="ece05-186">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="ece05-186">Windows Information Protection</span></span> | <span data-ttu-id="ece05-187">장치 조건부 액세스 정책 및 모바일 응용 프로그램 관리 정책</span><span class="sxs-lookup"><span data-stu-id="ece05-187">Device conditional access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="ece05-188">수준 2: 중요 데이터</span><span class="sxs-lookup"><span data-stu-id="ece05-188">Level 2: Sensitive</span></span> | <span data-ttu-id="ece05-189">수준 1 추가:</span><span class="sxs-lookup"><span data-stu-id="ece05-189">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="ece05-190">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ece05-190">Sensitivity labels</span></span> <BR> <span data-ttu-id="ece05-191">SharePoint Online 사이트에 대한 Office 365 레이블</span><span class="sxs-lookup"><span data-stu-id="ece05-191">Office 365 labels on SharePoint Online sites</span></span> <BR> <span data-ttu-id="ece05-192">SharePoint Online 및 Exchange Online에 대한 Office 365 데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="ece05-192">Office 365 Data Loss Prevention for SharePoint Online and Exchange Online</span></span> <BR> <span data-ttu-id="ece05-193">격리된 SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="ece05-193">Isolated SharePoint Online sites</span></span>  | <span data-ttu-id="ece05-194">수준 1 추가:</span><span class="sxs-lookup"><span data-stu-id="ece05-194">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="ece05-195">디지털 자산의 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ece05-195">Sensitivity labels on digital assets</span></span> <BR> <span data-ttu-id="ece05-196">Office 365 고급 데이터 거버넌스</span><span class="sxs-lookup"><span data-stu-id="ece05-196">Office 365 Advanced Data Governance</span></span> | <span data-ttu-id="ece05-197">수준 1</span><span class="sxs-lookup"><span data-stu-id="ece05-197">Level 1</span></span> |
| <span data-ttu-id="ece05-198">수준 3: 높은 규제 대상 데이터</span><span class="sxs-lookup"><span data-stu-id="ece05-198">Level 3: Highly regulated</span></span> | <span data-ttu-id="ece05-199">수준 2 추가:</span><span class="sxs-lookup"><span data-stu-id="ece05-199">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="ece05-200">영업 비밀 정보에 대한 BYOK(Bring Your Own Key) 암호화 및 보호</span><span class="sxs-lookup"><span data-stu-id="ece05-200">Bring Your Own Key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="ece05-201">Office 365 서비스와 상호 작용하는 LOB(기간 업무) 응용 프로그램에 대한 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="ece05-201">Azure Key Vault for line of business applications that interact with Office 365 services</span></span> | <span data-ttu-id="ece05-202">수준 2</span><span class="sxs-lookup"><span data-stu-id="ece05-202">Level 2</span></span> | <span data-ttu-id="ece05-203">수준 1</span><span class="sxs-lookup"><span data-stu-id="ece05-203">Level 1</span></span> |
|||||


## <a name="next-step"></a><span data-ttu-id="ece05-204">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ece05-204">Next step</span></span>

<span data-ttu-id="ece05-205">Contoso에서 어떻게 액세스 관리, 위협 방지, 정보 보호 및 보안 관리를 위해 Microsoft 365 Enterprise의 보안 기능을 사용했는지 [알아봅니다](contoso-security-summary.md).</span><span class="sxs-lookup"><span data-stu-id="ece05-205">[See](contoso-security-summary.md) how Contoso has used the security features across Microsoft 365 Enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="ece05-206">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ece05-206">See also</span></span>

[<span data-ttu-id="ece05-207">Microsoft 365 Enterprise의 정보 보호</span><span class="sxs-lookup"><span data-stu-id="ece05-207">Information protection for Microsoft 365 Enterprise</span></span>](infoprotect-infrastructure.md)

[<span data-ttu-id="ece05-208">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="ece05-208">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ece05-209">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="ece05-209">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)


