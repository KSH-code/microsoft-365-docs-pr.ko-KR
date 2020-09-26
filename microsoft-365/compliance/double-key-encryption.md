---
title: DKE (이중 암호화)
description: DKE를 사용 하면 중요 한 데이터를 보호 하 고 키에 대 한 모든 권한을 유지할 수 있습니다.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 39d7933014f1dc71f8c94e467954d36ede4fb451
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277535"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="2de33-103">Microsoft 365에 대 한 이중 키 암호화</span><span class="sxs-lookup"><span data-stu-id="2de33-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="2de33-104">*적용 대상: Microsoft 365, [microsoft 365 준수](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection) 에 대 한 이중 암호화*</span><span class="sxs-lookup"><span data-stu-id="2de33-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="2de33-105">*지침: [Azure Information Protection 통합 레이블 클라이언트 Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="2de33-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="2de33-106">*서비스 설명: [Microsoft 365 준수](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="2de33-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="2de33-107">DKE (이중 암호화)에서는 보호 된 콘텐츠에 액세스 하기 위해 두 개의 키를 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="2de33-108">Microsoft는 Microsoft Azure에 하나의 키를 저장 하 고 다른 키를 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="2de33-109">이중 키 암호화 서비스를 사용 하 여 키 중 하나에 대 한 모든 권한을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="2de33-110">중요 한 콘텐츠에 대 한 Azure Information Protection 통합 레이블 클라이언트를 사용 하 여 보호를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="2de33-111">이중 키 암호화는 클라우드 및 온-프레미스 배포를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="2de33-112">이러한 배포를 통해 보호 된 데이터를 저장할 때마다 암호화 된 데이터를 불투명 하 게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="2de33-113">클라우드 기반 테 넌 트 루트 키의 기본에 대 한 자세한 내용은 [Azure Information Protection 테 넌 트 키 계획 및 구현](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2de33-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="2de33-114">조직에서 DKE를 채택 해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="2de33-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="2de33-115">이중 키 암호화는 strictest 보호 요구 사항을 적용 하는 가장 중요 한 데이터를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="2de33-116">모든 데이터에 대 한 DKE가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-116">DKE is not intended for all data.</span></span> <span data-ttu-id="2de33-117">일반적으로는 전체 데이터의 극히 작은 부분만 보호 하기 위해 이중 암호화를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-117">In general, you'll be using Double Key Encryption to protect only a very small part of your overall data.</span></span> <span data-ttu-id="2de33-118">배포 하기 전에이 솔루션에 대 한 올바른 데이터를 식별 하기 위해 주의을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="2de33-119">경우에 따라 Microsoft에서 관리 하는 키를 사용 하거나 확인을 통해 Microsoft 정보 보호 같은 대부분의 데이터에 대해 범위를 좁히고 다른 솔루션을 사용 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-119">In some cases, you might need to narrow your scope and make use of other solutions for the majority of your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="2de33-120">이러한 솔루션은 보호 및 규정 요구 사항이 향상 되지 않는 문서에도 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="2de33-121">또한 이러한 솔루션을 사용 하면 가장 강력한 Office 365 서비스를 사용할 수 있습니다. DKE 암호화 된 콘텐츠와 함께 사용할 수 없는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="2de33-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-122">For example:</span></span>

- <span data-ttu-id="2de33-123">첨부 파일에 대 한 표시가 필요한 맬웨어 방지 및 스팸을 비롯 한 전송 규칙</span><span class="sxs-lookup"><span data-stu-id="2de33-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="2de33-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="2de33-124">Microsoft Delve</span></span>
- <span data-ttu-id="2de33-125">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2de33-125">eDiscovery</span></span>
- <span data-ttu-id="2de33-126">콘텐츠 검색 및 인덱싱</span><span class="sxs-lookup"><span data-stu-id="2de33-126">Content search and indexing</span></span>
- <span data-ttu-id="2de33-127">공동 작성 기능을 포함 하는 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="2de33-127">Office Web Apps including co-authoring functionality</span></span>

<span data-ttu-id="2de33-128">밉 SDK를 통해 DKE와 통합 되지 않은 모든 외부 응용 프로그램이 나 서비스는 암호화 된 데이터에 대 한 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="2de33-129">Microsoft Information Protection SDK 1.7 +에서는 이중 키 암호화를 지원 합니다. SDK와 통합 되는 응용 프로그램은 충분 한 사용 권한 및 통합을 포함 하 여이 데이터를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="2de33-130">조직에서는 Microsoft 정보 보호 기능 (분류 및 레이블 지정)을 사용 하 여 중요 한 데이터를 대부분 보호 하 고 업무상 중요 한 데이터에 대해 DKE를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="2de33-131">이중 키 암호화는 금융 서비스 및 의료 같은 고도로 규제 된 업계에서 매우 중요 한 데이터에 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-131">Double Key Encryption is particularly relevant for extremely sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="2de33-132">조직에 다음과 같은 요구 사항이 있는 경우 DKE를 사용 하 여 콘텐츠를 안전 하 게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="2de33-133">모든 상황에서 보호 된 콘텐츠의 암호를 *해독할 수 있도록* 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="2de33-134">Microsoft가 보호 된 데이터에 자체 액세스 하지 못하도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="2de33-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="2de33-135">지리적 경계 내에 키를 포함 하기 위한 규정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="2de33-136">데이터 암호화 및 암호 해독을 위해 보유 하는 모든 키가 데이터 센터에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="2de33-137">DKE에 대 한 시스템 및 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2de33-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="2de33-138">**Microsoft 365에 대 한 이중 키 암호화** 는 Microsoft 365 E5와 Office 365 E5와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="2de33-139">Microsoft 365 E5 라이선스가 없는 경우 [평가판](https://aka.ms/M365E5ComplianceTrial)에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="2de33-140">이러한 라이선스에 대 한 자세한 내용은 [보안 & 준수에 대 한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2de33-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="2de33-141">**Azure Information Protection**</span><span class="sxs-lookup"><span data-stu-id="2de33-141">**Azure Information Protection**.</span></span> <span data-ttu-id="2de33-142">DKE는 민감도 레이블에서 작동 하며 Azure Information Protection을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="2de33-143">최종 사용자는 Office 데스크톱 앱의 민감도 리본 메뉴를 통해 DKE 민감도 레이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-143">DKE sensitivity labels are made available to end-users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="2de33-144">보호 된 문서를 보호 하 고 사용 하려는 각 클라이언트 컴퓨터에 이러한 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="2de33-145">Windows에서 엔터프라이즈 버전 \* 12711 이상 (데스크톱 버전의 Word, PowerPoint 및 Excel) **용 Microsoft Office 앱**</span><span class="sxs-lookup"><span data-stu-id="2de33-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="2de33-146">**Azure Information Protection 통합 레이블 클라이언트** 버전 2.7.93.0 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="2de33-147">[Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=53018)에서 통합 레이블 클라이언트를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="2de33-148">DKE로 보호 된 콘텐츠를 저장 하 고 보기 위한 지원 되는 환경</span><span class="sxs-lookup"><span data-stu-id="2de33-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="2de33-149">**지원 되는 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="2de33-149">**Supported applications**.</span></span> <span data-ttu-id="2de33-150">Word, Excel 및 PowerPoint를 포함 하는 Windows의 [엔터프라이즈 클라이언트용 Microsoft 365 앱](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)</span><span class="sxs-lookup"><span data-stu-id="2de33-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="2de33-151">**온라인 콘텐츠 지원**</span><span class="sxs-lookup"><span data-stu-id="2de33-151">**Online content support**.</span></span> <span data-ttu-id="2de33-152">Microsoft SharePoint 및 비즈니스용 OneDrive에 모두 온라인으로 저장 된 문서 및 파일을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="2de33-153">전자 메일로 암호화 된 콘텐츠를 공유할 수 있지만 암호화 된 문서 및 파일은 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="2de33-154">대신 로컬 컴퓨터의 데스크톱 앱을 사용 하 여 보호 된 콘텐츠를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="2de33-155">DKE 배포 개요</span><span class="sxs-lookup"><span data-stu-id="2de33-155">Overview of deploying DKE</span></span>

<span data-ttu-id="2de33-156">이러한 일반적인 단계를 수행 하 여 DKE를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="2de33-157">이러한 단계를 완료 하면 최종 사용자가 이중 암호화로 중요 한 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-157">Once you've completed these steps, your end users will be able to protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="2de33-158">이 문서에 설명 된 대로 DKE 서비스를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="2de33-159">이중 키 암호화를 사용 하 여 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="2de33-160">[Microsoft 365 준수 센터](https://compliance.microsoft.com) 아래의 정보 보호로 이동한 후 이중 키 암호화로 새 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="2de33-161">[암호화를 적용 하려면 민감도 레이블을 사용 하 여 콘텐츠에 대 한 액세스 제한](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2de33-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="2de33-162">이중 키 암호화 레이블을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="2de33-163">Microsoft Office의 민감도 리본 메뉴에서 암호화 된 이중 키 레이블을 선택 하 여 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="2de33-164">몇 가지 단계를 완료 하 여 이중 암호화를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="2de33-165">이 문서에서는 숙련 된 관리자가 서비스를 성공적으로 배포 하는 데 필요한 자세한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="2de33-166">이렇게 하는 것이 어려우면 사용자가 직접 메서드를 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="2de33-167">DKE 배포</span><span class="sxs-lookup"><span data-stu-id="2de33-167">Deploy DKE</span></span>

<span data-ttu-id="2de33-168">이 문서와 배포 동영상은 Azure를 DKE 서비스의 배포 대상으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="2de33-169">다른 위치에 배포 하는 경우에는 고유한 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="2de33-170">[이중 키 암호화 배포 비디오](https://youtu.be/vDWfHN_kygg) 를 시청 하 여이 문서의 개념에 대 한 단계별 개요를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="2de33-171">완료 하는 데 약 18 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="2de33-172">이러한 일반적인 단계를 수행 하 여 조직에 대 한 이중 암호화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="2de33-173">DKE 서비스에 대 한 소프트웨어 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="2de33-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="2de33-174">이중 키 암호화 GitHub 리포지토리 복제</span><span class="sxs-lookup"><span data-stu-id="2de33-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="2de33-175">응용 프로그램 설정 수정</span><span class="sxs-lookup"><span data-stu-id="2de33-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="2de33-176">테스트 키 생성</span><span class="sxs-lookup"><span data-stu-id="2de33-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="2de33-177">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="2de33-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="2de33-178">DKE 서비스 배포 및 키 저장소 게시</span><span class="sxs-lookup"><span data-stu-id="2de33-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="2de33-179">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2de33-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="2de33-180">키 저장소 등록</span><span class="sxs-lookup"><span data-stu-id="2de33-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="2de33-181">DKE을 사용 하 여 민감도 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="2de33-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="2de33-182">클라이언트에서 DKE 사용</span><span class="sxs-lookup"><span data-stu-id="2de33-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="2de33-183">HYOK 레이블에서 보호 된 파일을 DKE 레이블로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2de33-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="2de33-184">작업이 완료 되 면 DKE을 사용 하 여 문서와 파일을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="2de33-185">자세한 내용은 [Office에서 파일 및 전자 메일에 민감도 레이블 적용](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2de33-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="2de33-186">DKE 서비스에 대 한 소프트웨어 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="2de33-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="2de33-187">DKE 서비스를 설치 하려는 컴퓨터에 이러한 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="2de33-188">**.Net Core 3.1 SDK**</span><span class="sxs-lookup"><span data-stu-id="2de33-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="2de33-189">[.Net Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)에서 SDK를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="2de33-190">**Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="2de33-190">**Visual Studio Code**.</span></span> <span data-ttu-id="2de33-191">Visual Studio Code from을 다운로드 [https://code.visualstudio.com/](https://code.visualstudio.com) 하세요.</span><span class="sxs-lookup"><span data-stu-id="2de33-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="2de33-192">설치가 완료 되 면 Visual Studio Code를 실행 하 고 Extensions **보기** 를 선택 \> **Extensions**합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="2de33-193">이러한 확장을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-193">Install these extensions.</span></span>

- <span data-ttu-id="2de33-194">Visual Studio 코드용 c # 코드</span><span class="sxs-lookup"><span data-stu-id="2de33-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="2de33-195">NuGet 패키지 관리자</span><span class="sxs-lookup"><span data-stu-id="2de33-195">NuGet Package Manager</span></span>

<span data-ttu-id="2de33-196">**Git 리소스**</span><span class="sxs-lookup"><span data-stu-id="2de33-196">**Git resources**.</span></span> <span data-ttu-id="2de33-197">다음 중 하나를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="2de33-198">Git</span><span class="sxs-lookup"><span data-stu-id="2de33-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="2de33-199">GitHub 데스크톱</span><span class="sxs-lookup"><span data-stu-id="2de33-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="2de33-200">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="2de33-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="2de33-201">**OpenSSL** DKE를 배포한 후 [테스트 키를 생성](#generate-test-keys) 하려면 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) 이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="2de33-202">환경 변수 경로에서 올바르게 호출 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="2de33-203">예를 들어 자세한 내용은 "설치 디렉터리를 PATH에 추가 합니다."를 참조 하십시오 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) .</span><span class="sxs-lookup"><span data-stu-id="2de33-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="2de33-204">DKE GitHub 리포지토리 복제</span><span class="sxs-lookup"><span data-stu-id="2de33-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="2de33-205">Microsoft는 GitHub 리포지토리에 DKE 원본 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="2de33-206">조직의 사용을 위해 로컬로 프로젝트를 빌드하기 위해 리포지토리를 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="2de33-207">DKE GitHub 리포지토리는에 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="2de33-208">다음 지침은 inexperienced git 또는 Visual Studio Code 사용자에 게 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="2de33-209">브라우저에서:로 이동 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="2de33-210">화면 오른쪽 방향으로 **코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="2de33-211">사용자의 UI 버전에 **복제 또는 다운로드** 단추가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="2de33-212">그런 다음 표시 되는 드롭다운 목록에서 복사 아이콘을 선택 하 여 클립보드에 URL을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="2de33-213">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-213">For example:</span></span>

   ![GitHub에서 이중 키 암호화 서비스 리포지토리 복제](../media/dke-clone.png)

3. <span data-ttu-id="2de33-215">Visual Studio Code에서 **View** \> **명령 색상표** 보기를 선택 하 고 **Git: 클론**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="2de33-216">목록에서 옵션으로 이동 하려면 입력을 시작 하 여 `git: clone` 항목을 필터링 한 다음 드롭다운에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="2de33-217">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-217">For example:</span></span>

   ![Visual Studio Code GIT: Clone 옵션](../media/dke-vscode-clone.png)

4. <span data-ttu-id="2de33-219">Git에서 복사한 URL을 텍스트 상자에 붙여넣고 **GitHub에서 복제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="2de33-220">**폴더 선택** 대화 상자가 나타나면 저장소를 저장할 위치를 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="2de33-221">프롬프트에서 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="2de33-222">Visual Studio Code에서 리포지토리가 열리고 왼쪽 아래에 현재 Git 분기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="2de33-223">분기는 **마스터**여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-223">The branch should be **master**.</span></span>

    <span data-ttu-id="2de33-224">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-224">For example:</span></span>

   ![Visual Studio 코드 마스터 분기](../media/dke-vscode-master.png)

6. <span data-ttu-id="2de33-226">분기 목록에서 word **마스터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-226">Select the word **master** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2de33-227">Master 분기를 선택 하면 프로젝트를 빌드하는 데 올바른 파일이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-227">Selecting the master branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="2de33-228">올바른 분기를 선택 하지 않으면 배포가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-228">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="2de33-229">이제 DKE 원본 리포지토리가 로컬로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-229">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="2de33-230">다음으로, 조직의 [응용 프로그램 설정을 수정](#modify-application-settings) 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-230">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="2de33-231">응용 프로그램 설정 수정</span><span class="sxs-lookup"><span data-stu-id="2de33-231">Modify application settings</span></span>

<span data-ttu-id="2de33-232">DKE 서비스를 배포 하려면 다음 유형의 응용 프로그램 설정을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-232">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="2de33-233">키 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="2de33-233">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="2de33-234">테 넌 트 및 키 설정</span><span class="sxs-lookup"><span data-stu-id="2de33-234">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="2de33-235">파일의 appsettings.js에서 응용 프로그램 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-235">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="2de33-236">이 파일은 DoubleKeyEncryptionService\src\customer-key-store.에서 로컬로 복제 한 DoubleKeyEncryptionService 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-236">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="2de33-237">예를 들어 Visual Studio Code에서는 다음 그림과 같이 파일을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-237">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![DKE 용 파일에서 appsettings.js찾기](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="2de33-239">키 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="2de33-239">Key access settings</span></span>

<span data-ttu-id="2de33-240">전자 메일 또는 역할 인증을 사용할지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-240">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="2de33-241">DKE에서는 이러한 인증 방법 중 하나를 한 번에 하나만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-241">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="2de33-242">**전자 메일 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="2de33-242">**Email authorization**.</span></span> <span data-ttu-id="2de33-243">조직에서 전자 메일 주소만 기반으로 하는 키에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-243">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="2de33-244">**역할 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="2de33-244">**Role authorization**.</span></span> <span data-ttu-id="2de33-245">조직에서 Active Directory 그룹을 기반으로 하는 키에 대 한 액세스 권한을 부여 하 고, 웹 서비스가 LDAP를 쿼리할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-245">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="2de33-246">**전자 메일 인증을 사용 하 여 DKE에 대 한 키 액세스 설정을 설정 하려면**</span><span class="sxs-lookup"><span data-stu-id="2de33-246">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="2de33-247">파일 \*\* 에서appsettings.js\*\* 열고 `AuthorizedEmailAddress` 설정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-247">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="2de33-248">권한을 부여 하려는 전자 메일 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-248">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="2de33-249">여러 전자 메일 주소는 큰따옴표와 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-249">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="2de33-250">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-250">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="2de33-251">설정을 찾고 `LDAPPath` 큰따옴표 사이에 있는 텍스트를 제거 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-251">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="2de33-252">큰따옴표를 자리에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-252">Leave the double quotes in place.</span></span> <span data-ttu-id="2de33-253">작업이 완료 되 면 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-253">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="2de33-254">설정을 찾아서 `AuthorizedRoles` 전체 줄을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-254">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="2de33-255">이 이미지는 전자 메일 권한 부여를 위해 올바르게 형식이 지정 된 파일 \*\* 의appsettings.js\*\* 를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-255">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![전자 메일 인증 방법을 보여 주는 appsettings.js파일](../media/dke-email-accesssetting.png)

<span data-ttu-id="2de33-257">**역할 인증을 사용 하 여 DKE에 대 한 키 액세스 설정을 설정 하려면**</span><span class="sxs-lookup"><span data-stu-id="2de33-257">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="2de33-258">파일 \*\* 에서appsettings.js\*\* 열고 `AuthorizedRoles` 설정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-258">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="2de33-259">권한을 부여 하려는 Active Directory 그룹 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-259">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="2de33-260">여러 그룹 이름은 큰따옴표와 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-260">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="2de33-261">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-261">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="2de33-262">설정을 찾고 `LDAPPath` Active Directory 도메인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-262">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="2de33-263">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-263">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="2de33-264">설정을 찾아서 `AuthorizedEmailAddress` 전체 줄을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-264">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="2de33-265">이 이미지는 역할 권한 부여를 위해 올바르게 형식이 지정 된 파일 \*\* 의appsettings.js\*\* 를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-265">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![역할 인증 방법을 보여 주는 파일의 appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="2de33-267">테 넌 트 및 키 설정</span><span class="sxs-lookup"><span data-stu-id="2de33-267">Tenant and key settings</span></span>

<span data-ttu-id="2de33-268">DKE 테 넌 트 및 키 설정은 파일 \*\* 의appsettings.js\*\* 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-268">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="2de33-269">**DKE에 대 한 테 넌 트 및 키 설정을 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="2de33-269">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="2de33-270">파일 \*\* 에서appsettings.js\*\* 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-270">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="2de33-271">설정을 찾은 `ValidIssuers` 후 `<tenantid>` 테 넌 트 ID로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-271">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="2de33-272">Azure 포털로 이동 하 여 [테 넌 트 속성](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)을 확인 하 여 테 넌 트 ID를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-272">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="2de33-273">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-273">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="2de33-274">를 찾습니다 `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="2de33-274">Locate the `JwtAudience`.</span></span> <span data-ttu-id="2de33-275">`<yourhostname>`DKE 서비스가 실행 될 컴퓨터의 호스트 이름으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-275">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="2de33-276">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-276">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="2de33-277">값은 `JwtAudience` 호스트 이름과 *정확히*일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-277">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="2de33-278">디버깅 하는 동안 **localhost: 5001** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-278">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="2de33-279">그러나 디버깅이 완료 되 면이 값을 서버의 호스트 이름으로 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-279">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="2de33-280">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="2de33-280">`TestKeys:Name`.</span></span> <span data-ttu-id="2de33-281">키의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-281">Enter a name for your key.</span></span> <span data-ttu-id="2de33-282">예: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="2de33-282">For example: `TestKey1`</span></span>
- <span data-ttu-id="2de33-283">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="2de33-283">`TestKeys:Id`.</span></span> <span data-ttu-id="2de33-284">GUID를 만들어 값으로 입력 `TestKeys:ID` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-284">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="2de33-285">예를 들면 `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-285">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="2de33-286">[온라인 Guid 생성기](https://guidgenerator.com/) 와 같은 사이트를 사용 하 여 GUID를 임의로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-286">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="2de33-287">**appsettings.js**의 테 넌 트 및 키 설정에 대 한 올바른 형식을 표시 하는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-287">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="2de33-288">`LDAPPath` 역할 인증에 대해 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-288">`LDAPPath` is configured for role authorization.</span></span>

![파일의 appsettings.js에 있는 DKE에 대 한 올바른 테 넌 트 및 키 설정을 표시 합니다.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="2de33-290">테스트 키 생성</span><span class="sxs-lookup"><span data-stu-id="2de33-290">Generate test keys</span></span>

<span data-ttu-id="2de33-291">응용 프로그램 설정을 정의한 후에는 공용 및 개인 테스트 키를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-291">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="2de33-292">키를 생성 하려면</span><span class="sxs-lookup"><span data-stu-id="2de33-292">To generate keys:</span></span>

1. <span data-ttu-id="2de33-293">Windows 시작 메뉴에서 OpenSSL 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-293">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="2de33-294">테스트 키를 저장할 폴더로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-294">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="2de33-295">이 작업의 단계를 완료 하 여 만든 파일은 동일한 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-295">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="2de33-296">새 테스트 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-296">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="2de33-297">개인 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-297">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="2de33-298">공개 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-298">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="2de33-299">텍스트 편집기에서 **pubkeyonly**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-299">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="2de33-300">파일의appsettings.js섹션에 있는 첫 번째 행과 마지막 줄을 제외한 **pubkeyonly pem** 파일의 모든 콘텐츠를 복사 합니다. `PublicPem` **appsettings.json**</span><span class="sxs-lookup"><span data-stu-id="2de33-300">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="2de33-301">텍스트 편집기에서 **privkeynopass**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-301">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="2de33-302">**Privkeynopass** 파일에서 첫 번째 줄을 제외한 모든 콘텐츠를 `PrivatePem` 파일 **의appsettings.js** 섹션에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-302">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="2de33-303">및 섹션 모두에서 공백 및 newlines를 모두 `PublicPem` 제거 `PrivatePem` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-303">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2de33-304">이 콘텐츠를 복사할 때는 PEM 데이터를 삭제 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2de33-304">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="2de33-305">Visual Studio Code에서 **Startup.cs** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-305">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="2de33-306">이 파일은 DoubleKeyEncryptionService\src\customer-key-store\.에서 로컬로 복제 한 DoubleKeyEncryptionService 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-306">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="2de33-307">다음 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-307">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. <span data-ttu-id="2de33-308">다음 텍스트를이 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-308">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="2de33-309">최종 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-309">The end results should look similar to the following.</span></span>

   ![공용 미리 보기용 startup.cs 파일](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="2de33-311">이제 [DKE 프로젝트를 빌드할](#build-the-project)준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-311">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="2de33-312">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="2de33-312">Build the project</span></span>

<span data-ttu-id="2de33-313">다음 지침을 사용 하 여 DKE 프로젝트를 로컬로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-313">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="2de33-314">Visual Studio Code의 dke 서비스 저장소에서 **View** \> **명령 색상표** 보기를 선택 하 고 프롬프트에서 **빌드** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-314">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="2de33-315">목록에서 **작업: 빌드 작업 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-315">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="2de33-316">빌드 작업을 찾을 수 없는 경우에는 **빌드 작업 구성을** 선택 하 고 다음과 같이 .net core에 대해 create build tasks를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-316">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![.NET에 대 한 누락 된 빌드 작업 구성](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="2de33-318">**서식 파일에서 tasks.js만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-318">Choose **Create tasks.json from template**.</span></span>

      ![DKE 템플릿의 파일에서 tasks.js만들기](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="2de33-320">템플릿 유형 목록에서 **.Net Core**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-320">From the list of template types, select **.NET Core**.</span></span>

      ![DKE에 대 한 올바른 서식 파일 선택](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="2de33-322">빌드 섹션에서 **customerkeystore** 파일의 경로를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-322">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="2de33-323">여기에 해당 하지 않으면 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-323">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="2de33-324">빌드를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-324">Run the build again.</span></span>

3. <span data-ttu-id="2de33-325">출력 창에 빨간색 오류가 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-325">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="2de33-326">빨간색 오류가 있으면 콘솔 출력을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-326">If there are red errors, check the console output.</span></span> <span data-ttu-id="2de33-327">이전 단계를 모두 올바르게 완료 했으며 올바른 빌드 버전이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-327">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="2de33-328">**Run** \> **디버깅 시작** 을 선택 하 여 프로세스를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-328">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="2de33-329">환경을 선택 하 라는 메시지가 표시 되 면 **.net core**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-329">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="2de33-330">일반적으로 .NET 핵심 디버거가 시작 `https://localhost:5001` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-330">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="2de33-331">테스트 키를 보려면 앞으로 이동 하 여 `https://localhost:5001` 슬래시 (/)와 키 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-331">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="2de33-332">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-332">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="2de33-333">키가 JSON 형식으로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-333">The key should display in JSON format.</span></span>

<span data-ttu-id="2de33-334">이제 설치가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-334">Your setup is now complete.</span></span> <span data-ttu-id="2de33-335">Keystore를 게시 하기 전에 JwtAudience 설정에 대 한 appsettings.json에서 호스트 값이 앱 서비스 호스트 이름과 정확히 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-335">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="2de33-336">빌드 문제를 해결 하기 위해 localhost로 변경 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-336">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="2de33-337">DKE 서비스 배포 및 키 저장소 게시</span><span class="sxs-lookup"><span data-stu-id="2de33-337">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="2de33-338">프로덕션 배포의 경우 타사 클라우드에서 서비스를 배포 하거나 [온-프레미스 시스템에 게시](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-338">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="2de33-339">다른 방법으로 키를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-339">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="2de33-340">조직에 가장 적합 한 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-340">Select the method that works best for your organization.</span></span>

<span data-ttu-id="2de33-341">파일럿 배포의 경우 Azure에서 배포 하 고 바로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-341">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="2de33-342">**DKE 배포를 호스트 하는 Azure Web App 인스턴스를 만들려면**</span><span class="sxs-lookup"><span data-stu-id="2de33-342">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="2de33-343">키 저장소를 게시 하려면 DKE 배포를 호스트 하는 Azure App Service 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-343">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="2de33-344">다음에는 생성 된 키를 Azure에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-344">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="2de33-345">브라우저에서 [Microsoft Azure 포털](https://ms.portal.azure.com)에 로그인 하 고 **앱 서비스**  >  **추가**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-345">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="2de33-346">구독 및 리소스 그룹을 선택 하 고 인스턴스 세부 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-346">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="2de33-347">DKE 서비스를 설치 하려는 컴퓨터의 호스트 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-347">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="2de33-348">파일 [\*\* 의appsettings.js\*\*](#tenant-and-key-settings) 에서 JwtAudience 설정에 대해 정의 된 이름과 이름이 같은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-348">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="2de33-349">이름에 입력 하는 값은 WebAppInstanceName입니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-349">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="2de33-350">**게시**에서 **코드**를 선택 하 고 **런타임 스택을**보려면 **.net Core 3.1**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-350">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="2de33-351">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-351">For example:</span></span>

   ![앱 서비스 추가](../media/dke-azure-add-app-service.png)

3. <span data-ttu-id="2de33-353">페이지 맨 아래에서 **검토 + 만들기**를 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-353">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="2de33-354">다음 중 하나를 수행 하 여 생성 된 키를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-354">Do one of the following to publish your generated keys:</span></span>

    - [<span data-ttu-id="2de33-355">ZipDeployUI를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="2de33-355">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="2de33-356">FTP를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="2de33-356">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="2de33-357">Visual Studio 2019 이상 버전을 통해 게시</span><span class="sxs-lookup"><span data-stu-id="2de33-357">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="2de33-358">ZipDeployUI를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="2de33-358">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="2de33-359">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-359">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="2de33-360">예: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="2de33-360">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="2de33-361">키 저장소의 코드 베이스에서 **customer-key-store\src\customer-key-store** 폴더로 이동 하 여이 폴더에 **customerkeystore** 파일이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-361">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="2de33-362">실행: **dotnet 게시**</span><span class="sxs-lookup"><span data-stu-id="2de33-362">Run: **dotnet publish**</span></span>

     <span data-ttu-id="2de33-363">출력 창에는 게시가 배포 된 디렉터리가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-363">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="2de33-364">예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="2de33-364">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="2de33-365">게시 디렉터리의 모든 파일을 .zip 파일로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-365">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="2de33-366">.Zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 파일의 루트 수준에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-366">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="2de33-367">위에서 연 ZipDeployUI 사이트에 만든 .zip 파일을 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-367">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="2de33-368">예: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="2de33-368">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="2de33-369">DKE가 배포 되었으며 만든 테스트 키로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-369">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="2de33-370">아래에서 [배포에 대 한 유효성 검사](#validate-your-deployment) 를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-370">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="2de33-371">FTP를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="2de33-371">Publish via FTP</span></span>

1. <span data-ttu-id="2de33-372">[위에서](#deploy-the-dke-service-and-publish-the-key-store)만든 앱 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-372">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

    <span data-ttu-id="2de33-373">브라우저에서 **Azure portal**  >  **App Service**  >  **배포 센터**  >  **수동 배포**  >  **FTP**  >  **대시보드로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-373">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="2de33-374">로컬 파일에 표시 되는 연결 문자열을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-374">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="2de33-375">이러한 문자열을 사용 하 여 웹 앱 서비스에 연결 하 고 FTP를 통해 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-375">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="2de33-376">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-376">For example:</span></span>

   ![FTP 대시보드에서 연결 문자열 복사](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="2de33-378">키 저장소의 코드 베이스에서 **customer-key-store\src\customer-key-store 디렉터리로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-378">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="2de33-379">이 디렉터리에 **customerkeystore** 파일이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-379">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="2de33-380">실행: **dotnet 게시**</span><span class="sxs-lookup"><span data-stu-id="2de33-380">Run: **dotnet publish**</span></span>

    <span data-ttu-id="2de33-381">출력에는 게시가 배포 된 디렉터리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-381">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="2de33-382">예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="2de33-382">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="2de33-383">게시 디렉터리의 모든 파일을 zip 파일로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-383">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="2de33-384">.Zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 파일의 루트 수준에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-384">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="2de33-385">FTP 클라이언트에서 복사한 연결 정보를 사용 하 여 앱 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-385">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="2de33-386">이전 단계에서 만든 .zip 파일을 웹 응용 프로그램의 루트 디렉터리에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-386">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="2de33-387">DKE가 배포 되었으며 만든 테스트 키로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-387">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="2de33-388">다음으로, [배포 유효성을 검사](#validate-your-deployment)합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-388">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="2de33-389">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2de33-389">Validate your deployment</span></span>

<span data-ttu-id="2de33-390">위에 설명 된 방법 중 하나를 사용 하 여 DKE를 배포한 후에는 배포 및 키 저장소 설정의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-390">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="2de33-391">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-391">Run:</span></span>

<span data-ttu-id="2de33-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span><span class="sxs-lookup"><span data-stu-id="2de33-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span></span>

<span data-ttu-id="2de33-393">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-393">For example:</span></span>

<span data-ttu-id="2de33-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span><span class="sxs-lookup"><span data-stu-id="2de33-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span></span>

<span data-ttu-id="2de33-395">출력에 오류가 표시 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-395">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="2de33-396">준비 되 면 [키 저장소를 등록](#register-your-key-store)합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-396">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="2de33-397">키 저장소 등록</span><span class="sxs-lookup"><span data-stu-id="2de33-397">Register your key store</span></span>

<span data-ttu-id="2de33-398">다음 단계를 수행 하면 DKE 서비스를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-398">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="2de33-399">레이블 만들기를 시작 하기 전에 dke 서비스를 등록 하는 것은 g를 배포 하는 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-399">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="2de33-400">DKE 서비스를 등록 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-400">To register the DKE service:</span></span>

1. <span data-ttu-id="2de33-401">브라우저에서 [Microsoft Azure portal](https://ms.portal.azure.com/)을 열고 **모든 서비스** \> **id** \> **앱 등록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-401">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="2de33-402">**새 등록**을 선택 하 고 의미 있는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-402">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="2de33-403">표시 된 옵션에서 계정 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-403">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="2de33-404">사용자 지정 하지 않은 도메인 (예: **onmicrosoft.com**)에서 Microsoft Azure를 사용 하는 경우 **에는이 조직 디렉터리의 계정만 선택 합니다 (Microsoft only 단일 테 넌 트).**</span><span class="sxs-lookup"><span data-stu-id="2de33-404">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="2de33-405">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-405">For example:</span></span>

   ![새 앱 등록](../media/dke-app-registration.png)

4. <span data-ttu-id="2de33-407">페이지 맨 아래에서 **등록** 을 선택 하 여 새 앱 등록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-407">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="2de33-408">새 앱 등록의 왼쪽 창에 있는 **관리**에서 **인증**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-408">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="2de33-409">**플랫폼 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-409">Select **Add a platform**.</span></span>

7. <span data-ttu-id="2de33-410">**플랫폼 구성** 팝업에서 **웹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-410">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="2de33-411">**리디렉션 uri**에서 이중 키 암호화 서비스의 URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-411">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="2de33-412">호스트 이름 및 도메인을 포함 하 여 앱 서비스 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-412">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="2de33-413">예: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="2de33-413">For example: https://mydkeservicetest.com</span></span>

    - <span data-ttu-id="2de33-414">입력 하는 URL은 DKE 서비스가 배포 되는 호스트 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-414">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
    - <span data-ttu-id="2de33-415">Visual Studio를 사용 하 여 로컬로 테스트 하는 경우를 사용 **https://localhost:5001** 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-415">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="2de33-416">모든 경우에 스키마는 **https**여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-416">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="2de33-417">호스트 이름이 앱 서비스 호스트 이름과 정확히 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-417">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="2de33-418">빌드 문제를 해결 하기 위해 변경 했을 수 있습니다 `localhost` .</span><span class="sxs-lookup"><span data-stu-id="2de33-418">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="2de33-419">**appsettings.js**설정에서이 값은 설정한 호스트 이름입니다 `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="2de33-419">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="2de33-420">**암시적 권한 부여**에서 **ID 토큰** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-420">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="2de33-421">변경 내용을 저장하려면 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-421">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="2de33-422">왼쪽 창에서 **API 노출**을 선택한 다음 응용 프로그램 ID URI 옆에 있는 **설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-422">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="2de33-423">여전히 **Api 노출** 페이지의 **이 API** 영역에 정의 된 범위에서 **범위 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-423">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="2de33-424">새 범위에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-424">In the new scope:</span></span>

    1. <span data-ttu-id="2de33-425">범위 이름을 **user_impersonation**로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-425">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="2de33-426">동의할 수 있는 관리자 및 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-426">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="2de33-427">필요한 나머지 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-427">Define any remaining values required.</span></span>

    4. <span data-ttu-id="2de33-428">**범위 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-428">Select **Add scope**.</span></span>

    5. <span data-ttu-id="2de33-429">맨 위에 있는 **저장** 을 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-429">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="2de33-430">여전히 **API 노출** 페이지의 **권한 있는 클라이언트 응용 프로그램** 영역에서 **클라이언트 응용 프로그램 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-430">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="2de33-431">새 클라이언트 응용 프로그램에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-431">In the new client application:</span></span>

    1. <span data-ttu-id="2de33-432">클라이언트 ID를 **d3590ed6-52b3-4102-aeff-aad2292ab01c**으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-432">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="2de33-433">이 값은 Microsoft Office 클라이언트 ID 이며 Office에서 키 저장소에 대 한 액세스 토큰을 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-433">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="2de33-434">**권한 있는 범위**에서 **user_impersonation** 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-434">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="2de33-435">**응용 프로그램 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-435">Select **Add application**.</span></span>

    4. <span data-ttu-id="2de33-436">맨 위에 있는 **저장** 을 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-436">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="2de33-437">이제 DKE 서비스가 등록 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-437">Your DKE service is now registered.</span></span> <span data-ttu-id="2de33-438">계속 [하 여 DKE를 사용 하 여 레이블을 만듭니다](#create-sensitivity-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="2de33-438">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="2de33-439">DKE을 사용 하 여 민감도 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="2de33-439">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="2de33-440">Microsoft 365 준수 센터에서 새 민감도 레이블을 만들고 암호화를 다른 방법으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-440">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="2de33-441">**이중 키 암호화 사용** 을 선택 하 고 키에 대 한 끝점 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-441">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="2de33-442">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-442">For example:</span></span>

![Microsoft 365 준수 센터에서 이중 키 암호화 사용을 선택 합니다.](../media/dke-use-dke.png)

<span data-ttu-id="2de33-444">추가 하는 모든 DKE 레이블은 최신 버전의 Microsoft 365 Apps for enterprise의 사용자에 게 표시 되기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-444">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="2de33-445">클라이언트가 새 레이블로 새로 고치는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-445">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="2de33-446">클라이언트에서 DKE 사용</span><span class="sxs-lookup"><span data-stu-id="2de33-446">Enable DKE in your client</span></span>

<span data-ttu-id="2de33-447">Office 참가자 인 경우 DKE가 사용 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-447">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="2de33-448">그렇지 않으면 다음 레지스트리 키를 추가 하 여 클라이언트에 대해 DKE를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-448">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="2de33-449">HYOK 레이블에서 보호 된 파일을 DKE 레이블로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2de33-449">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="2de33-450">원하는 경우 DKE를 설정 했으면 HYOK 레이블을 사용 하 여 보호 한 콘텐츠를 DKE 레이블로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-450">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="2de33-451">마이그레이션하려면 AIP 스캐너를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-451">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="2de33-452">스캐너 사용을 시작 하려면 [Azure Information Protection 통합 레이블 스캐너가 무엇 인가요?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2de33-452">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="2de33-453">콘텐츠를 마이그레이션하지 않으면 HYOK 보호 된 콘텐츠는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2de33-453">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
