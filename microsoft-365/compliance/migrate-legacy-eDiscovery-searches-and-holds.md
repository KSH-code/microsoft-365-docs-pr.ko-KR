---
title: 레거시 eDiscovery 검색 및 보류를 Microsoft 365 센터로 마이그레이션
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: aaae5e6bddc48f29cc0766fe26a1976672c7dd49
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310813"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="ba9b3-102">레거시 eDiscovery 검색 및 보류를 Microsoft 365 센터로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ba9b3-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="ba9b3-103">Microsoft 365 규정 준수 센터는 eDiscovery 사용에 대한 향상된 환경을 제공합니다. 높은 안정성, 더 나은 성능 및 eDiscovery 워크플로에 맞게 조정된 많은 기능(문제별로 콘텐츠를 구성하는 사례, 검토용 콘텐츠 및 분석을 검토하는 집합을 검토하여 중복에 가까운 그룹화, 전자 메일 스레딩, 테마 분석 및 예측 코딩)과 같은 검토를 위해 데이터를 선회하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance, and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="ba9b3-104">고객이 새 기능과 향상된 기능을 활용할 수 있도록 이 문서에서는 In-Place eDiscovery 검색 및 보류를 Exchange 관리 센터에서 Microsoft 365 준수 센터로 마이그레이션하는 방법에 대한 기본 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="ba9b3-105">다양한 시나리오가 있기 때문에 이 문서에서는 검색 및 보류를 보안 및 준수 센터의 핵심 eDiscovery 사례로 전환하기 위한 일반적인 Microsoft 365 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ba9b3-106">eDiscovery 사례를 항상 사용할 필요는 없지만 조직의 eDiscovery 사례에 액세스할 수 있는 권한을 할당할 수 있도록 하여 보안 계층을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ba9b3-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="ba9b3-107">Before you begin</span></span>

- <span data-ttu-id="ba9b3-108">이 문서에 설명된 PowerShell 명령을 실행하기 위해 Security & Compliance Center에서 eDiscovery 관리자 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="ba9b3-109">또한 Exchange 관리 센터에서 검색 관리 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="ba9b3-110">이 문서에서는 eDiscovery 보류를 만드는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="ba9b3-111">보류 정책은 비동기 프로세스를 통해 사서함에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="ba9b3-112">eDiscovery 보류를 만들 때 CaseHoldPolicy 및 CaseHoldRule을 모두 만들어야 합니다. 그렇지 않으면 보류가 만들어지지 않고 콘텐츠 위치가 보류되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="ba9b3-113">1단계: 커넥트 PowerShell Exchange Online 보안 센터 PowerShell을 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="ba9b3-114">첫 번째 단계는 PowerShell 및 보안 및 Exchange Online PowerShell에 & 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="ba9b3-115">다음 스크립트를 복사하여 PowerShell 창에 붙여 넣은 다음 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="ba9b3-116">연결할 조직의 자격 증명을 입력하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="ba9b3-117">이 PowerShell 세션의 다음 단계에서 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="ba9b3-118">2단계: eDiscovery 검색을 사용하여 In-Place 목록 Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ba9b3-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="ba9b3-119">인증한 후 **Get-MailboxSearch** cmdlet을 실행하여 In-Place eDiscovery 검색 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="ba9b3-120">다음 명령을 복사하여 PowerShell에 붙여 넣은 다음 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="ba9b3-121">검색 목록은 해당 이름 및 보류 상태와 함께 In-Place 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="ba9b3-122">cmdlet 출력은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell 예제 Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="ba9b3-124">3단계: 마이그레이션할 In-Place eDiscovery 검색 및 In-Place 보류에 대한 정보 얻음</span><span class="sxs-lookup"><span data-stu-id="ba9b3-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="ba9b3-125">다시 **Get-MailboxSearch** cmdlet을 사용하지만 이번에는 검색의 속성을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="ba9b3-126">이러한 속성은 나중에 사용할 수 있는 변수에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="ba9b3-127">다음 예에서는 **Get-MailboxSearch** cmdlet의 결과를 변수에 저장한 다음 검색의 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="ba9b3-128">이러한 두 명령의 출력은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-128">The output of these two commands will be similar to the following:</span></span>

