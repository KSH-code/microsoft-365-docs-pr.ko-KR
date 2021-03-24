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
description: Contoso가 엔터프라이즈용 Microsoft 365의 정보 보호 기능을 사용하여 클라우드에서 디지털 자산을 보호하는 방법을 이해합니다.
ms.openlocfilehash: 3bd778708e30253e53cc465e89f7b783141771de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051499"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="6fe21-103">Contoso Corporation의 정보 보호</span><span class="sxs-lookup"><span data-stu-id="6fe21-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="6fe21-104">Contoso는 정보 보안에 대해 심각하게 생각하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-104">Contoso is serious about their information security.</span></span> <span data-ttu-id="6fe21-105">제품 디자인 및 독점 제조 기술을 설명하는 지적 재산의 유출 또는 폐기는 경쟁적 불리한 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-105">Leakage or destruction of intellectual property that describes their product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="6fe21-106">Contoso는 중요한 디지털 자산을 클라우드로 이동하기 전에 엔터프라이즈용 Microsoft 365의 클라우드 기반 서비스에서 해당 사내 정보 분류 및 보호 요구 사항이 지원되는지 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-106">Before moving their sensitive digital assets to the cloud, Contoso made sure that their on-premises information classification and protection requirements were supported by the cloud-based services of Microsoft 365 for enterprise.</span></span>

## <a name="contoso-data-security-classification"></a><span data-ttu-id="6fe21-107">Contoso 데이터 보안 분류</span><span class="sxs-lookup"><span data-stu-id="6fe21-107">Contoso data security classification</span></span>

<span data-ttu-id="6fe21-108">Contoso는 데이터를 분석하고 다음 분류 수준을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-108">Contoso performed an analysis of their data and determined the following classification levels.</span></span>

| <span data-ttu-id="6fe21-109">수준 1: 기본 데이터</span><span class="sxs-lookup"><span data-stu-id="6fe21-109">Level 1: Baseline</span></span> | <span data-ttu-id="6fe21-110">수준 2: 중요 데이터</span><span class="sxs-lookup"><span data-stu-id="6fe21-110">Level 2: Sensitive</span></span> | <span data-ttu-id="6fe21-111">수준 3: 높은 규제 대상 데이터</span><span class="sxs-lookup"><span data-stu-id="6fe21-111">Level 3: Highly regulated</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="6fe21-112">데이터가 암호화되며 인증된 사용자에게만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-112">Data is encrypted and available only to authenticated users.</span></span><BR> <BR> <span data-ttu-id="6fe21-113">클라우드 기반 저장소 및 워크로드에 저장된 모든 데이터에 대해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-113">Provided for all data stored on-premises and in cloud-based storage and workloads.</span></span> <span data-ttu-id="6fe21-114">데이터는 서비스에 있는 동안 그리고 서비스 및 클라이언트 장치 간에 전송되는 동안 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-114">Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR><span data-ttu-id="6fe21-115">수준 1 데이터의 예로는 관리/영업/지원 담당자의 파일 및 일반적인 업무 관련 통신 내용(전자 메일)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-115">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="6fe21-116">수준 1의 기능과 함께 높은 수준의 인증 및 데이터 손실 방지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-116">Level 1 plus strong authentication and data loss protection.</span></span><BR> <BR> <span data-ttu-id="6fe21-117">강력한 인증에는 SMS 유효성 검사가 포함된 Azure AD MFA(Multi-Factor Authentication)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-117">Strong authentication includes Azure AD Multi-Factor Authentication (MFA) with SMS validation.</span></span> <span data-ttu-id="6fe21-118">데이터 손실 방지는 중요하거나 중요한 정보가 Microsoft 클라우드 외부로 이동하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-118">Data loss prevention ensures that sensitive or critical information doesn't travel outside the Microsoft cloud.</span></span><BR><BR><span data-ttu-id="6fe21-119">수준 2 데이터의 예로는 신제품 연구 개발 데이터 및 재무/법률 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-119">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="6fe21-120">수준 2의 기능과 함께 최고 수준의 암호화, 인증 및 감사 기능 제공</span><span class="sxs-lookup"><span data-stu-id="6fe21-120">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span><BR><BR><span data-ttu-id="6fe21-121">미사용 데이터 및 클라우드의 데이터에 대해 지역별 규정을 준수하는 최고 수준의 암호화 기능이 제공되며, 스마트 카드를 사용하는 MFA와 세분화된 감사/경고 기능도 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-121">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with MFA with smart cards and granular auditing and alerting.</span></span><BR> <BR><span data-ttu-id="6fe21-122">수준 3 데이터의 예로는 고객 및 파트너 개인 정보, 제품 엔지니어링 사양 및 독점 제조 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-122">Examples of Level 3 data are customer and partner personal information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contoso-information-policies"></a><span data-ttu-id="6fe21-123">Contoso 정보 정책</span><span class="sxs-lookup"><span data-stu-id="6fe21-123">Contoso information policies</span></span>
<span data-ttu-id="6fe21-124">다음 표에는 Contoso 정보 정책이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-124">The following table lists the Contoso information policies.</span></span>


