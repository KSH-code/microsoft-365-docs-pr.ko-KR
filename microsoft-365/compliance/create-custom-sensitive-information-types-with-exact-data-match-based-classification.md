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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 매치 기반 분류를 사용하여 사용자 지정 중요한 정보 유형을 만드는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c47d682d7b3c52fa5ca5b71386a764f3b3da693
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546960"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="0f315-103">분류에 기반한 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="0f315-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="0f315-104">[사용자 지정 중요한 정보 유형](custom-sensitive-info-types.md) 은 중요한 항목을 식별하는 데 사용되므로 해당 정보 유형이 실수로 또는 부적절하게 공유되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="0f315-105">다음을 기반으로 사용자 지정 중요한 정보 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="0f315-106">패턴</span><span class="sxs-lookup"><span data-stu-id="0f315-106">patterns</span></span>
- <span data-ttu-id="0f315-107"> *직원*, *배지*또는 *ID*와 같은 키워드 증명 정보</span><span class="sxs-lookup"><span data-stu-id="0f315-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="0f315-108">특정 패턴의 증거에 대한 문자 근접성</span><span class="sxs-lookup"><span data-stu-id="0f315-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="0f315-109">신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="0f315-109">confidence levels</span></span>

 <span data-ttu-id="0f315-110">이러한 사용자 지정 중요한 정보 유형은 대부분의 조직에 필요한 비즈니스 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="0f315-111">하지만 일반적인 패턴을 기반으로 일치 항목을 찾는 대신 정확한 데이터 값을 사용하는 사용자 지정 중요한 정보 유형을 원한다면 어떻게 해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="0f315-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="0f315-112">정확한 데이터 매치(EDM) 기반 분류를 사용하여 다음과 같이 설계된 사용자 지정 중요한 정보 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="0f315-113">동적이며 새로 고치기 가능</span><span class="sxs-lookup"><span data-stu-id="0f315-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="0f315-114">확장성 향상</span><span class="sxs-lookup"><span data-stu-id="0f315-114">be more scalable</span></span>
- <span data-ttu-id="0f315-115">가양성 수 감소</span><span class="sxs-lookup"><span data-stu-id="0f315-115">result in fewer false-positives</span></span>
- <span data-ttu-id="0f315-116">구조화된 중요한 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="0f315-116">work with structured sensitive data</span></span>
- <span data-ttu-id="0f315-117">중요한 정보를 더 안전하게 처리</span><span class="sxs-lookup"><span data-stu-id="0f315-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="0f315-118">여러 Microsoft 클라우드 서비스와 함께 사용 가능</span><span class="sxs-lookup"><span data-stu-id="0f315-118">be used with several Microsoft cloud services</span></span>

![EDM 기반 분류](../media/EDMClassification.png)

