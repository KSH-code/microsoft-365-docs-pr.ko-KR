---
title: GDPR
description: Microsoft 기술 참고 자료 — 삭제 요청 제출용 FastTrack 마이그레이션 도구 집합
keywords: FastTrack 마이그레이션, Microsoft 365 Education, Microsoft 365 설명서, GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 10a983297640ac4b65aaf181ef35ac19918e74fe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547391"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="fea56-104">삭제 요청 제출용 FastTrack 마이그레이션 도구 집합</span><span class="sxs-lookup"><span data-stu-id="fea56-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="fea56-105">도구 집합 용도</span><span class="sxs-lookup"><span data-stu-id="fea56-105">Toolset purpose</span></span>

<span data-ttu-id="fea56-p101">현재 FastTrack 마이그레이션에 연결된 고객의 경우, 사용자 계정을 삭제하면 Microsoft FastTrack 팀이 보유하는 데이터 복사본이 삭제되지 않습니다. FastTrack 팀은 오직 마이그레이션 완료 목적으로 복사본을 보유합니다. 마이그레이션하는 동안 Microsoft FastTrack 팀이 데이터 복사본도 삭제하게 하려면 이 도구 집합을 통해 요청을 제출하세요. 일반 업무 과정에서 Microsoft FastTrack은 마이그레이션이 완료되면 모든 데이터 복사본을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="fea56-109">지원되는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="fea56-109">Supported platforms</span></span>

<span data-ttu-id="fea56-p102">Microsoft는 Windows 플랫폼 및 PowerShell 콘솔에서 이 도구 집합의 최초 릴리스를 지원합니다. 이 도구 집합은 다음의 알려진 플랫폼을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>

<span data-ttu-id="fea56-112">***테이블 1 — 이 도구 집합에서 지원되는 플랫폼***</span><span class="sxs-lookup"><span data-stu-id="fea56-112">***Table 1 — Platforms supported by this toolset***</span></span>

****

|<span data-ttu-id="fea56-113">PowerShell 버전</span><span class="sxs-lookup"><span data-stu-id="fea56-113">PowerShell version</span></span>|<span data-ttu-id="fea56-114">Windows 7</span><span class="sxs-lookup"><span data-stu-id="fea56-114">Windows 7</span></span>|<span data-ttu-id="fea56-115">Windows 8</span><span class="sxs-lookup"><span data-stu-id="fea56-115">Windows 8</span></span>|<span data-ttu-id="fea56-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="fea56-116">Windows 10</span></span>|<span data-ttu-id="fea56-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fea56-117">Windows Server 2012</span></span>|<span data-ttu-id="fea56-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="fea56-118">Windows Server 2016</span></span>|
|:---:|:---:|:---:|:---:|:---:|:---:|
|<span data-ttu-id="fea56-119">5.0</span><span class="sxs-lookup"><span data-stu-id="fea56-119">5.0</span></span>|<span data-ttu-id="fea56-120">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="fea56-120">Not Supported</span></span>|<span data-ttu-id="fea56-121">않음</span><span class="sxs-lookup"><span data-stu-id="fea56-121">Supported</span></span>|<span data-ttu-id="fea56-122">지원됨</span><span class="sxs-lookup"><span data-stu-id="fea56-122">Supported</span></span>|<span data-ttu-id="fea56-123">지원됨</span><span class="sxs-lookup"><span data-stu-id="fea56-123">Supported</span></span>|<span data-ttu-id="fea56-124">않음</span><span class="sxs-lookup"><span data-stu-id="fea56-124">Supported</span></span>|
|<span data-ttu-id="fea56-125">5.1</span><span class="sxs-lookup"><span data-stu-id="fea56-125">5.1</span></span>|<span data-ttu-id="fea56-126">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="fea56-126">Not Supported</span></span>|<span data-ttu-id="fea56-127">않음</span><span class="sxs-lookup"><span data-stu-id="fea56-127">Supported</span></span>|<span data-ttu-id="fea56-128">지원됨</span><span class="sxs-lookup"><span data-stu-id="fea56-128">Supported</span></span>|<span data-ttu-id="fea56-129">지원됨</span><span class="sxs-lookup"><span data-stu-id="fea56-129">Supported</span></span>|<span data-ttu-id="fea56-130">지원됨</span><span class="sxs-lookup"><span data-stu-id="fea56-130">Supported</span></span>|
|

### <a name="obtaining-the-toolset"></a><span data-ttu-id="fea56-131">도구 집합 획득</span><span class="sxs-lookup"><span data-stu-id="fea56-131">Obtaining the toolset</span></span>

<span data-ttu-id="fea56-p103">이 도구 집합은 PowerShell 콘솔 응용 프로그램의 PowerShell 갤러리에서 사용할 수 있습니다. cmdlet 모듈의 위치를 찾고 로드하려면 먼저 PowerShell을 관리자 모드로 열어서 모듈을 설치할 수 있는 적절한 권한을 획득합니다. 이전에 PowerShell을 사용하지 않은 경우 Windows 작업 막대로 이동하여 검색 상자에 “PowerShell”을 입력합니다. 마우스 오른쪽 단추를 사용하여 콘솔 앱을 선택하고 **관리자 권한으로 실행**을 선택한 다음 **예**를 클릭하여 Windows PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell — 관리자 권한으로 실행](../media/fasttrack-powershell_image.png)

