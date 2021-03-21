---
title: eDiscovery 진단 정보 수집
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
description: Microsoft 지원 사례에 대한 eDiscovery 진단 정보를 수집하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926558"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="64115-103">eDiscovery 진단 정보 수집</span><span class="sxs-lookup"><span data-stu-id="64115-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="64115-104">경우에 따라 Microsoft 지원 엔지니어가 Core eDiscovery 또는 Advanced eDiscovery와 관련된 지원 사례를 열 때 해당 문제와 관련된 특정 정보를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="64115-105">이 문서에서는 지원 엔지니어가 문제를 조사하고 해결하는 데 도움이 되는 진단 정보를 수집하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="64115-106">일반적으로 Microsoft 기술 지원 엔지니어가 요청하기 전까지는 이 정보를 수집할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64115-107">이 문서에 설명된 cmdlet 및 진단 정보의 출력에는 조직의 소송 또는 내부 조사에 대한 중요한 정보가 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="64115-108">Microsoft 지원에 원시 진단 정보를 보내기 전에 정보를 검토하고 으로 바꾸어 중요한 정보(예: 소송 또는 조사 당사자에 대한 이름 또는 기타 정보)를 변경해야 `XXXXXXX` 합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="64115-109">또한 이 방법을 사용하면 Microsoft 기술 지원 엔지니어에게 정보가 다시 시정된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="64115-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="64115-110">Core eDiscovery에 대한 진단 정보 수집</span><span class="sxs-lookup"><span data-stu-id="64115-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="64115-111">Core eDiscovery에 대한 진단 정보를 수집하는 것은 cmdlet 기반이기 때문에 보안 및 준수 센터 powerShell을 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="64115-112">다음 PowerShell 예제에서는 cmdlet을 실행한 다음 출력을 지정된 텍스트 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="64115-113">대부분의 지원 사례에서는 이러한 명령 중 하나만 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64115-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="64115-114">다음 cmdlet을 실행하기 위해 보안 및 준수 [& PowerShell에 연결합니다. </span> ](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="64115-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="64115-115">연결한 후 다음 명령 중 하나 이상을 실행하고 자리 holders를 실제 개체 이름으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="64115-116">생성된 텍스트 파일을 검토하고 중요한 정보를 편집한 후 사례를 작업하는 Microsoft 기술 지원 엔지니어에게 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="64115-117">이 섹션의 명령을 실행하여 Microsoft 365 규정 준수 센터의  콘텐츠 검색 페이지에 나열된 검색 및 내보내기에 대한 진단 정보를 수집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="64115-118">검색에 대한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="64115-118">Collect information about searches</span></span>

<span data-ttu-id="64115-119">다음 명령은 콘텐츠 검색 또는 Core eDiscovery 사례와 연결된 검색과 관련된 문제를 조사할 때 유용한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="64115-120">검색 작업에 대한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="64115-120">Collect information about search actions</span></span>

<span data-ttu-id="64115-121">다음 명령은 핵심 eDiscovery 사례와 연결된 콘텐츠 검색 또는 검색의 결과 미리 보기, 내보내기 또는 제거와 관련된 문제를 조사하기 위해 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="64115-122">내보내기 탭에 나열된 내보내기를 클릭하여 검색 작업의 이름을 식별할 **수** 있습니다. 미리 보기 및 제거 작업의 이름을 식별하기 위해 **Get-ComplianceSearchAction** cmdlet을 실행하여 모든 작업의 목록을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="64115-123">검색 작업 이름의 형식은 를 추가하거나 해당 검색의 `_Preview` `_Export` 이름으로 `_Purge` 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="64115-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="64115-124">eDiscovery 보류에 대한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="64115-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="64115-125">Core eDiscovery 사례와 연결된 eDiscovery 보류가 예상대로 작동하지 않는 경우 다음 명령을 실행하여 eDiscovery 보류에 대한 케이스 보류 정책 및 관련 케이스 보류 규칙에 대한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="64115-126">다음 *명령의* 케이스 보류 정책 이름은 eDiscovery 보류의 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="64115-127">Core eDiscovery  사례의 보류 탭에서 이 이름을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="64115-128">모든 사례 정보 수집</span><span class="sxs-lookup"><span data-stu-id="64115-128">Collect all case information</span></span>

<span data-ttu-id="64115-129">경우에 따라 Microsoft 지원에서 문제를 조사하는 데 필요한 정보가 분명하지 않은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="64115-130">이 경우 Core eDiscovery 사례에 대한 모든 진단 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="64115-131">다음 *명령의 Core eDiscovery* 사례 이름은 Microsoft 365 규정 준수 센터의 **Core eDiscovery** 페이지에 표시되는 사례의 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="64115-132">Advanced eDiscovery에 대한 진단 정보 수집</span><span class="sxs-lookup"><span data-stu-id="64115-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="64115-133">Advanced  eDiscovery 사례의 설정 탭을 사용하면 사례에 대한 진단 정보를 빠르게 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="64115-134">진단 정보는 클립보드에 저장되어 텍스트 파일에 붙여넣고 Microsoft 지원에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="64115-135">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **모든 eDiscovery**> 표시를 > 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="64115-136">사례를 선택한 다음 설정 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="64115-137">사례 **정보에서** 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="64115-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="64115-138">플라이아웃 페이지에서 진단  정보 복사를 클릭하여 정보를 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="64115-139">메모장에서 텍스트 파일을 열고 텍스트 파일에 정보를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="64115-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="64115-140">텍스트 파일을 저장하고 다음과 같은 이름을 `AeD Diagnostic Info YYYY.MM.DD` 지정합니다(예: `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="64115-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="64115-141">파일을 검토하고 중요한 정보를 시정한 후 사례를 작업하는 Microsoft 기술 지원 엔지니어에게 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="64115-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>