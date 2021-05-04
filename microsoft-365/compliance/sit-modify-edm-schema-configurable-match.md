---
title: 구성 가능한 일치를 사용하도록 정확한 데이터 일치 스키마 수정
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
description: 구성 가능한 일치를 사용하도록 EDM 스키마를 수정하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d470b986d4a94206935efb832deec7171f8e404
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114196"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="1da1a-103">구성 가능한 일치를 사용하도록 정확한 데이터 일치 스키마 수정</span><span class="sxs-lookup"><span data-stu-id="1da1a-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="1da1a-104">EDM(정확한 데이터 일치) 기반 분류를 사용하면 중요한 정보 데이터베이스의 정확한 값을 참조하는 사용자 지정 중요한 정보 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="1da1a-105">정확한 문자열의 변형을 허용해야 하는 경우, *구성 가능한* 일치를 사용하여 Microsoft 365가 일부 구분 기호를 무시하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1da1a-106">이 절차를 사용하여 기존 EDM 스키마 및 데이터 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="1da1a-107">EDM 스키마 및 데이터 파일 업로드 목적으로 Microsoft 365에 연결하는 데 사용하는 컴퓨터에서 **EdmUploadAgent.exe** 를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="1da1a-108">아래 링크를 사용하여 구독에 적합한 **EdmUploadAgent.exe** 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="1da1a-109">[상업용 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 대부분의 상업용 고객이 사용</span><span class="sxs-lookup"><span data-stu-id="1da1a-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="1da1a-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 특히 높은 보안 정부 클라우드 구독자용</span><span class="sxs-lookup"><span data-stu-id="1da1a-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="1da1a-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 특히 미국 국방부 클라우드 고객용</span><span class="sxs-lookup"><span data-stu-id="1da1a-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="1da1a-112">EDM 업로드 에이전트에 권한을 부여하고 명령 프롬프트 창을 열어(관리자 권한으로) 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="1da1a-113">기존 스키마의 현재 복사본이 없는 경우, 다음 명령을 실행하려면 기존 스키마의 복사본을 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="1da1a-114">각 열이 “caseInsensitive” 및/또는 “ignoredDelimiters”를 활용하도록 스키마를 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="1da1a-115">“caseInsensitive”의 기본값은 “false”이며 “ignoredDelimiters”의 경우는 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="1da1a-116">일반 정규직 패턴을 감지하는 데 사용되는 기본 제공되는 사용자 지정 중요한정보 유형 및 기본 중요한 정보 유형은 ignoredDelimiters로 나열된 변형 입력 감지를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="1da1a-117">예를 들어, 기본 제공되는 SSN(미국 사회 보장 번호) 중요한 정보 유형은 SSN을 구성하는 그룹 번호 간의 대시, 공백 또는 공백 부족을 포함하는 데이터 변형을 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="1da1a-118">따라서, SSN에 대한 EDM의 ignoredDelimiters에 포함되는 것과 관련된 유일한 구분 기호는 대시와 공백입니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="1da1a-119">다음은 중요한 데이터에서 대소문자 변형을 인식하는 데 필요한 추가 열을 만들어서 대소문자 일치를 시뮬레이션하는 샘플 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="1da1a-120">위의 예에서 `caseInsensitive` 및 `ignoredDelimiters` 모두 추가되는 경우, 원래 `PolicyNumber`열의 변형은 더 이상 필요하지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="1da1a-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="1da1a-121">EDM이 구성 가능한 일치를 사용하도록 스키마를 업데이트하려면 `caseInsensitive` 및 `ignoredDelimiters` 플래그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="1da1a-122">다음과 같은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="1da1a-123">`ignoredDelimiters` 플래그는 영숫자가 아닌 모든 문자를 지원하며 다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="1da1a-124">\.</span><span class="sxs-lookup"><span data-stu-id="1da1a-124">\.</span></span>
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

<span data-ttu-id="1da1a-125">`ignoredDelimiters` 플래그는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="1da1a-126">0~9 사이 문자</span><span class="sxs-lookup"><span data-stu-id="1da1a-126">characters 0-9</span></span>
- <span data-ttu-id="1da1a-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="1da1a-127">A-Z</span></span>
- <span data-ttu-id="1da1a-128">a-z</span><span class="sxs-lookup"><span data-stu-id="1da1a-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="1da1a-129">[보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="1da1a-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="1da1a-130">조직에서 [테넌트 수준(공개 미리 보기)에서 Microsoft 365용 고객 키](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview)를 설정한 경우 정확한 데이터 일치는 암호화 기능을 자동으로 사용합니다. </span><span class="sxs-lookup"><span data-stu-id="1da1a-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="1da1a-131">상업용 클라우드의 E5 라이선스 테넌트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="1da1a-132">cmdlets를 한 번에 하나씩 실행하여 다음과 같이 스키마를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="1da1a-133">필요한 경우, 새 스키마 버전과 일치하도록 데이터 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="1da1a-134">선택적으로 다음을 실행하여 업로드하기 전에 csv 파일에 대해 유효성 검사를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="1da1a-135">모든 EdmUploadAgent.exe >에서 지원되는 매개 변수에 대한 자세한 내용은 다음을 실행합니다</span><span class="sxs-lookup"><span data-stu-id="1da1a-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="1da1a-136">명령 프롬프트 창을 열고(관리자 권한으로) 다음 명령을 실행하여 중요한 데이터를 해시하고 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1da1a-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="1da1a-137">관련 문서</span><span class="sxs-lookup"><span data-stu-id="1da1a-137">Related articles</span></span>

- [<span data-ttu-id="1da1a-138">분류에 기반한 정확한 데이터 일치를 사용한 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="1da1a-138">Create a custom sensitive information type with Exact Data Match based classification</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="1da1a-139">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="1da1a-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="1da1a-140">사용자 지정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="1da1a-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="1da1a-141">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="1da1a-141">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="1da1a-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1da1a-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="1da1a-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="1da1a-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)