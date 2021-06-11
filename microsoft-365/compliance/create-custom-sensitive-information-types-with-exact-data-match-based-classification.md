---
title: 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 매치 기반 분류를 사용하여 사용자 지정 중요한 정보 유형을 만드는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6839401bc1dd00acc45992f902a6360eb7f20120
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878199"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="c822c-103">분류에 기반한 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="c822c-103">Create custom sensitive information types with Exact Data Match based classification</span></span>



<span data-ttu-id="c822c-104">[사용자 지정 중요한 정보 유형](sensitive-information-type-learn-about.md)은 중요한 항목을 식별하는 데 도움을 주어 해당 항목이 실수로 또는 부적절하게 공유되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="c822c-105">다음을 기반으로 사용자 지정 SIT(중요한 정보 유형)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-105">You define a custom sensitive information type (SIT)based on:</span></span>

- <span data-ttu-id="c822c-106">패턴</span><span class="sxs-lookup"><span data-stu-id="c822c-106">patterns</span></span>
- <span data-ttu-id="c822c-107">*직원*, *배지* 또는 *ID* 와 같은 키워드 증명 정보</span><span class="sxs-lookup"><span data-stu-id="c822c-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="c822c-108">특정 패턴의 증거에 대한 문자 근접성</span><span class="sxs-lookup"><span data-stu-id="c822c-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="c822c-109">신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="c822c-109">confidence levels</span></span>

 <span data-ttu-id="c822c-110">이러한 사용자 지정 중요한 정보 유형은 대부분의 조직에 필요한 비즈니스 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="c822c-111">하지만 일반적인 패턴을 기반으로 일치 항목을 찾는 대신 정확한 데이터 값을 사용하는 사용자 지정 SIT(중요한 정보 유형)을 원한다면 어떻게 해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="c822c-111">But what if you wanted a custom sensitive information type (SIT) that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="c822c-112">정확한 데이터 매치(EDM) 기반 분류를 사용하여 다음과 같이 설계된 사용자 지정 중요한 정보 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="c822c-113">역동적이며 쉽게 새로 고침</span><span class="sxs-lookup"><span data-stu-id="c822c-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="c822c-114">확장성 향상</span><span class="sxs-lookup"><span data-stu-id="c822c-114">be more scalable</span></span>
- <span data-ttu-id="c822c-115">가양성 수 감소</span><span class="sxs-lookup"><span data-stu-id="c822c-115">result in fewer false-positives</span></span>
- <span data-ttu-id="c822c-116">구조화된 중요한 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="c822c-116">work with structured sensitive data</span></span>
- <span data-ttu-id="c822c-117">중요한 정보를 더 안전하게 처리</span><span class="sxs-lookup"><span data-stu-id="c822c-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="c822c-118">여러 Microsoft 클라우드 서비스와 함께 사용 가능</span><span class="sxs-lookup"><span data-stu-id="c822c-118">be used with several Microsoft cloud services</span></span>

![EDM 기반 분류](../media/EDMClassification.png)

<span data-ttu-id="c822c-120">EDM 기반 분류를 사용하면 중요한 정보 데이터베이스의 정확한 값을 참조하는 사용자 지정 중요한 정보 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="c822c-121">데이터베이스는 매일 새로 고칠 수 있으며 최대 1억 행의 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="c822c-122">직원, 환자 또는 고객이 계속 이동하고 기록이 변경됨에 따라 사용자 지정 중요한 정보 유형을 적절하고 최신인 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="c822c-123">또한 EDM 기반 분류를 [데이터 손실 방지 정책](dlp-learn-about-dlp.md) 또는 [Microsoft Cloud App Security 파일 정책](/cloud-app-security/data-protection-policies) 등의 정책과 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](dlp-learn-about-dlp.md) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="c822c-124">Microsoft 365 Information Protection은 다음에 대해 미리 보기 더블 바이트 문자 집합 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-124">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="c822c-125">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="c822c-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="c822c-126">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="c822c-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="c822c-127">한국어</span><span class="sxs-lookup"><span data-stu-id="c822c-127">Korean</span></span>
> - <span data-ttu-id="c822c-128">일본어</span><span class="sxs-lookup"><span data-stu-id="c822c-128">Japanese</span></span>
> 
> <span data-ttu-id="c822c-129">이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="c822c-130">자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
 

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="c822c-131">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="c822c-131">Required licenses and permissions</span></span>

