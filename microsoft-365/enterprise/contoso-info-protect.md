---
title: Contoso Corporation의 정보 보호
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso가 Microsoft 365의 정보 보호 기능을 사용 하 여 클라우드의 디지털 자산을 보호 하는 방법을 이해 합니다.
ms.openlocfilehash: 7cc51110a0bc4c87e57e71b2ddb42aa0dbaa288d
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558507"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="d8699-103">Contoso Corporation의 정보 보호</span><span class="sxs-lookup"><span data-stu-id="d8699-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="d8699-p101">Contoso는 정보 보안에 대해 심각 합니다. 제품 디자인 및 독점 제조 기술을 설명 하는 지적 재산의 누출 또는 파괴로 인해 경쟁 우위에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-p101">Contoso is serious about their information security. Leakage or destruction of intellectual property that describes their product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="d8699-106">Contoso는 중요 한 디지털 자산을 클라우드로 이동 하기 전에 온-프레미스 정보 분류 및 보호 요구 사항이 회사의 Microsoft 365 클라우드 기반 서비스에서 지원 되는지 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-106">Before moving their sensitive digital assets to the cloud, Contoso made sure that their on-premises information classification and protection requirements were supported by the cloud-based services of Microsoft 365 for enterprise.</span></span>

## <a name="contoso-data-security-classification"></a><span data-ttu-id="d8699-107">Contoso 데이터 보안 분류</span><span class="sxs-lookup"><span data-stu-id="d8699-107">Contoso data security classification</span></span>

<span data-ttu-id="d8699-108">Contoso는 데이터에 대 한 분석을 수행 하 고 다음과 같은 분류 수준을 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-108">Contoso performed an analysis of their data and determined the following classification levels.</span></span>

| <span data-ttu-id="d8699-109">수준 1: 기본 데이터</span><span class="sxs-lookup"><span data-stu-id="d8699-109">Level 1: Baseline</span></span> | <span data-ttu-id="d8699-110">수준 2: 중요 데이터</span><span class="sxs-lookup"><span data-stu-id="d8699-110">Level 2: Sensitive</span></span> | <span data-ttu-id="d8699-111">수준 3: 높은 규제 대상 데이터</span><span class="sxs-lookup"><span data-stu-id="d8699-111">Level 3: Highly regulated</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="d8699-112">데이터가 암호화되며 인증된 사용자에게만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-112">Data is encrypted and available only to authenticated users.</span></span><BR> <BR> <span data-ttu-id="d8699-p102">온-프레미스와 클라우드 기반 저장소 및 작업 부하에 저장 된 모든 데이터에 대해 제공 됩니다. 데이터는 서비스에 상주 하 고 서비스와 클라이언트 장치 간에 전송 되는 동안 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-p102">Provided for all data stored on-premises and in cloud-based storage and workloads. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR><span data-ttu-id="d8699-115">수준 1 데이터의 예로는 관리/영업/지원 담당자의 파일 및 일반적인 업무 관련 통신 내용(전자 메일)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-115">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="d8699-116">수준 1의 기능과 함께 높은 수준의 인증 및 데이터 손실 방지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-116">Level 1 plus strong authentication and data loss protection.</span></span><BR> <BR> <span data-ttu-id="d8699-117">강력한 인증에는 SMS 유효성 검사와 함께 Azure MFA (Multi-factor Authentication)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-117">Strong authentication includes Azure AD Multi-Factor Authentication (MFA) with SMS validation.</span></span> <span data-ttu-id="d8699-118">데이터 손실 방지는 중요 한 정보 또는 중요 한 정보가 Microsoft 클라우드 외부로 이동 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-118">Data loss prevention ensures that sensitive or critical information doesn't travel outside the Microsoft cloud.</span></span><BR><BR><span data-ttu-id="d8699-119">수준 2 데이터의 예로는 신제품 연구 개발 데이터 및 재무/법률 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-119">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="d8699-120">수준 2의 기능과 함께 최고 수준의 암호화, 인증 및 감사 기능 제공</span><span class="sxs-lookup"><span data-stu-id="d8699-120">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span><BR><BR><span data-ttu-id="d8699-121">미사용 데이터 및 클라우드의 데이터에 대해 지역별 규정을 준수하는 최고 수준의 암호화 기능이 제공되며, 스마트 카드를 사용하는 MFA와 세분화된 감사/경고 기능도 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-121">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with MFA with smart cards and granular auditing and alerting.</span></span><BR> <BR><span data-ttu-id="d8699-122">수준 3 데이터의 예로는 고객 및 파트너 개인 정보, 제품 엔지니어링 사양 및 독점 제조 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-122">Examples of Level 3 data are customer and partner personal information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contoso-information-policies"></a><span data-ttu-id="d8699-123">Contoso 정보 정책</span><span class="sxs-lookup"><span data-stu-id="d8699-123">Contoso information policies</span></span>
<span data-ttu-id="d8699-124">다음 표에는 Contoso 정보 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-124">The following table lists the Contoso information policies.</span></span>


