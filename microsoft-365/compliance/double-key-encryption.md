---
title: DKE (이중 암호화)
description: DKE를 사용 하면 중요 한 데이터를 보호 하 고 키에 대 한 모든 권한을 유지할 수 있습니다.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 47fc4bc47831970ef7a7f2087cf6c86b6fefb8c2
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201726"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="e1b28-103">DKE (이중 암호화)</span><span class="sxs-lookup"><span data-stu-id="e1b28-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="e1b28-104">*적용 대상: [Microsoft 365 준수](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="e1b28-104">*Applies to: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="e1b28-105">*지침: [Azure Information Protection 통합 레이블 클라이언트 Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="e1b28-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="e1b28-106">*서비스 설명: [Microsoft 365 준수](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="e1b28-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="e1b28-107">이 공용 미리 보기 버전의 DKE (이중 암호화)를 사용 하 여 Azure Information Protection 통합 레이블 클라이언트를 통해 중요 한 콘텐츠를 보호 하 고 키를 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-107">This public preview version of Double Key Encryption (DKE) enables you to use the Azure Information Protection Unified Labeling Client to protect highly sensitive content while maintaining full control of your key.</span></span>

<span data-ttu-id="e1b28-108">이중 키 암호화에는 함께 사용 하 여 보호 된 콘텐츠에 액세스 하는 두 개의 키가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-108">Double Key Encryption requires two keys, used together, to access protected content.</span></span> <span data-ttu-id="e1b28-109">Microsoft Azure에 하나의 키를 저장 하 고 다른 키를 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-109">You store one key in Microsoft Azure, and you hold the other key.</span></span>

<span data-ttu-id="e1b28-110">이중 키 암호화는 클라우드 및 온-프레미스 배포를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="e1b28-111">이러한 배포를 통해 보호 된 데이터를 저장할 때마다 암호화 된 데이터를 불투명 하 게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="e1b28-112">클라우드 기반 테 넌 트 루트 키의 기본에 대 한 자세한 내용은 [Azure Information Protection 테 넌 트 키 계획 및 구현](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1b28-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="e1b28-113">이중 키 암호화는 액세스 권한을 얻기 위해 은행 키와 고객 키를 둘 다 필요로 하는 안전 금고와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-113">Double Key Encryption is similar to a safety deposit box that requires both a bank key and a customer key to gain access.</span></span> <span data-ttu-id="e1b28-114">보호 된 콘텐츠의 암호를 해독 하려면 Microsoft 관리 되는 키와 고객 소유 키를 모두 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-114">To decrypt protected content, you must use both the Microsoft managed key and the customer-held key.</span></span>

<span data-ttu-id="e1b28-115">다음 비디오에서는 이중 키 암호화가 콘텐츠를 보호 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-115">The following video shows how Double Key Encryption works to secure your content.</span></span>

<span data-ttu-id="e1b28-116">조직에 다음과 같은 요구 사항이 있는 경우 DKE를 사용 하 여 콘텐츠를 안전 하 게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-116">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="e1b28-117">모든 상황에서 보호 된 콘텐츠의 암호를 *해독할 수 있도록* 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-117">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="e1b28-118">Microsoft가 보호 된 데이터에 자체 액세스 하지 못하도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="e1b28-118">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="e1b28-119">지리적 경계 내에 키를 포함 하기 위한 규정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-119">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="e1b28-120">데이터 암호화 및 암호 해독을 위한 모든 고객 보유 키가 데이터 센터에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-120">All customer-held keys for data encryption and decryption are maintained in your data center.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="e1b28-121">DKE에 대 한 시스템 및 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1b28-121">System and licensing requirements for DKE</span></span>

<span data-ttu-id="e1b28-122">Microsoft 365에 대 한 이중 키 암호화의이 공개 미리 보기 릴리스는 Microsoft 365 E5 및 Office 365 E5의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-122">This public preview release of Double Key Encryption for Microsoft 365 is available as part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="e1b28-123">Microsoft 365 E5 라이선스가 없는 경우 [평가판](https://aka.ms/M365E5ComplianceTrial)에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-123">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="e1b28-124">이러한 라이선스에 대 한 자세한 내용은 [보안 & 준수에 대 한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1b28-124">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="e1b28-125">**Office 참가자** 공개 미리 보기를 사용 하려면 Office 참가자 프로그램의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-125">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="e1b28-126">Office 참가자에 게 연결 하려면로 이동 [https://insider.office.com](https://insider.office.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-126">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="e1b28-127">구성원 인 경우 조직에 적합 한 배포 방법을 선택 하 여 Office 참가자 빌드를 배포할 수 있도록 환경을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-127">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="e1b28-128">자세한 내용은 [Office 참가자 빌드 배포 시작](https://insider.office.com/business/deploy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1b28-128">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="e1b28-129">**Azure Information Protection**</span><span class="sxs-lookup"><span data-stu-id="e1b28-129">**Azure Information Protection**.</span></span> <span data-ttu-id="e1b28-130">DKE는 민감도 레이블에서 작동 하며 Azure Information Protection을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-130">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="e1b28-131">DKE로 보호 된 콘텐츠를 저장 하 고 보기 위한 지원 되는 환경</span><span class="sxs-lookup"><span data-stu-id="e1b28-131">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="e1b28-132">**지원 되는 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="e1b28-132">**Supported applications**.</span></span> <span data-ttu-id="e1b28-133">Word, Excel 및 PowerPoint를 포함 하는 Windows의 [엔터프라이즈 클라이언트용 Microsoft 365 앱](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)</span><span class="sxs-lookup"><span data-stu-id="e1b28-133">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="e1b28-134">**온라인 콘텐츠 지원**</span><span class="sxs-lookup"><span data-stu-id="e1b28-134">**Online content support**.</span></span> <span data-ttu-id="e1b28-135">Microsoft SharePoint 및 비즈니스용 OneDrive에 모두 온라인으로 저장 된 문서 및 파일을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-135">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="e1b28-136">전자 메일로 암호화 된 콘텐츠를 공유할 수 있지만 암호화 된 문서 및 파일은 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-136">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="e1b28-137">대신 로컬 컴퓨터의 데스크톱 앱을 사용 하 여 보호 된 콘텐츠를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-137">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="e1b28-138">이 공개 미리 보기 문서 정보</span><span class="sxs-lookup"><span data-stu-id="e1b28-138">About this public preview article</span></span>

<span data-ttu-id="e1b28-139">몇 가지 단계를 완료 하 여 이중 암호화를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-139">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="e1b28-140">이 문서에서는 숙련 된 관리자가 서비스를 성공적으로 배포 하는 데 필요한 자세한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-140">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="e1b28-141">이 문서에서 설명 하는 배포 방법에 의해 공유 되는 git과 같은 일반적인 기술에 대 한 경험이 있는 경우에는 사용자가 직접 메서드를 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-141">If you're experienced with the common technologies, such as git, shared by the deployment methods described in this article, you can choose to use your own methods.</span></span>

<span data-ttu-id="e1b28-142">공개 미리 보기에서는 Azure에 이중 키 암호화 서비스를 배포 하는 방법에 대 한 단계별 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-142">For public preview, we've included step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="e1b28-143">이 시나리오는 프로덕션 환경에서 발생할 수 있는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-143">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="e1b28-144">Azure를 사용한 공개 미리 보기는 바로 배포 하 여 이중 키 암호화 사용을 시작할 수 있도록 하는 빠른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-144">For public preview using Azure is a quick way to deploy that lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="e1b28-145">네트워크에 로컬로 있든 다른 공급자를 사용 하 든 관계 없이 원하는 경우에 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-145">You can choose to deploy the service wherever you want, whether it's locally on your network or with another provider.</span></span> <span data-ttu-id="e1b28-146">해당 위치에 적합 한 방법을 사용 하 여 키 저장소를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-146">You'll need to publish the key store using methods appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="e1b28-147">이중 암호화 배포</span><span class="sxs-lookup"><span data-stu-id="e1b28-147">Deploy Double Key Encryption</span></span>

<span data-ttu-id="e1b28-148">이러한 일반적인 단계를 수행 하 여 조직에 대 한 이중 암호화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-148">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span> <span data-ttu-id="e1b28-149">이 문서의 예제에서는 Azure를 DKE 서비스의 배포 대상으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-149">The example in this article uses Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="e1b28-150">다른 위치에 배포 하는 경우에는 고유한 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-150">If you're deploying to another location, you'll need to provide your own values.</span></span>

1. [<span data-ttu-id="e1b28-151">소프트웨어 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="e1b28-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="e1b28-152">이중 키 암호화 GitHub 리포지토리 복제</span><span class="sxs-lookup"><span data-stu-id="e1b28-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="e1b28-153">응용 프로그램 설정 수정</span><span class="sxs-lookup"><span data-stu-id="e1b28-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="e1b28-154">테스트 키 생성</span><span class="sxs-lookup"><span data-stu-id="e1b28-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="e1b28-155">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="e1b28-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="e1b28-156">키 저장소 게시</span><span class="sxs-lookup"><span data-stu-id="e1b28-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="e1b28-157">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e1b28-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="e1b28-158">키 저장소 등록</span><span class="sxs-lookup"><span data-stu-id="e1b28-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="e1b28-159">민감도 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="e1b28-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="e1b28-160">작업이 완료 되 면 DKE을 사용 하 여 문서와 파일을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="e1b28-161">자세한 내용은 [Office에서 파일 및 전자 메일에 민감도 레이블 적용](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1b28-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="e1b28-162">소프트웨어 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="e1b28-162">Install software prerequisites</span></span>

<span data-ttu-id="e1b28-163">이중 키 암호화에는 두 가지 유형의 소프트웨어 필수 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="e1b28-164">이중 키 암호화 서비스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e1b28-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="e1b28-165">클라이언트 컴퓨터에 대 한 이중 키 암호화 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e1b28-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="e1b28-166">이중 키 암호화 서비스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e1b28-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="e1b28-167">DKE 서비스를 설치 하려는 컴퓨터에 이러한 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="e1b28-168">**.Net Core 3.1 SDK**</span><span class="sxs-lookup"><span data-stu-id="e1b28-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="e1b28-169">[.Net Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)에서 SDK를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="e1b28-170">**Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="e1b28-170">**Visual Studio Code**.</span></span> <span data-ttu-id="e1b28-171">Visual Studio Code from을 다운로드 [https://code.visualstudio.com/](https://code.visualstudio.com) 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1b28-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="e1b28-172">설치가 완료 되 면 Visual Studio Code를 실행 하 고 Extensions **보기** 를 선택 \> **Extensions**합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="e1b28-173">이러한 확장을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-173">Install these extensions.</span></span>

- <span data-ttu-id="e1b28-174">Visual Studio 코드용 c # 코드</span><span class="sxs-lookup"><span data-stu-id="e1b28-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="e1b28-175">NuGet 패키지 관리자</span><span class="sxs-lookup"><span data-stu-id="e1b28-175">NuGet Package Manager</span></span>

<span data-ttu-id="e1b28-176">**Microsoft Office 참가자**입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="e1b28-177">[배포 방법을](https://insider.office.com/business/deploy)하나 이상 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="e1b28-178">**Git 리소스**</span><span class="sxs-lookup"><span data-stu-id="e1b28-178">**Git resources**.</span></span> <span data-ttu-id="e1b28-179">다음 중 하나를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="e1b28-180">Git</span><span class="sxs-lookup"><span data-stu-id="e1b28-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="e1b28-181">GitHub 데스크톱</span><span class="sxs-lookup"><span data-stu-id="e1b28-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="e1b28-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="e1b28-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="e1b28-183">**OpenSSL** DKE를 배포한 후 [테스트 키를 생성](#generate-test-keys) 하려면 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) 이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="e1b28-184">환경 변수 경로에서 올바르게 호출 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="e1b28-185">예를 들어 자세한 내용은 "설치 디렉터리를 PATH에 추가 합니다."를 참조 하십시오 https://www.osradar.com/install-openssl-windows/ .</span><span class="sxs-lookup"><span data-stu-id="e1b28-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="e1b28-186">클라이언트 컴퓨터에 대 한 이중 키 암호화 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e1b28-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="e1b28-187">보호 된 문서를 보호 하 고 사용 하려는 각 클라이언트 컴퓨터에 이러한 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="e1b28-188">**Microsoft Office** 버전 \*. 12711 이상</span><span class="sxs-lookup"><span data-stu-id="e1b28-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="e1b28-189">**Azure Information Protection 통합 레이블 클라이언트** 버전 2.7.93.0 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="e1b28-190">[Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)에서 통합 레이블 클라이언트를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="e1b28-191">DKE GitHub 리포지토리 복제</span><span class="sxs-lookup"><span data-stu-id="e1b28-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="e1b28-192">Microsoft는 GitHub 리포지토리에 DKE 원본 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="e1b28-193">조직의 사용을 위해 로컬로 프로젝트를 빌드하기 위해 리포지토리를 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="e1b28-194">DKE GitHub 리포지토리는에 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="e1b28-195">다음 지침은 inexperienced git 또는 Visual Studio Code 사용자에 게 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="e1b28-196">브라우저에서 다음 위치로 이동 합니다.[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="e1b28-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="e1b28-197">화면 오른쪽 방향으로 **코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="e1b28-198">사용자의 UI 버전에 **복제 또는 다운로드** 단추가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="e1b28-199">그런 다음 표시 되는 드롭다운 목록에서 복사 아이콘을 선택 하 여 클립보드에 URL을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="e1b28-200">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="GitHub에서 이중 키 암호화 서비스 리포지토리 복제":::

3. <span data-ttu-id="e1b28-202">Visual Studio Code에서 **View** \> **명령 색상표** 보기를 선택 하 고 **Git: 클론**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="e1b28-203">목록에서 옵션으로 이동 하려면 입력을 시작 하 여 `git: clone` 항목을 필터링 한 다음 드롭다운에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="e1b28-204">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code GIT: Clone 옵션":::

4. <span data-ttu-id="e1b28-206">Git에서 복사한 URL을 텍스트 상자에 붙여넣고 **GitHub에서 복제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="e1b28-207">**폴더 선택** 대화 상자가 나타나면 저장소를 저장할 위치를 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="e1b28-208">프롬프트에서 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="e1b28-209">Visual Studio Code에서 리포지토리를 열고 왼쪽 아래에 현재 Git 분기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="e1b28-210">현재 분기는 **마스터**여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-210">Your current branch should be **master**.</span></span>

    <span data-ttu-id="e1b28-211">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Visual Studio 코드 마스터 분기":::

6. <span data-ttu-id="e1b28-213">Word **마스터를** 선택한 다음 분기 목록에서 **public_preview** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="e1b28-214">Public_preview 분기를 선택 하면 프로젝트를 빌드하는 데 올바른 파일이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="e1b28-215">올바른 분기를 선택 하지 않으면 배포가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="e1b28-216">이제 DKE 원본 리포지토리가 로컬로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="e1b28-217">다음으로, 조직의 [응용 프로그램 설정을 수정](#modify-application-settings) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="e1b28-218">응용 프로그램 설정 수정</span><span class="sxs-lookup"><span data-stu-id="e1b28-218">Modify application settings</span></span>

<span data-ttu-id="e1b28-219">DKE 서비스를 배포 하려면 다음 유형의 응용 프로그램 설정을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="e1b28-220">키 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="e1b28-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="e1b28-221">테 넌 트 및 키 설정</span><span class="sxs-lookup"><span data-stu-id="e1b28-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="e1b28-222">파일의 appsettings.js에서 응용 프로그램 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="e1b28-223">이 파일은 DoubleKeyEncryptionService\src\customer-key-store.에서 로컬로 복제 한 DoubleKeyEncryptionService 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="e1b28-224">예를 들어 Visual Studio Code에서는 다음 그림과 같이 파일을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="DKE 용 파일에서 appsettings.js찾기":::

#### <a name="key-access-settings"></a><span data-ttu-id="e1b28-226">키 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="e1b28-226">Key access settings</span></span>

<span data-ttu-id="e1b28-227">전자 메일 또는 역할 인증을 사용할지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="e1b28-228">DKE에서는 이러한 인증 방법 중 하나를 한 번에 하나만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="e1b28-229">**전자 메일 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="e1b28-229">**Email authorization**.</span></span> <span data-ttu-id="e1b28-230">조직에서 전자 메일 주소만 기반으로 하는 키에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="e1b28-231">**역할 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="e1b28-231">**Role authorization**.</span></span> <span data-ttu-id="e1b28-232">조직에서 Active Directory 그룹을 기반으로 하는 키에 대 한 액세스 권한을 부여 하 고, 웹 서비스가 LDAP를 쿼리할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="e1b28-233">DKE에 대 한 키 액세스 설정을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-233">To set key access settings for DKE:</span></span>

1. <span data-ttu-id="e1b28-234">파일 **의appsettings.js** 에서 다음 설정 중 하나만 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-234">In the **appsettings.json** file, define only one of these settings:</span></span>

   - <span data-ttu-id="e1b28-235">전자 메일 인증을 위해 **AuthorizedEmailAddresses** 설정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-235">For email authorization, locate the **AuthorizedEmailAddresses** setting.</span></span> <span data-ttu-id="e1b28-236">권한을 부여 하려는 전자 메일 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-236">Add the email address that you want to authorize.</span></span> <span data-ttu-id="e1b28-237">여러 전자 메일 주소는 큰따옴표와 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="e1b28-238">예: **"' AuthorizedEmailAddresses '": ["email1@company.com", "email2@company.com", email3@company.com]**</span><span class="sxs-lookup"><span data-stu-id="e1b28-238">For example: **" ‘AuthorizedEmailAddresses’ ": ["email1@company.com", "email2@company.com ", email3@company.com]**</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="전자 메일 인증 방법을 보여 주는 파일에appsettings.js":::

   - <span data-ttu-id="e1b28-240">역할 권한 부여에 대해 **AuthorizedRoles** 설정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-240">For role authorization, locate the **AuthorizedRoles** setting.</span></span> <span data-ttu-id="e1b28-241">권한을 부여 하려는 ActiveDirectory 그룹 이름을 사용 하 여 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-241">Define with the ActiveDirectory group names you want to authorize.</span></span> <span data-ttu-id="e1b28-242">예: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span><span class="sxs-lookup"><span data-stu-id="e1b28-242">For example: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="역할 인증 방법을 보여 주는 파일의appsettings.js":::

2. <span data-ttu-id="e1b28-244">선택한 인증 방법에 해당 하지 않는 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-244">Remove the setting that isn't relevant for your chosen authorization method.</span></span>

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="e1b28-245">테 넌 트 및 키 설정</span><span class="sxs-lookup"><span data-stu-id="e1b28-245">Tenant and key settings</span></span>

<span data-ttu-id="e1b28-246">DKE 테 넌 트 및 키 설정은 파일 **의appsettings.js** 및 **startup.cs** 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-246">DKE tenant and key settings are located in the **appsettings.json** file and the **startup.cs** file.</span></span>

<span data-ttu-id="e1b28-247">파일의 **appsettings.js** 에서 다음 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-247">In the **appsettings.json** file, modify the following values:</span></span>

- <span data-ttu-id="e1b28-248">**ValidIssuers**</span><span class="sxs-lookup"><span data-stu-id="e1b28-248">**ValidIssuers**.</span></span> <span data-ttu-id="e1b28-249">`<tenantid>`테 넌 트 GUID로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-249">Replace `<tenantid>` with your tenant GUID.</span></span>
- <span data-ttu-id="e1b28-250">**JwtAudience**</span><span class="sxs-lookup"><span data-stu-id="e1b28-250">**JwtAudience**.</span></span> <span data-ttu-id="e1b28-251">`<yourhostname>`DKE 서비스가 실행 될 컴퓨터의 호스트 이름으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-251">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e1b28-252">JwtAudience의 값은 호스트의 이름과 *정확히*일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-252">The value for JwtAudience must match the name of your host *exactly*.</span></span> <span data-ttu-id="e1b28-253">디버깅 하는 동안 **localhost: 5000** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-253">You may use **localhost:5000** while debugging.</span></span> <span data-ttu-id="e1b28-254">그러나 디버깅이 완료 되 면이 값을 서버의 호스트 이름으로 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-254">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="e1b28-255">**LDAPPath**</span><span class="sxs-lookup"><span data-stu-id="e1b28-255">**LDAPPath**.</span></span> <span data-ttu-id="e1b28-256">값을 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-256">Set the value as follows:</span></span>

  - <span data-ttu-id="e1b28-257">역할 인증을 사용 중인 경우에는 LDAP 도메인을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-257">If you're using role authorization, enter the LDAP domain.</span></span>
  - <span data-ttu-id="e1b28-258">전자 메일 권한 부여를 사용 중인 경우에는이 값을 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-258">If you're using email authorization, leave this value empty.</span></span>

   <span data-ttu-id="e1b28-259">자세한 내용은 [키 액세스 설정을](#key-access-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1b28-259">For more information, see [Key access settings](#key-access-settings).</span></span>

- <span data-ttu-id="e1b28-260">**Testkeys: 이름**입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-260">**TestKeys:Name**.</span></span> <span data-ttu-id="e1b28-261">키의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-261">Enter a name for your key.</span></span> <span data-ttu-id="e1b28-262">예: **TestKey1**</span><span class="sxs-lookup"><span data-stu-id="e1b28-262">Example: **TestKey1**</span></span>
- <span data-ttu-id="e1b28-263">**Testkeys: Id** GUID를 만들고 **Testkeys: ID** 값으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-263">**TestKeys:Id**. Create a GUID and enter it as the **TestKeys:ID** value.</span></span> <span data-ttu-id="e1b28-264">예: **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span><span class="sxs-lookup"><span data-stu-id="e1b28-264">For example, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span></span> <span data-ttu-id="e1b28-265">[온라인 Guid 생성기](https://guidgenerator.com/) 와 같은 사이트를 사용 하 여 GUID를 임의로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-265">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

### <a name="generate-test-keys"></a><span data-ttu-id="e1b28-266">테스트 키 생성</span><span class="sxs-lookup"><span data-stu-id="e1b28-266">Generate test keys</span></span>

<span data-ttu-id="e1b28-267">응용 프로그램 설정을 정의한 후에는 공용 및 개인 테스트 키를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-267">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="e1b28-268">키를 생성 하려면</span><span class="sxs-lookup"><span data-stu-id="e1b28-268">To generate keys:</span></span>

1. <span data-ttu-id="e1b28-269">Windows 시작 메뉴에서 OpenSSL 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-269">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="e1b28-270">테스트 키를 저장할 폴더로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-270">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="e1b28-271">이 작업의 단계를 완료 하 여 만든 파일은 동일한 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-271">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="e1b28-272">새 테스트 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-272">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="e1b28-273">개인 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-273">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="e1b28-274">공개 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-274">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="e1b28-275">텍스트 편집기에서 **pubkeyonly**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-275">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="e1b28-276">첫 번째 및 마지막 줄을 제외한 **pubkeyonly. pem** 파일의 모든 콘텐츠를 파일 **의appsettings.js** **publicpem** 섹션에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-276">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the **PublicPem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="e1b28-277">텍스트 편집기에서 **privkeynopass**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-277">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="e1b28-278">**Privkeynopass** 파일에서 첫 번째 줄을 제외한 모든 콘텐츠를 파일의 **appsettings.js** **PrivatePem** 섹션에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-278">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the **PrivatePem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="e1b28-279">**Publicpem** 및 **PrivatePem** 섹션에서 공백 및 newlines를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-279">Remove all blank spaces and newlines in both the **PublicPem** and **PrivatePem** sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e1b28-280">이 콘텐츠를 복사할 때는 PEM 데이터를 삭제 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e1b28-280">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="e1b28-281">**Startup.cs** 파일을 열고 다음 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-281">Open the **Startup.cs** file, and locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

1. <span data-ttu-id="e1b28-282">다음 텍스트를이 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-282">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="e1b28-283">최종 결과는 다음 그림과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-283">The end results should look similar to the following picture.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="공용 미리 보기용 startup.cs 파일":::

<span data-ttu-id="e1b28-285">이제 [DKE 프로젝트를 빌드할](#build-the-project)준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-285">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="e1b28-286">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="e1b28-286">Build the project</span></span>

<span data-ttu-id="e1b28-287">다음 지침을 사용 하 여 DKE 프로젝트를 로컬로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-287">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="e1b28-288">Visual Studio Code의 dke 서비스 저장소에서 **View** \> **명령 색상표** 보기를 선택 하 고 프롬프트에서 **빌드** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-288">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="e1b28-289">목록에서 **작업: 빌드 작업 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-289">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="e1b28-290">빌드 작업을 찾을 수 없는 경우에는 **빌드 작업 구성을** 선택 하 고 다음과 같이 .net core에 대해 create build tasks를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-290">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text=".NET에 대 한 누락 된 빌드 작업 구성":::

   1. <span data-ttu-id="e1b28-292">**서식 파일에서 tasks.js만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-292">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="DKE 템플릿의 파일에서 tasks.js만들기":::

   2. <span data-ttu-id="e1b28-294">템플릿 유형 목록에서 **.Net Core**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-294">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="DKE 템플릿의 파일에서 tasks.js만들기":::

   3. <span data-ttu-id="e1b28-296">빌드 섹션에서 **customerkeystore** 파일의 경로를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-296">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="e1b28-297">여기에 해당 하지 않으면 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-297">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="e1b28-298">빌드를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-298">Run the build again.</span></span>

1. <span data-ttu-id="e1b28-299">출력 창에 빨간색 오류가 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-299">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="e1b28-300">빨간색 오류가 있으면 콘솔 출력을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-300">If there are red errors, check the console output.</span></span> <span data-ttu-id="e1b28-301">이전 단계를 모두 올바르게 완료 했으며 올바른 빌드 버전이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-301">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

1. <span data-ttu-id="e1b28-302">**실행** \> **디버깅을 시작** 하 여 프로세스를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-302">**Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="e1b28-303">환경을 선택 하 라는 메시지가 표시 되 면 **.net core**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-303">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="e1b28-304">일반적으로 .NET 핵심 디버거가 시작 **https://localhost:5001** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-304">The .NET core debugger typically launches to **https://localhost:5001**.</span></span> <span data-ttu-id="e1b28-305">테스트 키를 보려면으로 이동 하 여 **https://localhost:5001** 슬래시 (/)와 키 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-305">To view your test key, go to **https://localhost:5001**, and append a forward slash (/) and the name of your key.</span></span>

<span data-ttu-id="e1b28-306">예를 들어:**https://localhost:5001/TestKey1**</span><span class="sxs-lookup"><span data-stu-id="e1b28-306">For example: **https://localhost:5001/TestKey1**</span></span>

<span data-ttu-id="e1b28-307">키가 JSON 형식으로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-307">The key should display in JSON format.</span></span>

<span data-ttu-id="e1b28-308">이제 설치가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-308">Your setup is now complete.</span></span> <span data-ttu-id="e1b28-309">Keystore를 게시 하기 전에 JwtAudience 설정에 대 한 appsettings.json에서 호스트 값이 앱 서비스 호스트 이름과 정확히 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-309">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="e1b28-310">빌드 문제를 해결 하기 위해 localhost로 변경 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-310">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="e1b28-311">키 저장소 게시</span><span class="sxs-lookup"><span data-stu-id="e1b28-311">Publish the key store</span></span>

<span data-ttu-id="e1b28-312">다음 단계에서는 Azure App Service 인스턴스를 만들어 DKE 배포를 호스팅하고, 생성 된 키를 Azure에 게시 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-312">The following steps describe how to create an Azure App Service instance to host your DKE deployment, and how to publish your generated keys to Azure.</span></span>

<span data-ttu-id="e1b28-313">DKE 배포를 호스트 하는 Azure Web App 인스턴스를 만들려면:</span><span class="sxs-lookup"><span data-stu-id="e1b28-313">To create an Azure Web App instance to host your DKE deployment:</span></span>

1. <span data-ttu-id="e1b28-314">브라우저에서 [Microsoft Azure 포털](https://ms.portal.azure.com)에 로그인 하 고 **앱 서비스**  >  **추가**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-314">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="e1b28-315">구독 및 리소스 그룹을 선택 하 고 인스턴스 세부 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-315">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="e1b28-316">DKE 서비스를 설치 하려는 컴퓨터의 호스트 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-316">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="e1b28-317">파일 [**의appsettings.js**](#tenant-and-key-settings) 에서 JwtAudience 설정에 대해 정의 된 이름과 이름이 같은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-317">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="e1b28-318">이름에 입력 하는 값은 WebAppInstanceName입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-318">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="e1b28-319">**게시**에서 **코드**를 선택 하 고 **런타임 스택을**보려면 **.net Core 3.1**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-319">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="e1b28-320">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-320">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="앱 서비스 추가":::

1. <span data-ttu-id="e1b28-322">페이지 맨 아래에서 **검토 + 만들기**를 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-322">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="e1b28-323">다음 중 하나를 수행 하 여 생성 된 키를 Azure에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-323">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="e1b28-324">ZipDeployUI를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="e1b28-324">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="e1b28-325">FTP를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="e1b28-325">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="e1b28-326">Visual Studio 2019 이상 버전을 통해 게시</span><span class="sxs-lookup"><span data-stu-id="e1b28-326">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="e1b28-327">온-프레미스 시스템에 게시</span><span class="sxs-lookup"><span data-stu-id="e1b28-327">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="e1b28-328">다른 방법으로 키를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-328">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="e1b28-329">조직에 가장 적합 한 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-329">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="e1b28-330">[Visual Studio를 통해](https://docs.microsoft.com/aspnet/core/tutorials/) [온-프레미스 시스템](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) 에 게시 하는 방법에 대 한 자세한 내용은 [ASP .net 설명서](https://docs.microsoft.com/aspnet/core/)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1b28-330">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="e1b28-331">이러한 방법 중 하나를 사용 하는 경우에는 작업을 마친 후 쉽게 반환할 수 있도록 별도의 탭에서 명령을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-331">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="e1b28-332">ZipDeployUI를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="e1b28-332">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="e1b28-333">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-333">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="e1b28-334">예: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e1b28-334">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="e1b28-335">키 저장소의 코드 베이스에서 **customer-key-store\src\customer-key-store** 폴더로 이동 하 여이 폴더에 **customerkeystore** 파일이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-335">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="e1b28-336">실행: **dotnet 게시**</span><span class="sxs-lookup"><span data-stu-id="e1b28-336">Run: **dotnet publish**</span></span>

     <span data-ttu-id="e1b28-337">출력 창에는 게시가 배포 된 디렉터리가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-337">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="e1b28-338">예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="e1b28-338">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="e1b28-339">게시 디렉터리의 모든 파일을 .zip 파일로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-339">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="e1b28-340">.Zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 파일의 루트 수준에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-340">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="e1b28-341">위에서 연 ZipDeployUI 사이트에 만든 .zip 파일을 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-341">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="e1b28-342">예: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e1b28-342">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="e1b28-343">DKE가 배포 되었으며 만든 테스트 키로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-343">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="e1b28-344">아래에서 [배포에 대 한 유효성 검사](#validate-your-deployment) 를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-344">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="e1b28-345">FTP를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="e1b28-345">Publish via FTP</span></span>

1. <span data-ttu-id="e1b28-346">[위에서](#publish-the-key-store)만든 앱 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-346">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="e1b28-347">브라우저에서 **Azure portal**  >  **App Service**  >  **배포 센터**  >  **수동 배포**  >  **FTP**  >  **대시보드로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-347">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="e1b28-348">로컬 파일에 표시 되는 연결 문자열을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-348">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="e1b28-349">이러한 문자열을 사용 하 여 웹 앱 서비스에 연결 하 고 FTP를 통해 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-349">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="e1b28-350">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-350">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="FTP 대시보드에서 연결 문자열 복사":::

1. <span data-ttu-id="e1b28-352">키 저장소의 코드 베이스에서 **customer-key-store\src\customer-key-store 디렉터리로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-352">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="e1b28-353">이 디렉터리에 **customerkeystore** 파일이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-353">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="e1b28-354">실행: **dotnet 게시**</span><span class="sxs-lookup"><span data-stu-id="e1b28-354">Run: **dotnet publish**</span></span>

    <span data-ttu-id="e1b28-355">출력에는 게시가 배포 된 디렉터리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-355">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="e1b28-356">예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="e1b28-356">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="e1b28-357">게시 디렉터리의 모든 파일을 zip 파일로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-357">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="e1b28-358">.Zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 파일의 루트 수준에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-358">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="e1b28-359">FTP 클라이언트에서 복사한 연결 정보를 사용 하 여 앱 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-359">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="e1b28-360">이전 단계에서 만든 .zip 파일을 웹 응용 프로그램의 루트 디렉터리에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-360">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="e1b28-361">DKE가 배포 되었으며 만든 테스트 키로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-361">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="e1b28-362">다음으로, [배포 유효성을 검사](#validate-your-deployment)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-362">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="e1b28-363">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e1b28-363">Validate your deployment</span></span>

<span data-ttu-id="e1b28-364">위에 설명 된 방법 중 하나를 사용 하 여 DKE를 배포한 후에는 배포 및 키 저장소 설정의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-364">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="e1b28-365">를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-365">Run:</span></span>

<span data-ttu-id="e1b28-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeymykey url/</span><span class="sxs-lookup"><span data-stu-id="e1b28-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="e1b28-367">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-367">For example:</span></span>

<span data-ttu-id="e1b28-368">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="e1b28-368">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="e1b28-369">출력에 오류가 표시 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-369">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="e1b28-370">준비 되 면 [키 저장소를 등록](#register-your-key-store)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-370">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="e1b28-371">키 저장소 등록</span><span class="sxs-lookup"><span data-stu-id="e1b28-371">Register your key store</span></span>

<span data-ttu-id="e1b28-372">다음 단계를 수행 하면 키 저장소를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-372">The following steps enable you to register your key store.</span></span> <span data-ttu-id="e1b28-373">레이블 만들기를 시작 하기 전에 키 저장소를 등록 하는 것은 DKE를 배포 하는 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-373">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="e1b28-374">키 저장소를 등록 하려면:</span><span class="sxs-lookup"><span data-stu-id="e1b28-374">To register your key store:</span></span>

1. <span data-ttu-id="e1b28-375">브라우저에서 [Microsoft Azure portal](https://ms.portal.azure.com/)을 열고 **모든 서비스** \> **id** \> **앱 등록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-375">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="e1b28-376">**새 등록**을 선택 하 고 의미 있는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-376">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="e1b28-377">표시 된 옵션에서 계정 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-377">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="e1b28-378">사용자 지정 하지 않은 도메인 (예: **onmicrosoft.com**)에서 Microsoft Azure를 사용 하는 경우 **에는이 조직 디렉터리의 계정만 선택 합니다 (Microsoft only 단일 테 넌 트).**</span><span class="sxs-lookup"><span data-stu-id="e1b28-378">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="e1b28-379">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-379">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="새 앱 등록":::

4. <span data-ttu-id="e1b28-381">페이지 맨 아래에서 **등록** 을 선택 하 여 새 앱 등록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-381">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="e1b28-382">새 앱 등록의 왼쪽 창에 있는 **관리**에서 **인증**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-382">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="e1b28-383">**플랫폼 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-383">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="e1b28-384">**플랫폼 구성** 팝업에서 **웹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-384">On the **Configure platforms** popup select **Web**.</span></span>
 
8. <span data-ttu-id="e1b28-385">**리디렉션 uri** 에서 이중 키 암호화 서비스의 URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-385">Under **Redirect URIs** enter the URI of your double key encryption service.</span></span> <span data-ttu-id="e1b28-386">호스트 이름 및 도메인을 포함 하 여 앱 서비스 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-386">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="e1b28-387">예: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="e1b28-387">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="e1b28-388">입력 하는 URL은 키 저장소가 배포 된 호스트 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-388">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="e1b28-389">Visual Studio를 사용 하 여 로컬로 테스트 하는 경우를 사용 **https://localhost:5001** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-389">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="e1b28-390">모든 경우에 스키마는 **https**여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-390">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="e1b28-391">호스트 이름이 앱 서비스 호스트 이름과 정확히 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-391">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="e1b28-392">빌드 문제를 해결 하기 위해 localhost로 변경 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-392">You may have changed it to localhost to troubleshoot the build.</span></span> <span data-ttu-id="e1b28-393">appsettings.js에서이는 JwtAudience 설정에 대 한 값으로 식별 된 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-393">In appsettings.json, this is the hostname you identified as the value for the JwtAudience setting.</span></span>

6. <span data-ttu-id="e1b28-394">**암시적 권한 부여**에서 **ID 토큰** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-394">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="e1b28-395">변경 내용을 저장하려면 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-395">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="e1b28-396">왼쪽 창에서 **API 노출**을 선택한 다음 응용 프로그램 ID URI 옆에 있는 **설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-396">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="e1b28-397">여전히 **Api 노출** 페이지의 **이 API** 영역에 정의 된 범위에서 **범위 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-397">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="e1b28-398">새 범위에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-398">In the new scope:</span></span>

    1. <span data-ttu-id="e1b28-399">범위 이름을 **user_impersonation**로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-399">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="e1b28-400">동의할 수 있는 관리자 및 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-400">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="e1b28-401">필요한 나머지 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-401">Define any remaining values required.</span></span>

    4. <span data-ttu-id="e1b28-402">**범위 추가를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1b28-402">Select **Add scope.**</span></span>

    <span data-ttu-id="e1b28-403">맨 위에 있는 **저장** 을 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-403">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="e1b28-404">여전히 **API 노출** 페이지의 **권한 있는 클라이언트 응용 프로그램** 영역에서 **클라이언트 응용 프로그램 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-404">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="e1b28-405">새 클라이언트 응용 프로그램에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-405">In the new client application:</span></span>

    1. <span data-ttu-id="e1b28-406">클라이언트 ID를 **d3590ed6-52b3-4102-aeff-aad2292ab01c**으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-406">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="e1b28-407">이 값은 Microsoft Office 클라이언트 ID 이며 Office에서 키 저장소에 대 한 액세스 토큰을 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-407">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="e1b28-408">**권한 있는 범위**에서 **user_impersonation** 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-408">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="e1b28-409">**응용 프로그램 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-409">Select **Add application**.</span></span>

    4. <span data-ttu-id="e1b28-410">맨 위에 있는 **저장** 을 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-410">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="e1b28-411">이제 DKE 키 저장소가 등록 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-411">Your DKE key store is now registered.</span></span> <span data-ttu-id="e1b28-412">계속 [하 여 DKE를 사용 하 여 레이블을 만듭니다](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="e1b28-412">Continue  by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="e1b28-413">DKE을 사용 하 여 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="e1b28-413">Create labels using DKE</span></span>

<span data-ttu-id="e1b28-414">키 저장소를 등록 한 후에는 Microsoft 365 준수 센터에서 민감도 레이블을 설정 하 고 레이블에 이중 키 암호화를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-414">Once you've registered your key store, set up sensitivity labels in the Microsoft 365 compliance center and apply double key encryption to those labels.</span></span>

<span data-ttu-id="e1b28-415">레이블 생성 UI에서 **이중 키 암호화 사용** 옵션을 선택 하 고 키에 대 한 끝점 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-415">In the label creation UI, select the **Use Double Key Encryption** option and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="e1b28-416">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-416">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Microsoft 365 준수 센터에서 이중 키 암호화 사용을 선택 합니다.":::

<span data-ttu-id="e1b28-418">추가 하는 모든 DKE 레이블은 최신 버전의 Microsoft 365 Apps for enterprise의 사용자에 게 표시 되기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-418">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="e1b28-419">클라이언트가 새 레이블로 새로 고치는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-419">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="e1b28-420">클라이언트에서 DKE 사용</span><span class="sxs-lookup"><span data-stu-id="e1b28-420">Enable DKE in your client</span></span>

<span data-ttu-id="e1b28-421">Microsoft Office의 민감도 리본 아래에 DKE 레이블이 나타나지 않으면 클라이언트에서 DKE가 사용 하도록 설정 되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-421">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="e1b28-422">다음 레지스트리 키를 추가 하 여 클라이언트에 대해 DKE를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b28-422">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