<span data-ttu-id="c822c-132">이 문서에 설명된 작업을 수행하려면 전역 관리자, 준수 관리자 또는 Exchange Online 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="c822c-133">DLP 권한에 관한 자세한 내용은 [권한](data-loss-prevention-policies.md#permissions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="c822c-134">EDM 기반 분류가 이 구독에 포함되어 있습니다</span><span class="sxs-lookup"><span data-stu-id="c822c-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="c822c-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c822c-135">Office 365 E5</span></span>
- <span data-ttu-id="c822c-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c822c-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="c822c-137">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="c822c-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="c822c-138">Microsoft E5/A5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="c822c-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="c822c-139">구독을 위한 포털 링크</span><span class="sxs-lookup"><span data-stu-id="c822c-139">Portal links for your subscription</span></span>


|<span data-ttu-id="c822c-140">포털</span><span class="sxs-lookup"><span data-stu-id="c822c-140">Portal</span></span>  |<span data-ttu-id="c822c-141">전세계/GCC</span><span class="sxs-lookup"><span data-stu-id="c822c-141">World Wide/GCC</span></span>  |<span data-ttu-id="c822c-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="c822c-142">GCC-High</span></span>  |<span data-ttu-id="c822c-143">DOD</span><span class="sxs-lookup"><span data-stu-id="c822c-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="c822c-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="c822c-144">Office SCC</span></span>     |  <span data-ttu-id="c822c-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="c822c-145">protection.office.com</span></span>       |<span data-ttu-id="c822c-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="c822c-146">scc.office365.us</span></span>         |<span data-ttu-id="c822c-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="c822c-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="c822c-148">Microsoft 365 보안 센터</span><span class="sxs-lookup"><span data-stu-id="c822c-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="c822c-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c822c-149">security.microsoft.com</span></span>         |<span data-ttu-id="c822c-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="c822c-150">security.microsoft.us</span></span>         |<span data-ttu-id="c822c-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="c822c-151">security.apps.mil</span></span>|
|<span data-ttu-id="c822c-152">Microsoft 365 규정 준수 센터</span><span class="sxs-lookup"><span data-stu-id="c822c-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="c822c-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c822c-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="c822c-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="c822c-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="c822c-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="c822c-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="c822c-156">워크플로 한 눈에 보기</span><span class="sxs-lookup"><span data-stu-id="c822c-156">The work flow at a glance</span></span>

|<span data-ttu-id="c822c-157">단계</span><span class="sxs-lookup"><span data-stu-id="c822c-157">Phase</span></span>  |<span data-ttu-id="c822c-158">필요한 사항</span><span class="sxs-lookup"><span data-stu-id="c822c-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="c822c-159">1단계: EDM 기반 분류 설정</span><span class="sxs-lookup"><span data-stu-id="c822c-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="c822c-160">(필요한 대로 수행)</span><span class="sxs-lookup"><span data-stu-id="c822c-160">(As needed)</span></span><br/><span data-ttu-id="c822c-161">- [데이터베이스 스키마 편집](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="c822c-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="c822c-162">- [스키마 제거](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="c822c-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="c822c-163">- 중요한 데이터에 대한 읽기 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="c822c-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="c822c-164">- XML 형식의 데이터베이스 스키마(예제 제공)</span><span class="sxs-lookup"><span data-stu-id="c822c-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="c822c-165">- XML 형식의 규칙 패키지(예제 제공)</span><span class="sxs-lookup"><span data-stu-id="c822c-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="c822c-166">- 보안 및 준수 센터에 대한 관리자 권한(Windows PowerShell 사용)</span><span class="sxs-lookup"><span data-stu-id="c822c-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="c822c-167">2부: 중요 한 데이터를 해시하고 업로드</span><span class="sxs-lookup"><span data-stu-id="c822c-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="c822c-168">(필요한 대로 수행)</span><span class="sxs-lookup"><span data-stu-id="c822c-168">(As needed)</span></span><br/>[<span data-ttu-id="c822c-169">데이터 새로 고침</span><span class="sxs-lookup"><span data-stu-id="c822c-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="c822c-170">- 사용자 지정 보안 그룹 및 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="c822c-170">- Custom security group and user account</span></span><br/><span data-ttu-id="c822c-171">- EDM 업로드 에이전트가 있는 컴퓨터에 대한 로컬 관리자 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="c822c-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="c822c-172">- 중요한 데이터에 대한 읽기 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="c822c-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="c822c-173">- 데이터를 새로 고치는 프로세스 및 일정</span><span class="sxs-lookup"><span data-stu-id="c822c-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="c822c-174">3단계: Microsoft 클라우드 서비스로 EDM 기반 분류 사용</span><span class="sxs-lookup"><span data-stu-id="c822c-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="c822c-175">- DLP를 포함하는 Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="c822c-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="c822c-176">- EDM 기반 분류 기능 사용</span><span class="sxs-lookup"><span data-stu-id="c822c-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="c822c-177">1단계: EDM 기반 분류 설정</span><span class="sxs-lookup"><span data-stu-id="c822c-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="c822c-178">EDM 기반 분류 설정 및 구성에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="c822c-179">중요한 데이터를 .csv .tsv 형식으로 저장</span><span class="sxs-lookup"><span data-stu-id="c822c-179">Saving sensitive data in .csv or .tsv format</span></span>](#save-sensitive-data-in-csv-or-tsv-format)
2. [<span data-ttu-id="c822c-180">중요한 정보 데이터베이스 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="c822c-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="c822c-181">규칙 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="c822c-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a><span data-ttu-id="c822c-182">중요한 데이터를 .csv .tsv 형식으로 저장</span><span class="sxs-lookup"><span data-stu-id="c822c-182">Save sensitive data in .csv or .tsv format</span></span>

1. <span data-ttu-id="c822c-183">사용하려는 중요한 정보를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="c822c-184">데이터를 앱에 내보낼 수 Microsoft Excel 텍스트 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-184">Export the data to an app, such as Microsoft Excel, and save the file in a text file.</span></span> <span data-ttu-id="c822c-185">이 파일은 파일 형식(.csv), .tsv(탭으로 구분된 값) 또는 파이프 구분(|) 형식으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-185">The file can be saved in .csv (comma-separated values), .tsv (tab-separated values), or pipe-separated (|) format.</span></span> <span data-ttu-id="c822c-186">데이터 값에 주소와 같은 콤보가 포함될 수 있는 경우 .tsv 형식을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-186">The .tsv format is recommended in cases where your data values may included commas, such as street addresses.</span></span>
<span data-ttu-id="c822c-187">데이터 파일에는 최대 다음을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-187">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="c822c-188">최대 1억 개의 중요한 데이터 행</span><span class="sxs-lookup"><span data-stu-id="c822c-188">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="c822c-189">데이터 원본당 최대 32개의 열(필드)</span><span class="sxs-lookup"><span data-stu-id="c822c-189">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="c822c-190">검색 가능으로 표시된 최대 5개의 열(필드)</span><span class="sxs-lookup"><span data-stu-id="c822c-190">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="c822c-191">첫 번째 행에 EDM 기반 분류에 사용되는 필드 이름이 .csv 또는 .tsv 파일의 중요한 데이터를 구조화합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-191">Structure the sensitive data in the .csv or .tsv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="c822c-192">파일에 "ssn", "birthdate", "firstname", "lastname" 등의 필드 이름이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-192">In your file you might have field names such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="c822c-193">열 머리글 이름에는 공백이나 밑줄이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-193">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="c822c-194">예를 들어, 이 문서에서 사용하는 샘플 .csv 파일은 *PatientRecords.csv* 라고 하며, 해당 열에는 *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* 등이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-194">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="c822c-195">중요한 데이터 필드의 형식에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-195">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="c822c-196">특히 콘텐츠에 콤보가 포함될 수 있는 필드(예: "Seattle,WA" 값이 포함된 주소)는 구문 분석할 때 .csv 필드로 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-196">In particular, fields that may contain commas in their content, for example, a street address that contains the value "Seattle,WA" would be parsed as two separate fields when parsed if the .csv format is selected.</span></span> <span data-ttu-id="c822c-197">이를 방지하기 위해 .tsv 형식을 사용하거나 중요한 데이터 테이블에서 값이 들어 있는 콤보를 두 번 따옴표로 둘러싸습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-197">To avoid this, use the .tsv format or surrounded the comma containing values by double quotes in the sensitive data table.</span></span> <span data-ttu-id="c822c-198">값을 포함하는 콤보에 공백도 포함되어 있는 경우 해당 형식과 일치하는 사용자 지정 SIT를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-198">If comma containing values also contain spaces, you need to create a custom SIT that matches the corresponding format.</span></span> <span data-ttu-id="c822c-199">예를 들어 콤보 및 공백이 있는 여러 단어 문자열을 검색하는 SIT입니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-199">For example, a SIT that detects multi-word string with commas and spaces in it.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="c822c-200">중요한 정보 데이터베이스의 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="c822c-200">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="c822c-201">비즈니스 또는 기술상의 이유로 PowerShell 또는 명령줄을 사용하여 스키마 및 EDM에 중요한 정보 유형 패턴(규칙 패키지)을 생성하지 않는 것을 선호하는 경우 [정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사](sit-edm-wizard.md)를 사용하여 스키마를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-201">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="c822c-202">스키마 및 EDM 중요한 정보 유형 패턴을 생성했으면 EDM 기반 중요한 정보 유형을 사용할 수 있도록 하는 데 필요한 모든 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-202">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="c822c-203">정확한 데이터 일치 스키마 및 중요 정보 유형 마법사는 월드 와이드 및 GCC 클라우드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-203">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="c822c-204">중요한 정보 데이터의 스키마를 XML 형식으로 정의합니다(아래 예제와 비슷).</span><span class="sxs-lookup"><span data-stu-id="c822c-204">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="c822c-205">이 스키마 파일의 이름을 **edm.xml** 로 지정하고 데이터베이스의 각 열에 구문을 사용하는 줄이 있도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-205">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="c822c-206">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="c822c-206">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="c822c-207">*필드 이름* 값에 열 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-207">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="c822c-208">최대 5개의 필드까지 검색할 수 있게 하려는 필드에 *searchable="true"* 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-208">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="c822c-209">하나 이상의 필드를 검색할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-209">At least one field must be searchable.</span></span>

      <span data-ttu-id="c822c-210">예를 들어 다음 XML 파일은 검색 가능하도록 지정된 5개의 필드(*PatientID*, *MRN*, *SSN*, *Phone* 및 *DOB*)가 있는 환자 레코드 데이터베이스의 스키마를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-210">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="c822c-211">(여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="c822c-211">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="c822c-212">caseInsensitive 및 ignoredDelimiters 필드를 사용하여 구성 가능한 일치</span><span class="sxs-lookup"><span data-stu-id="c822c-212">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="c822c-213">위의 XML 샘플은 `caseInsensitive` 및 `ignoredDelimiters` 필드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-213">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span> 

<span data-ttu-id="c822c-214">스키마 정의에서 `true` 값에 설정된 \***caseInsensitive** _ 필드를 포함하면 EDM은 `PatientID` 필드의 대소문자 차이에 기반한 항목을 제외하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-214">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="c822c-215">따라서 EDM은 `PatientID` _ *FOO-1234*\* 및 **fOo-1234** 가 동일하다고 볼 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-215">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="c822c-216">지원되는 문자와 함께  \***ignoredDelimiters** _ 필드를 포함하면 EDM은 `PatientID`에서 해당 문자를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-216">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="c822c-217">따라서 EDM은 `PatientID` _ *FOO-1234*\* 및 `PatientID` **FOO#1234** 가 동일하다고 볼 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-217">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="c822c-218">`ignoredDelimiters` 플래그는 영숫자가 아닌 모든 문자를 지원하며 다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-218">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="c822c-219">\.</span><span class="sxs-lookup"><span data-stu-id="c822c-219">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \; 

<span data-ttu-id="c822c-220">`ignoredDelimiters` 플래그는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-220">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="c822c-221">0~9 사이 문자</span><span class="sxs-lookup"><span data-stu-id="c822c-221">characters 0-9</span></span>
- <span data-ttu-id="c822c-222">A-Z</span><span class="sxs-lookup"><span data-stu-id="c822c-222">A-Z</span></span>
- <span data-ttu-id="c822c-223">a-z</span><span class="sxs-lookup"><span data-stu-id="c822c-223">a-z</span></span>
- \"
- \,

<span data-ttu-id="c822c-224">이 예에서 `caseInsensitive` 및 `ignoredDelimiters` 모두 사용되는 경우, EDM은 **FOO-1234** 및 **fOo#1234** 가 동일하다고 보고, 환자 기록을 중요한 정보 유형으로 분류합니다. </span><span class="sxs-lookup"><span data-stu-id="c822c-224">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span> 

4. <span data-ttu-id="c822c-225">[보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="c822c-225">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="c822c-226">데이터베이스 스키마를 업로드 하려면 다음과 같은 cmdlet을 한 번에 하나씩 실행하십시오:</span><span class="sxs-lookup"><span data-stu-id="c822c-226">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="c822c-227">다음과 같이 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-227">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="c822c-228">확인</span><span class="sxs-lookup"><span data-stu-id="c822c-228">Confirm</span></span>
      >
      > <span data-ttu-id="c822c-229">이 작업을 수행하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="c822c-229">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="c822c-230">'patientrecords' 데이터 저장소의 새로운 EDM 스키마를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-230">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="c822c-231">\[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):</span><span class="sxs-lookup"><span data-stu-id="c822c-231">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="c822c-232">확인하지 않고 변경 사항을 적용하려면, 5단계에서 New-DlpEdmSchema -FileData $edmSchemaXml 대신 이 cmdlet을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="c822c-232">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="c822c-233">EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-233">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="c822c-234">추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-234">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="c822c-235">규칙 패키지 설정</span><span class="sxs-lookup"><span data-stu-id="c822c-235">Set up a rule package</span></span>

1. <span data-ttu-id="c822c-236">다음 예제와 같이 in XML 형식(유니코드 인코딩 사용)에 규칙 패키지를 생성하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-236">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="c822c-237">(여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="c822c-237">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="c822c-238">규칙 패키지를 설정할 때 .csv .tsv 파일을 올바르게 참조하고 파일을edm.xml **합니다.**</span><span class="sxs-lookup"><span data-stu-id="c822c-238">When you set up your rule package, make sure to correctly reference your .csv or .tsv file and **edm.xml** file.</span></span> <span data-ttu-id="c822c-239">(여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="c822c-239">You can copy, modify, and use our example.</span></span> <span data-ttu-id="c822c-240">이 샘플 xml에서 EDM 중요 유형을 만들려면 다음 필드를 사용자 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-240">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="c822c-241">**RulePack ID & ExactMatch ID**:[New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)를 사용하여 GUID를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-241">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="c822c-242">**Datastore**: 이 필드는 사용할 EDM 조회 데이터 저장소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-242">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="c822c-243">구성된 EDM 스키마의 데이터 원본 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-243">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="c822c-244">**idMatch**: 이 필드는 EDM의 기본 요소를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-244">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="c822c-245">Matches: 정확한 조회에 사용할 필드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-245">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="c822c-246">데이터 저장소의 EDM 스키마에서 검색 가능한 필드 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-246">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="c822c-247">Classification: 이 필드는 EDM 조회를 트리거하는 중요한 유형 일치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-247">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="c822c-248">기존 기본 제공 이름이나 GUID 또는 사용자 지정 중요 유형 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-248">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="c822c-249">제공된 중요 정보 유형과 일치하는 문자열은 해시되고 중요 정보 테이블의 모든 항목과 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-249">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="c822c-250">성능 문제가 발생하지 않도록 하려면 EDM에서 사용자 지정 중요 정보 유형을 분류 요소로 사용하는 경우 지원 키워드를 추가하거나 사용자 지정 분류에 중요한 정보 유형의 정의에 형식을 포함하여 많은 비율(예: "임의의 숫자" 또는 "임의의 5글자")과 일치하는 내용을 사용하지 않도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-250">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span> 

      - <span data-ttu-id="c822c-251">**Match:** 이 필드는 idMatch의 근접성에서 찾은 추가 증명을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-251">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="c822c-252">Matches: 데이터 저장소의 EDM 스키마에 필드 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-252">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="c822c-253">**리소스:** 이 섹션에서는 여러 로캘에서 중요한 유형의 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-253">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="c822c-254">idRef: ExactMatch ID의 GUID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-254">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="c822c-255">이름 및 설명: 필요에 따라 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-255">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. <span data-ttu-id="c822c-256">다음의 PowerShell cmdlet을 한 번에 하나씩 실행하여 규칙 패키지를 업로드하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-256">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="c822c-257">이 시점에서 EDM 기반 분류를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-257">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="c822c-258">다음 단계는 중요 한 데이터를 해시한 다음 인덱싱하는 해시를 업로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-258">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="c822c-259">PatientRecords 스키마가 검색 가능한 5개의 필드를 정의한 이전 절차에서 *PatientID*, *MRN*, *SSN*, *Phone*, 및 *DOB* 를 불러오십시오.</span><span class="sxs-lookup"><span data-stu-id="c822c-259">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="c822c-260">예제 규칙 패키지에는 이러한 필드가 포함되어 있으며 검색 가능한 필드 당 하나의 *ExactMatch* 항목과 함께 데이터베이스 스키마 파일(**edm.xml**)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-260">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="c822c-261">다음의 ExactMatch 항목을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-261">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="c822c-262">이 예에서는 다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-262">In this example, note that:</span></span>

- <span data-ttu-id="c822c-263">데이터 저장소 이름은 이전에 생성한 .csv 파일을 참조합니다(**데이터 저장소 = "PatientRecords"**).</span><span class="sxs-lookup"><span data-stu-id="c822c-263">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="c822c-264">idmatch 값은 데이터베이스 스키마 파일(**idMatch matches = "SSN"**)에 나열된 검색 가능한 필드를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-264">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="c822c-265">분류 값이 기존 또는 사용자 지정 중요한 정보 유형(**분류 = "미국 주민 등록 번호 (SSN)"**)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-265">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="c822c-266">(이 경우 미국 주민 등록 번호의 기존의 중요한 정보 유형을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="c822c-266">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="c822c-267">EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-267">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="c822c-268">추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-268">The update must complete before you execute steps that use the additions.</span></span>
 
<span data-ttu-id="c822c-269">EDM 중요한 정보 유형으로 규칙 패키지를 가져와 중요한 데이터 테이블을 가져온 후 규정 준수 센터의 EDM 마법사에서 **테스트** 함수를 사용하여 새로 만든 유형을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-269">After you have imported your rule package with your EDM sensitive info type and have imported your sensitive data table, you can test your newly created type by using the **Test** function in the EDM wizard in the compliance center.</span></span> <span data-ttu-id="c822c-270">이 기능의 사용 지침은 [정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사 사용](sit-edm-wizard.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-270">See [Use the Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) for instructions on using this functionality.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="c822c-271">EDM 기반 분류에 대한 스키마 편집</span><span class="sxs-lookup"><span data-stu-id="c822c-271">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="c822c-272">EDM 기반 분류에 사용되는 필드를 변경하는 것과 같이 **edm.xml** 파일을 변경하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-272">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="c822c-273">**구성 가능한 일치** 의 장점을 얻기 위해 EDM 스키마 및 데이터 파일을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-273">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="c822c-274">구성된 경우, EDM은 항목을 평가할 때 대소문자 차이 및 일부 구분 기호를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-274">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="c822c-275">이렇게 하면 XML 스키마와 중요한 데이터 파일을 더 쉽게 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-275">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="c822c-276">자세한 내용은 [구성 가능한 일치를 사용하도록 정확한 데이터 일치 스키마 수정](sit-modify-edm-schema-configurable-match.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-276">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="c822c-277">**edm.xml** 파일을 편집하십시오(이 문서의 [스키마 정의](#define-the-schema-for-your-database-of-sensitive-information) 섹션에서 논의한 파일입니다).</span><span class="sxs-lookup"><span data-stu-id="c822c-277">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="c822c-278">[보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="c822c-278">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="c822c-279">데이터베이스 스키마를 업데이트하려면 다음과 같은 cmdlet을 한 번에 하나씩 실행하십시오:</span><span class="sxs-lookup"><span data-stu-id="c822c-279">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="c822c-280">다음과 같이 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-280">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="c822c-281">확인</span><span class="sxs-lookup"><span data-stu-id="c822c-281">Confirm</span></span>
      >
      > <span data-ttu-id="c822c-282">이 작업을 수행하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="c822c-282">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="c822c-283">'patientrecords' 데이터 저장소의 새로운 EDM 스키마를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-283">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="c822c-284">\[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):</span><span class="sxs-lookup"><span data-stu-id="c822c-284">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="c822c-285">확인하지 않고 변경 사항을 적용하려면, 3단계에서 Set-DlpEdmSchema -FileData $edmSchemaXml 대신 이 cmdlet을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="c822c-285">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="c822c-286">EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-286">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="c822c-287">추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-287">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="c822c-288">EDM 기반 분류에 대한 스키마 제거</span><span class="sxs-lookup"><span data-stu-id="c822c-288">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="c822c-289">(필요한 경우) EDM 기반 분류에 사용 중인 스키마를 제거하려면 다음 단계를 따르십시오:</span><span class="sxs-lookup"><span data-stu-id="c822c-289">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="c822c-290">[보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="c822c-290">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c822c-291">다음의 PowerShell cmdlet을 실행하여 "patientrecords"의 데이터 저장소 이름을 제거하려는 저장소 이름으로 대체하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-291">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="c822c-292">다음을 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-292">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="c822c-293">확인</span><span class="sxs-lookup"><span data-stu-id="c822c-293">Confirm</span></span>
      >
      > <span data-ttu-id="c822c-294">이 작업을 수행하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="c822c-294">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="c822c-295">'patientrecords' 데이터 저장소의 EDM 스키마를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-295">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="c822c-296">\[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):</span><span class="sxs-lookup"><span data-stu-id="c822c-296">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="c822c-297">확인하지 않고 변경 사항을 적용하려면, 2단계에서 Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false 대신 이 cmdlet을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="c822c-297">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="c822c-298">2부: 중요한 데이터를 해시하고 업로드</span><span class="sxs-lookup"><span data-stu-id="c822c-298">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="c822c-299">이 단계에서는 사용자 지정 보안 그룹 및 사용자 계정을 설정하고 EDM 업로드 에이전트 도구를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-299">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="c822c-300">그런 다음 이 도구를 사용하여 중요한 데이터를 해시하고 해시한 데이터를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-300">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="c822c-301">해시 및 업로드는 한 대의 컴퓨터를 사용하여 수행하거나 보안 강화를 위해 업로드 단계에서 해싱 단계를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-301">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="c822c-302">한 대의 컴퓨터에서 해시하고 업로드하려면 Microsoft 365 테넌트에 직접 연결할 수 있는 컴퓨터에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-302">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="c822c-303">이렇게하려면 해싱을 위해 일반 텍스트 중요 데이터 파일이 해당 컴퓨터에 있어야합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-303">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="c822c-p129">일반 텍스트 중요 데이터 파일을 노출하지 않으려면 안전한 위치에 있는 컴퓨터에서 해당 파일에서 해시한 다음 업로드를 위해 Microsoft 365 테넌트에 직접 연결할 수 있는 컴퓨터에 해시 파일과 솔트 파일을 복사할 수 있습니다. 이 시나리오의 경우 두 대의 컴퓨터 모두 EDMUploadAgent가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-p129">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload. In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c822c-306">정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사를 사용하여 스키마 및 패턴 파일을 만든 경우 이 절차에 대한 스키마를 ***다운로드해야*** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-306">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you ***must*** download the schema for this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="c822c-307">조직에서 테넌트 [](customer-key-overview.md)Microsoft 365 사용자에 대한 고객 키를 설정한 경우 정확한 데이터 일치는 암호화 기능을 자동으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-307">If your organization has set up [Customer Key for Microsoft 365 at the tenant level](customer-key-overview.md), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="c822c-308">상업용 클라우드의 E5 라이선스 테넌트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-308">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="c822c-309">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c822c-309">Prerequisites</span></span>

- <span data-ttu-id="c822c-310">**EDM\_DataUploaders** 보안 그룹에 추가될 Microsoft 365용 회사 또는 학교 계정</span><span class="sxs-lookup"><span data-stu-id="c822c-310">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="c822c-311">EDMUploadAgent 실행을 위한 .NET 버전 4.6.2가있는 Windows 10 또는 Windows Server 2016 시스템</span><span class="sxs-lookup"><span data-stu-id="c822c-311">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="c822c-312">다음에 대한 업로드 컴퓨터의 디렉토리 :</span><span class="sxs-lookup"><span data-stu-id="c822c-312">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="c822c-313">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="c822c-313">EDMUploadAgent</span></span>
    - <span data-ttu-id="c822c-314">예제에 설명된 .csv 또는 .tsv 형식의PatientRecords.csv파일 </span><span class="sxs-lookup"><span data-stu-id="c822c-314">your sensitive item file in .csv or .tsv format, **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="c822c-315">및 출력 해시 및 솔트 파일</span><span class="sxs-lookup"><span data-stu-id="c822c-315">and the output hash and salt files</span></span>
    - <span data-ttu-id="c822c-316">**edm.xml** 파일의 데이터 저장소 이름(이 예에서는 `PatientRecords`)</span><span class="sxs-lookup"><span data-stu-id="c822c-316">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="c822c-317">[정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사](sit-edm-wizard.md)를 사용한 경우 \*\*\*\*다운로드해야만\*\*\* 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-317">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="c822c-318">보안 그룹 및 사용자 계정 설정</span><span class="sxs-lookup"><span data-stu-id="c822c-318">Set up the security group and user account</span></span>

1. <span data-ttu-id="c822c-319">전역 관리자로서 [구독에 대한 적절한 링크](#portal-links-for-your-subscription)를 사용하여 관리 센터로 이동하고 **EDM\_ DataUploaders** 라는 [보안 그룹을 만듭니다](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="c822c-319">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="c822c-320">한 명 이상의 사용자를 **EDM\_DataUploaders** 보안 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-320">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="c822c-321">(이러한 사용자가 중요한 정보 데이터베이스를 관리합니다.)</span><span class="sxs-lookup"><span data-stu-id="c822c-321">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="c822c-322">한 대의 컴퓨터에서 해시 및 업로드</span><span class="sxs-lookup"><span data-stu-id="c822c-322">Hash and upload from one computer</span></span>

<span data-ttu-id="c822c-323">이 컴퓨터는 Microsoft 365 테넌트에 직접 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-323">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="c822c-324">이 절차를 시작하기 전에 본인이 **EDM\_DataUploaders** 보안 그룹의 구성원인지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-324">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

> [!TIP]
> <span data-ttu-id="c822c-325">원하는 경우 업로드하기 전에 .csv .tsv 파일에 대해 유효성 검사를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-325">Optionally, you can run a validation against your .csv or .tsv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
><span data-ttu-id="c822c-326">모든 EdmUploadAgent.exe >에서 지원되는 매개 변수에 대한 자세한 내용은 다음을 실행합니다</span><span class="sxs-lookup"><span data-stu-id="c822c-326">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`


#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="c822c-327">구독 유형별 EDM 업로드 에이전트에 대한 링크</span><span class="sxs-lookup"><span data-stu-id="c822c-327">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="c822c-328">[상업용 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 대부분의 상업용 고객이 사용</span><span class="sxs-lookup"><span data-stu-id="c822c-328">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="c822c-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 특히 높은 보안 정부 클라우드 구독자용</span><span class="sxs-lookup"><span data-stu-id="c822c-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="c822c-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 특히 미국 국방부 클라우드 고객용</span><span class="sxs-lookup"><span data-stu-id="c822c-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="c822c-331">EDMUploadAgent에 대한 작업 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-331">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="c822c-332">예를 들어, **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="c822c-332">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="c822c-333">여기에 **PatientRecords.csv** 파일을 배치하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-333">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="c822c-334">구독에 적합한 [EDM 업로드 에이전트](#links-to-edm-upload-agent-by-subscription-type)를 1단계에서 만든 디렉토리에 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-334">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c822c-335">위 링크의 EDMUploadAgent는 해시된 데이터에 솔트 값을 자동으로 추가하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-335">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="c822c-336">또는 자신의 솔트 값을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-336">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="c822c-337">이 버전을 사용한 후에는 이전 버전의 EDMUploadAgent를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-337">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="c822c-338">EDMUploadAgent를 사용하여 하루에 두 번만 지정된 데이터 저장소에 데이터를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-338">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="c822c-p134">지원되는 명령 매개 변수에 대한 목록을 얻으려면 에이전트(인수 없음)를 실행하세요. 예를 들면 'EdmUploadAgent.exe'가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-p134">To a get a list out of the supported command parameters, run the agent no arguments. For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="c822c-341">EDM 업로드 에이전트에 권한을 부여하고 명령 프롬프트 창을 열고 (관리자 권한으로) **C:\EDM\Data** 디렉토리로 전환한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-341">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="c822c-342">EDM_DataUploaders 보안 그룹에 추가된 Microsoft 365용 회사 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-342">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="c822c-343">테넌트 정보는 연결을 위해 사용자 계정에서 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-343">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="c822c-344">선택 사항: 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사를 사용하여 스키마 및 패턴 파일을 생성한 경우 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-344">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   `EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

4. <span data-ttu-id="c822c-345">중요한 데이터를 해시하고 업로드하려면 명령 프롬프트 창에서 다음 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-345">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"]`

   <span data-ttu-id="c822c-346">예: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="c822c-346">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="c822c-347">중요한 데이터 파일의 기본 형식은 콤보로 구분된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-347">The default format for the sensitive data file is comma-separated values.</span></span> <span data-ttu-id="c822c-348">/ColumnSeparator 매개 변수를 사용하여 "{Tab}" 옵션을 지정하여 탭으로 구분된 파일을 지정하거나 "|" 옵션을 지정하여 파이프로 구분된 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-348">You can specify a tab-separated file by indicating the "{Tab}" option with the /ColumnSeparator parameter, or you can specify a pipe-separated file by indicating the "|" option.</span></span>  
   <span data-ttu-id="c822c-349">이 명령은 보안을 강화하기 위해 임의로 생성된 솔트 값을 해시에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-349">This command will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="c822c-350">선택에 따라, 고유한 솔트 값을 사용하려면 **/Salt <saltvalue>** 를 명령에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-350">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="c822c-351">이 값은 길이가 64자여야 하며 a-z 문자와 0-9만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-351">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="c822c-352">다음 명령을 실행하여 업로드 상태를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-352">Check the upload status by running this command:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

   <span data-ttu-id="c822c-353">예: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="c822c-353">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="c822c-354">상태가 **ProcessingInProgress** 인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-354">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="c822c-355">상태가 **완료** 로 변경될 때까지 몇 분마다 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-355">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="c822c-356">상태가 완료되면 EDM 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-356">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="c822c-357">별도의 해시 및 업로드</span><span class="sxs-lookup"><span data-stu-id="c822c-357">Separate Hash and upload</span></span>

<span data-ttu-id="c822c-358">안전한 환경의 컴퓨터에서 해시를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-358">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="c822c-359">선택 사항: 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사를 사용하여 스키마 및 패턴 파일을 생성한 경우 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-359">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

1. <span data-ttu-id="c822c-360">명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-360">Run the following command in Command Prompt windows:</span></span>

   `EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] >`

   <span data-ttu-id="c822c-361">예를 들면 :</span><span class="sxs-lookup"><span data-stu-id="c822c-361">For example:</span></span>

   > <span data-ttu-id="c822c-362">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="c822c-362">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="c822c-363">**/Salt <saltvalue>** 옵션을 지정하지 않은 경우 해시 파일과 이러한 확장자를 가진 솔트 파일이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-363">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
   - <span data-ttu-id="c822c-364">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="c822c-364">.EdmHash</span></span>
   - <span data-ttu-id="c822c-365">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="c822c-365">.EdmSalt</span></span>

2. <span data-ttu-id="c822c-366">테넌트에 중요한 항목.csv .tsv 파일(PatientRecords)을 업로드하는 데 사용할 컴퓨터에 안전한 .csv 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-366">Copy these files in a secure fashion to the computer you will use to upload your sensitive items .csv or .tsv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="c822c-367">해시된 데이터를 업로드하려면 Windows 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-367">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   `EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

   <span data-ttu-id="c822c-368">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="c822c-368">For example:</span></span>

   > <span data-ttu-id="c822c-369">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="c822c-369">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


   <span data-ttu-id="c822c-370">중요한 데이터가 업로드 되었는지 확인하려면 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-370">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /GetDataStore`

   <span data-ttu-id="c822c-371">데이터 저장소 목록 및 마지막 업데이트 날짜를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-371">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="c822c-372">특정 저장소에 대한 모든 데이터 업로드를 표시하려면 Windows 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-372">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

   <span data-ttu-id="c822c-373">계속하여 [중요한 정보 데이터베이스 새로 고침](#refreshing-your-sensitive-information-database)의 프로세스 및 일정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-373">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="c822c-374">이제 Microsoft 클라우드 서비스로 EDM 기반 분류를 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-374">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="c822c-375">예를 들어 [EDM 기반 분류를 사용하여 DLP 정책을 설정](#to-create-a-dlp-policy-with-edm)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-375">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="c822c-376">중요한 정보 데이터베이스 새로 고침</span><span class="sxs-lookup"><span data-stu-id="c822c-376">Refreshing your sensitive information database</span></span>

<span data-ttu-id="c822c-377">중요한 정보 데이터베이스를 매일 새로 고칠 수 있으며, EDM 업로드 도구를 사용하여 중요한 데이터를 다시 색인화한 다음 색인화된 데이터를 다시 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-377">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="c822c-378">중요한 정보 데이터베이스를 새로 고치는 빈도(매일 또는 매주)와 프로세스를 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-378">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="c822c-379">중요한 데이터를 앱으로 다시 내보내고(예: Microsoft Excel) 파일을 .csv .tsv 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-379">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv or .tsv format.</span></span> <span data-ttu-id="c822c-380">[중요한 데이터 해시 및 업로드](#part-2-hash-and-upload-the-sensitive-data)에 설명된 단계를 따를 때 사용한 것과 동일한 파일 이름과 위치를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-380">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="c822c-381">.csv 또는 .tsv 파일의 구조(필드 이름)가 변경되지 않은 경우 데이터를 새로 고칠 때 데이터베이스 체계 파일을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-381">If there are no changes to the structure (field names) of the .csv or .tsv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="c822c-382">하지만 변경해야 하는 경우 데이터베이스 스키마와 규칙 패키지를 적절하게 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-382">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="c822c-383">[작업 스케줄러](/windows/desktop/TaskSchd/task-scheduler-start-page)를 사용하여 [중요한 데이터 해시 및 업로드](#part-2-hash-and-upload-the-sensitive-data) 절차의 2단계와 3단계를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-383">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="c822c-384">다음과 같은 여러 방법을 사용하여 작업을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-384">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="c822c-385">메서드</span><span class="sxs-lookup"><span data-stu-id="c822c-385">Method</span></span>             | <span data-ttu-id="c822c-386">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="c822c-386">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="c822c-387">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c822c-387">Windows PowerShell</span></span>     | <span data-ttu-id="c822c-388">[ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) 문서와 이 문서에 있는 [예제 Windows PowerShell 스크립트](#example-powershell-script-for-task-scheduler)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-388">See the [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="c822c-389">작업 스케줄러 API</span><span class="sxs-lookup"><span data-stu-id="c822c-389">Task Scheduler API</span></span>     | <span data-ttu-id="c822c-390">[작업 스케줄러](/windows/desktop/TaskSchd/using-the-task-scheduler) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c822c-390">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="c822c-391">Windows 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c822c-391">Windows user interface</span></span> | <span data-ttu-id="c822c-392">Windows에서 **시작** 을 클릭하고 작업 스케줄러를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-392">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="c822c-393">그런 다음 결과 목록에서 **작업 스케줄러** 를 마우스 오른쪽 단추로 클릭하고 **관리자로 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-393">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="c822c-394">작업 스케줄러의 예제 Windows PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="c822c-394">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="c822c-395">이 섹션에는 데이터를 해시하고 해시 데이터를 업로드하는 작업을 예약하는 데 사용할 수 있는 예제 PowerShell 스크립트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-395">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="c822c-396">해시를 예약하고 결합된 단계로 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="c822c-396">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="c822c-397">해시를 예약하고 별도의 단계로 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="c822c-397">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password

```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="c822c-398">3단계: Microsoft 클라우드 서비스로 EDM 기반 분류 사용</span><span class="sxs-lookup"><span data-stu-id="c822c-398">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="c822c-399">이러한 위치는 지원 EDM 중요 정보 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-399">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="c822c-400">Exchange Online용 DLP(전자 메일)</span><span class="sxs-lookup"><span data-stu-id="c822c-400">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="c822c-401">비즈니스용 OneDrive(파일)</span><span class="sxs-lookup"><span data-stu-id="c822c-401">OneDrive for Business (files)</span></span>
- <span data-ttu-id="c822c-402">Microsoft Teams(대화)</span><span class="sxs-lookup"><span data-stu-id="c822c-402">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="c822c-403">SharePoint용 DLP(파일)</span><span class="sxs-lookup"><span data-stu-id="c822c-403">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="c822c-404">Microsoft Cloud App Security DLP 정책</span><span class="sxs-lookup"><span data-stu-id="c822c-404">Microsoft Cloud App Security DLP policies</span></span>
- <span data-ttu-id="c822c-405">서버 쪽 자동 레이블 지정 정책 - 상업용 클라우드 고객에게 제공</span><span class="sxs-lookup"><span data-stu-id="c822c-405">Server-side auto-labeling policies - available for commercial cloud customers</span></span> <!--, UNCOMMENT THIS ON 6/15 and government cloud customers-->

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="c822c-406">EDM으로 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c822c-406">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="c822c-407">[구독에 적합한 링크](#portal-links-for-your-subscription)를 사용하여 보안 및 규정 준수 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-407">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="c822c-408">**데이터 손실 방지** \>**정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-408">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="c822c-409">**정책 만들기** \> **사용자 지정** \> **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-409">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="c822c-410">**정책 이름 지정** 탭에서 이름과 설명을 지정한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-410">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="c822c-411">**위치 선택** 탭에서 **특정 위치 선택 허용** 을 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-411">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="c822c-412">**상태** 열에서 **Exchange 전자 메일, OneDrive 계정, Teams 채팅 및 채널 메시지** 를 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-412">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="c822c-413">**정책 설정** 탭에서 **고급 설정 사용** 을 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-413">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="c822c-414">**+ 새 규칙** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-414">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="c822c-415">**이름** 섹션에서 규칙의 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-415">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="c822c-416">**조건** 섹션의 **+ 조건 추가** 목록에서 **콘텐츠가 중요한 유형을 포함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-416">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![콘텐츠가 중요한 정보 유형을 포함](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="c822c-418">규칙 패키지를 설정할 때 만든 중요한 정보 유형을 검색한 다음 **+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-418">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="c822c-419">그런 다음 **완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-419">Then choose **Done**.</span></span>

12. <span data-ttu-id="c822c-420">**사용자 알림**, **사용자 재정의**, **인시던트 보고서** 등의 규칙에 관한 옵션 선택을 완료한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-420">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="c822c-421">**정책 설정** 탭에서 규칙을 검토하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-421">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="c822c-422">정책을 바로 설정할지, 테스트할지, 아니면 설정 해제한 상태로 유지할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-422">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="c822c-423">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-423">Then choose **Next**.</span></span>

15. <span data-ttu-id="c822c-424">**설정 검토** 탭에서 정책을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-424">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="c822c-425">필요한 대로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-425">Make any needed changes.</span></span> <span data-ttu-id="c822c-426">준비가 되면 **만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-426">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="c822c-427">새로운 DLP 정책이 데이터 센터에 적용되는 데 1시간 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="c822c-427">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c822c-428">관련 문서</span><span class="sxs-lookup"><span data-stu-id="c822c-428">Related articles</span></span>

- [<span data-ttu-id="c822c-429">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="c822c-429">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="c822c-430">중요한 정보 유형에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="c822c-430">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="c822c-431">데이터 손실 방지에 대해 자세한 알아보기</span><span class="sxs-lookup"><span data-stu-id="c822c-431">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="c822c-432">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c822c-432">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="c822c-433">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="c822c-433">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="c822c-434">구성 가능한 일치를 사용하도록 정확한 데이터 일치 스키마 수정</span><span class="sxs-lookup"><span data-stu-id="c822c-434">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)
