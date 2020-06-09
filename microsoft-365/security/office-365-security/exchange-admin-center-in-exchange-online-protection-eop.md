---
title: 독립 실행형 EOP의 Exchange 관리 센터
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: EOP (독립 실행형 Exchange Online Protection)의 웹 관리 인터페이스에 대해 알아봅니다.
ms.openlocfilehash: 777597489e54c642220cb42f0c686b675101897f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617001"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="e083a-103">독립 실행형 EOP의 Exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="e083a-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="e083a-104">EAC (Exchange 관리 센터)는 독립 실행형 EOP (Exchange Online Protection)에 대 한 웹 기반 관리 콘솔입니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="e083a-105">이 항목의 Exchange Online 버전을 찾으시나요?</span><span class="sxs-lookup"><span data-stu-id="e083a-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="e083a-106">Exchange [Online의 exchange 관리 센터를](https://docs.microsoft.com/exchange/exchange-admin-center)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e083a-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="e083a-107">EOP에서 EAC 열기</span><span class="sxs-lookup"><span data-stu-id="e083a-107">Open the EAC in EOP</span></span>

<span data-ttu-id="e083a-108">독립 실행형 EOP 고객은 다음 방법을 사용 하 여 EAC에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="e083a-109">**Microsoft 365 관리 센터에서 다음을 수행 합니다**.</span><span class="sxs-lookup"><span data-stu-id="e083a-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="e083a-110">으로 이동 하 여 <https://admin.microsoft.com> **모두 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Microsoft 365 관리 센터에서 모두 표시를 클릭 합니다.](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="e083a-112">**관리 센터** 섹션에서 **모든 관리 센터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Microsoft 365 관리 센터에서 모든 관리 센터를 클릭 합니다.](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="e083a-114">**모든 관리 센터** 페이지에서 **Exchange Online Protection**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="e083a-115">로 직접 이동 `https://admin.protection.outlook.com/ecp/` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="e083a-116">EOP의 EAC에 있는 일반적인 사용자 인터페이스 요소</span><span class="sxs-lookup"><span data-stu-id="e083a-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="e083a-117">이 섹션에서는 EMC에 있는 사용자 인터페이스 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="e083a-119">기능 창</span><span class="sxs-lookup"><span data-stu-id="e083a-119">Feature Pane</span></span>

<span data-ttu-id="e083a-p102">이 창은 EAC에서 수행할 대부분의 작업에 대한 첫 번째 탐색 수준으로, 기능 영역별로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="e083a-122">**받는 사람**:이 기능을 통해 그룹 및 외부 연락처를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="e083a-123">**사용 권한**: 관리자 역할을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="e083a-124">**준수 관리**:이 기능을 통해 관리자 역할 그룹 보고서 및 관리자 감사 로그 보고서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="e083a-125">**보호**:이 기능을 통해 맬웨어 방지 정책, 기본 연결 필터 정책 및 dkim을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e083a-126">맬웨어 방지 정책 및 보안 & 준수 센터의 기본 연결 필터 정책을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="e083a-127">자세한 내용은 [EOP에서 맬웨어 방지 정책 구성](configure-anti-malware-policies.md) 및 [EOP에서 연결 필터링 구성을](configure-the-connection-filter-policy.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e083a-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="e083a-128">**메일 흐름**:이 기능을 통해 메일 흐름 규칙 (전송 규칙이 라고도 함), 허용 도메인 및 커넥터를 관리할 수 있을 뿐 아니라 메시지 추적을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="e083a-129">**하이브리드**:이 기능을 통해 [하이브리드 구성 마법사](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)를 실행할 수 있으며 [Exchange Online PowerShell 모듈](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="e083a-130">탭</span><span class="sxs-lookup"><span data-stu-id="e083a-130">Tabs</span></span>

<span data-ttu-id="e083a-p104">탭은 두 번째 탐색 수준입니다. 각 기능 영역에는 각각의 기능을 나타내는 다양한 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="e083a-133">도구 모음</span><span class="sxs-lookup"><span data-stu-id="e083a-133">Toolbar</span></span>

