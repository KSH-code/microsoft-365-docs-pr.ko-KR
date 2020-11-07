---
title: EDiscovery 진단 정보 수집
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 지원 사례에 대 한 eDiscovery 진단 정보를 수집 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944399"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="f0e29-103">EDiscovery 진단 정보 수집</span><span class="sxs-lookup"><span data-stu-id="f0e29-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="f0e29-104">Microsoft 기술 지원 엔지니어가 핵심 eDiscovery 또는 고급 eDiscovery와 관련 된 지원 사례를 열 때 발생 하는 문제에 대 한 특정 정보가 필요한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="f0e29-105">이 문서에서는 엔지니어가 문제를 조사 하 고 해결할 수 있도록 진단 정보를 수집 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="f0e29-106">일반적으로 Microsoft 지원 엔지니어가이 정보를 수집할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0e29-107">이 문서에서 설명 하는 cmdlet 및 진단 정보의 출력에는 조직의 소송 또는 내부 조사에 대 한 중요 한 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="f0e29-108">Microsoft 지원에 원시 진단 정보를 보내기 전에 정보를 검토 하 고 중요 한 정보 (예: 이름 또는 파티에 대 한 기타 정보)를 교체 하 여 소송 또는 조사로 교정 해야 합니다 `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="f0e29-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="f0e29-109">이 방법을 사용 하는 경우 해당 정보가 redacted Microsoft 지원 엔지니어 에게도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="f0e29-110">핵심 eDiscovery에 대 한 진단 정보 수집</span><span class="sxs-lookup"><span data-stu-id="f0e29-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="f0e29-111">핵심 eDiscovery에 대 한 진단 정보 수집은 cmdlet 기반 이므로 보안 & 준수 센터 PowerShell을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="f0e29-112">다음 PowerShell 예제에서는 cmdlet을 실행 한 다음 지정 된 텍스트 파일에 출력을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="f0e29-113">대부분의 지원 사례에서는 다음 명령 중 하나를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="f0e29-114">다음 cmdlet을 실행 하려면 [보안 & 준수 센터 </span> PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="f0e29-115">연결 되 면 다음 명령 중 하나 이상을 실행 하 고 자리 표시자를 실제 개체 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="f0e29-116">생성 된 텍스트 파일을 검토 한 후 중요 한 정보를 redacting Microsoft 고객 지원 엔지니어에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e29-117">이 섹션의 명령을 실행 하 여 Microsoft 365 준수 센터의 **콘텐츠 검색** 페이지에 나열 된 검색 및 내보내기에 대 한 진단 정보를 수집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="f0e29-118">검색에 대 한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="f0e29-118">Collect information about searches</span></span>

<span data-ttu-id="f0e29-119">다음 명령은 중요 eDiscovery 사례와 연결 된 검색 또는 콘텐츠 검색 관련 문제를 조사할 때 유용한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="f0e29-120">검색 작업에 대 한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="f0e29-120">Collect information about search actions</span></span>

<span data-ttu-id="f0e29-121">다음 명령은 중요 eDiscovery 사례와 연결 된 콘텐츠 검색 또는 검색 결과를 미리 보거나 내보내거나 삭제 하 여 문제를 조사 하기 위한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="f0e29-122">**내보내기 탭에** 나열 된 내보내기를 클릭 하 여 검색 작업의 이름을 확인할 수 있습니다. 미리 보기 및 지우기 작업의 이름을 확인 하려면 **new-compliancesearchaction** cmdlet을 실행 하 여 모든 작업 목록을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="f0e29-123">검색 작업 이름의 형식은 `_Preview` `_Export` `_Purge` 해당 검색의 이름에 추가, 또는 이름을 통해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="f0e29-124">EDiscovery 보류에 대 한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="f0e29-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="f0e29-125">핵심 eDiscovery 사례와 연결 된 eDiscovery 보류가 예상 대로 작동 하지 않는 경우 다음 명령을 실행 하 여 eDiscovery 보존에 대 한 케이스 보류 정책 및 관련 케이스 보류 규칙에 대 한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="f0e29-126">다음 명령에 포함 된 *서비스 케이스 보류 정책 이름은* eDiscovery 보류의 이름과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="f0e29-127">이 이름은 핵심 eDiscovery 사례의 **보류** 탭에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="f0e29-128">모든 사례 정보 수집</span><span class="sxs-lookup"><span data-stu-id="f0e29-128">Collect all case information</span></span>

<span data-ttu-id="f0e29-129">Microsoft 지원 서비스에서 문제를 조사 하는 데 필요한 정보가 명확 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="f0e29-130">이러한 상황에서는 핵심적인 eDiscovery 사례에 대 한 모든 진단 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="f0e29-131">다음 명령의 *핵심 ediscovery 사례 이름은* Microsoft 365 준수 센터의 **핵심 ediscovery** 페이지에 표시 되는 사례 이름과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="f0e29-132">고급 eDiscovery에 대 한 진단 정보 수집</span><span class="sxs-lookup"><span data-stu-id="f0e29-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="f0e29-133">고급 eDiscovery 사례의 **설정** 탭에서는 사례에 대 한 진단 정보를 빠르게 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="f0e29-134">진단 정보는 클립보드에 저장 되므로 텍스트 파일에 붙여 넣고 Microsoft 지원으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="f0e29-135">로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 다음 **모두 표시 > EDiscovery > 고급** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="f0e29-136">사례를 선택 하 고 **설정** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="f0e29-137">**사례 정보** 에서 **선택을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-137">Under **Case Information** , click **Select**.</span></span>

4. <span data-ttu-id="f0e29-138">플라이 아웃 페이지에서 **진단 정보 복사** 를 클릭 하 여 정보를 클립보드로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="f0e29-139">메모장에서 텍스트 파일을 열고 텍스트 파일에 정보를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="f0e29-140">텍스트 파일을 저장 하 고 이름을 해당 이름 `AeD Diagnostic Info YYYY.MM.DD` (예:)으로 변경 `AeD Diagnostic Info 2020.11.03` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="f0e29-141">파일을 검토 한 후 중요 한 정보를 redacting Microsoft 고객 지원 엔지니어가 해당 사례를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e29-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