![PowerShell — 앱을 변경할 수 있도록 허용](../media/fasttrack-run-powershell_image.png)

<span data-ttu-id="fea56-138">콘솔이 열려 있으므로 스트립트 실행에 관한 사용 권한을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-138">Now that the console is open, you need to set permissions for script execution.</span></span> <span data-ttu-id="fea56-139">스크립트를 실행할 수 있도록 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-139">Type the following command to allow the scripts to run:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

<span data-ttu-id="fea56-140">관리자 판단에 따라 범위를 변경할 수 있으므로 이 작업을 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-140">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="fea56-141">***실행 정책 설정***</span><span class="sxs-lookup"><span data-stu-id="fea56-141">***Set Execution Policy***</span></span>

![PowerShell에서 실행 정책 변경 설정](../media/powershell-set-execution-policy_image.png)

<span data-ttu-id="fea56-143">이제 콘솔이 스크립트를 허용하도록 설정되었으므로 다음 명령을 실행하여 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-143">Now that the console is set to allow the script, run this next command to install the module:</span></span>

```powershell
Install-Module -Name Microsoft.FastTrack -Repository PSGallery -WarningAction SilentlyContinue -Force
```

### <a name="prerequisites-for-module"></a><span data-ttu-id="fea56-144">모듈의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fea56-144">Prerequisites for module</span></span>

<span data-ttu-id="fea56-p105">이 모듈을 성공적으로 실행하려는 경우 종속 모듈이 설치되어 있지 않으면 먼저 설치해야 합니다. PowerShell을 다시 시작해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>

<span data-ttu-id="fea56-147">DSR을 제출하려면 Office 365 자격 증명을 사용하여 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-147">In order to submit a DSR, you must first log in using your Office 365 credentials.</span></span> <span data-ttu-id="fea56-148">적절한 자격 증명을 입력하면 전역 관리자 상태의 유효성을 검사하고 테넌트 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-148">Entering the proper credentials will validate your global administrator status and collect tenant information.</span></span>

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM>
```

<span data-ttu-id="fea56-149">성공적으로 로그인하면 현재 PowerShell 세션의 나머지에 대해 FastTrack 모듈과 함께 사용하기 위해 자격 증명 및 키가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-149">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="fea56-150">상업 환경 이외의 클라우드 환경에 연결해야 하는 경우 다음 유효한 환경 중 하나를 사용하여 *로그인* 명령에 *-Environment*를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-150">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>

- <span data-ttu-id="fea56-151">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="fea56-151">AzureCloud</span></span>
- <span data-ttu-id="fea56-152">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="fea56-152">AzureChinaCloud</span></span>
- <span data-ttu-id="fea56-153">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="fea56-153">AzureGermanCloud</span></span>
- <span data-ttu-id="fea56-154">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="fea56-154">AzureUSGovernmentCloud</span></span>

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM> -Environment <cloud environment>
```

<span data-ttu-id="fea56-155">DSR 요청을 제줄하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-155">To submit a DSR request, run the following command:</span></span>

```powershell
Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail SubjectUserEmail@mycompany.com
```

<span data-ttu-id="fea56-156">성공하면, cmdlet에서 트랜잭션 ID 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-156">On success, the cmdlet will return a Transaction ID object.</span></span> <span data-ttu-id="fea56-157">트랜잭션 ID를 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="fea56-157">Please retain the Transaction ID.</span></span>

#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="fea56-158">요청 트랜잭션의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="fea56-158">Checking the status of a request transaction</span></span>

<span data-ttu-id="fea56-159">이전에 가져온 트랜잭션 ID를 사용하여 다음 함수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-159">Run the following function using the previously obtained Transaction ID:</span></span>

```powershell
Get-FastTrackGdprDsrRequest -TransactionID "YourTransactionID"
```

#### <a name="transaction-status-codes"></a><span data-ttu-id="fea56-160">트랜잭션 상태 코드</span><span class="sxs-lookup"><span data-stu-id="fea56-160">Transaction Status Codes</span></span>

|<span data-ttu-id="fea56-161">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="fea56-161">Transaction</span></span>|<span data-ttu-id="fea56-162">상태</span><span class="sxs-lookup"><span data-stu-id="fea56-162">Status</span></span>|
|---|---|
|<span data-ttu-id="fea56-163">**만든 날짜**</span><span class="sxs-lookup"><span data-stu-id="fea56-163">**Created**</span></span>|<span data-ttu-id="fea56-164">요청이 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-164">Request has been created.</span></span>|
|<span data-ttu-id="fea56-165">**실패**</span><span class="sxs-lookup"><span data-stu-id="fea56-165">**Failed**</span></span>|<span data-ttu-id="fea56-166">요청을 만들지 못했습니다. 다시 제출하거나 지원 팀에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="fea56-166">Request failed to create, please resubmit, or contact support.</span></span>|
|<span data-ttu-id="fea56-167">**완료**</span><span class="sxs-lookup"><span data-stu-id="fea56-167">**Completed**</span></span>|<span data-ttu-id="fea56-168">요청이 완료되어 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fea56-168">Request has been completed and sanitized.</span></span>|
|

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->

## <a name="learn-more"></a><span data-ttu-id="fea56-169">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="fea56-169">Learn more</span></span>

[<span data-ttu-id="fea56-170">Microsoft 보안 센터</span><span class="sxs-lookup"><span data-stu-id="fea56-170">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