<span data-ttu-id="e083a-p105">대부분의 탭은 클릭하면 도구 모음이 표시됩니다. 도구 모음에는 특정 작업을 수행하는 아이콘이 있습니다. 다음 표에서는 아이콘과 그 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

||||
|---|---|---|
|<span data-ttu-id="e083a-137">**아이콘**</span><span class="sxs-lookup"><span data-stu-id="e083a-137">**Icon**</span></span>|<span data-ttu-id="e083a-138">**이름**</span><span class="sxs-lookup"><span data-stu-id="e083a-138">**Name**</span></span>|<span data-ttu-id="e083a-139">**작업**</span><span class="sxs-lookup"><span data-stu-id="e083a-139">**Action**</span></span>|
|![아이콘 추가](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="e083a-141">추가, 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="e083a-141">Add, New</span></span>|<span data-ttu-id="e083a-p106">이 아이콘을 사용하면 새 개체를 만들 수 있습니다. 일부 아이콘에는 아래쪽 화살표가 있으며 이 화살표를 클릭하면 만들 수 있는 추가 개체가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![편집 아이콘](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="e083a-145">편집</span><span class="sxs-lookup"><span data-stu-id="e083a-145">Edit</span></span>|<span data-ttu-id="e083a-146">이 아이콘을 사용하면 개체를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-146">Use this icon to edit an object.</span></span>|
|![삭제 아이콘](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="e083a-148">삭제</span><span class="sxs-lookup"><span data-stu-id="e083a-148">Delete</span></span>|<span data-ttu-id="e083a-p107">이 아이콘을 사용하면 개체를 삭제할 수 있습니다. 일부 삭제 아이콘에는 아래쪽 화살표가 있으며 이 화살표를 클릭하면 추가 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![검색 아이콘](../../media/ITPro-EAC-.gif)|<span data-ttu-id="e083a-152">검색</span><span class="sxs-lookup"><span data-stu-id="e083a-152">Search</span></span>|<span data-ttu-id="e083a-153">이 아이콘을 사용하면 찾으려는 개체에 대한 검색어를 입력할 수 있는 검색 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![새로 고침 아이콘](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="e083a-155">새로 고침</span><span class="sxs-lookup"><span data-stu-id="e083a-155">Refresh</span></span>|<span data-ttu-id="e083a-156">이 아이콘을 사용하면 목록 보기를 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-156">Use this icon to refresh the list view.</span></span>|
|![기타 옵션 아이콘](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="e083a-158">기타 옵션</span><span class="sxs-lookup"><span data-stu-id="e083a-158">More options</span></span>|<span data-ttu-id="e083a-p108">이 아이콘을 사용하면 해당 탭의 개체에 대해 수행할 수 있는 기타 작업을 볼 수 있습니다. 예를 들어 **받는 사람 \> 사용자**에서 이 아이콘을 클릭하면 **고급 검색**을 수행할 수 있는 옵션이 표시됩니다.  </span><span class="sxs-lookup"><span data-stu-id="e083a-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.gif)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="e083a-163">위쪽 화살표와 아래쪽 화살표</span><span class="sxs-lookup"><span data-stu-id="e083a-163">Up arrow and down arrow</span></span>|<span data-ttu-id="e083a-164">이 아이콘을 사용하면 개체 우선 순위를 위나 아래로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-164">Use these icons to move an object's priority up or down.</span></span>|
|![아이콘 제거](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="e083a-166">제거</span><span class="sxs-lookup"><span data-stu-id="e083a-166">Remove</span></span>|<span data-ttu-id="e083a-167">이 아이콘을 사용하면 목록에서 개체를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="e083a-168">목록 보기</span><span class="sxs-lookup"><span data-stu-id="e083a-168">List View</span></span>

<span data-ttu-id="e083a-p109">탭을 선택하면 대부분의 경우 목록 보기가 표시됩니다. EAC 목록 보기 내에서 약 10,000개의 개체를 볼 수 있습니다. 또한 결과로 페이징할 수 있도록 페이징이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="e083a-172">세부 정보 창</span><span class="sxs-lookup"><span data-stu-id="e083a-172">Details Pane</span></span>

<span data-ttu-id="e083a-p110">목록 보기에서 개체를 선택하면 해당 개체에 대한 정보가 세부 정보 창에 표시됩니다. 세부 정보 창에 관리 작업이 포함된 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="e083a-175">내 소식 타일 및 도움말</span><span class="sxs-lookup"><span data-stu-id="e083a-175">Me tile and Help</span></span>

<span data-ttu-id="e083a-p111">**내 소식** 타일을 통해 EAC에서 로그아웃하고 다른 사용자로 로그인할 수 있습니다. **도움말**![도움말 아이콘](../../media/ITPro-EAC-HelpIcon.gif) 드롭다운 메뉴에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-p111">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="e083a-178">**도움말**: ![ ](../../media/ITPro-EAC-HelpIcon.gif) 온라인 도움말 콘텐츠를 보려면 도움말 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="e083a-179">**사용자 의견**: 사용자 의견을 남겨 두세요.</span><span class="sxs-lookup"><span data-stu-id="e083a-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="e083a-180">**커뮤니티**: 커뮤니티 포럼에서 답변을 찾기 위한 질문을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="e083a-181">**사용 안 함 버블**: 도움말 버블에는 개체를 만들거나 편집할 때 필드에 대 한 상황에 맞는 도움말이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="e083a-182">풍선형 도움말을 끌 수 있으며, 풍선형 도움말을 사용하지 않도록 설정한 경우에는 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="e083a-183">**명령 로깅 표시**: EAC에서 구성한 사항에 따라 해당 PowerShell 명령을 표시 하는 새 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="e083a-184">지원되는 브라우저</span><span class="sxs-lookup"><span data-stu-id="e083a-184">Supported Browsers</span></span>

<span data-ttu-id="e083a-185">최상의 EAC 사용 환경을 위해 항상 최신 브라우저, Office 클라이언트 및 앱을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="e083a-186">또한 소프트웨어 업데이트가 제공되면 이를 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="e083a-187">서비스의 지원 되는 브라우저 및 시스템 요구 사항에 대 한 자세한 내용은 [Office의 시스템 요구 사항을](https://products.office.com/office-system-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e083a-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="e083a-188">지원되는 언어</span><span class="sxs-lookup"><span data-stu-id="e083a-188">Supported languages</span></span>

<span data-ttu-id="e083a-189">다음은 독립 실행형 EOP에서 EAC에 대해 지원 되 고 사용할 수 있는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="e083a-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="e083a-190">암하라어</span><span class="sxs-lookup"><span data-stu-id="e083a-190">Amharic</span></span>

- <span data-ttu-id="e083a-191">아랍어</span><span class="sxs-lookup"><span data-stu-id="e083a-191">Arabic</span></span>

- <span data-ttu-id="e083a-192">바스크어(바스크)</span><span class="sxs-lookup"><span data-stu-id="e083a-192">Basque (Basque)</span></span>

- <span data-ttu-id="e083a-193">뱅골어(인도)</span><span class="sxs-lookup"><span data-stu-id="e083a-193">Bengali (India)</span></span>

- <span data-ttu-id="e083a-194">불가리아어</span><span class="sxs-lookup"><span data-stu-id="e083a-194">Bulgarian</span></span>

- <span data-ttu-id="e083a-195">카탈로니아어</span><span class="sxs-lookup"><span data-stu-id="e083a-195">Catalan</span></span>

- <span data-ttu-id="e083a-196">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="e083a-196">Chinese (Simplified)</span></span>

- <span data-ttu-id="e083a-197">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="e083a-197">Chinese (Traditional)</span></span>

- <span data-ttu-id="e083a-198">크로아티아어</span><span class="sxs-lookup"><span data-stu-id="e083a-198">Croatian</span></span>

- <span data-ttu-id="e083a-199">체코어</span><span class="sxs-lookup"><span data-stu-id="e083a-199">Czech</span></span>

- <span data-ttu-id="e083a-200">덴마크어</span><span class="sxs-lookup"><span data-stu-id="e083a-200">Danish</span></span>

- <span data-ttu-id="e083a-201">네덜란드어</span><span class="sxs-lookup"><span data-stu-id="e083a-201">Dutch</span></span>

- <span data-ttu-id="e083a-202">네덜란드어</span><span class="sxs-lookup"><span data-stu-id="e083a-202">Dutch</span></span>

- <span data-ttu-id="e083a-203">영어</span><span class="sxs-lookup"><span data-stu-id="e083a-203">English</span></span>

- <span data-ttu-id="e083a-204">에스토니아어</span><span class="sxs-lookup"><span data-stu-id="e083a-204">Estonian</span></span>

- <span data-ttu-id="e083a-205">필리핀어(필리핀)</span><span class="sxs-lookup"><span data-stu-id="e083a-205">Filipino (Philippines)</span></span>

- <span data-ttu-id="e083a-206">핀란드어</span><span class="sxs-lookup"><span data-stu-id="e083a-206">Finnish</span></span>

- <span data-ttu-id="e083a-207">프랑스어</span><span class="sxs-lookup"><span data-stu-id="e083a-207">French</span></span>

- <span data-ttu-id="e083a-208">갈리시아어</span><span class="sxs-lookup"><span data-stu-id="e083a-208">Galician</span></span>

- <span data-ttu-id="e083a-209">독일어</span><span class="sxs-lookup"><span data-stu-id="e083a-209">German</span></span>

- <span data-ttu-id="e083a-210">그리스어</span><span class="sxs-lookup"><span data-stu-id="e083a-210">Greek</span></span>

- <span data-ttu-id="e083a-211">구자라트어</span><span class="sxs-lookup"><span data-stu-id="e083a-211">Gujarati</span></span>

- <span data-ttu-id="e083a-212">히브리어</span><span class="sxs-lookup"><span data-stu-id="e083a-212">Hebrew</span></span>

- <span data-ttu-id="e083a-213">힌디어</span><span class="sxs-lookup"><span data-stu-id="e083a-213">Hindi</span></span>

- <span data-ttu-id="e083a-214">헝가리어</span><span class="sxs-lookup"><span data-stu-id="e083a-214">Hungarian</span></span>

- <span data-ttu-id="e083a-215">아이슬란드어</span><span class="sxs-lookup"><span data-stu-id="e083a-215">Icelandic</span></span>

- <span data-ttu-id="e083a-216">인도네시아어</span><span class="sxs-lookup"><span data-stu-id="e083a-216">Indonesian</span></span>

- <span data-ttu-id="e083a-217">이탈리아어</span><span class="sxs-lookup"><span data-stu-id="e083a-217">Italian</span></span>

- <span data-ttu-id="e083a-218">일본어</span><span class="sxs-lookup"><span data-stu-id="e083a-218">Japanese</span></span>

- <span data-ttu-id="e083a-219">칸나다어</span><span class="sxs-lookup"><span data-stu-id="e083a-219">Kannada</span></span>

- <span data-ttu-id="e083a-220">카자흐어</span><span class="sxs-lookup"><span data-stu-id="e083a-220">Kazakh</span></span>

- <span data-ttu-id="e083a-221">스와힐리어</span><span class="sxs-lookup"><span data-stu-id="e083a-221">Kiswahili</span></span>

- <span data-ttu-id="e083a-222">한국어</span><span class="sxs-lookup"><span data-stu-id="e083a-222">Korean</span></span>

- <span data-ttu-id="e083a-223">라트비아어</span><span class="sxs-lookup"><span data-stu-id="e083a-223">Latvian</span></span>

- <span data-ttu-id="e083a-224">리투아니아어</span><span class="sxs-lookup"><span data-stu-id="e083a-224">Lithuanian</span></span>

- <span data-ttu-id="e083a-225">말레이어(브루나이)</span><span class="sxs-lookup"><span data-stu-id="e083a-225">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="e083a-226">말레이어(말레이시아)</span><span class="sxs-lookup"><span data-stu-id="e083a-226">Malay (Malaysia)</span></span>

- <span data-ttu-id="e083a-227">말라얄람어</span><span class="sxs-lookup"><span data-stu-id="e083a-227">Malayalam</span></span>

- <span data-ttu-id="e083a-228">마라티어</span><span class="sxs-lookup"><span data-stu-id="e083a-228">Marathi</span></span>

- <span data-ttu-id="e083a-229">노르웨이어(복말)</span><span class="sxs-lookup"><span data-stu-id="e083a-229">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="e083a-230">노르웨이어(니노르스크)</span><span class="sxs-lookup"><span data-stu-id="e083a-230">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="e083a-231">오리야어</span><span class="sxs-lookup"><span data-stu-id="e083a-231">Oriya</span></span>

- <span data-ttu-id="e083a-232">페르시아어</span><span class="sxs-lookup"><span data-stu-id="e083a-232">Persian</span></span>

- <span data-ttu-id="e083a-233">폴란드어</span><span class="sxs-lookup"><span data-stu-id="e083a-233">Polish</span></span>

- <span data-ttu-id="e083a-234">포르투갈어(브라질)</span><span class="sxs-lookup"><span data-stu-id="e083a-234">Portuguese (Brazil)</span></span>

- <span data-ttu-id="e083a-235">포르투갈어(포르투갈)</span><span class="sxs-lookup"><span data-stu-id="e083a-235">Portuguese (Portugal)</span></span>

- <span data-ttu-id="e083a-236">루마니아어</span><span class="sxs-lookup"><span data-stu-id="e083a-236">Romanian</span></span>

- <span data-ttu-id="e083a-237">러시아어</span><span class="sxs-lookup"><span data-stu-id="e083a-237">Russian</span></span>

- <span data-ttu-id="e083a-238">세르비아어(키릴 자모, 세르비아)</span><span class="sxs-lookup"><span data-stu-id="e083a-238">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="e083a-239">세르비아어(라틴 문자)</span><span class="sxs-lookup"><span data-stu-id="e083a-239">Serbian (Latin)</span></span>

- <span data-ttu-id="e083a-240">슬로바키아어</span><span class="sxs-lookup"><span data-stu-id="e083a-240">Slovak</span></span>

- <span data-ttu-id="e083a-241">슬로베니아어</span><span class="sxs-lookup"><span data-stu-id="e083a-241">Slovenian</span></span>

- <span data-ttu-id="e083a-242">스페인어</span><span class="sxs-lookup"><span data-stu-id="e083a-242">Spanish</span></span>

- <span data-ttu-id="e083a-243">스웨덴어</span><span class="sxs-lookup"><span data-stu-id="e083a-243">Swedish</span></span>

- <span data-ttu-id="e083a-244">타밀어</span><span class="sxs-lookup"><span data-stu-id="e083a-244">Tamil</span></span>

- <span data-ttu-id="e083a-245">텔루구어</span><span class="sxs-lookup"><span data-stu-id="e083a-245">Telugu</span></span>

- <span data-ttu-id="e083a-246">태국어</span><span class="sxs-lookup"><span data-stu-id="e083a-246">Thai</span></span>

- <span data-ttu-id="e083a-247">터키어</span><span class="sxs-lookup"><span data-stu-id="e083a-247">Turkish</span></span>

- <span data-ttu-id="e083a-248">우크라이나어</span><span class="sxs-lookup"><span data-stu-id="e083a-248">Ukrainian</span></span>

- <span data-ttu-id="e083a-249">우르두어</span><span class="sxs-lookup"><span data-stu-id="e083a-249">Urdu</span></span>

- <span data-ttu-id="e083a-250">베트남어</span><span class="sxs-lookup"><span data-stu-id="e083a-250">Vietnamese</span></span>

- <span data-ttu-id="e083a-251">웨일스어</span><span class="sxs-lookup"><span data-stu-id="e083a-251">Welsh</span></span>