![개별 검색에 대해 Get-MailboxSearch PowerShell 출력의 예](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="ba9b3-130">이 예제에서 보류 In-Place 기간은 *무기한(ItemHoldPeriod: Unlimited)입니다.*</span><span class="sxs-lookup"><span data-stu-id="ba9b3-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="ba9b3-131">이는 eDiscovery 및 법적 조사 시나리오에서 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="ba9b3-132">보존 기간의 값이 무기한과 다른 경우 보존이 보존 시나리오에서 콘텐츠를 보존하는 데 사용되고 있기 때문에 그 이유가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="ba9b3-133">보존 시나리오를 위해 Security & Compliance Center PowerShell에서 eDiscovery cmdlet을 사용하는 대신 [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) 및 [New-RetentionComplianceRule을](/powershell/module/exchange/new-retentioncompliancerule) 사용하여 콘텐츠를 보존하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="ba9b3-134">이러한 cmdlet을 사용하는 결과는 **New-CaseHoldPolicy** 및 **New-CaseHoldRule** 사용과 비슷하지만 보존 기간 및 보존 기간이 만료된 후 콘텐츠를 삭제하는 등의 보존 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="ba9b3-135">또한 보존 cmdlet을 사용하면 보존 보류를 eDiscovery 사례와 연결하지 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="ba9b3-136">4단계: Microsoft 365 센터에서 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="ba9b3-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="ba9b3-137">eDiscovery 보류를 만들 경우 보류를 연결하기 위한 eDiscovery 사례를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="ba9b3-138">다음 예제에서는 선택한 이름을 사용하여 eDiscovery 사례를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="ba9b3-139">나중에 사용할 변수에 새 사례의 속성을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="ba9b3-140">사례를 만든 후 명령을 실행하여 `$case | FL` 이러한 속성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![명령 실행 New-ComplianceCase 예](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="ba9b3-142">5단계: eDiscovery 보류 만들기</span><span class="sxs-lookup"><span data-stu-id="ba9b3-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="ba9b3-143">사례를 만든 후 보류를 만들어 이전 단계에서 만든 사례와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="ba9b3-144">사례 보류 정책과 케이스 보류 규칙을 모두 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="ba9b3-145">케이스 보류 정책을 만든 후에 케이스 보류 규칙을 만들지 않은 경우 eDiscovery 보류가 만들어지지 않습니다. 또한 어떠한 콘텐츠도 보류되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="ba9b3-146">다음 명령을 실행하여 마이그레이션할 eDiscovery 보류를 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="ba9b3-147">이러한 예제에서는 마이그레이션할 In-Place Hold의 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="ba9b3-148">첫 번째 명령은 새 케이스 보류 정책을 만들고 속성을 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="ba9b3-149">두 번째 명령은 해당 케이스 보류 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![NewCaseHoldPolicy 및 NewCaseHoldRule cmdlet 사용 예](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="ba9b3-151">6단계: eDiscovery 보류 확인</span><span class="sxs-lookup"><span data-stu-id="ba9b3-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="ba9b3-152">보류를 만들 때 문제가 없는지 확인하기 위해 보류 배포 상태가 성공적이지 검사하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="ba9b3-153">배포는 이전 단계에서 *ExchangeLocation* 매개 변수에 지정된 모든 콘텐츠 위치에 보류가 적용되었다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="ba9b3-154">이를 위해 **Get-CaseHoldPolicy** cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="ba9b3-155">이전 단계에서 만든  $policy 변수에 저장된 속성은 변수에서 자동으로 업데이트되지 않습니다. 배포가 성공하는지 확인하려면 cmdlet을 다시 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="ba9b3-156">케이스 보류 정책을 성공적으로 배포하는 데 5분에서 24시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="ba9b3-157">다음 명령을 실행하여 eDiscovery 보류가 성공적으로 배포되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="ba9b3-158">*DistributionStatus* **속성의 Success** 값은 콘텐츠 위치에 보류가 설정되었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="ba9b3-159">배포가 아직 완료되지 않은 경우 **보류** 중 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell Get-CaseHoldPolicy 예제](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="ba9b3-161">7단계: 검색 만들기</span><span class="sxs-lookup"><span data-stu-id="ba9b3-161">Step 7: Create the search</span></span>

<span data-ttu-id="ba9b3-162">마지막 단계는 3단계에서 식별한 검색을 다시 만들어 사례와 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="ba9b3-163">검색을 만든 후 **Start-ComplianceSearch** cmdlet을 사용하여 검색을 실행하거나 나중에 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-ComplianceSearch 예제](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="ba9b3-165">8단계: 규정 준수 센터에서 사례 확인, Microsoft 365 검색</span><span class="sxs-lookup"><span data-stu-id="ba9b3-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="ba9b3-166">모든 것이 올바르게 설정되어 있는지 확인하려면 의 Microsoft 365 준수 센터로 이동하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) **eDiscovery**> 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 준수 센터 eDiscovery](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="ba9b3-168">3단계에서 만든 사례는 **Core eDiscovery 페이지에 나열됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ba9b3-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="ba9b3-169">사례를 열고 4단계에서 만든 보류가 보류 탭에 **나열되어** 있습니다. 보류를 선택하여 보류가 적용되는 사서함 수 및 배포 상태를 포함하여 플라이아웃 페이지에서 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Hold** tab. You can select the hold to see details on the flyout page, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![Microsoft 365 준수 센터의 eDiscovery 보류](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="ba9b3-171">7단계에서 만든 검색은 사례의 **검색** 탭에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-171">The search that you created in Step 7 is listed on the **Searches** tab of the case.</span></span>

![Microsoft 365 준수 센터에서 eDiscovery 사례 검색](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="ba9b3-173">In-Place eDiscovery 검색을 마이그레이션하지만 eDiscovery 사례와 연결하지 않는 경우 이 검색은 Microsoft 365 준수 센터의 콘텐츠 검색 페이지에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="ba9b3-174">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ba9b3-174">More information</span></span>

- <span data-ttu-id="ba9b3-175">In-Place 관리 In-Place eDiscovery & 보류에 대한 자세한 내용은 Exchange 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="ba9b3-176">원본 위치 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ba9b3-176">In-Place eDiscovery</span></span>](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="ba9b3-177">원본 위치 유지 및 소송 보존</span><span class="sxs-lookup"><span data-stu-id="ba9b3-177">In-Place Hold and Litigation Hold</span></span>](/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="ba9b3-178">문서에 사용된 PowerShell cmdlet에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="ba9b3-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ba9b3-179">Get-MailboxSearch</span></span>](/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="ba9b3-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="ba9b3-180">New-ComplianceCase</span></span>](/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="ba9b3-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="ba9b3-181">New-CaseHoldPolicy</span></span>](/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="ba9b3-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="ba9b3-182">New-CaseHoldRule</span></span>](/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="ba9b3-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="ba9b3-183">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="ba9b3-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ba9b3-184">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="ba9b3-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ba9b3-185">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="ba9b3-186">규정 준수 센터에 Microsoft 365 자세한 내용은 Microsoft 365 준수 센터 [개요를 참조하세요.](microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="ba9b3-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>