| <span data-ttu-id="d8699-125">값</span><span class="sxs-lookup"><span data-stu-id="d8699-125">Value</span></span> | <span data-ttu-id="d8699-126">Access</span><span class="sxs-lookup"><span data-stu-id="d8699-126">Access</span></span> | <span data-ttu-id="d8699-127">데이터 보존</span><span class="sxs-lookup"><span data-stu-id="d8699-127">Data retention</span></span> | <span data-ttu-id="d8699-128">정보 보호</span><span class="sxs-lookup"><span data-stu-id="d8699-128">Information protection</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="d8699-129">비즈니스 가치가 낮은 데이터(수준 1: 기본 데이터)</span><span class="sxs-lookup"><span data-stu-id="d8699-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="d8699-130">모든 권한을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-130">Allow access to all.</span></span>  | <span data-ttu-id="d8699-131">6개월</span><span class="sxs-lookup"><span data-stu-id="d8699-131">6 months</span></span> | <span data-ttu-id="d8699-132">암호화 사용.</span><span class="sxs-lookup"><span data-stu-id="d8699-132">Use encryption.</span></span> |
| <span data-ttu-id="d8699-133">비즈니스 가치가 중간 정도인 데이터(수준 2: 중요 데이터)</span><span class="sxs-lookup"><span data-stu-id="d8699-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="d8699-134">Contoso 직원, 하도급 업자 및 파트너에 대 한 액세스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-134">Allow access to Contoso employees, subcontractors, and partners.</span></span> <BR><BR> <span data-ttu-id="d8699-135">MFA, TLS(전송 계층 보안) 및 MAM(모바일 응용 프로그램 관리) 사용.</span><span class="sxs-lookup"><span data-stu-id="d8699-135">Use MFA, Transport Layer Security (TLS), and Mobile Application Management (MAM).</span></span> | <span data-ttu-id="d8699-136">2년</span><span class="sxs-lookup"><span data-stu-id="d8699-136">2 years</span></span>  | <span data-ttu-id="d8699-137">데이터 무결성을 위해 해시 값 사용.</span><span class="sxs-lookup"><span data-stu-id="d8699-137">Use hash values for data integrity.</span></span>  |
| <span data-ttu-id="d8699-138">비즈니스 가치가 높은 데이터(수준 3: 높은 규제 대상 데이터)</span><span class="sxs-lookup"><span data-stu-id="d8699-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="d8699-139">엔지니어링/제조 부문 임원과 책임자에 대해 액세스 허용.</span><span class="sxs-lookup"><span data-stu-id="d8699-139">Allow access to executives and leads in engineering and manufacturing.</span></span> <BR> <BR> <span data-ttu-id="d8699-140">관리되는 네트워크 장치만 있는 RMS(권한 관리 시스템).</span><span class="sxs-lookup"><span data-stu-id="d8699-140">Rights Management System (RMS) with managed network devices only.</span></span>  | <span data-ttu-id="d8699-141">7년</span><span class="sxs-lookup"><span data-stu-id="d8699-141">7 years</span></span>  | <span data-ttu-id="d8699-142">거부 없음이 설정된 디지털 서명 사용.</span><span class="sxs-lookup"><span data-stu-id="d8699-142">Use digital signatures for non-repudiation.</span></span>  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a><span data-ttu-id="d8699-143">엔터프라이즈에 대 한 Microsoft 365을 사용한 정보 보호를 위한 Contoso 경로</span><span class="sxs-lookup"><span data-stu-id="d8699-143">The Contoso path to information protection with Microsoft 365 for enterprise</span></span>

