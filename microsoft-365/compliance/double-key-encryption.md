---
title: 이중 키 암호화(DKE)
description: DKE를 사용하면 키에 대한 모든 제어를 유지하면서 매우 중요한 데이터를 보호할 수 있습니다.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: b9696f26dd8f68ba291eab50e11a4cb6dd55ab7a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226914"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="fd33b-103">이중 키 암호화 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd33b-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="fd33b-104">*적용 사항: [Microsoft 365,](https://www.microsoft.com/microsoft-365/business/compliance-management)Microsoft 365 준수, [Azure Information Protection에](https://azure.microsoft.com/pricing/details/information-protection) 대한 이중 키 암호화*</span><span class="sxs-lookup"><span data-stu-id="fd33b-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="fd33b-105">*지침: Azure Information Protection 통합 레이블 [클라이언트를 Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="fd33b-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="fd33b-106">*서비스 설명: Microsoft 365 [규정 준수](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="fd33b-106">*Service description for: [Microsoft 365 Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="fd33b-107">DKE(이중 키 암호화)는 두 개의 키를 함께 사용하여 보호된 콘텐츠에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="fd33b-108">Microsoft는 키 하나를 Microsoft Azure 다른 키를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="fd33b-109">이중 키 암호화 서비스를 사용하여 키 중 하나에 대한 모든 제어를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="fd33b-110">Azure Information Protection 통합 레이블 지정 클라이언트를 사용하여 매우 중요한 콘텐츠에 보호를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="fd33b-111">이중 키 암호화는 클라우드 및 사내 배포를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="fd33b-112">이러한 배포를 통해 보호된 데이터를 저장할 때마다 암호화된 데이터가 불투명하게 유지되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="fd33b-113">기본 클라우드 기반 테넌트 루트 키에 대한 자세한 내용은 Azure Information Protection 테넌트 키 계획 및 [구현을 참조하세요.](/azure/information-protection/plan-implement-tenant-key)</span><span class="sxs-lookup"><span data-stu-id="fd33b-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="fd33b-114">조직에서 DKE를 채택해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="fd33b-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="fd33b-115">이중 키 암호화는 가장 엄격한 보호 요구 사항을 준수하는 가장 중요한 데이터를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="fd33b-116">DKE는 모든 데이터를 위한 것이 아니며,</span><span class="sxs-lookup"><span data-stu-id="fd33b-116">DKE is not intended for all data.</span></span> <span data-ttu-id="fd33b-117">일반적으로 이중 키 암호화를 사용하여 전체 데이터의 일부만 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="fd33b-118">배포하기 전에 이 솔루션에 사용할 올바른 데이터를 식별할 때 신심해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="fd33b-119">경우에 따라 범위를 좁히고 Microsoft 관리 키 또는 BYOK를 사용하는 경우와 같은 대부분의 데이터에 Microsoft Information Protection 다른 솔루션을 활용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="fd33b-120">이러한 솔루션은 향상된 보호 및 규정 요구 사항을 준수하지 않는 문서에 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="fd33b-121">또한 이러한 솔루션을 사용하면 가장 강력한 Office 365 사용할 수 있습니다. DKE로 암호화된 콘텐츠와 함께 사용할 수 없는 서비스</span><span class="sxs-lookup"><span data-stu-id="fd33b-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="fd33b-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-122">For example:</span></span>

- <span data-ttu-id="fd33b-123">첨부 파일을 표시해야 하는 맬웨어 방지 및 스팸 방지를 포함한 전송 규칙</span><span class="sxs-lookup"><span data-stu-id="fd33b-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="fd33b-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="fd33b-124">Microsoft Delve</span></span>
- <span data-ttu-id="fd33b-125">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fd33b-125">eDiscovery</span></span>
- <span data-ttu-id="fd33b-126">콘텐츠 검색 및 인덱싱</span><span class="sxs-lookup"><span data-stu-id="fd33b-126">Content search and indexing</span></span>
- <span data-ttu-id="fd33b-127">Office 공동자치 기능을 포함한 웹앱</span><span class="sxs-lookup"><span data-stu-id="fd33b-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="fd33b-128">MIP SDK를 통해 DKE와 통합되지 않은 외부 응용 프로그램 또는 서비스는 암호화된 데이터에 대해 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="fd33b-129">이 Microsoft Information Protection SDK 1.7+는 이중 키 암호화를 지원합니다. SDK와 통합되는 응용 프로그램은 충분한 사용 권한 및 통합을 통해 이 데이터를 추론할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="fd33b-130">조직은 Microsoft 정보 보호 기능(분류 및 레이블 지정)을 사용하여 대부분의 중요한 데이터를 보호하고 중요 중요 데이터에만 DKE를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="fd33b-131">이중 키 암호화는 금융 서비스 및 의료와 같은 높은 규제 대상 산업의 중요한 데이터와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="fd33b-132">조직에 다음 요구 사항이 있는 경우 DKE를 사용하여 콘텐츠 보안을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="fd33b-133">모든 상황에서 보호된 콘텐츠의 암호 해독만 할 수 있도록 하려는 경우 </span><span class="sxs-lookup"><span data-stu-id="fd33b-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="fd33b-134">Microsoft가 자체로 보호된 데이터에 액세스하는 것을 원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="fd33b-135">지리적 경계 내에 키를 보유하기 위한 규정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="fd33b-136">데이터 암호화 및 암호 해독을 위해 보유하는 모든 키는 데이터 센터에서 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="fd33b-137">DKE에 대한 시스템 및 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd33b-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="fd33b-138">**이중 키 암호화는** Microsoft 365 함께 Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="fd33b-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="fd33b-139">라이선스가 없는 Microsoft 365 E5 평가판에 등록할 수 [있습니다.](https://aka.ms/M365E5ComplianceTrial)</span><span class="sxs-lookup"><span data-stu-id="fd33b-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="fd33b-140">이러한 라이선스에 대한 자세한 내용은 보안 Microsoft 365 규정 준수에 대한 [& 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="fd33b-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="fd33b-141">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-141">**Azure Information Protection**.</span></span> <span data-ttu-id="fd33b-142">DKE는 민감도 레이블과 함께 작동하며 Azure Information Protection이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="fd33b-143">DKE 민감도 레이블은 데스크톱 앱의 민감도 리본을 통해 최종 Office 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="fd33b-144">보호된 문서를 보호하고 사용하려는 각 클라이언트 컴퓨터에 이러한 선행 요구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="fd33b-145">**Microsoft Office 엔터프라이즈용 앱** 버전 2009 이상(데스크톱 버전의 Word, PowerPoint 및 Excel)Windows.</span><span class="sxs-lookup"><span data-stu-id="fd33b-145">**Microsoft Office Apps for enterprise** version 2009 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="fd33b-146">**Azure Information Protection 통합 레이블 지정 클라이언트** 버전 2.7.93.0 이상.</span><span class="sxs-lookup"><span data-stu-id="fd33b-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="fd33b-147">Microsoft 다운로드 센터에서 통합 레이블 지정 클라이언트를 [다운로드하여 설치합니다.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="fd33b-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="fd33b-148">DKE로 보호된 콘텐츠를 저장하고 보기 위한 지원되는 환경</span><span class="sxs-lookup"><span data-stu-id="fd33b-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="fd33b-149">**지원되는 응용 프로그램**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-149">**Supported applications**.</span></span> <span data-ttu-id="fd33b-150">[엔터프라이즈용 Microsoft 365 앱,](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) Windows 및 Excel 클라이언트를 PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="fd33b-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="fd33b-151">**온라인 콘텐츠 지원**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-151">**Online content support**.</span></span> <span data-ttu-id="fd33b-152">이중 키 암호화로 보호된 문서와 파일은 Microsoft 365 및 Microsoft SharePoint 모두에서 비즈니스용 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fd33b-152">You can store documents and files protected with Double Key Encryption online in both Microsoft SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="fd33b-153">이러한 위치에 업로드하기 전에 지원되는 응용 프로그램에서 DKE로 문서 및 파일에 레이블을 지정하고 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-153">You must label and protect documents and files with DKE by supported applications before you upload to these locations.</span></span> <span data-ttu-id="fd33b-154">암호화된 콘텐츠를 전자 메일로 공유할 수 있지만 암호화된 문서와 파일은 온라인으로 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-154">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="fd33b-155">대신 로컬 컴퓨터에서 지원되는 데스크톱 응용 프로그램 및 클라이언트를 사용하여 보호된 콘텐츠를 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-155">Instead, you must view protected content using the supported desktop applications and clients on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="fd33b-156">DKE 배포 개요</span><span class="sxs-lookup"><span data-stu-id="fd33b-156">Overview of deploying DKE</span></span>

<span data-ttu-id="fd33b-157">DKE를 설정하기 위해 다음과 같은 일반적인 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-157">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="fd33b-158">이러한 단계를 완료하면 최종 사용자가 이중 키 암호화를 사용하여 매우 중요한 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-158">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="fd33b-159">이 문서에 설명된 바와 같이 DKE 서비스를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-159">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="fd33b-160">이중 키 암호화를 사용하여 레이블을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-160">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="fd33b-161">앱의 정보 보호로 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com) 이중 키 암호화를 사용하여 새 레이블을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-161">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="fd33b-162">민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠에 대한 [액세스 제한을 참조하세요.](./encryption-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="fd33b-162">See [Restrict access to content by using sensitivity labels to apply encryption](./encryption-sensitivity-labels.md).</span></span>

3. <span data-ttu-id="fd33b-163">이중 키 암호화 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-163">Use Double Key Encryption labels.</span></span> <span data-ttu-id="fd33b-164">사용자 지정의 민감도 리본에서 이중 키 암호화 레이블을 선택하여 데이터를 Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="fd33b-164">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="fd33b-165">몇 가지 방법으로 이중 키 암호화를 배포하는 단계를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-165">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="fd33b-166">이 문서에서는 경험이 적은 관리자가 서비스를 성공적으로 배포할 수 있도록 자세한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-166">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="fd33b-167">원하는 경우 자체 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-167">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="fd33b-168">DKE 배포</span><span class="sxs-lookup"><span data-stu-id="fd33b-168">Deploy DKE</span></span>

<span data-ttu-id="fd33b-169">이 문서 및 배포 비디오에서는 Azure를 DKE 서비스의 배포 대상으로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fd33b-169">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="fd33b-170">다른 위치에 배포하는 경우 자체 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-170">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="fd33b-171">이중 키 암호화 [배포](https://youtu.be/vDWfHN_kygg) 비디오를 시청하여 이 문서의 개념에 대한 단계별 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-171">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="fd33b-172">비디오를 완료하는 데 18분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-172">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="fd33b-173">조직에 대해 이중 키 암호화를 설정하기 위해 다음과 같은 일반적인 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-173">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="fd33b-174">DKE 서비스에 대한 소프트웨어 선행 구성</span><span class="sxs-lookup"><span data-stu-id="fd33b-174">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="fd33b-175">리포지토리에서 이중 GitHub 암호화 복제</span><span class="sxs-lookup"><span data-stu-id="fd33b-175">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="fd33b-176">응용 프로그램 설정 수정</span><span class="sxs-lookup"><span data-stu-id="fd33b-176">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="fd33b-177">테스트 키 생성</span><span class="sxs-lookup"><span data-stu-id="fd33b-177">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="fd33b-178">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="fd33b-178">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="fd33b-179">DKE 서비스 배포 및 키 저장소 게시</span><span class="sxs-lookup"><span data-stu-id="fd33b-179">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="fd33b-180">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="fd33b-180">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="fd33b-181">키 저장소 등록</span><span class="sxs-lookup"><span data-stu-id="fd33b-181">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="fd33b-182">DKE를 사용하여 민감도 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="fd33b-182">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="fd33b-183">클라이언트에서 DKE 사용</span><span class="sxs-lookup"><span data-stu-id="fd33b-183">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="fd33b-184">HYOK 레이블에서 DKE 레이블로 보호된 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="fd33b-184">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="fd33b-185">완료되면 DKE를 사용하여 문서 및 파일을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-185">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="fd33b-186">자세한 내용은 [에서 파일](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)및 전자 메일에 민감도 레이블 적용을 Office.</span><span class="sxs-lookup"><span data-stu-id="fd33b-186">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="fd33b-187">DKE 서비스에 대한 소프트웨어 선행 구성</span><span class="sxs-lookup"><span data-stu-id="fd33b-187">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="fd33b-188">DKE 서비스를 설치하려는 컴퓨터에 이러한 선행 구성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-188">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="fd33b-189">**.NET Core 3.1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-189">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="fd33b-190">[.NET Core 3.1 다운로드에서 SDK를 다운로드하여 설치합니다.](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="fd33b-190">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="fd33b-191">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-191">**Visual Studio Code**.</span></span> <span data-ttu-id="fd33b-192">에서 Visual Studio Code [https://code.visualstudio.com/](https://code.visualstudio.com) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-192">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="fd33b-193">설치한 후 Visual Studio Code 확장  \> **보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-193">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="fd33b-194">이러한 확장을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-194">Install these extensions.</span></span>

- <span data-ttu-id="fd33b-195">C# 대한 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fd33b-195">C# for Visual Studio Code</span></span>

- <span data-ttu-id="fd33b-196">NuGet 패키지 관리자</span><span class="sxs-lookup"><span data-stu-id="fd33b-196">NuGet Package Manager</span></span>

<span data-ttu-id="fd33b-197">**Git 리소스**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-197">**Git resources**.</span></span> <span data-ttu-id="fd33b-198">다음 중 하나를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-198">Download and install one of the following.</span></span>

- [<span data-ttu-id="fd33b-199">Git</span><span class="sxs-lookup"><span data-stu-id="fd33b-199">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="fd33b-200">GitHub 데스크톱</span><span class="sxs-lookup"><span data-stu-id="fd33b-200">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="fd33b-201">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="fd33b-201">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="fd33b-202">**OpenSSL** DKE를 배포한 후 [](#generate-test-keys) 테스트 키를 생성하려면 [OpenSSL이](https://slproweb.com/products/Win32OpenSSL.html) 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-202">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="fd33b-203">환경 변수 경로에서 올바르게 호출하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-203">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="fd33b-204">예를 들어 자세한 내용은 "PATH에 설치 디렉터리 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) 추가"를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd33b-204">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="fd33b-205">DKE 데이터베이스 GitHub 복제</span><span class="sxs-lookup"><span data-stu-id="fd33b-205">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="fd33b-206">Microsoft는 DKE 원본 파일을 로컬 저장소에 GitHub 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-206">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="fd33b-207">리포지토리를 복제하여 조직에서 사용할 수 있도록 프로젝트를 로컬로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-207">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="fd33b-208">DKE GitHub 리포지토리는 에 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-208">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="fd33b-209">다음 지침은 비경제적 git 또는 Visual Studio Code 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-209">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="fd33b-210">브라우저에서 로 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 이동하세요. .</span><span class="sxs-lookup"><span data-stu-id="fd33b-210">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="fd33b-211">화면 오른쪽에서 코드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-211">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="fd33b-212">UI 버전에 복제 또는 다운로드 **단추가 표시될 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-212">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="fd33b-213">그런 다음 나타나는 드롭다운에서 복사 아이콘을 선택하여 URL을 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-213">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="fd33b-214">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-214">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd33b-215">![이중 키 암호화 서비스 리포지토리를 GitHub](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="fd33b-215">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="fd33b-216">다음 Visual Studio Code 보기 명령  팔레트 보기를 \> **선택하고** **Git: 복제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-216">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="fd33b-217">목록의 옵션으로 이동하려면 입력을 시작하여 항목을 필터링한 다음 `git: clone` 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-217">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="fd33b-218">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-218">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd33b-219">![Visual Studio Code GIT:Clone 옵션](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="fd33b-219">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="fd33b-220">텍스트 상자에 Git에서 복사한 URL을 붙여넣고 에서 **복제를 GitHub.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-220">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="fd33b-221">나타나는 **폴더 선택** 대화 상자에서 리포지토리를 저장할 위치를 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-221">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="fd33b-222">프롬프트에서 열기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-222">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="fd33b-223">리포지토리가 Visual Studio Code 왼쪽 아래에 현재 Git 분기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-223">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="fd33b-224">예를 들어 분기는 **main** 입니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-224">For example,  The branch should be **main**.</span></span> <span data-ttu-id="fd33b-225">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-225">For example:</span></span>

   ![주 분기를 표시하는 Visual Studio Code DKE 리포지터의 스크린샷](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="fd33b-227">주 분기에 없는 경우 해당 분기를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-227">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="fd33b-228">다음 Visual Studio Code 분기를 선택하고 표시하는  분기 목록에서 main을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-228">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="fd33b-229">주 분기를 선택하면 프로젝트를 빌드할 올바른 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-229">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="fd33b-230">올바른 분기를 선택하지 않은 경우 배포가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-230">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="fd33b-231">이제 DKE 원본 리포지토리가 로컬로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-231">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="fd33b-232">그런 다음 [조직의 응용 프로그램](#modify-application-settings) 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-232">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="fd33b-233">응용 프로그램 설정 수정</span><span class="sxs-lookup"><span data-stu-id="fd33b-233">Modify application settings</span></span>

<span data-ttu-id="fd33b-234">DKE 서비스를 배포하려면 다음과 같은 유형의 응용 프로그램 설정을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-234">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="fd33b-235">키 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="fd33b-235">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="fd33b-236">테넌트 및 키 설정</span><span class="sxs-lookup"><span data-stu-id="fd33b-236">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="fd33b-237">파일에서 응용 프로그램 설정을 appsettings.js있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-237">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="fd33b-238">이 파일은 로컬로 복제한 DoubleKeyEncryptionService 리포지션의 DoubleKeyEncryptionService\src\customer-key-store에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-238">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="fd33b-239">예를 들어 Visual Studio Code 그림과 같이 파일을 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-239">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![DKE에 appsettings.js파일을 위치합니다.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="fd33b-241">키 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="fd33b-241">Key access settings</span></span>

<span data-ttu-id="fd33b-242">전자 메일 또는 역할 권한 부여를 사용할지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd33b-242">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="fd33b-243">DKE는 한 번의 인증 방법 중 하나만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-243">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="fd33b-244">**전자 메일 권한 부여**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-244">**Email authorization**.</span></span> <span data-ttu-id="fd33b-245">조직에서 전자 메일 주소만 기준으로 키에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-245">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="fd33b-246">**역할 권한 부여**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-246">**Role authorization**.</span></span> <span data-ttu-id="fd33b-247">조직에서 Active Directory 그룹을 기반으로 키에 대한 액세스 권한을 부여할 수 있도록 허용하며 웹 서비스가 LDAP를 쿼리할 수 있도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-247">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

##### <a name="to-set-key-access-settings-for-dke-using-email-authorization"></a><span data-ttu-id="fd33b-248">전자 메일 권한 부여를 사용하여 DKE에 대한 키 액세스 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fd33b-248">To set key access settings for DKE using email authorization</span></span>

1. <span data-ttu-id="fd33b-249">파일에서 **appsettings.js열고** 설정을 `AuthorizedEmailAddress` 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-249">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="fd33b-250">승인할 전자 메일 주소 또는 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-250">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="fd33b-251">여러 전자 메일 주소를 따옴표와 각자 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-251">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="fd33b-252">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-252">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="fd33b-253">설정을 찾아서 따옴표 `LDAPPath` 사이에 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 있는 텍스트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-253">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="fd33b-254">따옴표를 그대로 다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-254">Leave the double quotes in place.</span></span> <span data-ttu-id="fd33b-255">완료되면 설정이 다음과 같이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-255">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="fd33b-256">설정을 `AuthorizedRoles` 찾아 전체 줄을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-256">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="fd33b-257">이 이미지는 전자 **메일appsettings.js** 올바르게 형식이 지정되어 있는 파일의 파일 형식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-257">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![전자 appsettings.js방법을 보여 주며 파일의 파일](../media/dke-email-accesssetting.png)

##### <a name="to-set-key-access-settings-for-dke-using-role-authorization"></a><span data-ttu-id="fd33b-259">역할 권한 부여를 사용하여 DKE에 대한 키 액세스 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fd33b-259">To set key access settings for DKE using role authorization</span></span>

1. <span data-ttu-id="fd33b-260">파일에서 **appsettings.js열고** 설정을 `AuthorizedRoles` 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-260">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="fd33b-261">승인할 Active Directory 그룹 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-261">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="fd33b-262">여러 그룹 이름을 따옴표와 각자 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-262">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="fd33b-263">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-263">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="fd33b-264">설정을 `LDAPPath` 찾아 Active Directory 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-264">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="fd33b-265">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-265">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="fd33b-266">설정을 `AuthorizedEmailAddress` 찾아 전체 줄을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-266">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="fd33b-267">이 이미지는 역할 **appsettings.js** 올바르게 형식이 지정되어 있는 파일의 파일 형식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-267">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.js권한 부여 방법을 보여 주는 파일에 대한 파일 관리](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="fd33b-269">테넌트 및 키 설정</span><span class="sxs-lookup"><span data-stu-id="fd33b-269">Tenant and key settings</span></span>

<span data-ttu-id="fd33b-270">DKE 테넌트 및 키 설정은 파일의appsettings.js **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-270">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

##### <a name="to-configure-tenant-and-key-settings-for-dke"></a><span data-ttu-id="fd33b-271">DKE에 대한 테넌트 및 키 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="fd33b-271">To configure tenant and key settings for DKE</span></span>

1. <span data-ttu-id="fd33b-272">파일에서 **appsettings.js를 니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-272">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="fd33b-273">설정을 `ValidIssuers` 찾아 `<tenantid>` 테넌트 ID로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-273">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="fd33b-274">Azure Portal로 이동하고 테넌트 속성을 확인하여 테넌트 [ID를 찾을 수 있습니다.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="fd33b-274">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="fd33b-275">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-275">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

> [!NOTE]
> <span data-ttu-id="fd33b-276">키 저장소에 대한 외부 B2B 액세스를 사용하도록 설정하려면 이러한 외부 테넌트도 유효한 발급자 목록의 일부로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-276">If you want to enable external B2B access to your key store, you will also need to include these external tenants as part of the valid issuers' list.</span></span>

<span data-ttu-id="fd33b-277">`JwtAudience`를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-277">Locate the `JwtAudience`.</span></span> <span data-ttu-id="fd33b-278">DKE 서비스가 실행될 컴퓨터의 호스트 `<yourhostname>` 이름으로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-278">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="fd33b-279">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-279">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="fd33b-280">의 값은 정확히 호스트의 `JwtAudience` 이름과 *일치해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="fd33b-280">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="fd33b-281">디버깅하는 동안 **localhost:5001을** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-281">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="fd33b-282">그러나 디버깅이 완료되면 이 값을 서버의 호스트 이름으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-282">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="fd33b-283">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="fd33b-283">`TestKeys:Name`.</span></span> <span data-ttu-id="fd33b-284">키 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-284">Enter a name for your key.</span></span> <span data-ttu-id="fd33b-285">예: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="fd33b-285">For example: `TestKey1`</span></span>
- <span data-ttu-id="fd33b-286">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="fd33b-286">`TestKeys:Id`.</span></span> <span data-ttu-id="fd33b-287">GUID를 만들고 값으로 `TestKeys:ID` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-287">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="fd33b-288">예를 들면 `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-288">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="fd33b-289">온라인 GUID 생성기와 같은 사이트를 사용하여 [GUID를](https://guidgenerator.com/) 임의로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-289">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="fd33b-290">이 이미지는 의 테넌트 및 키 설정에 대한 **올바른 형식을appsettings.js.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-290">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="fd33b-291">`LDAPPath` 는 역할 권한 부여를 위해 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-291">`LDAPPath` is configured for role authorization.</span></span>

![파일에서 DKE에 대한 올바른 테넌트 및 키 appsettings.js표시됩니다.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="fd33b-293">테스트 키 생성</span><span class="sxs-lookup"><span data-stu-id="fd33b-293">Generate test keys</span></span>

<span data-ttu-id="fd33b-294">응용 프로그램 설정이 정의되면 공개 및 개인 테스트 키를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-294">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="fd33b-295">키를 생성하는 경우:</span><span class="sxs-lookup"><span data-stu-id="fd33b-295">To generate keys:</span></span>

1. <span data-ttu-id="fd33b-296">시작 Windows 시작 메뉴 OpenSSL 명령 프롬프트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-296">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="fd33b-297">테스트 키를 저장할 폴더로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-297">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="fd33b-298">이 작업의 단계를 완료하여 만든 파일은 같은 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-298">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="fd33b-299">새 테스트 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-299">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="fd33b-300">개인 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-300">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="fd33b-301">공개 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-301">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="fd33b-302">텍스트 편집기에서 **pubkeyonly.pem을 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-302">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="fd33b-303">첫 줄과 마지막 줄을 제외한 **pubkeyonly.pem** 파일의 모든 콘텐츠를 파일에서 파일로appsettings.js`PublicPem` **섹션에 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-303">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="fd33b-304">텍스트 편집기에서 **privkeynopass.pem을 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-304">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="fd33b-305">첫 줄과 마지막 줄을 제외한 **privkeynopass.pem** 파일의 모든 콘텐츠를 파일에서 파일로appsettings.js`PrivatePem` **섹션에 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-305">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="fd33b-306">및 섹션에서 공백과 줄임 표시를 `PublicPem` `PrivatePem` 모두 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-306">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fd33b-307">이 콘텐츠를 복사할 때 PEM 데이터를 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-307">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="fd33b-308">In Visual Studio Code, browse to the **Startup.cs** file.</span><span class="sxs-lookup"><span data-stu-id="fd33b-308">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="fd33b-309">이 파일은 로컬로 복제한 DoubleKeyEncryptionService 리포지션의 DoubleKeyEncryptionService\src\customer-key-store\에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-309">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="fd33b-310">다음 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-310">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="fd33b-311">이러한 줄을 다음 텍스트로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-311">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="fd33b-312">최종 결과는 다음과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-312">The end results should look similar to the following.</span></span>

    ![공개 미리 보기용 startup.cs 파일](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="fd33b-314">이제 [DKE 프로젝트를 빌드할 준비가 완료되었습니다.](#build-the-project)</span><span class="sxs-lookup"><span data-stu-id="fd33b-314">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="fd33b-315">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="fd33b-315">Build the project</span></span>

<span data-ttu-id="fd33b-316">다음 지침을 사용하여 DKE 프로젝트를 로컬로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-316">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="fd33b-317">Visual Studio Code DKE 서비스 리포지토리에서 명령  팔레트 보기를 선택한 다음 프롬프트에 \>  **빌드를** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-317">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="fd33b-318">목록에서 작업: 빌드 작업 **실행 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-318">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="fd33b-319">빌드 작업을 찾을 수 없는  경우 다음과 같이 빌드 작업 구성을 선택하고 .NET core에 대해 빌드를 하나씩 만드면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-319">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![.NET에 대한 누락된 빌드 작업 구성](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="fd33b-321">템플릿에서 **tasks.js만들기 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-321">Choose **Create tasks.json from template**.</span></span>

      ![DKE용 tasks.js파일에서 파일로 파일 만들기](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="fd33b-323">템플릿 유형 목록에서 **.NET Core 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-323">From the list of template types, select **.NET Core**.</span></span>

      ![DKE에 대한 올바른 템플릿 선택](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="fd33b-325">빌드 섹션에서 **customerkeystore.csproj** 파일의 경로를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-325">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="fd33b-326">이 목록에 없는 경우 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-326">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="fd33b-327">빌드를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-327">Run the build again.</span></span>

3. <span data-ttu-id="fd33b-328">출력 창에 빨간색 오류가 없는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-328">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="fd33b-329">빨간색 오류가 있는 경우 콘솔 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-329">If there are red errors, check the console output.</span></span> <span data-ttu-id="fd33b-330">이전 단계를 모두 올바르게 완료하고 올바른 빌드 버전이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-330">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="fd33b-331">**디버깅** 시작 \> **실행을 선택하여** 프로세스를 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-331">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="fd33b-332">환경을 선택하라는 메시지가 표시될 경우 **.NET core 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-332">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="fd33b-333">.NET 코어 디버거는 일반적으로 에 `https://localhost:5001` 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-333">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="fd33b-334">테스트 키를 확인하기 위해 으로 이동하여 슬래시(/) 및 키 이름을 `https://localhost:5001` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-334">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="fd33b-335">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-335">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="fd33b-336">키는 JSON 형식으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-336">The key should display in JSON format.</span></span>

<span data-ttu-id="fd33b-337">이제 설치가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-337">Your setup is now complete.</span></span> <span data-ttu-id="fd33b-338">키스토어를 게시하기 전에 appsettings.js에서 JwtAudience 설정에 대해 호스트 이름의 값이 앱 서비스 호스트 이름과 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-338">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="fd33b-339">빌드 문제를 해결하기 위해 localhost로 변경한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-339">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="fd33b-340">DKE 서비스 배포 및 키 저장소 게시</span><span class="sxs-lookup"><span data-stu-id="fd33b-340">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="fd33b-341">프로덕션 배포의 경우 타사 클라우드에 서비스를 배포하거나, 사내 시스템에 [게시합니다.](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)</span><span class="sxs-lookup"><span data-stu-id="fd33b-341">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1).</span></span>

<span data-ttu-id="fd33b-342">키를 배포하는 다른 방법을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-342">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="fd33b-343">조직에 가장 적합한 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-343">Select the method that works best for your organization.</span></span>

<span data-ttu-id="fd33b-344">파일럿 배포의 경우 Azure에 배포하고 바로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-344">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

#### <a name="to-create-an-azure-web-app-instance-to-host-your-dke-deployment"></a><span data-ttu-id="fd33b-345">DKE 배포를 호스트할 Azure Web App 인스턴스를 만들면</span><span class="sxs-lookup"><span data-stu-id="fd33b-345">To create an Azure Web App instance to host your DKE deployment</span></span>

<span data-ttu-id="fd33b-346">키 저장소를 게시하기 위해 Azure 앱 서비스 인스턴스를 만들어 DKE 배포를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-346">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="fd33b-347">다음으로 생성된 키를 Azure에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-347">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="fd33b-348">브라우저에서 Microsoft Azure [포털에](https://ms.portal.azure.com)로그인하고 앱 서비스 추가 로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-348">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="fd33b-349">구독 및 리소스 그룹을 선택하고 인스턴스 세부 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-349">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="fd33b-350">DKE 서비스를 설치할 컴퓨터의 호스트 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-350">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="fd33b-351">on 파일의 JwtAudience 설정에 정의된 이름과appsettings.js [**합니다.**](#tenant-and-key-settings)</span><span class="sxs-lookup"><span data-stu-id="fd33b-351">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="fd33b-352">이름에 대해 제공하는 값은 WebAppInstanceName도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-352">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="fd33b-353">**게시에서** 코드를 **선택하고** 런타임 스택에 대해 **.NET Core 3.1을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="fd33b-353">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="fd33b-354">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-354">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd33b-355">![앱 서비스 추가](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="fd33b-355">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="fd33b-356">At the bottom of the page, select **Review + create**, and then select **Add**.</span><span class="sxs-lookup"><span data-stu-id="fd33b-356">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="fd33b-357">다음 중 하나를 사용하여 생성된 키를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-357">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="fd33b-358">ZipDeployUI를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="fd33b-358">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="fd33b-359">FTP를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="fd33b-359">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="fd33b-360">Visual Studio 2019 이상을 통해 게시</span><span class="sxs-lookup"><span data-stu-id="fd33b-360">Publish via Visual Studio 2019 or later</span></span>](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="fd33b-361">ZipDeployUI를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="fd33b-361">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="fd33b-362">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-362">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="fd33b-363">예: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="fd33b-363">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="fd33b-364">키 저장소의 코드베이스에서 **customer-key-store\src\customer-key-store** 폴더로 이동한 다음 이 폴더에 **customerkeystore.csproj** 파일이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-364">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="fd33b-365">실행: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="fd33b-365">Run: **dotnet publish**</span></span>

   <span data-ttu-id="fd33b-366">출력 창에는 게시가 배포된 디렉터리가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-366">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="fd33b-367">예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="fd33b-367">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="fd33b-368">게시 디렉터리의 모든 파일을 파일로 .zip 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-368">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="fd33b-369">.zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 수준에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-369">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="fd33b-370">만든 .zip 파일을 끌어서 위에서 연 ZipDeployUI 사이트로 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-370">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="fd33b-371">예: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="fd33b-371">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="fd33b-372">DKE가 배포된 후 만든 테스트 키를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-372">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="fd33b-373">아래의 배포 [유효성 검사를 계속](#validate-your-deployment) 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-373">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="fd33b-374">FTP를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="fd33b-374">Publish via FTP</span></span>

1. <span data-ttu-id="fd33b-375">커넥트 만든 앱 서비스에 [대한 설명입니다.](#deploy-the-dke-service-and-publish-the-key-store)</span><span class="sxs-lookup"><span data-stu-id="fd33b-375">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="fd33b-376">브라우저에서 **Azure Portal** 앱 서비스 배포 센터 수동 배포  >    >    >  FTP **대시보드로**  >    >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-376">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="fd33b-377">표시되는 연결 문자열을 로컬 파일에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-377">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="fd33b-378">이러한 문자열을 사용하여 Web App 서비스에 연결하고 FTP를 통해 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-378">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="fd33b-379">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-379">For example:</span></span>

   ![FTP 대시보드에서 연결 문자열 복사](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="fd33b-381">키 저장소에 대한 코드베이스에서 고객 키 **저장소\src\customer-key-store 디렉터리로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-381">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="fd33b-382">이 디렉터리에 **customerkeystore.csproj** 파일이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-382">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="fd33b-383">실행: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="fd33b-383">Run: **dotnet publish**</span></span>

   <span data-ttu-id="fd33b-384">출력에는 게시가 배포된 디렉터리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-384">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="fd33b-385">예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="fd33b-385">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="fd33b-386">게시 디렉터리의 모든 파일을 zip 파일로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-386">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="fd33b-387">.zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 수준에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-387">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="fd33b-388">FTP 클라이언트에서 복사한 연결 정보를 사용하여 앱 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-388">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="fd33b-389">업로드 만든 .zip Web App의 루트 디렉터리로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-389">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="fd33b-390">DKE가 배포된 후 만든 테스트 키를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-390">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="fd33b-391">그런 다음 [배포의 유효성을 검사합니다.](#validate-your-deployment)</span><span class="sxs-lookup"><span data-stu-id="fd33b-391">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="fd33b-392">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="fd33b-392">Validate your deployment</span></span>

<span data-ttu-id="fd33b-393">위에서 설명한 방법 중 하나를 사용하여 DKE를 배포한 후 배포 및 키 저장소 설정의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-393">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="fd33b-394">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-394">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="fd33b-395">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-395">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="fd33b-396">출력에 오류가 나타나지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-396">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="fd33b-397">준비가 되면 키 [저장소를 등록합니다.](#register-your-key-store)</span><span class="sxs-lookup"><span data-stu-id="fd33b-397">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="fd33b-398">키 이름은 대소문자 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-398">The key name is case sensitive.</span></span> <span data-ttu-id="fd33b-399">파일에서 키에 나타나는 키 appsettings.js입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-399">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="fd33b-400">키 저장소 등록</span><span class="sxs-lookup"><span data-stu-id="fd33b-400">Register your key store</span></span>

<span data-ttu-id="fd33b-401">다음 단계를 통해 DKE 서비스를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-401">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="fd33b-402">레이블 만들기를 시작하기 전에 DKE 서비스를 등록하는 것이 DKE 배포의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-402">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="fd33b-403">DKE 서비스를 등록하는 경우:</span><span class="sxs-lookup"><span data-stu-id="fd33b-403">To register the DKE service:</span></span>

1. <span data-ttu-id="fd33b-404">브라우저에서 Microsoft Azure [포털을 열고](https://ms.portal.azure.com/)모든 서비스  ID 앱 \>  \> **등록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-404">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="fd33b-405">새 **등록 을** 선택하고 의미 있는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-405">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="fd33b-406">표시되는 옵션에서 계정 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-406">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="fd33b-407">사용자 지정이 아닌 도메인(예: Microsoft Azure )에서 onmicrosoft.com 를 사용하는 경우 이 조직 디렉터리의 계정만(Microsoft 전용 - 단일 **테넌트)을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-407">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="fd33b-408">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-408">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd33b-409">![새 앱 등록](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="fd33b-409">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="fd33b-410">페이지 아래쪽에서 등록을  선택하여 새 앱 등록을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="fd33b-410">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="fd33b-411">새 앱 등록의 왼쪽 창에 있는 관리에서 **인증을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-411">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="fd33b-412">플랫폼 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-412">Select **Add a platform**.</span></span>

7. <span data-ttu-id="fd33b-413">플랫폼 **구성** 팝업에서 웹 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-413">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="fd33b-414">URI **리디렉션에서** 이중 키 암호화 서비스의 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-414">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="fd33b-415">호스트 이름과 도메인을 모두 포함하여 앱 서비스 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-415">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="fd33b-416">예: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="fd33b-416">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="fd33b-417">입력하는 URL은 DKE 서비스가 배포된 호스트 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-417">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="fd33b-418">로컬로 테스트하는 경우 를 **https://localhost:5001** Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd33b-418">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="fd33b-419">모든 경우에 스키마는 **https 되어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-419">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="fd33b-420">호스트 이름을 앱 서비스 호스트 이름과 정확히 일치하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-420">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="fd33b-421">빌드 문제를 해결하기 위해 `localhost` 변경한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-421">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="fd33b-422">에서 **appsettings.js** 이 값은 에 대해 설정한 호스트 `JwtAudience` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-422">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="fd33b-423">**암시적 부여에서** **ID 토큰** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-423">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="fd33b-424">**저장** 을 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-424">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="fd33b-425">왼쪽 창에서 **API** 노출을 선택한 다음 응용 프로그램 ID URI 옆에 있는 설정 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-425">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="fd33b-426">API 표시 **페이지의** 이 **API에** 정의된 범위에서 범위 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-426">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="fd33b-427">새 범위에서 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-427">In the new scope:</span></span>

    1. <span data-ttu-id="fd33b-428">범위 이름을 에 로 **user_impersonation.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-428">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="fd33b-429">동의할 수 있는 관리자 및 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-429">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="fd33b-430">필요한 나머지 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-430">Define any remaining values required.</span></span>

    4. <span data-ttu-id="fd33b-431">범위 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-431">Select **Add scope**.</span></span>

    5. <span data-ttu-id="fd33b-432">맨 **위에** 저장을 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-432">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="fd33b-433">API 표시 **페이지의** 권한이 부여된 클라이언트 응용 프로그램 **영역에서** 클라이언트 응용 프로그램 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-433">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="fd33b-434">새 클라이언트 응용 프로그램에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-434">In the new client application:</span></span>

    1. <span data-ttu-id="fd33b-435">클라이언트 ID를 로 `d3590ed6-52b3-4102-aeff-aad2292ab01c` 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-435">Define the Client ID as `d3590ed6-52b3-4102-aeff-aad2292ab01c`.</span></span> <span data-ttu-id="fd33b-436">이 값은 Microsoft Office 클라이언트 ID로, Office 저장소에 대한 액세스 토큰을 얻을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-436">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="fd33b-437">권한이 **부여된 범위에서** user_impersonation **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-437">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="fd33b-438">응용 **프로그램 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd33b-438">Select **Add application**.</span></span>

    4. <span data-ttu-id="fd33b-439">맨 **위에** 저장을 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-439">Select **Save** at the top to save your changes.</span></span>

    5. <span data-ttu-id="fd33b-440">이러한 단계를 반복하지만 이번에는 클라이언트 ID를 로 `c00e9d32-3c8d-4a7d-832b-029040e7db99` 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-440">Repeat these steps, but this time, define the client ID as `c00e9d32-3c8d-4a7d-832b-029040e7db99`.</span></span> <span data-ttu-id="fd33b-441">이 값은 Azure Information Protection 통합 레이블 지정 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-441">This value is the Azure Information Protection unified labeling client ID.</span></span>

<span data-ttu-id="fd33b-442">이제 DKE 서비스가 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-442">Your DKE service is now registered.</span></span> <span data-ttu-id="fd33b-443">[DKE를 사용하여 레이블을 만들어 계속합니다.](#create-sensitivity-labels-using-dke)</span><span class="sxs-lookup"><span data-stu-id="fd33b-443">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="fd33b-444">DKE를 사용하여 민감도 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="fd33b-444">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="fd33b-445">이 Microsoft 365 규정 준수 센터 새 민감도 레이블을 만들고 다른 경우처럼 암호화를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-445">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="fd33b-446">이중 **키 암호화 사용을 선택하고** 키의 끝점 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-446">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="fd33b-447">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-447">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fd33b-448">![다음 목록에서 이중 키 암호화 Microsoft 365 규정 준수 센터](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="fd33b-448">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="fd33b-449">추가한 모든 DKE 레이블은 최신 버전의 엔터프라이즈용 Microsoft 365 앱.</span><span class="sxs-lookup"><span data-stu-id="fd33b-449">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="fd33b-450">클라이언트가 새 레이블로 새로 고쳐지기까지 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-450">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="fd33b-451">클라이언트에서 DKE 사용</span><span class="sxs-lookup"><span data-stu-id="fd33b-451">Enable DKE in your client</span></span>

<span data-ttu-id="fd33b-452">If you're an Office Insider, DKE is enabled for you.</span><span class="sxs-lookup"><span data-stu-id="fd33b-452">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="fd33b-453">그렇지 않은 경우 다음 레지스트리 키를 추가하여 클라이언트에 대해 DKE를 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd33b-453">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="fd33b-454">HYOK 레이블에서 DKE 레이블로 보호된 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="fd33b-454">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="fd33b-455">원하는 경우 DKE 설정이 완료되면 HYOK 레이블을 사용하여 보호한 콘텐츠를 DKE 레이블로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-455">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="fd33b-456">마이그레이션하려면 AIP 스캐너를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-456">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="fd33b-457">스캐너 사용을 시작하기 위해 Azure Information Protection 통합 레이블 지정 [스캐너란?을 참조하세요.](/azure/information-protection/deploy-aip-scanner)</span><span class="sxs-lookup"><span data-stu-id="fd33b-457">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="fd33b-458">콘텐츠를 마이그레이션하지 않는 경우 HYOK로 보호된 콘텐츠는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd33b-458">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