| <span data-ttu-id="6fe21-125">값</span><span class="sxs-lookup"><span data-stu-id="6fe21-125">Value</span></span> | <span data-ttu-id="6fe21-126">Access</span><span class="sxs-lookup"><span data-stu-id="6fe21-126">Access</span></span> | <span data-ttu-id="6fe21-127">데이터 보존</span><span class="sxs-lookup"><span data-stu-id="6fe21-127">Data retention</span></span> | <span data-ttu-id="6fe21-128">정보 보호</span><span class="sxs-lookup"><span data-stu-id="6fe21-128">Information protection</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="6fe21-129">비즈니스 가치가 낮은 데이터(수준 1: 기본 데이터)</span><span class="sxs-lookup"><span data-stu-id="6fe21-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="6fe21-130">모두에 대한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-130">Allow access to all.</span></span>  | <span data-ttu-id="6fe21-131">6개월</span><span class="sxs-lookup"><span data-stu-id="6fe21-131">6 months</span></span> | <span data-ttu-id="6fe21-132">암호화 사용.</span><span class="sxs-lookup"><span data-stu-id="6fe21-132">Use encryption.</span></span> |
| <span data-ttu-id="6fe21-133">비즈니스 가치가 중간 정도인 데이터(수준 2: 중요 데이터)</span><span class="sxs-lookup"><span data-stu-id="6fe21-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="6fe21-134">Contoso 직원, 하도급업자 및 파트너에 대한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-134">Allow access to Contoso employees, subcontractors, and partners.</span></span> <BR><BR> <span data-ttu-id="6fe21-135">MFA, TLS(전송 계층 보안) 및 MAM(모바일 응용 프로그램 관리) 사용.</span><span class="sxs-lookup"><span data-stu-id="6fe21-135">Use MFA, Transport Layer Security (TLS), and Mobile Application Management (MAM).</span></span> | <span data-ttu-id="6fe21-136">2년</span><span class="sxs-lookup"><span data-stu-id="6fe21-136">2 years</span></span>  | <span data-ttu-id="6fe21-137">데이터 무결성을 위해 해시 값 사용.</span><span class="sxs-lookup"><span data-stu-id="6fe21-137">Use hash values for data integrity.</span></span>  |
| <span data-ttu-id="6fe21-138">비즈니스 가치가 높은 데이터(수준 3: 높은 규제 대상 데이터)</span><span class="sxs-lookup"><span data-stu-id="6fe21-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="6fe21-139">엔지니어링/제조 부문 임원과 책임자에 대해 액세스 허용.</span><span class="sxs-lookup"><span data-stu-id="6fe21-139">Allow access to executives and leads in engineering and manufacturing.</span></span> <BR> <BR> <span data-ttu-id="6fe21-140">관리되는 네트워크 장치만 있는 RMS(권한 관리 시스템).</span><span class="sxs-lookup"><span data-stu-id="6fe21-140">Rights Management System (RMS) with managed network devices only.</span></span>  | <span data-ttu-id="6fe21-141">7년</span><span class="sxs-lookup"><span data-stu-id="6fe21-141">7 years</span></span>  | <span data-ttu-id="6fe21-142">거부 없음이 설정된 디지털 서명 사용.</span><span class="sxs-lookup"><span data-stu-id="6fe21-142">Use digital signatures for non-repudiation.</span></span>  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a><span data-ttu-id="6fe21-143">엔터프라이즈용 Microsoft 365를 통해 정보 보호에 대한 Contoso 경로</span><span class="sxs-lookup"><span data-stu-id="6fe21-143">The Contoso path to information protection with Microsoft 365 for enterprise</span></span>