<span data-ttu-id="d8699-144">Contoso는 다음 단계를 수행 하 여 정보 보호 요구 사항에 대해 Microsoft 365 for enterprise를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-144">Contoso followed these steps to prepare Microsoft 365 for enterprise for their information-protection requirements:</span></span>

1. <span data-ttu-id="d8699-145">보호할 정보 식별</span><span class="sxs-lookup"><span data-stu-id="d8699-145">Identify what information to protect</span></span>

   <span data-ttu-id="d8699-146">Contoso는 온-프레미스 SharePoint 사이트 및 파일 공유에 있는 기존의 디지털 자산을 광범위 하 게 검토 했으며 각 자산을 분류 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each asset.</span></span>

2. <span data-ttu-id="d8699-147">데이터 수준에 대 한 액세스, 보존 및 정보 보호 정책 결정</span><span class="sxs-lookup"><span data-stu-id="d8699-147">Determine access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="d8699-148">Contoso는 데이터 수준에 따라, 자세한 정책 요구 사항을 결정했습니다. 이러한 요구 사항은 기존 디지털 자산이 클라우드로 전환될 때 보호하는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="d8699-149">다양 한 정보 수준에 대 한 민감도 레이블 및 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="d8699-149">Create sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="d8699-150">Contoso는 암호화, 사용 권한 및 워터마크를 포함하여 높은 규제 대상 레이블을 사용하여 데이터 수준에 맞게 민감도 레이블을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-150">Contoso created sensitivity labels for their data levels, with their highly regulated label that includes encryption, permissions, and watermarks.</span></span>

4.  <span data-ttu-id="d8699-151">온-프레미스 SharePoint 사이트 및 파일 공유의 데이터를 새 SharePoint 사이트로 이동</span><span class="sxs-lookup"><span data-stu-id="d8699-151">Move data from on-premises SharePoint sites and file shares to their new SharePoint sites</span></span>

    <span data-ttu-id="d8699-152">새 SharePoint 사이트로 마이그레이션된 파일에는 해당 사이트에 할당된 기본 보존 레이블이 상속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-152">The files migrated to the new SharePoint sites inherited the default retention labels assigned to the site.</span></span>

5.  <span data-ttu-id="d8699-153">직원 교육 새 문서에 민감도 레이블을 사용 하는 방법, 새 SharePoint 사이트를 만들 때 Contoso IT 그룹과 상호 작용 하는 방법 및 SharePoint 사이트에 항상 디지털 자산을 저장 하는 방법</span><span class="sxs-lookup"><span data-stu-id="d8699-153">Train employees how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint sites, and to always store digital assets on SharePoint sites</span></span>

    <span data-ttu-id="d8699-154">잘못 된 작업자 정보를 변경 하는 것은 일반적으로 클라우드의 정보 보호 전환에서 가장 어려운 부분으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-154">Changing bad worker information-storage habits is often considered the hardest part of the information protection transition for the cloud.</span></span> <span data-ttu-id="d8699-155">Contoso IT 및 관리 직원은 항상 클라우드에서 디지털 자산을 레이블을 지정 및 저장 하 고, 온-프레미스 파일 공유를 사용 하지 않고, 타사 클라우드 저장소 서비스 또는 USB 드라이브를 사용 하지 않도록 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-155">Contoso IT and management needed to get employees to always label and store their digital assets in the cloud, refrain from using on-premises file shares, and not use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="d8699-156">정보 보호에 대한 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="d8699-156">Conditional Access policies for information protection</span></span>