<span data-ttu-id="0f315-120">EDM 기반 분류를 사용하면 중요한 정보 데이터베이스의 정확한 값을 참조하는 사용자 지정 중요한 정보 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="0f315-121">데이터베이스는 매일 새로 고칠 수 있으며 최대 1억 행의 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="0f315-122">직원, 환자 또는 고객이 계속 이동하고 기록이 변경됨에 따라 사용자 지정 중요한 정보 유형을 적절하고 최신인 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="0f315-123">또한 EDM 기반 분류를 [데이터 손실 방지 정책(DLP)](data-loss-prevention-policies.md) 또는 [Microsoft Cloud App Security 파일 정책](https://docs.microsoft.com/cloud-app-security/data-protection-policies) 등의 정책과 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="0f315-124">Microsoft 365 Information Protection은 이제 다음에 대해 미리보기 더블 바이트 문자 집합 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="0f315-125">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="0f315-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="0f315-126">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="0f315-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="0f315-127">한국어</span><span class="sxs-lookup"><span data-stu-id="0f315-127">Korean</span></span>
> - <span data-ttu-id="0f315-128">일본어</span><span class="sxs-lookup"><span data-stu-id="0f315-128">Japanese</span></span>
> 
><span data-ttu-id="0f315-129">이 미리 보기는 상용 클라우드에서만 실행되며 롤아웃은 다음으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-129">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="0f315-130">일본</span><span class="sxs-lookup"><span data-stu-id="0f315-130">Japan</span></span>
> - <span data-ttu-id="0f315-131">한국</span><span class="sxs-lookup"><span data-stu-id="0f315-131">Korea</span></span>
> - <span data-ttu-id="0f315-132">중국</span><span class="sxs-lookup"><span data-stu-id="0f315-132">China</span></span>
> - <span data-ttu-id="0f315-133">홍콩</span><span class="sxs-lookup"><span data-stu-id="0f315-133">Hong Kong</span></span>
> - <span data-ttu-id="0f315-134">마카오</span><span class="sxs-lookup"><span data-stu-id="0f315-134">Macau</span></span>
> - <span data-ttu-id="0f315-135">대만</span><span class="sxs-lookup"><span data-stu-id="0f315-135">Taiwan</span></span>
>
><span data-ttu-id="0f315-136">이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-136">This support is available for sensitive information types.</span></span> <span data-ttu-id="0f315-137">자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-137">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="0f315-138">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="0f315-138">Required licenses and permissions</span></span>

<span data-ttu-id="0f315-139">이 문서에 설명된 작업을 수행하려면 전역 관리자, 준수 관리자 또는 Exchange Online 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-139">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="0f315-140">DLP 권한에 관한 자세한 내용은  [사용 권한](data-loss-prevention-policies.md#permissions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-140">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="0f315-141">EDM 기반 분류가 이 구독에 포함되어 있습니다</span><span class="sxs-lookup"><span data-stu-id="0f315-141">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="0f315-142">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="0f315-142">Office 365 E5</span></span>
- <span data-ttu-id="0f315-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0f315-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="0f315-144">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="0f315-144">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="0f315-145">Microsoft E5/A5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="0f315-145">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="0f315-146">구독을 위한 포털 링크</span><span class="sxs-lookup"><span data-stu-id="0f315-146">Portal links for your subscription</span></span>


|<span data-ttu-id="0f315-147">포털</span><span class="sxs-lookup"><span data-stu-id="0f315-147">Portal</span></span>  |<span data-ttu-id="0f315-148">전세계/GCC</span><span class="sxs-lookup"><span data-stu-id="0f315-148">World Wide/GCC</span></span>  |<span data-ttu-id="0f315-149">GCC-High</span><span class="sxs-lookup"><span data-stu-id="0f315-149">GCC-High</span></span>  |<span data-ttu-id="0f315-150">DOD</span><span class="sxs-lookup"><span data-stu-id="0f315-150">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="0f315-151">Office SCC</span><span class="sxs-lookup"><span data-stu-id="0f315-151">Office SCC</span></span>     |  <span data-ttu-id="0f315-152">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="0f315-152">protection.office.com</span></span>       |<span data-ttu-id="0f315-153">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="0f315-153">scc.office365.us</span></span>         |<span data-ttu-id="0f315-154">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="0f315-154">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="0f315-155">Microsoft 365 보안 센터</span><span class="sxs-lookup"><span data-stu-id="0f315-155">Microsoft 365 Security center</span></span>     |<span data-ttu-id="0f315-156">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0f315-156">security.microsoft.com</span></span>         |<span data-ttu-id="0f315-157">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="0f315-157">security.microsoft.us</span></span>         |<span data-ttu-id="0f315-158">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="0f315-158">security.apps.mil</span></span>|
|<span data-ttu-id="0f315-159">Microsoft 365 규정 준수 센터</span><span class="sxs-lookup"><span data-stu-id="0f315-159">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="0f315-160">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0f315-160">compliance.microsoft.com</span></span>         |<span data-ttu-id="0f315-161">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="0f315-161">compliance.microsoft.us</span></span>         |<span data-ttu-id="0f315-162">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="0f315-162">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="0f315-163">워크플로 한 눈에 보기</span><span class="sxs-lookup"><span data-stu-id="0f315-163">The work flow at a glance</span></span>

|<span data-ttu-id="0f315-164">단계</span><span class="sxs-lookup"><span data-stu-id="0f315-164">Phase</span></span>  |<span data-ttu-id="0f315-165">필요한 사항</span><span class="sxs-lookup"><span data-stu-id="0f315-165">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="0f315-166">1단계: EDM 기반 분류 설정</span><span class="sxs-lookup"><span data-stu-id="0f315-166">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="0f315-167">(필요한 대로 수행)</span><span class="sxs-lookup"><span data-stu-id="0f315-167">(As needed)</span></span><br/><span data-ttu-id="0f315-168">- [데이터베이스 스키마 편집](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="0f315-168">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="0f315-169">- [스키마 제거](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="0f315-169">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="0f315-170">- 중요한 데이터에 대한 읽기 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="0f315-170">- Read access to the sensitive data</span></span><br/><span data-ttu-id="0f315-171">- XML 형식의 데이터베이스 스키마(예제 제공)</span><span class="sxs-lookup"><span data-stu-id="0f315-171">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="0f315-172">- XML 형식의 규칙 패키지(예제 제공)</span><span class="sxs-lookup"><span data-stu-id="0f315-172">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="0f315-173">- 보안 및 준수 센터에 대한 관리자 권한(Windows PowerShell 사용)</span><span class="sxs-lookup"><span data-stu-id="0f315-173">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="0f315-174">2부: 중요 한 데이터를 해시하고 업로드</span><span class="sxs-lookup"><span data-stu-id="0f315-174">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="0f315-175">(필요한 대로 수행)</span><span class="sxs-lookup"><span data-stu-id="0f315-175">(As needed)</span></span><br/>[<span data-ttu-id="0f315-176">데이터 새로 고침</span><span class="sxs-lookup"><span data-stu-id="0f315-176">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="0f315-177">- 사용자 지정 보안 그룹 및 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="0f315-177">- Custom security group and user account</span></span><br/><span data-ttu-id="0f315-178">- EDM 업로드 에이전트가 있는 컴퓨터에 대한 로컬 관리자 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="0f315-178">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="0f315-179">- 중요한 데이터에 대한 읽기 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="0f315-179">- Read access to the sensitive data</span></span><br/><span data-ttu-id="0f315-180">- 데이터를 새로 고치는 프로세스 및 일정</span><span class="sxs-lookup"><span data-stu-id="0f315-180">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="0f315-181">3단계: Microsoft 클라우드 서비스로 EDM 기반 분류 사용</span><span class="sxs-lookup"><span data-stu-id="0f315-181">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="0f315-182">- DLP를 포함하는 Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="0f315-182">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="0f315-183">- EDM 기반 분류 기능 사용</span><span class="sxs-lookup"><span data-stu-id="0f315-183">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="0f315-184">1단계: EDM 기반 분류 설정</span><span class="sxs-lookup"><span data-stu-id="0f315-184">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="0f315-185">EDM 기반 분류 설정 및 구성에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-185">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="0f315-186">Csv 형식으로 중요한 데이터 저장</span><span class="sxs-lookup"><span data-stu-id="0f315-186">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="0f315-187">중요한 정보 데이터베이스 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="0f315-187">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="0f315-188">규칙 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="0f315-188">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="0f315-189">.csv 형식으로 중요한 데이터 저장</span><span class="sxs-lookup"><span data-stu-id="0f315-189">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="0f315-190">사용하려는 중요한 정보를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-190">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="0f315-191">Microsoft Excel과 같은 앱에 데이터를 내보내고 .csv 형식으로 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-191">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="0f315-192">데이터 파일에는 최대 다음을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-192">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="0f315-193">최대 1억 개의 중요한 데이터 행</span><span class="sxs-lookup"><span data-stu-id="0f315-193">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="0f315-194">데이터 원본당 최대 32개의 열(필드)</span><span class="sxs-lookup"><span data-stu-id="0f315-194">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="0f315-195">검색 가능으로 표시된 최대 5개의 열(필드)</span><span class="sxs-lookup"><span data-stu-id="0f315-195">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="0f315-196">첫 번째 행에 EDM 기반 분류에 사용한 필드의 이름이 포함되도록 .csv 파일에 중요한 데이터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-196">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="0f315-197">.csv 파일에는 "ssn", "birthdate", "firstname", "lastname"와 같은 필드 이름이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-197">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="0f315-198">열 머리글 이름에는 공백이나 밑줄이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-198">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="0f315-199">예를 들어, 이 문서에서 사용하는 샘플 csv 파일은  *PatientRecords.csv*라고 하며 해당 열에는  *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* 등이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-199">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="0f315-200">중요한 정보 데이터베이스의 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="0f315-200">Define the schema for your database of sensitive information</span></span>

3. <span data-ttu-id="0f315-201">중요한 정보 데이터의 스키마를 XML 형식으로 정의합니다(아래 예제와 비슷).</span><span class="sxs-lookup"><span data-stu-id="0f315-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="0f315-202">이 스키마 파일의 이름을  **edm.xml**로 지정하고 데이터베이스의 각 열에 구문을 사용하는 줄이 있도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="0f315-203">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="0f315-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="0f315-204"> *Field name* 값에 열 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="0f315-205">최대 5개의 필드까지 검색할 수 있게 하려는 필드에 *searchable="true"* 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="0f315-206">하나 이상의 필드를 검색할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="0f315-207">예를 들어 다음 XML 파일에서는 5개의 *필드(PatientID*, *MRN*, *SSN*, *Phone* 및 *DOB*)가 검색 가능으로 지정된 환자 레코드 데이터베이스의 스키마를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="0f315-208">(여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="0f315-208">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" />
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

4. <span data-ttu-id="0f315-209">[보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="0f315-209">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="0f315-210">데이터베이스 스키마를 업로드 하려면 다음과 같은 cmdlet을 한 번에 하나씩 실행하십시오:</span><span class="sxs-lookup"><span data-stu-id="0f315-210">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="0f315-211">다음과 같이 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-211">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="0f315-212">확인</span><span class="sxs-lookup"><span data-stu-id="0f315-212">Confirm</span></span>
      >
      > <span data-ttu-id="0f315-213">이 작업을 수행하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="0f315-213">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="0f315-214">'patientrecords' 데이터 저장소의 새로운 EDM 스키마를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-214">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="0f315-215">\[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):</span><span class="sxs-lookup"><span data-stu-id="0f315-215">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="0f315-216">5단계에서 확인하지 않고 변경 사항을 적용하려면 New-DlpEdmSchema -FileData $edmSchemaXml 대신 해당 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-216">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="0f315-217">EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-217">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="0f315-218">추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-218">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="0f315-219">규칙 패키지 설정</span><span class="sxs-lookup"><span data-stu-id="0f315-219">Set up a rule package</span></span>

1. <span data-ttu-id="0f315-220">다음 예제와 같이 in XML 형식(유니코드 인코딩 사용)에 규칙 패키지를 생성하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-220">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="0f315-221">(여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="0f315-221">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="0f315-222">규칙 패키지를 설정하는 경우 .csv 파일과 **edm.xml** 파일을 정확하게 참조하도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-222">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="0f315-223">(여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="0f315-223">You can copy, modify, and use our example.</span></span> <span data-ttu-id="0f315-224">이 샘플 xml에서 EDM 중요 유형을 만들려면 다음 필드를 사용자 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-224">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="0f315-225">**RulePack ID & ExactMatch ID**: [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)를  사용하여 GUID를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-225">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="0f315-226">**Datastore**: 이 필드는 사용할 EDM 조회 데이터 저장소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-226">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="0f315-227">구성된 EDM 스키마의 데이터 원본 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-227">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="0f315-228">**idMatch**: 이 필드는 EDM의 기본 요소를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-228">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="0f315-229">Matches: 정확한 조회에 사용할 필드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-229">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="0f315-230">데이터 저장소의 EDM 스키마에서 검색 가능한 필드 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-230">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="0f315-231">Classification: 이 필드는 EDM 조회를 트리거하는 중요한 유형 일치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-231">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="0f315-232">기존의 기본 제공 분류 또는 사용자 지정 분류의 이름 또는 GUID를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-232">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="0f315-233">**Match:** 이 필드는 idMatch의 근접성에서 찾은 추가 증명을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-233">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="0f315-234">Matches: 데이터 저장소의 EDM 스키마에 필드 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-234">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="0f315-235">**리소스:** 이 섹션에서는 여러 로캘에서 중요한 유형의 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-235">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="0f315-236">idRef: ExactMatch ID의 GUID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-236">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="0f315-237">이름 및 설명: 필요에 따라 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-237">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="0f315-238">다음의 PowerShell cmdlet을 한 번에 하나씩 실행하여 규칙 패키지를 업로드하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-238">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="0f315-239">이 시점에서 EDM 기반 분류를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-239">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="0f315-240">다음 단계는 중요 한 데이터를 해시한 다음 인덱싱하는 해시를 업로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-240">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="0f315-241">PatientRecords 스키마가 검색 가능한 것으로 5개의 필드를 정의한 이전 절차에서 *PatientID*, *MRN*, *SSN*, *Phone* 및 *DOB*를 불러오세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-241">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="0f315-242">예제 규칙 패키지에는 해당 필드가 포함되어 있으며 검색 가능한 필드당 하나의 *ExactMatch* 항목과 함께 데이터베이스 스키마 파일(**edm.xml**)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-242">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="0f315-243">다음의 ExactMatch 항목을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-243">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="0f315-244">이 예에서는 다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-244">In this example, note that:</span></span>

- <span data-ttu-id="0f315-245">데이터 저장소 이름은 이전에 생성한 .csv 파일( **데이터 저장소 = "PatientRecords"**)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-245">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="0f315-246">idmatch 값은 데이터베이스 스키마 파일( **idMatch matches = "SSN"**)에 나열된 검색 가능한 필드를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-246">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="0f315-247">분류 값이 기존 또는 사용자 지정 중요한 정보 유형( **분류 = "미국 SSN(사회 보장 번호)"**)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-247">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="0f315-248">(이 경우 미국 주민 등록 번호의 기존의 중요한 정보 유형을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="0f315-248">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="0f315-249">EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-249">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="0f315-250">추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-250">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="0f315-251">EDM 기반 분류에 대한 스키마 편집</span><span class="sxs-lookup"><span data-stu-id="0f315-251">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="0f315-252">EDM 기반 분류에 사용되는 필드를 변경하는 것과 같이 **edm.xml** 파일을 변경하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-252">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="0f315-253">**edm.xml** 파일을 편집하세요.(해당 문서의 [스키마 정의](#define-the-schema-for-your-database-of-sensitive-information) 섹션에서 다루는 파일입니다.)</span><span class="sxs-lookup"><span data-stu-id="0f315-253">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="0f315-254">[보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="0f315-254">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="0f315-255">데이터베이스 스키마를 업데이트하려면 다음과 같은 cmdlet을 한 번에 하나씩 실행하십시오:</span><span class="sxs-lookup"><span data-stu-id="0f315-255">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="0f315-256">다음과 같이 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-256">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="0f315-257">확인</span><span class="sxs-lookup"><span data-stu-id="0f315-257">Confirm</span></span>
      >
      > <span data-ttu-id="0f315-258">이 작업을 수행하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="0f315-258">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="0f315-259">'patientrecords' 데이터 저장소의 새로운 EDM 스키마를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-259">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="0f315-260">\[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):</span><span class="sxs-lookup"><span data-stu-id="0f315-260">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="0f315-261">3단계에서 확인하지 않고 변경 사항을 적용하려면 Set-DlpEdmSchema -FileData $edmSchemaXml 대신 해당 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-261">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="0f315-262">EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-262">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="0f315-263">추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-263">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="0f315-264">EDM 기반 분류에 대한 스키마 제거</span><span class="sxs-lookup"><span data-stu-id="0f315-264">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="0f315-265">(필요한 경우) EDM 기반 분류에 사용 중인 스키마를 제거하려면 다음 단계를 따르십시오:</span><span class="sxs-lookup"><span data-stu-id="0f315-265">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="0f315-266">[보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="0f315-266">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="0f315-267">다음의 PowerShell cmdlet을 실행하여 "patientrecords"의 데이터 저장소 이름을 제거하려는 저장소 이름으로 대체하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-267">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="0f315-268">다음을 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-268">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="0f315-269">확인</span><span class="sxs-lookup"><span data-stu-id="0f315-269">Confirm</span></span>
      >
      > <span data-ttu-id="0f315-270">이 작업을 수행하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="0f315-270">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="0f315-271">'patientrecords' 데이터 저장소의 EDM 스키마를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-271">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="0f315-272">\[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):</span><span class="sxs-lookup"><span data-stu-id="0f315-272">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="0f315-273">2단계에서 확인하지 않고 변경 사항을 적용하려면 Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false 대신 해당 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-273">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


<!-- salt notes
need two salting procedures, one for onestep from the externally facing and another for two step, on an internal machine then the upload from the external machine

- create A  folder put the edmupload agent and, csv and salt file there, run all processes there
- 
- stuff you need to have first: DataStoreName, /DataFile name (csv file)  /Hashlocation

- salt can be randomly generated by Microsoft or can be provided by the customer. If provided by the customer it must follow  format of 64 character, and can contain only letters or 0-9 characters.  Use a website to generate a valid salt value.
 
- can run EDMuploadagent.exe from PS or Windows cmd window . tested on Windows Server 2016 or Windows 10 and dot net version 4.6.2

when defiuning the schema file the searchable fields must be either an out of box SIT or custom SIT, only 5 fields )column headings) can be searchable

1. From outbound access device from the cmd prompt run EdmUploadAgent.exe /Authorize -  
2. data store schema must have already been uploaded
3.  create hash first then do upload
4. EdmUploadAgent.exe /CreateHash /DataFile (where the data file is ) E:\emd\test\data\schema32_1000000,csv /HashLocation  (where to store it) E:\edm\tat\hash this makes the salt file and the hash file as output
5. next is upload EdmUploadAgent.exe /UploadHash /DataStoreName (found in the Schema file DataSore name="FOO" /HashFile (path to hash file locaztion and file name /HashLocation path to hash)  for example
1.EdmUploadAgent/exe /UploadHash /DataStoreName schema321 /HashFile E:\edm\test\hash\schema32_10000000.EdmHash /HashLocation E:\edm\test\hash  -this one  uses MSFT generated salt, so no need to provide

Salt is an optional parameter so if yo uwant to use a custom salt add /salt and the salt value if salt file not copied to the outbound machine 

OR copy both files hash and salt to the same directory and the commmand will get both


OR do it in single step hash, salt ulopad

!! once they download the updated upload agent they will always have SALT, there is no going back.


all in one step: EdmUploadAgent.exe /UploadData /DataStoreName schema321 /DataFile E:\edm\test\data\schema32_10000.csv /HashLocation E:\edm\test\hash

tshooting/check status cmd



Once it gets to completed the admin can start using it in the custom SIT

they have to get their own custom SALT

just copy SALT over in a secure fashion










1.
6.
7.
1.  


 -->

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="0f315-274">2부: 중요한 데이터를 해시하고 업로드</span><span class="sxs-lookup"><span data-stu-id="0f315-274">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="0f315-275">이 단계에서는 사용자 지정 보안 그룹 및 사용자 계정을 설정하고 EDM 업로드 에이전트 도구를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-275">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="0f315-276">그런 다음 이 도구를 사용하여 중요한 데이터를 해시하고 해시한 데이터를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-276">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="0f315-277">해시 및 업로드는 한 대의 컴퓨터를 사용하여 수행하거나 보안 강화를 위해 업로드 단계에서 해싱 단계를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-277">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="0f315-278">한 대의 컴퓨터에서 해시하고 업로드하려면 Microsoft 365 테넌트에 직접 연결할 수 있는 컴퓨터에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-278">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="0f315-279">이렇게하려면 해싱을 위해 일반 텍스트 중요 데이터 파일이 해당 컴퓨터에 있어야합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-279">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="0f315-280">일반 텍스트 중요 데이터 파일을 노출하지 않으려면 안전한 위치에 있는 컴퓨터에서 해당 파일에서 해시한 다음 업로드를 위해 Microsoft 365 테넌트에 직접 연결할 수 있는 컴퓨터에 해시 파일과 솔트 파일을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-280">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="0f315-281">이 시나리오에서는 두 컴퓨터 모두에 EDMUploadAgent가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-281">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="0f315-282">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0f315-282">Prerequisites</span></span>

- <span data-ttu-id="0f315-283">**EDM\_DataUploaders** 보안 그룹에 추가될 Microsoft 365용 회사 또는 학교 계정</span><span class="sxs-lookup"><span data-stu-id="0f315-283">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="0f315-284">EDMUploadAgent 실행을 위한 .NET 버전 4.6.2가있는 Windows 10 또는 Windows Server 2016 시스템</span><span class="sxs-lookup"><span data-stu-id="0f315-284">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="0f315-285">다음에 대한 업로드 컴퓨터의 디렉토리 :</span><span class="sxs-lookup"><span data-stu-id="0f315-285">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="0f315-286">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="0f315-286">EDMUploadAgent</span></span>
    - <span data-ttu-id="0f315-287">예제의 csv 형식 **PatientRecords.csv**의 중요한 항목 파일</span><span class="sxs-lookup"><span data-stu-id="0f315-287">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="0f315-288">및 출력 해시 및 솔트 파일</span><span class="sxs-lookup"><span data-stu-id="0f315-288">and the output hash and salt files</span></span>
    - <span data-ttu-id="0f315-289">**edm.xml** 파일의 데이터 저장소 이름(이 예에서는 `PatientRecords`)</span><span class="sxs-lookup"><span data-stu-id="0f315-289">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="0f315-290">보안 그룹 및 사용자 계정 설정</span><span class="sxs-lookup"><span data-stu-id="0f315-290">Set up the security group and user account</span></span>

1. <span data-ttu-id="0f315-291">전역 관리자로서 [구독에 대한 적절한 링크](#portal-links-for-your-subscription)를 사용하여 관리 센터로 이동하고  [EDM](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)DataUploaders 라는 보안  **그룹 생성\_을 수행합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f315-291">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="0f315-292">한 명 이상의 사용자를 **EDM\_DataUploaders** 보안 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-292">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="0f315-293">(이러한 사용자가 중요한 정보 데이터베이스를 관리합니다.)</span><span class="sxs-lookup"><span data-stu-id="0f315-293">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="0f315-294">한 대의 컴퓨터에서 해시 및 업로드</span><span class="sxs-lookup"><span data-stu-id="0f315-294">Hash and upload from one computer</span></span>

<span data-ttu-id="0f315-295">이 컴퓨터는 Microsoft 365 테넌트에 직접 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-295">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="0f315-296">이 절차를 시작하기 전에  **EDM\_ DataUploaders**  보안 그룹의 구성원인지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-296">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="0f315-297">구독 유형별 EDM 업로드 에이전트에 대한 링크</span><span class="sxs-lookup"><span data-stu-id="0f315-297">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="0f315-298">상업용 + GCC</span><span class="sxs-lookup"><span data-stu-id="0f315-298">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="0f315-299">GCC-High</span><span class="sxs-lookup"><span data-stu-id="0f315-299">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="0f315-300">DoD</span><span class="sxs-lookup"><span data-stu-id="0f315-300">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="0f315-301">EDMUploadAgent에 대한 작업 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-301">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="0f315-302">예를 들어, **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="0f315-302">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="0f315-303">여기에 **PatientRecords.csv** 파일을 배치하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-303">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="0f315-304">구독에 적합한 [EDM 업로드 에이전트](#links-to-edm-upload-agent-by-subscription-type)를 1단계에서 만든 디렉토리에 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-304">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="0f315-305">위 링크의 EDMUploadAgent는 해시된 데이터에 솔트 값을 자동으로 추가하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-305">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="0f315-306">또는 자신의 솔트 값을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-306">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="0f315-307">이 버전을 사용한 후에는 이전 버전의 EDMUploadAgent를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-307">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="0f315-308">EDMUploadAgent를 사용하여 하루에 두 번만 지정된 데이터 저장소에 데이터를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-308">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="0f315-309">지원되는 명령 매개 변수에 대한 목록을 얻으려면 에이전트(인수 없음)를 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-309">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="0f315-310">예를 들어 'EdmUploadAgent'가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-310">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="0f315-311">EDM 업로드 에이전트에 권한을 부여하고 명령 프롬프트 창을 열고 (관리자 권한으로) **C:\EDM\Data** 디렉토리로 전환한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-311">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="0f315-312">EDM_DataUploaders 보안 그룹에 추가된 Microsoft 365용 회사 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-312">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="0f315-313">테넌트 정보는 연결을 위해 사용자 계정에서 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-313">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="0f315-314">중요한 데이터를 해시하고 업로드하려면 명령 프롬프트 창에서 다음 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-314">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="0f315-315">예: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="0f315-315">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="0f315-316">보안 강화를 위해 임의로 생성된 솔트 값을 해시에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-316">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="0f315-317">선택에 따라, 고유한 솔트 값을 사용하려면 **/Salt <saltvalue>** 를 명령에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-317">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="0f315-318">이 값은 길이가 64자여야 하며 a-z 문자와 0-9만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-318">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="0f315-319">다음 명령을 실행하여 업로드 상태를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-319">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="0f315-320">예: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="0f315-320">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="0f315-321">상태가 **ProcessingInProgress**인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-321">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="0f315-322">상태가 **완료**로 변경될 때까지 몇 분마다 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-322">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="0f315-323">상태가 완료되면 EDM 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-323">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="0f315-324">별도의 해시 및 업로드</span><span class="sxs-lookup"><span data-stu-id="0f315-324">Separate Hash and upload</span></span>

<span data-ttu-id="0f315-325">안전한 환경의 컴퓨터에서 해시를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-325">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="0f315-326">명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-326">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="0f315-327">예를 들면 :</span><span class="sxs-lookup"><span data-stu-id="0f315-327">For example:</span></span>

> <span data-ttu-id="0f315-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="0f315-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="0f315-329">**/Salt <saltvalue>** 옵션을 지정하지 않은 경우 해시 파일과 이러한 확장자를 가진 솔트 파일이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-329">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="0f315-330">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="0f315-330">.EdmHash</span></span>
- <span data-ttu-id="0f315-331">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="0f315-331">.EdmSalt</span></span>

2. <span data-ttu-id="0f315-332">중요한 항목 csv 파일(PatientRecords)을 테넌트에 업로드하는 데 사용할 컴퓨터에 이러한 파일을 안전한 방식으로 복사하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-332">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="0f315-333">해시된 데이터를 업로드하려면 Windows 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-333">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="0f315-334">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="0f315-334">For example:</span></span>

> <span data-ttu-id="0f315-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="0f315-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="0f315-336">중요한 데이터가 업로드 되었는지 확인하려면 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-336">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="0f315-337">데이터 저장소 목록 및 마지막 업데이트 날짜를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-337">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="0f315-338">특정 저장소에 대한 모든 데이터 업로드를 표시하려면 Windows 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-338">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="0f315-339">계속하여 [중요한 정보 데이터베이스 새로 고침](#refreshing-your-sensitive-information-database)의 프로세스 및 일정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-339">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="0f315-340">이제 Microsoft 클라우드 서비스로 EDM 기반 분류를 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-340">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="0f315-341">예를 들어 [EDM 기반 분류를 사용하여 DLP 정책을 설정](#to-create-a-dlp-policy-with-edm)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-341">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="0f315-342">중요한 정보 데이터베이스 새로 고침</span><span class="sxs-lookup"><span data-stu-id="0f315-342">Refreshing your sensitive information database</span></span>

<span data-ttu-id="0f315-343">중요한 정보 데이터베이스를 매일 새로 고칠 수 있으며, EDM 업로드 도구를 사용하여 중요한 데이터를 다시 색인화한 다음 색인화된 데이터를 다시 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-343">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="0f315-344">중요한 정보 데이터베이스를 새로 고치는 빈도(매일 또는 매주)와 프로세스를 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-344">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="0f315-345">Microsoft Excel과 같은 앱에 중요한 데이터를 다시 내보내고 .csv 형식으로 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-345">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="0f315-346"> [해시에 설명 된 단계를 수행하고 중요한 데이터](#part-2-hash-and-upload-the-sensitive-data)를 업로드할 때 사용한 것과 동일한 파일 이름과 위치를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-346">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="0f315-347">.csv 파일의 구조(필드 이름)를 변경하지 않은 경우 데이터를 새로 고칠 때 데이터베이스 스키마 파일을 변경하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-347">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="0f315-348">하지만 변경해야 하는 경우 데이터베이스 스키마와 규칙 패키지를 적절하게 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-348">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="0f315-349"> [해시에서 2단계와 3단계를 자동화하고 중요한 데이터](#part-2-hash-and-upload-the-sensitive-data) 절차를 업로드하려면 [작업 스케줄러](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-349">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="0f315-350">다음과 같은 여러 방법을 사용하여 작업을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-350">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="0f315-351">메서드</span><span class="sxs-lookup"><span data-stu-id="0f315-351">Method</span></span>             | <span data-ttu-id="0f315-352">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="0f315-352">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="0f315-353">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f315-353">Windows PowerShell</span></span>     | <span data-ttu-id="0f315-354"> [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) 문서와 이 문서에 있는 [예제 PowerShell 스크립트](#example-powershell-script-for-task-scheduler)를  참고하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-354">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="0f315-355">작업 스케줄러 API</span><span class="sxs-lookup"><span data-stu-id="0f315-355">Task Scheduler API</span></span>     | <span data-ttu-id="0f315-356"> [작업 스케줄러](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f315-356">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="0f315-357">Windows 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f315-357">Windows user interface</span></span> | <span data-ttu-id="0f315-358">Windows에서 **시작**을 클릭하고 작업 스케줄러를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-358">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="0f315-359">그런 다음 결과 목록에서 **작업 스케줄러**를 마우스 오른쪽 단추로 클릭하고 **관리자로 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-359">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="0f315-360">작업 스케줄러의 예제 Windows PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="0f315-360">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="0f315-361">이 섹션에는 데이터를 해시하고 해시 데이터를 업로드하는 작업을 예약하는 데 사용할 수 있는 예제 PowerShell 스크립트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-361">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="0f315-362">해시를 예약하고 결합된 단계로 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="0f315-362">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation
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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="0f315-363">해시를 예약하고 별도의 단계로 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="0f315-363">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="0f315-364">3단계: Microsoft 클라우드 서비스로 EDM 기반 분류 사용</span><span class="sxs-lookup"><span data-stu-id="0f315-364">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="0f315-365">이러한 위치는 지원 EDM 중요 정보 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-365">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="0f315-366">Exchange Online용 DLP(전자 메일)</span><span class="sxs-lookup"><span data-stu-id="0f315-366">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="0f315-367">비즈니스용 OneDrive(파일)</span><span class="sxs-lookup"><span data-stu-id="0f315-367">OneDrive for Business (files)</span></span>
- <span data-ttu-id="0f315-368">Microsoft Teams(대화)</span><span class="sxs-lookup"><span data-stu-id="0f315-368">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="0f315-369">SharePoint용 DLP(파일)</span><span class="sxs-lookup"><span data-stu-id="0f315-369">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="0f315-370">Microsoft Cloud App Security DLP 정책</span><span class="sxs-lookup"><span data-stu-id="0f315-370">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="0f315-371">다음 시나리오에 대한 EDM 중요 정보 유형은 현재 개발 중이지만, 아직 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-371">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="0f315-372">민감도 레이블과 보존 레이블의 자동 분류</span><span class="sxs-lookup"><span data-stu-id="0f315-372">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="0f315-373">EDM으로 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0f315-373">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="0f315-374">[구독에 적합한 링크](#portal-links-for-your-subscription)를 사용하여 보안 및 규정 준수 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-374">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="0f315-375"> **데이터 손실 방지** \> **정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-375">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="0f315-376"> **정책 만들기** \> **사용자 지정** \> **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-376">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="0f315-377"> **정책 이름 지정** 탭에 이름과 설명을 지정하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-377">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="0f315-378"> **위치 선택** 탭에서 **특정 위치 선택 허용**을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-378">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="0f315-379"> **상태** 열에서 **Exchange 전자 메일, OneDrive 계정, Teams 채팅 및 채널 메시지** 를 선택하고  **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-379">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="0f315-380"> **정책 설정** 탭에서 **고급 설정 사용**을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-380">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="0f315-381"> **+ 새 규칙**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-381">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="0f315-382"> **이름** 섹션에서 규칙의 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-382">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="0f315-383"> **조건** 섹션의 **+ 조건 추가** 목록에서 **콘텐츠에 중요한 유형 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-383">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![콘텐츠에 중요한 정보 유형이 포함됨](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="0f315-385">규칙 패키지를 설치할 때 만든 중요한 정보 유형을 검색한 다음  **+ 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-385">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="0f315-386">그런 다음 **완료**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-386">Then choose **Done**.</span></span>

12. <span data-ttu-id="0f315-387"> **사용자 알림**, **사용자 재정의**, **인시던트 보고서** 등의 규칙에 관한 옵션 선택을 완료한 다음 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-387">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="0f315-388"> **정책 설정** 탭에서 규칙을 검토하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-388">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="0f315-389">정책을 바로 설정할지, 테스트할지, 아니면 설정 해제한 상태로 유지할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-389">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="0f315-390">그런 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-390">Then choose **Next**.</span></span>

15. <span data-ttu-id="0f315-391"> **설정 검토** 탭에서 정책을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-391">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="0f315-392">필요한 대로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-392">Make any needed changes.</span></span> <span data-ttu-id="0f315-393">준비가 되면 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-393">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="0f315-394">새로운 DLP 정책이 데이터 센터에 적용되는 데 1시간 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="0f315-394">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0f315-395">관련 문서</span><span class="sxs-lookup"><span data-stu-id="0f315-395">Related articles</span></span>

- [<span data-ttu-id="0f315-396">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="0f315-396">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="0f315-397">사용자 지정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="0f315-397">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="0f315-398">DLP 정책 개요</span><span class="sxs-lookup"><span data-stu-id="0f315-398">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="0f315-399">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0f315-399">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="0f315-400">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="0f315-400">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)