<span data-ttu-id="6fe21-144">Contoso는 다음 단계를 수행하여 엔터프라이즈용 Microsoft 365의 정보 보호 요구 사항을 준비했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-144">Contoso followed these steps to prepare Microsoft 365 for enterprise for their information-protection requirements:</span></span>

1. <span data-ttu-id="6fe21-145">보호할 정보 식별</span><span class="sxs-lookup"><span data-stu-id="6fe21-145">Identify what information to protect</span></span>

   <span data-ttu-id="6fe21-146">Contoso는 사내 SharePoint 사이트 및 파일 공유에 있는 기존 디지털 자산을 광범위하게 검토하고 각 자산을 분류했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each asset.</span></span>

2. <span data-ttu-id="6fe21-147">데이터 수준에 대한 액세스, 보존 및 정보 보호 정책 결정</span><span class="sxs-lookup"><span data-stu-id="6fe21-147">Determine access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="6fe21-148">Contoso는 데이터 수준에 따라, 자세한 정책 요구 사항을 결정했습니다. 이러한 요구 사항은 기존 디지털 자산이 클라우드로 전환될 때 보호하는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="6fe21-149">다양한 정보 수준에 대한 민감도 레이블 및 해당 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="6fe21-149">Create sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="6fe21-150">Contoso는 암호화, 사용 권한 및 워터마크를 포함하여 높은 규제 대상 레이블을 사용하여 데이터 수준에 맞게 민감도 레이블을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-150">Contoso created sensitivity labels for their data levels, with their highly regulated label that includes encryption, permissions, and watermarks.</span></span>

4.  <span data-ttu-id="6fe21-151">사내 SharePoint 사이트 및 파일 공유에서 새 SharePoint 사이트로 데이터 이동</span><span class="sxs-lookup"><span data-stu-id="6fe21-151">Move data from on-premises SharePoint sites and file shares to their new SharePoint sites</span></span>

    <span data-ttu-id="6fe21-152">새 SharePoint 사이트로 마이그레이션된 파일에는 해당 사이트에 할당된 기본 보존 레이블이 상속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-152">The files migrated to the new SharePoint sites inherited the default retention labels assigned to the site.</span></span>

5.  <span data-ttu-id="6fe21-153">직원에게 새 문서에 민감도 레이블을 사용하는 방법, 새 SharePoint 사이트를 만들 때 Contoso IT와 상호 작용하는 방법, 그리고 항상 SharePoint 사이트에 디지털 자산을 저장하는 방법을 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-153">Train employees how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint sites, and to always store digital assets on SharePoint sites</span></span>

    <span data-ttu-id="6fe21-154">잘못된 작업자 정보 저장 습관을 변경하는 것은 종종 클라우드의 정보 보호 전환에서 가장 어려운 부분으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-154">Changing bad worker information-storage habits is often considered the hardest part of the information protection transition for the cloud.</span></span> <span data-ttu-id="6fe21-155">Contoso IT 및 경영진은 직원들이 항상 디지털 자산에 레이블을 지정하고 클라우드에 저장하고, 사내 파일 공유를 사용하지 말고, 타사 클라우드 저장소 서비스 또는 USB 드라이브를 사용하지 못하게 하는 데 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-155">Contoso IT and management needed to get employees to always label and store their digital assets in the cloud, refrain from using on-premises file shares, and not use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="6fe21-156">정보 보호에 대한 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="6fe21-156">Conditional Access policies for information protection</span></span>

