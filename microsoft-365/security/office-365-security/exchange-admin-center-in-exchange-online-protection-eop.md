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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: 독립 실행형 EOP(Exchange Online Protection)의 웹 관리 인터페이스에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206786"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="3b818-103">독립 실행형 EOP의 Exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="3b818-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3b818-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="3b818-104">**Applies to**</span></span>
-  [<span data-ttu-id="3b818-105">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="3b818-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="3b818-106">EAC(Exchange 관리 센터)는 독립 실행형 EOP(Exchange Online Protection)를 위한 웹 기반 관리 콘솔입니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="3b818-107">이 항목의 Exchange Online 버전을 찾으시나요?</span><span class="sxs-lookup"><span data-stu-id="3b818-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="3b818-108">[Exchange Online의 Exchange 관리 센터를 참조하세요.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="3b818-108">See [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="3b818-109">EOP에서 EAC 열기</span><span class="sxs-lookup"><span data-stu-id="3b818-109">Open the EAC in EOP</span></span>

<span data-ttu-id="3b818-110">독립 실행형 EOP 고객은 다음 방법을 사용하여 EAC에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="3b818-111">**Microsoft 365 관리 센터에서:**</span><span class="sxs-lookup"><span data-stu-id="3b818-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="3b818-112">으로 <https://admin.microsoft.com> 이동하여 모두 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3b818-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Microsoft 365 관리 센터에서 모두 표시를 클릭합니다.](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="3b818-114">나타나는 **관리 센터** 섹션에서 모든 관리 **센터 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3b818-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Microsoft 365 관리 센터의 모든 관리 센터를 클릭합니다.](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="3b818-116">나타나는 **모든 관리 센터** 페이지에서 Exchange **Online Protection 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3b818-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="3b818-117">으로 `https://admin.protection.outlook.com/ecp/` 바로 이동</span><span class="sxs-lookup"><span data-stu-id="3b818-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="3b818-118">EOP의 EAC에 있는 일반적인 사용자 인터페이스 요소</span><span class="sxs-lookup"><span data-stu-id="3b818-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="3b818-119">이 섹션에서는 EMC에 있는 사용자 인터페이스 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Exchange Online Protection의 Exchange 관리 센터](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="3b818-121">기능 창</span><span class="sxs-lookup"><span data-stu-id="3b818-121">Feature Pane</span></span>

<span data-ttu-id="3b818-p102">이 창은 EAC에서 수행할 대부분의 작업에 대한 첫 번째 탐색 수준으로, 기능 영역별로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="3b818-124">**받는 사람:** 그룹 및 외부 연락처를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="3b818-125">**사용 권한:** 관리자 역할을 관리할 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="3b818-126">**준수 관리:** 관리자 역할 그룹 보고서와 관리자 감사 로그 보고서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="3b818-127">**보호:** 맬웨어 방지 정책, 기본 연결 필터 정책 및 DKIM을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3b818-128">맬웨어 방지 정책 및 기본 연결 필터 정책은 보안 및 준수 센터에서 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="3b818-129">자세한 내용은 [EOP에서](configure-anti-malware-policies.md) 맬웨어 방지 정책 구성 및 EOP에서 연결 필터링 [구성을 참조하세요.](configure-the-connection-filter-policy.md)</span><span class="sxs-lookup"><span data-stu-id="3b818-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="3b818-130">**메일 흐름:** 메일 흐름 규칙(전송 규칙), 허용 도메인 및 커넥터를 관리하고 메시지 추적을 실행할 수 있는 위치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="3b818-131">**하이브리드:** 하이브리드 구성 마법사를 [](/Exchange/hybrid-configuration-wizard)실행할 수 있으며 Exchange Online PowerShell 모듈을 [설치할 수 있는 위치입니다.](/powershell/exchange/mfa-connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3b818-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="3b818-132">탭</span><span class="sxs-lookup"><span data-stu-id="3b818-132">Tabs</span></span>

<span data-ttu-id="3b818-p104">탭은 두 번째 탐색 수준입니다. 각 기능 영역에는 각각의 기능을 나타내는 다양한 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="3b818-135">도구 모음</span><span class="sxs-lookup"><span data-stu-id="3b818-135">Toolbar</span></span>

<span data-ttu-id="3b818-p105">대부분의 탭은 클릭하면 도구 모음이 표시됩니다. 도구 모음에는 특정 작업을 수행하는 아이콘이 있습니다. 다음 표에서는 아이콘과 그 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="3b818-139">아이콘</span><span class="sxs-lookup"><span data-stu-id="3b818-139">Icon</span></span>|<span data-ttu-id="3b818-140">이름</span><span class="sxs-lookup"><span data-stu-id="3b818-140">Name</span></span>|<span data-ttu-id="3b818-141">작업</span><span class="sxs-lookup"><span data-stu-id="3b818-141">Action</span></span>|
|---|---|---|
|![아이콘 추가](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="3b818-143">추가, 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="3b818-143">Add, New</span></span>|<span data-ttu-id="3b818-p106">이 아이콘을 사용하면 새 개체를 만들 수 있습니다. 일부 아이콘에는 아래쪽 화살표가 있으며 이 화살표를 클릭하면 만들 수 있는 추가 개체가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![편집 아이콘](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="3b818-147">편집</span><span class="sxs-lookup"><span data-stu-id="3b818-147">Edit</span></span>|<span data-ttu-id="3b818-148">이 아이콘을 사용하면 개체를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-148">Use this icon to edit an object.</span></span>|
|![삭제 아이콘](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="3b818-150">삭제</span><span class="sxs-lookup"><span data-stu-id="3b818-150">Delete</span></span>|<span data-ttu-id="3b818-p107">이 아이콘을 사용하면 개체를 삭제할 수 있습니다. 일부 삭제 아이콘에는 아래쪽 화살표가 있으며 이 화살표를 클릭하면 추가 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![검색 아이콘](../../media/ITPro-EAC-.gif)|<span data-ttu-id="3b818-154">검색</span><span class="sxs-lookup"><span data-stu-id="3b818-154">Search</span></span>|<span data-ttu-id="3b818-155">이 아이콘을 사용하면 찾으려는 개체에 대한 검색어를 입력할 수 있는 검색 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![새로 고침 아이콘](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="3b818-157">새로 고침</span><span class="sxs-lookup"><span data-stu-id="3b818-157">Refresh</span></span>|<span data-ttu-id="3b818-158">이 아이콘을 사용하면 목록 보기를 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-158">Use this icon to refresh the list view.</span></span>|
|![기타 옵션 아이콘](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="3b818-160">기타 옵션</span><span class="sxs-lookup"><span data-stu-id="3b818-160">More options</span></span>|<span data-ttu-id="3b818-p108">이 아이콘을 사용하면 해당 탭의 개체에 대해 수행할 수 있는 기타 작업을 볼 수 있습니다. 예를 들어 **받는 사람 \> 사용자** 에서 이 아이콘을 클릭하면 **고급 검색** 을 수행할 수 있는 옵션이 표시됩니다.  </span><span class="sxs-lookup"><span data-stu-id="3b818-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.gif)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="3b818-165">위쪽 화살표와 아래쪽 화살표</span><span class="sxs-lookup"><span data-stu-id="3b818-165">Up arrow and down arrow</span></span>|<span data-ttu-id="3b818-166">이 아이콘을 사용하면 개체 우선 순위를 위나 아래로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-166">Use these icons to move an object's priority up or down.</span></span>|
|![아이콘 제거](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="3b818-168">제거</span><span class="sxs-lookup"><span data-stu-id="3b818-168">Remove</span></span>|<span data-ttu-id="3b818-169">이 아이콘을 사용하면 목록에서 개체를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="3b818-170">목록 보기</span><span class="sxs-lookup"><span data-stu-id="3b818-170">List View</span></span>

<span data-ttu-id="3b818-p109">탭을 선택하면 대부분의 경우 목록 보기가 표시됩니다. EAC 목록 보기 내에서 약 10,000개의 개체를 볼 수 있습니다. 또한 결과로 페이징할 수 있도록 페이징이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="3b818-174">세부 정보 창</span><span class="sxs-lookup"><span data-stu-id="3b818-174">Details Pane</span></span>

<span data-ttu-id="3b818-p110">목록 보기에서 개체를 선택하면 해당 개체에 대한 정보가 세부 정보 창에 표시됩니다. 세부 정보 창에 관리 작업이 포함된 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="3b818-177">내 소식 타일 및 도움말</span><span class="sxs-lookup"><span data-stu-id="3b818-177">Me tile and Help</span></span>

<span data-ttu-id="3b818-178">**내 소식** 타일을 통해 EAC에서 로그아웃하고 다른 사용자로 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="3b818-179">도움말 **아이콘** ![ ](../../media/ITPro-EAC-HelpIcon.gif) 드롭다운 메뉴에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="3b818-180">**도움말:** 도움말 ![ 아이콘을 ](../../media/ITPro-EAC-HelpIcon.gif) 클릭하여 온라인 도움말 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="3b818-181">**피드백:** 피드백을 남기기.</span><span class="sxs-lookup"><span data-stu-id="3b818-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="3b818-182">**커뮤니티:** 커뮤니티 포럼에서 답변 찾기에 대한 질문을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="3b818-183">**풍선형 도움말 사용** 안 하게 설정 : 풍선형 도움말에는 개체를 만들거나 편집할 때 필드에 대한 상황에 맞는 도움말이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="3b818-184">풍선형 도움말을 끌 수 있으며, 풍선형 도움말을 사용하지 않도록 설정한 경우에는 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="3b818-185">**명령 로깅 표시:** EAC에서 구성한 명령에 따라 해당하는 PowerShell 명령을 표시하는 새 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="3b818-186">지원되는 브라우저</span><span class="sxs-lookup"><span data-stu-id="3b818-186">Supported Browsers</span></span>

<span data-ttu-id="3b818-187">최상의 EAC 사용 환경을 위해 항상 최신 브라우저, Office 클라이언트 및 앱을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="3b818-188">또한 소프트웨어 업데이트가 제공되면 이를 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="3b818-189">서비스의 지원되는 브라우저 및 시스템 요구 사항에 대한 자세한 내용은 Office의 시스템 요구 [사항을 참조하세요.](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="3b818-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="3b818-190">지원되는 언어</span><span class="sxs-lookup"><span data-stu-id="3b818-190">Supported languages</span></span>

<span data-ttu-id="3b818-191">독립 실행형 EOP에서 EAC에 대해 지원 및 사용할 수 있는 언어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b818-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="3b818-192">암하라어</span><span class="sxs-lookup"><span data-stu-id="3b818-192">Amharic</span></span>
- <span data-ttu-id="3b818-193">아랍어</span><span class="sxs-lookup"><span data-stu-id="3b818-193">Arabic</span></span>
- <span data-ttu-id="3b818-194">바스크어(바스크)</span><span class="sxs-lookup"><span data-stu-id="3b818-194">Basque (Basque)</span></span>
- <span data-ttu-id="3b818-195">뱅골어(인도)</span><span class="sxs-lookup"><span data-stu-id="3b818-195">Bengali (India)</span></span>
- <span data-ttu-id="3b818-196">불가리아어</span><span class="sxs-lookup"><span data-stu-id="3b818-196">Bulgarian</span></span>
- <span data-ttu-id="3b818-197">카탈로니아어</span><span class="sxs-lookup"><span data-stu-id="3b818-197">Catalan</span></span>
- <span data-ttu-id="3b818-198">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="3b818-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="3b818-199">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="3b818-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="3b818-200">크로아티아어</span><span class="sxs-lookup"><span data-stu-id="3b818-200">Croatian</span></span>
- <span data-ttu-id="3b818-201">체코어</span><span class="sxs-lookup"><span data-stu-id="3b818-201">Czech</span></span>
- <span data-ttu-id="3b818-202">덴마크어</span><span class="sxs-lookup"><span data-stu-id="3b818-202">Danish</span></span>
- <span data-ttu-id="3b818-203">네덜란드어</span><span class="sxs-lookup"><span data-stu-id="3b818-203">Dutch</span></span>
- <span data-ttu-id="3b818-204">영어</span><span class="sxs-lookup"><span data-stu-id="3b818-204">English</span></span>
- <span data-ttu-id="3b818-205">에스토니아어</span><span class="sxs-lookup"><span data-stu-id="3b818-205">Estonian</span></span>
- <span data-ttu-id="3b818-206">필리핀어(필리핀)</span><span class="sxs-lookup"><span data-stu-id="3b818-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="3b818-207">핀란드어</span><span class="sxs-lookup"><span data-stu-id="3b818-207">Finnish</span></span>
- <span data-ttu-id="3b818-208">프랑스어</span><span class="sxs-lookup"><span data-stu-id="3b818-208">French</span></span>
- <span data-ttu-id="3b818-209">갈리시아어</span><span class="sxs-lookup"><span data-stu-id="3b818-209">Galician</span></span>
- <span data-ttu-id="3b818-210">독일어</span><span class="sxs-lookup"><span data-stu-id="3b818-210">German</span></span>
- <span data-ttu-id="3b818-211">그리스어</span><span class="sxs-lookup"><span data-stu-id="3b818-211">Greek</span></span>
- <span data-ttu-id="3b818-212">구자라트어</span><span class="sxs-lookup"><span data-stu-id="3b818-212">Gujarati</span></span>
- <span data-ttu-id="3b818-213">히브리어</span><span class="sxs-lookup"><span data-stu-id="3b818-213">Hebrew</span></span>
- <span data-ttu-id="3b818-214">힌디어</span><span class="sxs-lookup"><span data-stu-id="3b818-214">Hindi</span></span>
- <span data-ttu-id="3b818-215">헝가리어</span><span class="sxs-lookup"><span data-stu-id="3b818-215">Hungarian</span></span>
- <span data-ttu-id="3b818-216">아이슬란드어</span><span class="sxs-lookup"><span data-stu-id="3b818-216">Icelandic</span></span>
- <span data-ttu-id="3b818-217">인도네시아어</span><span class="sxs-lookup"><span data-stu-id="3b818-217">Indonesian</span></span>
- <span data-ttu-id="3b818-218">이탈리아어</span><span class="sxs-lookup"><span data-stu-id="3b818-218">Italian</span></span>
- <span data-ttu-id="3b818-219">일본어</span><span class="sxs-lookup"><span data-stu-id="3b818-219">Japanese</span></span>
- <span data-ttu-id="3b818-220">칸나다어</span><span class="sxs-lookup"><span data-stu-id="3b818-220">Kannada</span></span>
- <span data-ttu-id="3b818-221">카자흐어</span><span class="sxs-lookup"><span data-stu-id="3b818-221">Kazakh</span></span>
- <span data-ttu-id="3b818-222">스와힐리어</span><span class="sxs-lookup"><span data-stu-id="3b818-222">Kiswahili</span></span>
- <span data-ttu-id="3b818-223">한국어</span><span class="sxs-lookup"><span data-stu-id="3b818-223">Korean</span></span>
- <span data-ttu-id="3b818-224">라트비아어</span><span class="sxs-lookup"><span data-stu-id="3b818-224">Latvian</span></span>
- <span data-ttu-id="3b818-225">리투아니아어</span><span class="sxs-lookup"><span data-stu-id="3b818-225">Lithuanian</span></span>
- <span data-ttu-id="3b818-226">말레이어(브루나이)</span><span class="sxs-lookup"><span data-stu-id="3b818-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="3b818-227">말레이어(말레이시아)</span><span class="sxs-lookup"><span data-stu-id="3b818-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="3b818-228">말라얄람어</span><span class="sxs-lookup"><span data-stu-id="3b818-228">Malayalam</span></span>
- <span data-ttu-id="3b818-229">마라티어</span><span class="sxs-lookup"><span data-stu-id="3b818-229">Marathi</span></span>
- <span data-ttu-id="3b818-230">노르웨이어(복말)</span><span class="sxs-lookup"><span data-stu-id="3b818-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="3b818-231">노르웨이어(니노르스크)</span><span class="sxs-lookup"><span data-stu-id="3b818-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="3b818-232">오리야어</span><span class="sxs-lookup"><span data-stu-id="3b818-232">Oriya</span></span>
- <span data-ttu-id="3b818-233">페르시아어</span><span class="sxs-lookup"><span data-stu-id="3b818-233">Persian</span></span>
- <span data-ttu-id="3b818-234">폴란드어</span><span class="sxs-lookup"><span data-stu-id="3b818-234">Polish</span></span>
- <span data-ttu-id="3b818-235">포르투갈어(브라질)</span><span class="sxs-lookup"><span data-stu-id="3b818-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="3b818-236">포르투갈어(포르투갈)</span><span class="sxs-lookup"><span data-stu-id="3b818-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="3b818-237">루마니아어</span><span class="sxs-lookup"><span data-stu-id="3b818-237">Romanian</span></span>
- <span data-ttu-id="3b818-238">러시아어</span><span class="sxs-lookup"><span data-stu-id="3b818-238">Russian</span></span>
- <span data-ttu-id="3b818-239">세르비아어(키릴 자모, 세르비아)</span><span class="sxs-lookup"><span data-stu-id="3b818-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="3b818-240">세르비아어(라틴 문자)</span><span class="sxs-lookup"><span data-stu-id="3b818-240">Serbian (Latin)</span></span>
- <span data-ttu-id="3b818-241">슬로바키아어</span><span class="sxs-lookup"><span data-stu-id="3b818-241">Slovak</span></span>
- <span data-ttu-id="3b818-242">슬로베니아어</span><span class="sxs-lookup"><span data-stu-id="3b818-242">Slovenian</span></span>
- <span data-ttu-id="3b818-243">스페인어</span><span class="sxs-lookup"><span data-stu-id="3b818-243">Spanish</span></span>
- <span data-ttu-id="3b818-244">스웨덴어</span><span class="sxs-lookup"><span data-stu-id="3b818-244">Swedish</span></span>
- <span data-ttu-id="3b818-245">타밀어</span><span class="sxs-lookup"><span data-stu-id="3b818-245">Tamil</span></span>
- <span data-ttu-id="3b818-246">텔루구어</span><span class="sxs-lookup"><span data-stu-id="3b818-246">Telugu</span></span>
- <span data-ttu-id="3b818-247">태국어</span><span class="sxs-lookup"><span data-stu-id="3b818-247">Thai</span></span>
- <span data-ttu-id="3b818-248">터키어</span><span class="sxs-lookup"><span data-stu-id="3b818-248">Turkish</span></span>
- <span data-ttu-id="3b818-249">우크라이나어</span><span class="sxs-lookup"><span data-stu-id="3b818-249">Ukrainian</span></span>
- <span data-ttu-id="3b818-250">우르두어</span><span class="sxs-lookup"><span data-stu-id="3b818-250">Urdu</span></span>
- <span data-ttu-id="3b818-251">베트남어</span><span class="sxs-lookup"><span data-stu-id="3b818-251">Vietnamese</span></span>
- <span data-ttu-id="3b818-252">웨일스어</span><span class="sxs-lookup"><span data-stu-id="3b818-252">Welsh</span></span>