<span data-ttu-id="d8699-157">Exchange Online 및 SharePoint 배포의 일환으로 Contoso는 다음과 같은 조건부 액세스 정책 집합을 구성 하 고 해당 그룹에 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-157">As part of their rollout of Exchange Online and SharePoint, Contoso configured the following set of Conditional Access policies and applied them to the appropriate groups:</span></span>

- [<span data-ttu-id="d8699-158">장치 정책에 대한 관리 및 비관리 응용 프로그램 액세스</span><span class="sxs-lookup"><span data-stu-id="d8699-158">Managed and unmanaged application access on devices policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="d8699-159">Exchange Online 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="d8699-159">Exchange Online access policies</span></span>](../security/office-365-security/secure-email-recommended-policies.md)
- [<span data-ttu-id="d8699-160">SharePoint 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="d8699-160">SharePoint access policies</span></span>](../security/office-365-security/sharepoint-file-access-policies.md)

<span data-ttu-id="d8699-161">정보 보호에 대 한 Contoso 정책의 결과 집합은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-161">Here's resulting set of Contoso policies for information protection.</span></span>

![장치, Exchange Online 및 SharePoint 조건부 액세스 정책](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
><span data-ttu-id="d8699-163">또한 Contoso는 ID 및 로그인에 대한 조건부 액세스 정책을 추가로 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-163">Contoso also configured additional Conditional Access policies for identity and sign-in.</span></span> <span data-ttu-id="d8699-164">[Contoso Corporation ID](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8699-164">See [Identity for the Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>
>

<span data-ttu-id="d8699-165">이러한 정책은 다음을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-165">These policies ensure that:</span></span>

- <span data-ttu-id="d8699-166">허용 되는 앱 및 조직의 데이터로 수행할 수 있는 작업은 앱 보호 정책에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-166">Apps that are allowed and the actions they can take with the organization's data are defined by app protection policies.</span></span>
- <span data-ttu-id="d8699-167">PC 및 모바일 장치는 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-167">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="d8699-168">Exchange Online은 Exchange Online에 Office 365 메시지 암호화 (OME)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-168">Exchange Online uses Office 365 message encryption (OME) for Exchange Online.</span></span>
- <span data-ttu-id="d8699-169">SharePoint에서는 앱 적용 제한을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-169">SharePoint uses app-enforced restrictions.</span></span>
- <span data-ttu-id="d8699-170">SharePoint는 브라우저 전용 액세스에 대해 액세스 제어 정책을 사용하고 관리되지 않는 장치에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-170">SharePoint uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a><span data-ttu-id="d8699-171">Microsoft 365 for enterprise 기능을 Contoso 데이터 수준으로 매핑</span><span class="sxs-lookup"><span data-stu-id="d8699-171">Mapping Microsoft 365 for enterprise features to Contoso data levels</span></span>

<span data-ttu-id="d8699-172">다음 표에는 Contoso 데이터 수준이 기업에 대 한 Microsoft 365의 정보 보호 기능에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-172">The following table maps Contoso data levels to information protection features in Microsoft 365 for enterprise.</span></span>

| <span data-ttu-id="d8699-173">수준</span><span class="sxs-lookup"><span data-stu-id="d8699-173">Level</span></span> | <span data-ttu-id="d8699-174">Microsoft 365 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="d8699-174">Microsoft 365 cloud services</span></span> | <span data-ttu-id="d8699-175">Windows 10 및 Microsoft Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="d8699-175">Windows 10 and Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="d8699-176">보안 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="d8699-176">Security and compliance</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="d8699-177">수준 1: 기본 데이터</span><span class="sxs-lookup"><span data-stu-id="d8699-177">Level 1: Baseline</span></span>  | <span data-ttu-id="d8699-178">SharePoint 및 Exchange Online 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="d8699-178">SharePoint and Exchange Online Conditional Access policies</span></span> <BR> <span data-ttu-id="d8699-179">SharePoint 사이트에 대한 권한</span><span class="sxs-lookup"><span data-stu-id="d8699-179">Permissions on SharePoint sites</span></span> | <span data-ttu-id="d8699-180">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="d8699-180">Sensitivity labels</span></span> <BR> <span data-ttu-id="d8699-181">BitLocker</span><span class="sxs-lookup"><span data-stu-id="d8699-181">BitLocker</span></span> <BR> <span data-ttu-id="d8699-182">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="d8699-182">Windows Information Protection</span></span> | <span data-ttu-id="d8699-183">장치 조건부 액세스 정책 및 모바일 응용 프로그램 관리 정책</span><span class="sxs-lookup"><span data-stu-id="d8699-183">Device Conditional Access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="d8699-184">수준 2: 중요 데이터</span><span class="sxs-lookup"><span data-stu-id="d8699-184">Level 2: Sensitive</span></span> | <span data-ttu-id="d8699-185">수준 1 추가:</span><span class="sxs-lookup"><span data-stu-id="d8699-185">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="d8699-186">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="d8699-186">Sensitivity labels</span></span> <BR> <span data-ttu-id="d8699-187">SharePoint 사이트의 Microsoft 365 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="d8699-187">Microsoft 365 retention labels on SharePoint sites</span></span> <BR> <span data-ttu-id="d8699-188">SharePoint Online 및 Exchange Online용 데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="d8699-188">Data Loss Prevention for SharePoint and Exchange Online</span></span> <BR> <span data-ttu-id="d8699-189">격리된 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="d8699-189">Isolated SharePoint sites</span></span>  | <span data-ttu-id="d8699-190">수준 1 추가:</span><span class="sxs-lookup"><span data-stu-id="d8699-190">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="d8699-191">디지털 자산의 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="d8699-191">Sensitivity labels on digital assets</span></span>  | <span data-ttu-id="d8699-192">수준 1</span><span class="sxs-lookup"><span data-stu-id="d8699-192">Level 1</span></span> |
| <span data-ttu-id="d8699-193">수준 3: 높은 규제 대상 데이터</span><span class="sxs-lookup"><span data-stu-id="d8699-193">Level 3: Highly regulated</span></span> | <span data-ttu-id="d8699-194">수준 2 추가:</span><span class="sxs-lookup"><span data-stu-id="d8699-194">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="d8699-195">거래 비밀 정보에 대 한 사용자 키 (BYOK) 암호화 및 보호</span><span class="sxs-lookup"><span data-stu-id="d8699-195">Bring your own key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="d8699-196">Microsoft 365 서비스와 상호 작용 하는 기간 업무 (lob) 응용 프로그램에 대 한 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="d8699-196">Azure Key Vault for line-of-business applications that interact with Microsoft 365 services</span></span> | <span data-ttu-id="d8699-197">수준 2</span><span class="sxs-lookup"><span data-stu-id="d8699-197">Level 2</span></span> | <span data-ttu-id="d8699-198">수준 1</span><span class="sxs-lookup"><span data-stu-id="d8699-198">Level 1</span></span> |
|||||

<span data-ttu-id="d8699-199">다음은 Contoso information protection 구성의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-199">Here's the resulting Contoso information-protection configuration.</span></span>

![Contoso의 결과 정보 보호 구성](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a><span data-ttu-id="d8699-201">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d8699-201">Next step</span></span>

<span data-ttu-id="d8699-202">Contoso에서 id 및 액세스 관리, 위협 방지, 정보 보호 및 보안 관리를 위해 [Microsoft 365의 보안 기능](contoso-security-summary.md) 을 사용 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d8699-202">Learn how Contoso uses the [security features across Microsoft 365 for enterprise](contoso-security-summary.md) for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8699-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8699-203">See also</span></span>

[<span data-ttu-id="d8699-204">보안 로드맵</span><span class="sxs-lookup"><span data-stu-id="d8699-204">Security roadmap</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[<span data-ttu-id="d8699-205">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="d8699-205">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d8699-206">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="d8699-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