<span data-ttu-id="6fe21-157">Contoso는 Exchange Online 및 SharePoint 출시의 일환으로 다음과 같은 조건부 액세스 정책 집합을 구성하고 해당 그룹에 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-157">As part of their rollout of Exchange Online and SharePoint, Contoso configured the following set of Conditional Access policies and applied them to the appropriate groups:</span></span>

- [<span data-ttu-id="6fe21-158">장치 정책에 대한 관리 및 비관리 응용 프로그램 액세스</span><span class="sxs-lookup"><span data-stu-id="6fe21-158">Managed and unmanaged application access on devices policies</span></span>](../security/defender-365-security/identity-access-policies.md)
- [<span data-ttu-id="6fe21-159">Exchange Online 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="6fe21-159">Exchange Online access policies</span></span>](../security/defender-365-security/secure-email-recommended-policies.md)
- [<span data-ttu-id="6fe21-160">SharePoint 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="6fe21-160">SharePoint access policies</span></span>](../security/defender-365-security/sharepoint-file-access-policies.md)

<span data-ttu-id="6fe21-161">정보 보호를 위한 Contoso 정책의 결과 집합은 다음과 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-161">Here's resulting set of Contoso policies for information protection.</span></span>

![장치, Exchange Online 및 SharePoint 조건부 액세스 정책](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
><span data-ttu-id="6fe21-163">또한 Contoso는 ID 및 로그인에 대한 조건부 액세스 정책을 추가로 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-163">Contoso also configured additional Conditional Access policies for identity and sign-in.</span></span> <span data-ttu-id="6fe21-164">[Contoso Corporation ID](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fe21-164">See [Identity for the Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>
>

<span data-ttu-id="6fe21-165">이러한 정책은 다음을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-165">These policies ensure that:</span></span>

- <span data-ttu-id="6fe21-166">허용되는 앱과 조직 데이터로 수행할 수 있는 작업은 앱 보호 정책에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-166">Apps that are allowed and the actions they can take with the organization's data are defined by app protection policies.</span></span>
- <span data-ttu-id="6fe21-167">PC 및 모바일 장치는 규격이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-167">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="6fe21-168">Exchange Online에서는 Exchange Online에 OME(Office 365 메시지 암호화)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-168">Exchange Online uses Office 365 message encryption (OME) for Exchange Online.</span></span>
- <span data-ttu-id="6fe21-169">SharePoint는 앱 적용 제한을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-169">SharePoint uses app-enforced restrictions.</span></span>
- <span data-ttu-id="6fe21-170">SharePoint는 브라우저 전용 액세스에 대해 액세스 제어 정책을 사용하고 관리되지 않는 장치에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-170">SharePoint uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a><span data-ttu-id="6fe21-171">엔터프라이즈용 Microsoft 365 기능을 Contoso 데이터 수준에 매핑</span><span class="sxs-lookup"><span data-stu-id="6fe21-171">Mapping Microsoft 365 for enterprise features to Contoso data levels</span></span>

<span data-ttu-id="6fe21-172">다음 표에서는 Contoso 데이터 수준을 엔터프라이즈용 Microsoft 365의 정보 보호 기능에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-172">The following table maps Contoso data levels to information protection features in Microsoft 365 for enterprise.</span></span>

| <span data-ttu-id="6fe21-173">수준</span><span class="sxs-lookup"><span data-stu-id="6fe21-173">Level</span></span> | <span data-ttu-id="6fe21-174">Microsoft 365 클라우드 서비스</span><span class="sxs-lookup"><span data-stu-id="6fe21-174">Microsoft 365 cloud services</span></span> | <span data-ttu-id="6fe21-175">Windows 10 및 엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="6fe21-175">Windows 10 and Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="6fe21-176">보안 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="6fe21-176">Security and compliance</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="6fe21-177">수준 1: 기본 데이터</span><span class="sxs-lookup"><span data-stu-id="6fe21-177">Level 1: Baseline</span></span>  | <span data-ttu-id="6fe21-178">SharePoint 및 Exchange Online 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="6fe21-178">SharePoint and Exchange Online Conditional Access policies</span></span> <BR> <span data-ttu-id="6fe21-179">SharePoint 사이트에 대한 권한</span><span class="sxs-lookup"><span data-stu-id="6fe21-179">Permissions on SharePoint sites</span></span> | <span data-ttu-id="6fe21-180">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="6fe21-180">Sensitivity labels</span></span> <BR> <span data-ttu-id="6fe21-181">BitLocker</span><span class="sxs-lookup"><span data-stu-id="6fe21-181">BitLocker</span></span> <BR> <span data-ttu-id="6fe21-182">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="6fe21-182">Windows Information Protection</span></span> | <span data-ttu-id="6fe21-183">장치 조건부 액세스 정책 및 모바일 응용 프로그램 관리 정책</span><span class="sxs-lookup"><span data-stu-id="6fe21-183">Device Conditional Access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="6fe21-184">수준 2: 중요 데이터</span><span class="sxs-lookup"><span data-stu-id="6fe21-184">Level 2: Sensitive</span></span> | <span data-ttu-id="6fe21-185">수준 1 추가:</span><span class="sxs-lookup"><span data-stu-id="6fe21-185">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="6fe21-186">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="6fe21-186">Sensitivity labels</span></span> <BR> <span data-ttu-id="6fe21-187">SharePoint 사이트의 Microsoft 365 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="6fe21-187">Microsoft 365 retention labels on SharePoint sites</span></span> <BR> <span data-ttu-id="6fe21-188">SharePoint Online 및 Exchange Online용 데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="6fe21-188">Data Loss Prevention for SharePoint and Exchange Online</span></span> <BR> <span data-ttu-id="6fe21-189">격리된 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="6fe21-189">Isolated SharePoint sites</span></span>  | <span data-ttu-id="6fe21-190">수준 1 추가:</span><span class="sxs-lookup"><span data-stu-id="6fe21-190">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="6fe21-191">디지털 자산의 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="6fe21-191">Sensitivity labels on digital assets</span></span>  | <span data-ttu-id="6fe21-192">수준 1</span><span class="sxs-lookup"><span data-stu-id="6fe21-192">Level 1</span></span> |
| <span data-ttu-id="6fe21-193">수준 3: 높은 규제 대상 데이터</span><span class="sxs-lookup"><span data-stu-id="6fe21-193">Level 3: Highly regulated</span></span> | <span data-ttu-id="6fe21-194">수준 2 추가:</span><span class="sxs-lookup"><span data-stu-id="6fe21-194">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="6fe21-195">BYOK(Bring your own key) encryption and protection for trade secret information</span><span class="sxs-lookup"><span data-stu-id="6fe21-195">Bring your own key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="6fe21-196">Microsoft 365 서비스와 상호 작용하는 비즈니스용 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="6fe21-196">Azure Key Vault for line-of-business applications that interact with Microsoft 365 services</span></span> | <span data-ttu-id="6fe21-197">수준 2</span><span class="sxs-lookup"><span data-stu-id="6fe21-197">Level 2</span></span> | <span data-ttu-id="6fe21-198">수준 1</span><span class="sxs-lookup"><span data-stu-id="6fe21-198">Level 1</span></span> |
|||||

<span data-ttu-id="6fe21-199">결과 Contoso 정보 보호 구성은 다음과 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-199">Here's the resulting Contoso information-protection configuration.</span></span>

![Contoso의 결과 정보 보호 구성](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a><span data-ttu-id="6fe21-201">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6fe21-201">Next step</span></span>

<span data-ttu-id="6fe21-202">Contoso에서 ID 및 액세스 관리, 위협 방지, 정보 보호 및 보안 관리를 위해 [엔터프라이즈용 Microsoft 365의](contoso-security-summary.md) 보안 기능을 사용하는 방법을 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe21-202">Learn how Contoso uses the [security features across Microsoft 365 for enterprise](contoso-security-summary.md) for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fe21-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fe21-203">See also</span></span>

[<span data-ttu-id="6fe21-204">보안 로드맵</span><span class="sxs-lookup"><span data-stu-id="6fe21-204">Security roadmap</span></span>](../security/defender-365-security/security-roadmap.md)

[<span data-ttu-id="6fe21-205">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="6fe21-205">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6fe21-206">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="6fe21-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)