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
ms.openlocfilehash: 0c66afa22c8712455a875bc8ca4ddcad1678e2e7
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602001"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="a01a3-103">DKE (이중 암호화)</span><span class="sxs-lookup"><span data-stu-id="a01a3-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="a01a3-104">*적용 대상: Microsoft 365 공개 미리 보기, [microsoft 365 준수](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection) 에 대 한 이중 암호화*</span><span class="sxs-lookup"><span data-stu-id="a01a3-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="a01a3-105">*지침: [Azure Information Protection 통합 레이블 클라이언트 Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="a01a3-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="a01a3-106">*서비스 설명: [Microsoft 365 준수](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="a01a3-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="a01a3-107">DKE (이중 암호화)에서는 보호 된 콘텐츠에 액세스 하기 위해 두 개의 키를 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="a01a3-108">Microsoft Azure에 하나의 키를 저장 하 고 다른 키를 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="a01a3-109">Azure Information Protection 통합 레이블 클라이언트는 중요 한 콘텐츠를 보호 하지만 키 중 하나에 대 한 모든 권한을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="a01a3-110">이중 키 암호화는 클라우드 및 온-프레미스 배포를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="a01a3-111">이러한 배포를 통해 보호 된 데이터를 저장할 때마다 암호화 된 데이터를 불투명 하 게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="a01a3-112">클라우드 기반 테 넌 트 루트 키의 기본에 대 한 자세한 내용은 [Azure Information Protection 테 넌 트 키 계획 및 구현](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a01a3-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

<span data-ttu-id="a01a3-113">조직에 다음과 같은 요구 사항이 있는 경우 DKE를 사용 하 여 콘텐츠를 안전 하 게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-113">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="a01a3-114">모든 상황에서 보호 된 콘텐츠의 암호를 *해독할 수 있도록* 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-114">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="a01a3-115">Microsoft가 보호 된 데이터에 자체 액세스 하지 못하도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="a01a3-115">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="a01a3-116">지리적 경계 내에 키를 포함 하기 위한 규정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-116">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="a01a3-117">데이터 암호화 및 암호 해독을 위해 보유 하는 모든 키가 데이터 센터에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-117">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="a01a3-118">DKE에 대 한 시스템 및 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a01a3-118">System and licensing requirements for DKE</span></span>

<span data-ttu-id="a01a3-119">Microsoft 365에 대 한 이중 키 암호화는 Microsoft 365 E5와 Office 365 E5와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-119">Double Key Encryption for Microsoft 365 comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="a01a3-120">Microsoft 365 E5 라이선스가 없는 경우 [평가판](https://aka.ms/M365E5ComplianceTrial)에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-120">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="a01a3-121">이러한 라이선스에 대 한 자세한 내용은 [보안 & 준수에 대 한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a01a3-121">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="a01a3-122">**Office 참가자** 공개 미리 보기를 사용 하려면 Office 참가자 프로그램의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-122">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="a01a3-123">Office 참가자에 게 연결 하려면로 이동 [https://insider.office.com](https://insider.office.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-123">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="a01a3-124">구성원 인 경우 조직에 적합 한 배포 방법을 선택 하 여 Office 참가자 빌드를 배포할 수 있도록 환경을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-124">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="a01a3-125">자세한 내용은 [Office 참가자 빌드 배포 시작](https://insider.office.com/business/deploy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a01a3-125">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="a01a3-126">**Azure Information Protection**</span><span class="sxs-lookup"><span data-stu-id="a01a3-126">**Azure Information Protection**.</span></span> <span data-ttu-id="a01a3-127">DKE는 민감도 레이블에서 작동 하며 Azure Information Protection을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-127">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="a01a3-128">DKE로 보호 된 콘텐츠를 저장 하 고 보기 위한 지원 되는 환경</span><span class="sxs-lookup"><span data-stu-id="a01a3-128">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="a01a3-129">**지원 되는 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="a01a3-129">**Supported applications**.</span></span> <span data-ttu-id="a01a3-130">Word, Excel 및 PowerPoint를 포함 하는 Windows의 [엔터프라이즈 클라이언트용 Microsoft 365 앱](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)</span><span class="sxs-lookup"><span data-stu-id="a01a3-130">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="a01a3-131">**온라인 콘텐츠 지원**</span><span class="sxs-lookup"><span data-stu-id="a01a3-131">**Online content support**.</span></span> <span data-ttu-id="a01a3-132">Microsoft SharePoint 및 비즈니스용 OneDrive에 모두 온라인으로 저장 된 문서 및 파일을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-132">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="a01a3-133">전자 메일로 암호화 된 콘텐츠를 공유할 수 있지만 암호화 된 문서 및 파일은 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-133">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="a01a3-134">대신 로컬 컴퓨터의 데스크톱 앱을 사용 하 여 보호 된 콘텐츠를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-134">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="a01a3-135">이 공개 미리 보기 문서 정보</span><span class="sxs-lookup"><span data-stu-id="a01a3-135">About this public preview article</span></span>

<span data-ttu-id="a01a3-136">몇 가지 단계를 완료 하 여 이중 암호화를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-136">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="a01a3-137">이 문서에서는 숙련 된 관리자가 서비스를 성공적으로 배포 하는 데 필요한 자세한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-137">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="a01a3-138">이렇게 하는 것이 어려우면 사용자가 직접 메서드를 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-138">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="a01a3-139">이 문서에서는 Azure에 이중 키 암호화 서비스를 배포 하는 방법에 대 한 단계별 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-139">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="a01a3-140">이 시나리오는 프로덕션 환경에서 발생할 수 있는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-140">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="a01a3-141">공개 미리 보기의 경우 Azure를 사용 하는 것이 DKE를 빠르게 배포 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-141">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="a01a3-142">Azure에 배포 하면 이중 키 암호화를 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-142">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="a01a3-143">서비스를 네트워크에 로컬로 배포 하거나 다른 공급자와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-143">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="a01a3-144">해당 위치에 적합 한 방법을 사용 하 여 키 저장소를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-144">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="a01a3-145">이중 암호화 배포</span><span class="sxs-lookup"><span data-stu-id="a01a3-145">Deploy Double Key Encryption</span></span>

<span data-ttu-id="a01a3-146">이 문서와 배포 동영상은 Azure를 DKE 서비스의 배포 대상으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-146">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="a01a3-147">다른 위치에 배포 하는 경우에는 고유한 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-147">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="a01a3-148">[이중 키 암호화 배포 비디오](https://youtu.be/vDWfHN_kygg) 를 시청 문서의 개념에 대 한 단계별 개요를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a01a3-148">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="a01a3-149">완료 하는 데 약 18 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-149">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="a01a3-150">이러한 일반적인 단계를 수행 하 여 조직에 대 한 이중 암호화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-150">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="a01a3-151">소프트웨어 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="a01a3-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="a01a3-152">이중 키 암호화 GitHub 리포지토리 복제</span><span class="sxs-lookup"><span data-stu-id="a01a3-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="a01a3-153">응용 프로그램 설정 수정</span><span class="sxs-lookup"><span data-stu-id="a01a3-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="a01a3-154">테스트 키 생성</span><span class="sxs-lookup"><span data-stu-id="a01a3-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="a01a3-155">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="a01a3-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="a01a3-156">키 저장소 게시</span><span class="sxs-lookup"><span data-stu-id="a01a3-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="a01a3-157">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a01a3-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="a01a3-158">키 저장소 등록</span><span class="sxs-lookup"><span data-stu-id="a01a3-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="a01a3-159">민감도 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="a01a3-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="a01a3-160">작업이 완료 되 면 DKE을 사용 하 여 문서와 파일을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="a01a3-161">자세한 내용은 [Office에서 파일 및 전자 메일에 민감도 레이블 적용](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a01a3-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="a01a3-162">소프트웨어 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="a01a3-162">Install software prerequisites</span></span>

<span data-ttu-id="a01a3-163">이중 키 암호화에는 두 가지 유형의 소프트웨어 필수 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="a01a3-164">이중 키 암호화 서비스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a01a3-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="a01a3-165">클라이언트 컴퓨터에 대 한 이중 키 암호화 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a01a3-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="a01a3-166">이중 키 암호화 서비스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a01a3-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="a01a3-167">DKE 서비스를 설치 하려는 컴퓨터에 이러한 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="a01a3-168">**.Net Core 3.1 SDK**</span><span class="sxs-lookup"><span data-stu-id="a01a3-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="a01a3-169">[.Net Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)에서 SDK를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="a01a3-170">**Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="a01a3-170">**Visual Studio Code**.</span></span> <span data-ttu-id="a01a3-171">Visual Studio Code from을 다운로드 [https://code.visualstudio.com/](https://code.visualstudio.com) 하세요.</span><span class="sxs-lookup"><span data-stu-id="a01a3-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="a01a3-172">설치가 완료 되 면 Visual Studio Code를 실행 하 고 Extensions **보기** 를 선택 \> **Extensions**합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="a01a3-173">이러한 확장을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-173">Install these extensions.</span></span>

- <span data-ttu-id="a01a3-174">Visual Studio 코드용 c # 코드</span><span class="sxs-lookup"><span data-stu-id="a01a3-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="a01a3-175">NuGet 패키지 관리자</span><span class="sxs-lookup"><span data-stu-id="a01a3-175">NuGet Package Manager</span></span>

<span data-ttu-id="a01a3-176">**Microsoft Office 참가자**입니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="a01a3-177">[배포 방법을](https://insider.office.com/business/deploy)하나 이상 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="a01a3-178">**Git 리소스**</span><span class="sxs-lookup"><span data-stu-id="a01a3-178">**Git resources**.</span></span> <span data-ttu-id="a01a3-179">다음 중 하나를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="a01a3-180">Git</span><span class="sxs-lookup"><span data-stu-id="a01a3-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="a01a3-181">GitHub 데스크톱</span><span class="sxs-lookup"><span data-stu-id="a01a3-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="a01a3-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="a01a3-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="a01a3-183">**OpenSSL** DKE를 배포한 후 [테스트 키를 생성](#generate-test-keys) 하려면 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) 이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="a01a3-184">환경 변수 경로에서 올바르게 호출 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="a01a3-185">예를 들어 자세한 내용은 "설치 디렉터리를 PATH에 추가 합니다."를 참조 하십시오 https://www.osradar.com/install-openssl-windows/ .</span><span class="sxs-lookup"><span data-stu-id="a01a3-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="a01a3-186">클라이언트 컴퓨터에 대 한 이중 키 암호화 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a01a3-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="a01a3-187">보호 된 문서를 보호 하 고 사용 하려는 각 클라이언트 컴퓨터에 이러한 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="a01a3-188">**Microsoft Office** 버전 \*. 12711 이상</span><span class="sxs-lookup"><span data-stu-id="a01a3-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="a01a3-189">**Azure Information Protection 통합 레이블 클라이언트** 버전 2.7.93.0 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="a01a3-190">[Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)에서 통합 레이블 클라이언트를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="a01a3-191">DKE GitHub 리포지토리 복제</span><span class="sxs-lookup"><span data-stu-id="a01a3-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="a01a3-192">Microsoft는 GitHub 리포지토리에 DKE 원본 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="a01a3-193">조직의 사용을 위해 로컬로 프로젝트를 빌드하기 위해 리포지토리를 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="a01a3-194">DKE GitHub 리포지토리는에 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="a01a3-195">다음 지침은 inexperienced git 또는 Visual Studio Code 사용자에 게 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="a01a3-196">브라우저에서 다음 위치로 이동 합니다.[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="a01a3-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="a01a3-197">화면 오른쪽 방향으로 **코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="a01a3-198">사용자의 UI 버전에 **복제 또는 다운로드** 단추가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="a01a3-199">그런 다음 표시 되는 드롭다운 목록에서 복사 아이콘을 선택 하 여 클립보드에 URL을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="a01a3-200">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-200">For example:</span></span>

   ![GitHub에서 이중 키 암호화 서비스 리포지토리 복제](../media/dke-clone.png)

3. <span data-ttu-id="a01a3-202">Visual Studio Code에서 **View** \> **명령 색상표** 보기를 선택 하 고 **Git: 클론**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="a01a3-203">목록에서 옵션으로 이동 하려면 입력을 시작 하 여 `git: clone` 항목을 필터링 한 다음 드롭다운에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="a01a3-204">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-204">For example:</span></span>

   ![Visual Studio Code GIT: Clone 옵션](../media/dke-vscode-clone.png)

4. <span data-ttu-id="a01a3-206">Git에서 복사한 URL을 텍스트 상자에 붙여넣고 **GitHub에서 복제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="a01a3-207">**폴더 선택** 대화 상자가 나타나면 저장소를 저장할 위치를 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="a01a3-208">프롬프트에서 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="a01a3-209">Visual Studio Code에서 리포지토리를 열고 왼쪽 아래에 현재 Git 분기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="a01a3-210">분기는 **마스터**여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-210">The branch should be **master**.</span></span>

    <span data-ttu-id="a01a3-211">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-211">For example:</span></span>

   ![Visual Studio 코드 마스터 분기](../media/dke-vscode-master.png)

6. <span data-ttu-id="a01a3-213">Word **마스터를** 선택한 다음 분기 목록에서 **public_preview** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a01a3-214">Public_preview 분기를 선택 하면 프로젝트를 빌드하는 데 올바른 파일이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="a01a3-215">올바른 분기를 선택 하지 않으면 배포가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="a01a3-216">이제 DKE 원본 리포지토리가 로컬로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="a01a3-217">다음으로, 조직의 [응용 프로그램 설정을 수정](#modify-application-settings) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="a01a3-218">응용 프로그램 설정 수정</span><span class="sxs-lookup"><span data-stu-id="a01a3-218">Modify application settings</span></span>

<span data-ttu-id="a01a3-219">DKE 서비스를 배포 하려면 다음 유형의 응용 프로그램 설정을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="a01a3-220">키 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="a01a3-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="a01a3-221">테 넌 트 및 키 설정</span><span class="sxs-lookup"><span data-stu-id="a01a3-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="a01a3-222">파일의 appsettings.js에서 응용 프로그램 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="a01a3-223">이 파일은 DoubleKeyEncryptionService\src\customer-key-store.에서 로컬로 복제 한 DoubleKeyEncryptionService 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="a01a3-224">예를 들어 Visual Studio Code에서는 다음 그림과 같이 파일을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![DKE 용 파일에서 appsettings.js찾기](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="a01a3-226">키 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="a01a3-226">Key access settings</span></span>

<span data-ttu-id="a01a3-227">전자 메일 또는 역할 인증을 사용할지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="a01a3-228">DKE에서는 이러한 인증 방법 중 하나를 한 번에 하나만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="a01a3-229">**전자 메일 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="a01a3-229">**Email authorization**.</span></span> <span data-ttu-id="a01a3-230">조직에서 전자 메일 주소만 기반으로 하는 키에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="a01a3-231">**역할 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="a01a3-231">**Role authorization**.</span></span> <span data-ttu-id="a01a3-232">조직에서 Active Directory 그룹을 기반으로 하는 키에 대 한 액세스 권한을 부여 하 고, 웹 서비스가 LDAP를 쿼리할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="a01a3-233">**전자 메일 인증을 사용 하 여 DKE에 대 한 키 액세스 설정을 설정 하려면**</span><span class="sxs-lookup"><span data-stu-id="a01a3-233">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="a01a3-234">파일 **에서appsettings.js** 열고 `AuthorizedEmailAddress` 설정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-234">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="a01a3-235">권한을 부여 하려는 전자 메일 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-235">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="a01a3-236">여러 전자 메일 주소는 큰따옴표와 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-236">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="a01a3-237">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-237">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="a01a3-238">설정을 찾고 `LDAPPath` 큰따옴표 사이에 있는 텍스트를 제거 `If role authorization is used then this is the LDAP path` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-238">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="a01a3-239">큰따옴표를 자리에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-239">Leave the double quotes in place.</span></span> <span data-ttu-id="a01a3-240">작업이 완료 되 면 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-240">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="a01a3-241">설정을 찾아서 `AuthorizedRoles` 전체 줄을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-241">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="a01a3-242">이 이미지는 전자 메일 권한 부여를 위해 올바르게 형식이 지정 된 파일 **의appsettings.js** 를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-242">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![전자 메일 인증 방법을 보여 주는 appsettings.js파일](../media/dke-email-accesssetting.png)

<span data-ttu-id="a01a3-244">**역할 인증을 사용 하 여 DKE에 대 한 키 액세스 설정을 설정 하려면**</span><span class="sxs-lookup"><span data-stu-id="a01a3-244">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="a01a3-245">파일 **에서appsettings.js** 열고 `AuthorizedRoles` 설정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-245">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="a01a3-246">권한을 부여 하려는 Active Directory 그룹 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-246">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="a01a3-247">여러 그룹 이름은 큰따옴표와 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-247">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="a01a3-248">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-248">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="a01a3-249">설정을 찾고 `LDAPPath` Active Directory 도메인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-249">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="a01a3-250">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-250">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="a01a3-251">설정을 찾아서 `AuthorizedEmailAddress` 전체 줄을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-251">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="a01a3-252">이 이미지는 역할 권한 부여를 위해 올바르게 형식이 지정 된 파일 **의appsettings.js** 를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-252">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![역할 인증 방법을 보여 주는 파일의 appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="a01a3-254">테 넌 트 및 키 설정</span><span class="sxs-lookup"><span data-stu-id="a01a3-254">Tenant and key settings</span></span>

<span data-ttu-id="a01a3-255">DKE 테 넌 트 및 키 설정은 파일 **의appsettings.js** 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-255">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="a01a3-256">**DKE에 대 한 테 넌 트 및 키 설정을 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="a01a3-256">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="a01a3-257">파일 **에서appsettings.js** 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-257">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="a01a3-258">설정을 찾은 `ValidIssuers` 후 `<tenantid>` 테 넌 트 ID로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-258">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="a01a3-259">Azure 포털로 이동 하 여 [테 넌 트 속성](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)을 확인 하 여 테 넌 트 ID를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-259">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="a01a3-260">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-260">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="a01a3-261">를 찾습니다 `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="a01a3-261">Locate the `JwtAudience`.</span></span> <span data-ttu-id="a01a3-262">`<yourhostname>`DKE 서비스가 실행 될 컴퓨터의 호스트 이름으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-262">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="a01a3-263">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-263">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="a01a3-264">값은 `JwtAudience` 호스트 이름과 *정확히*일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-264">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="a01a3-265">디버깅 하는 동안 **localhost: 5001** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-265">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="a01a3-266">그러나 디버깅이 완료 되 면이 값을 서버의 호스트 이름으로 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-266">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="a01a3-267">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="a01a3-267">`TestKeys:Name`.</span></span> <span data-ttu-id="a01a3-268">키의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-268">Enter a name for your key.</span></span> <span data-ttu-id="a01a3-269">예: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="a01a3-269">For example: `TestKey1`</span></span>
- <span data-ttu-id="a01a3-270">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="a01a3-270">`TestKeys:Id`.</span></span> <span data-ttu-id="a01a3-271">GUID를 만들어 값으로 입력 `TestKeys:ID` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-271">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="a01a3-272">예를 들면 `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-272">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="a01a3-273">[온라인 Guid 생성기](https://guidgenerator.com/) 와 같은 사이트를 사용 하 여 GUID를 임의로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-273">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="a01a3-274">**appsettings.js**의 테 넌 트 및 키 설정에 대 한 올바른 형식을 표시 하는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-274">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="a01a3-275">`LDAPPath`역할 인증에 대해 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-275">`LDAPPath` is configured for role authorization.</span></span>

![파일의 appsettings.js에 있는 DKE에 대 한 올바른 테 넌 트 및 키 설정을 표시 합니다.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="a01a3-277">테스트 키 생성</span><span class="sxs-lookup"><span data-stu-id="a01a3-277">Generate test keys</span></span>

<span data-ttu-id="a01a3-278">응용 프로그램 설정을 정의한 후에는 공용 및 개인 테스트 키를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-278">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="a01a3-279">키를 생성 하려면</span><span class="sxs-lookup"><span data-stu-id="a01a3-279">To generate keys:</span></span>

1. <span data-ttu-id="a01a3-280">Windows 시작 메뉴에서 OpenSSL 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-280">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="a01a3-281">테스트 키를 저장할 폴더로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-281">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="a01a3-282">이 작업의 단계를 완료 하 여 만든 파일은 동일한 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-282">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="a01a3-283">새 테스트 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-283">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="a01a3-284">개인 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-284">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="a01a3-285">공개 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-285">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="a01a3-286">텍스트 편집기에서 **pubkeyonly**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-286">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="a01a3-287">파일의appsettings.js섹션에 있는 첫 번째 행과 마지막 줄을 제외한 **pubkeyonly pem** 파일의 모든 콘텐츠를 복사 합니다. `PublicPem` **appsettings.json**</span><span class="sxs-lookup"><span data-stu-id="a01a3-287">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="a01a3-288">텍스트 편집기에서 **privkeynopass**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-288">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="a01a3-289">**Privkeynopass** 파일에서 첫 번째 줄을 제외한 모든 콘텐츠를 `PrivatePem` 파일 **의appsettings.js** 섹션에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-289">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="a01a3-290">및 섹션 모두에서 공백 및 newlines를 모두 `PublicPem` 제거 `PrivatePem` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-290">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a01a3-291">이 콘텐츠를 복사할 때는 PEM 데이터를 삭제 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a01a3-291">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="a01a3-292">Visual Studio Code에서 **Startup.cs** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-292">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="a01a3-293">이 파일은 DoubleKeyEncryptionService\src\customer-key-store\.에서 로컬로 복제 한 DoubleKeyEncryptionService 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-293">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="a01a3-294">다음 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-294">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="a01a3-295">다음 텍스트를이 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-295">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="a01a3-296">최종 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-296">The end results should look similar to the following.</span></span>

   ![공용 미리 보기용 startup.cs 파일](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="a01a3-298">이제 [DKE 프로젝트를 빌드할](#build-the-project)준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-298">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="a01a3-299">프로젝트 빌드</span><span class="sxs-lookup"><span data-stu-id="a01a3-299">Build the project</span></span>

<span data-ttu-id="a01a3-300">다음 지침을 사용 하 여 DKE 프로젝트를 로컬로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-300">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="a01a3-301">Visual Studio Code의 dke 서비스 저장소에서 **View** \> **명령 색상표** 보기를 선택 하 고 프롬프트에서 **빌드** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-301">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="a01a3-302">목록에서 **작업: 빌드 작업 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-302">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="a01a3-303">빌드 작업을 찾을 수 없는 경우에는 **빌드 작업 구성을** 선택 하 고 다음과 같이 .net core에 대해 create build tasks를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-303">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![.NET에 대 한 누락 된 빌드 작업 구성](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="a01a3-305">**서식 파일에서 tasks.js만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-305">Choose **Create tasks.json from template**.</span></span>

   ![DKE 템플릿의 파일에서 tasks.js만들기](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="a01a3-307">템플릿 유형 목록에서 **.Net Core**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-307">From the list of template types, select **.NET Core**.</span></span>

   ![DKE 템플릿의 파일에서 tasks.js만들기](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="a01a3-309">빌드 섹션에서 **customerkeystore** 파일의 경로를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-309">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="a01a3-310">여기에 해당 하지 않으면 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-310">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="a01a3-311">빌드를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-311">Run the build again.</span></span>

1. <span data-ttu-id="a01a3-312">출력 창에 빨간색 오류가 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-312">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="a01a3-313">빨간색 오류가 있으면 콘솔 출력을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-313">If there are red errors, check the console output.</span></span> <span data-ttu-id="a01a3-314">이전 단계를 모두 올바르게 완료 했으며 올바른 빌드 버전이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-314">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="a01a3-315">**Run** \> **디버깅 시작** 을 선택 하 여 프로세스를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-315">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="a01a3-316">환경을 선택 하 라는 메시지가 표시 되 면 **.net core**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-316">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="a01a3-317">일반적으로 .net 핵심 디버거는 ' ' '를 시작 하 https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 고 슬래시 (/)와 키 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-317">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="a01a3-318">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-318">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="a01a3-319">키가 JSON 형식으로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-319">The key should display in JSON format.</span></span>

<span data-ttu-id="a01a3-320">이제 설치가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-320">Your setup is now complete.</span></span> <span data-ttu-id="a01a3-321">Keystore를 게시 하기 전에 JwtAudience 설정에 대 한 appsettings.json에서 호스트 값이 앱 서비스 호스트 이름과 정확히 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-321">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="a01a3-322">빌드 문제를 해결 하기 위해 localhost로 변경 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-322">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="a01a3-323">키 저장소 게시</span><span class="sxs-lookup"><span data-stu-id="a01a3-323">Publish the key store</span></span>

<span data-ttu-id="a01a3-324">키 저장소를 게시 하려면 DKE 배포를 호스트 하는 Azure App Service 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-324">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="a01a3-325">다음에는 생성 된 키를 Azure에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-325">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="a01a3-326">**DKE 배포를 호스트 하는 Azure Web App 인스턴스를 만들려면**</span><span class="sxs-lookup"><span data-stu-id="a01a3-326">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="a01a3-327">브라우저에서 [Microsoft Azure 포털](https://ms.portal.azure.com)에 로그인 하 고 **앱 서비스**  >  **추가**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-327">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="a01a3-328">구독 및 리소스 그룹을 선택 하 고 인스턴스 세부 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-328">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="a01a3-329">DKE 서비스를 설치 하려는 컴퓨터의 호스트 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-329">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="a01a3-330">파일 [**의appsettings.js**](#tenant-and-key-settings) 에서 JwtAudience 설정에 대해 정의 된 이름과 이름이 같은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-330">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="a01a3-331">이름에 입력 하는 값은 WebAppInstanceName입니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-331">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="a01a3-332">**게시**에서 **코드**를 선택 하 고 **런타임 스택을**보려면 **.net Core 3.1**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-332">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="a01a3-333">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-333">For example:</span></span>

   ![앱 서비스 추가](../media/dke-azure-add-app-service.png)

1. <span data-ttu-id="a01a3-335">페이지 맨 아래에서 **검토 + 만들기**를 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-335">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="a01a3-336">다음 중 하나를 수행 하 여 생성 된 키를 Azure에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-336">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="a01a3-337">ZipDeployUI를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="a01a3-337">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="a01a3-338">FTP를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="a01a3-338">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="a01a3-339">Visual Studio 2019 이상 버전을 통해 게시</span><span class="sxs-lookup"><span data-stu-id="a01a3-339">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="a01a3-340">온-프레미스 시스템에 게시</span><span class="sxs-lookup"><span data-stu-id="a01a3-340">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="a01a3-341">다른 방법으로 키를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="a01a3-342">조직에 가장 적합 한 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-342">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="a01a3-343">[Visual Studio를 통해](https://docs.microsoft.com/aspnet/core/tutorials/) [온-프레미스 시스템](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) 에 게시 하는 방법에 대 한 자세한 내용은 [ASP .net 설명서](https://docs.microsoft.com/aspnet/core/)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a01a3-343">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="a01a3-344">이러한 방법 중 하나를 사용 하는 경우에는 작업을 마친 후 쉽게 반환할 수 있도록 별도의 탭에서 명령을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-344">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="a01a3-345">ZipDeployUI를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="a01a3-345">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="a01a3-346">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-346">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="a01a3-347">예: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="a01a3-347">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="a01a3-348">키 저장소의 코드 베이스에서 **customer-key-store\src\customer-key-store** 폴더로 이동 하 여이 폴더에 **customerkeystore** 파일이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-348">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="a01a3-349">실행: **dotnet 게시**</span><span class="sxs-lookup"><span data-stu-id="a01a3-349">Run: **dotnet publish**</span></span>

     <span data-ttu-id="a01a3-350">출력 창에는 게시가 배포 된 디렉터리가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-350">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="a01a3-351">예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="a01a3-351">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="a01a3-352">게시 디렉터리의 모든 파일을 .zip 파일로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-352">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="a01a3-353">.Zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 파일의 루트 수준에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-353">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="a01a3-354">위에서 연 ZipDeployUI 사이트에 만든 .zip 파일을 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-354">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="a01a3-355">예: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="a01a3-355">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="a01a3-356">DKE가 배포 되었으며 만든 테스트 키로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-356">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="a01a3-357">아래에서 [배포에 대 한 유효성 검사](#validate-your-deployment) 를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-357">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="a01a3-358">FTP를 통해 게시</span><span class="sxs-lookup"><span data-stu-id="a01a3-358">Publish via FTP</span></span>

1. <span data-ttu-id="a01a3-359">[위에서](#publish-the-key-store)만든 앱 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-359">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="a01a3-360">브라우저에서 **Azure portal**  >  **App Service**  >  **배포 센터**  >  **수동 배포**  >  **FTP**  >  **대시보드로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-360">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="a01a3-361">로컬 파일에 표시 되는 연결 문자열을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-361">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="a01a3-362">이러한 문자열을 사용 하 여 웹 앱 서비스에 연결 하 고 FTP를 통해 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-362">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="a01a3-363">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-363">For example:</span></span>

   ![FTP 대시보드에서 연결 문자열 복사](../media/dke-ftp-dashboard.png)

1. <span data-ttu-id="a01a3-365">키 저장소의 코드 베이스에서 **customer-key-store\src\customer-key-store 디렉터리로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-365">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="a01a3-366">이 디렉터리에 **customerkeystore** 파일이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-366">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="a01a3-367">실행: **dotnet 게시**</span><span class="sxs-lookup"><span data-stu-id="a01a3-367">Run: **dotnet publish**</span></span>

    <span data-ttu-id="a01a3-368">출력에는 게시가 배포 된 디렉터리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-368">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="a01a3-369">예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="a01a3-369">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="a01a3-370">게시 디렉터리의 모든 파일을 zip 파일로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-370">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="a01a3-371">.Zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 파일의 루트 수준에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-371">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="a01a3-372">FTP 클라이언트에서 복사한 연결 정보를 사용 하 여 앱 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-372">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="a01a3-373">이전 단계에서 만든 .zip 파일을 웹 응용 프로그램의 루트 디렉터리에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-373">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="a01a3-374">DKE가 배포 되었으며 만든 테스트 키로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-374">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="a01a3-375">다음으로, [배포 유효성을 검사](#validate-your-deployment)합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-375">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="a01a3-376">배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a01a3-376">Validate your deployment</span></span>

<span data-ttu-id="a01a3-377">위에 설명 된 방법 중 하나를 사용 하 여 DKE를 배포한 후에는 배포 및 키 저장소 설정의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-377">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="a01a3-378">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-378">Run:</span></span>

<span data-ttu-id="a01a3-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeymykey url/</span><span class="sxs-lookup"><span data-stu-id="a01a3-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="a01a3-380">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-380">For example:</span></span>

<span data-ttu-id="a01a3-381">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="a01a3-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="a01a3-382">출력에 오류가 표시 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-382">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="a01a3-383">준비 되 면 [키 저장소를 등록](#register-your-key-store)합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-383">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="a01a3-384">키 저장소 등록</span><span class="sxs-lookup"><span data-stu-id="a01a3-384">Register your key store</span></span>

<span data-ttu-id="a01a3-385">다음 단계를 수행 하면 키 저장소를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-385">The following steps enable you to register your key store.</span></span> <span data-ttu-id="a01a3-386">레이블 만들기를 시작 하기 전에 키 저장소를 등록 하는 것은 DKE를 배포 하는 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-386">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="a01a3-387">키 저장소를 등록 하려면:</span><span class="sxs-lookup"><span data-stu-id="a01a3-387">To register your key store:</span></span>

1. <span data-ttu-id="a01a3-388">브라우저에서 [Microsoft Azure portal](https://ms.portal.azure.com/)을 열고 **모든 서비스** \> **id** \> **앱 등록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-388">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="a01a3-389">**새 등록**을 선택 하 고 의미 있는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-389">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="a01a3-390">표시 된 옵션에서 계정 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-390">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="a01a3-391">사용자 지정 하지 않은 도메인 (예: **onmicrosoft.com**)에서 Microsoft Azure를 사용 하는 경우 **에는이 조직 디렉터리의 계정만 선택 합니다 (Microsoft only 단일 테 넌 트).**</span><span class="sxs-lookup"><span data-stu-id="a01a3-391">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="a01a3-392">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-392">For example:</span></span>

   ![새 앱 등록](../media/dke-app-registration.png)

4. <span data-ttu-id="a01a3-394">페이지 맨 아래에서 **등록** 을 선택 하 여 새 앱 등록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-394">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="a01a3-395">새 앱 등록의 왼쪽 창에 있는 **관리**에서 **인증**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-395">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="a01a3-396">**플랫폼 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-396">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="a01a3-397">**플랫폼 구성** 팝업에서 **웹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-397">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="a01a3-398">**리디렉션 uri**에서 이중 키 암호화 서비스의 URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-398">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="a01a3-399">호스트 이름 및 도메인을 포함 하 여 앱 서비스 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-399">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="a01a3-400">예: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="a01a3-400">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="a01a3-401">입력 하는 URL은 키 저장소가 배포 된 호스트 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-401">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="a01a3-402">Visual Studio를 사용 하 여 로컬로 테스트 하는 경우를 사용 **https://localhost:5001** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-402">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="a01a3-403">모든 경우에 스키마는 **https**여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-403">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="a01a3-404">호스트 이름이 앱 서비스 호스트 이름과 정확히 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-404">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="a01a3-405">빌드 문제를 해결 하기 위해 변경 했을 수 있습니다 `localhost` .</span><span class="sxs-lookup"><span data-stu-id="a01a3-405">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="a01a3-406">**appsettings.js**설정에서이 값은 설정한 호스트 이름입니다 `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="a01a3-406">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="a01a3-407">**암시적 권한 부여**에서 **ID 토큰** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-407">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="a01a3-408">변경 내용을 저장하려면 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-408">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="a01a3-409">왼쪽 창에서 **API 노출**을 선택한 다음 응용 프로그램 ID URI 옆에 있는 **설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-409">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="a01a3-410">여전히 **Api 노출** 페이지의 **이 API** 영역에 정의 된 범위에서 **범위 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-410">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="a01a3-411">새 범위에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-411">In the new scope:</span></span>

    1. <span data-ttu-id="a01a3-412">범위 이름을 **user_impersonation**로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-412">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="a01a3-413">동의할 수 있는 관리자 및 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-413">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="a01a3-414">필요한 나머지 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-414">Define any remaining values required.</span></span>

    4. <span data-ttu-id="a01a3-415">**범위 추가를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a01a3-415">Select **Add scope.**</span></span>

    <span data-ttu-id="a01a3-416">맨 위에 있는 **저장** 을 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-416">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="a01a3-417">여전히 **API 노출** 페이지의 **권한 있는 클라이언트 응용 프로그램** 영역에서 **클라이언트 응용 프로그램 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-417">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="a01a3-418">새 클라이언트 응용 프로그램에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-418">In the new client application:</span></span>

    1. <span data-ttu-id="a01a3-419">클라이언트 ID를 **d3590ed6-52b3-4102-aeff-aad2292ab01c**으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-419">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="a01a3-420">이 값은 Microsoft Office 클라이언트 ID 이며 Office에서 키 저장소에 대 한 액세스 토큰을 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-420">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="a01a3-421">**권한 있는 범위**에서 **user_impersonation** 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-421">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="a01a3-422">**응용 프로그램 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-422">Select **Add application**.</span></span>

    4. <span data-ttu-id="a01a3-423">맨 위에 있는 **저장** 을 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-423">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="a01a3-424">이제 DKE 키 저장소가 등록 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-424">Your DKE key store is now registered.</span></span> <span data-ttu-id="a01a3-425">계속 [하 여 DKE를 사용 하 여 레이블을 만듭니다](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="a01a3-425">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="a01a3-426">DKE을 사용 하 여 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="a01a3-426">Create labels using DKE</span></span>

<span data-ttu-id="a01a3-427">Microsoft 365 준수 센터에서 새 민감도 레이블을 만들고 암호화를 다른 방법으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-427">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="a01a3-428">**이중 키 암호화 사용** 을 선택 하 고 키에 대 한 끝점 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-428">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="a01a3-429">예제:</span><span class="sxs-lookup"><span data-stu-id="a01a3-429">For example:</span></span>

![Microsoft 365 준수 센터에서 이중 키 암호화 사용을 선택 합니다.](../media/dke-use-dke.png)

<span data-ttu-id="a01a3-431">추가 하는 모든 DKE 레이블은 최신 버전의 Microsoft 365 Apps for enterprise의 사용자에 게 표시 되기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-431">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="a01a3-432">클라이언트가 새 레이블로 새로 고치는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-432">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="a01a3-433">클라이언트에서 DKE 사용</span><span class="sxs-lookup"><span data-stu-id="a01a3-433">Enable DKE in your client</span></span>

<span data-ttu-id="a01a3-434">다음 레지스트리 키를 추가 하 여 클라이언트에 대해 DKE를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01a3-434">Enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
