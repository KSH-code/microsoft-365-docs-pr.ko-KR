---
title: Microsoft 준수 관리자 및 GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자는 Microsoft Service Trust Portal의 무료 워크플로 기반 위험 평가 도구입니다. 준수 관리자를 사용하면 Microsoft 클라우드 서비스와 관련된 규정 준수 활동을 추적, 할당 및 확인할 수 있습니다.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595805"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="eb5ad-104">Microsoft 준수 관리자 및 GDPR</span><span class="sxs-lookup"><span data-stu-id="eb5ad-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="eb5ad-105">유럽 연합에서 제정한 GDPR(일반 데이터 보호 규정)은 규정 준수 전략에 영향을 미치고 준수 관리자에서 사용되는 사용자 및 고객 정보를 관리하기 위한 특정 작업을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="eb5ad-106">사용자 개인 정보 설정</span><span class="sxs-lookup"><span data-stu-id="eb5ad-106">User Privacy settings</span></span>

<span data-ttu-id="eb5ad-107">특정 규정을 준수하려면 조직에서 사용자 기록 데이터를 삭제할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="eb5ad-108">준수 관리자는 **관리자가** 다음을 할 수 있는 사용자 개인 정보 설정 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="eb5ad-109">사용자 검색</span><span class="sxs-lookup"><span data-stu-id="eb5ad-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="eb5ad-110">계정 데이터 기록의 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="eb5ad-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="eb5ad-111">사용자 데이터 기록 삭제</span><span class="sxs-lookup"><span data-stu-id="eb5ad-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="eb5ad-112">사용자 검색</span><span class="sxs-lookup"><span data-stu-id="eb5ad-112">Search for a user</span></span>

<span data-ttu-id="eb5ad-113">사용자 계정을 검색하려면</span><span class="sxs-lookup"><span data-stu-id="eb5ad-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="eb5ad-114">사용자 전자 메일 별칭(@ 기호 왼쪽의 정보)을 입력하고 오른쪽의 도메인 접미사 목록에서 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="eb5ad-115">등록된 도메인이 여러 개 있는 조직의 경우 도메인 이름 접미사가 올바른지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="eb5ad-116">사용자 이름을 올바르게 입력한 경우 검색을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb5ad-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="eb5ad-117">사용자 계정이 반환되지 않는 경우 페이지에 User를 찾을 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="eb5ad-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="eb5ad-118">사용자의 전자 메일 주소 정보를 확인하고 필요한 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="eb5ad-119">다시 시도하려면 검색을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb5ad-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="eb5ad-120">반환된 사용자 계정의 경우 단추의 텍스트가 **검색에서 지우기로** **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="eb5ad-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="eb5ad-121">이는 반환된 사용자 계정이 추가 기능에 대한 운영 컨텍스트이고 이러한 함수가 이 사용자 계정에 적용될 것 입니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="eb5ad-122">검색 결과를 지우고 다른 사용자를 검색하려면 지우기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb5ad-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="eb5ad-123">계정 데이터 기록의 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="eb5ad-123">Export a report of account data history</span></span>

<span data-ttu-id="eb5ad-124">식별된 각 사용자 계정에 대해 계정에 연결된 종속성 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="eb5ad-125">이 정보를 사용하여 열려 있는 작업 항목을 다시 재배치하거나 이전에 업로드한 증거에 대한 액세스를 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="eb5ad-126">보고서를 생성하고 내보내려면:</span><span class="sxs-lookup"><span data-stu-id="eb5ad-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="eb5ad-127">내보내기 **기능을** 선택하여 반환된 사용자 계정에 현재 할당된 준수 관리자 컨트롤 작업 항목 및 해당 사용자가 업로드한 문서 목록의 보고서를 생성하고 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="eb5ad-128">할당된 작업이나 업로드된 문서가 없는 경우 "이 사용자에 대한 데이터가 없습니다."라는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="eb5ad-129">보고서는 활성 브라우저 창의 백그라운드에서 다운로드됩니다. 브라우저 다운로드 기록을 확인하려는 다운로드 팝업이 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="eb5ad-130">문서를 열어 보고서 데이터를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb5ad-131">보고서 데이터는 작업 항목 할당 기록에 대한 상태 변경 내용을 보존하고 표시하는 기록 목록이 아니며,</span><span class="sxs-lookup"><span data-stu-id="eb5ad-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="eb5ad-132">생성된 보고서는 보고서가 실행될 때 할당된 컨트롤 작업 항목(보고서에 기록된 날짜 및 타임스탬프)의 스냅숏입니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="eb5ad-133">예를 들어 동일한 사용자에 대해 보고서가 다시 생성되는 경우 이후에 작업 항목을 다시 지정하면 다른 스냅숏 보고서 데이터가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="eb5ad-134">사용자 데이터 기록 삭제</span><span class="sxs-lookup"><span data-stu-id="eb5ad-134">Delete user data history</span></span>

<span data-ttu-id="eb5ad-135">반환된 사용자에게 할당된 모든 컨트롤 작업 항목을 '지정되지 않은'으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="eb5ad-136">반환된 **사용자가 업로드한** 문서의 값으로 업로드한 값을 '사용자 제거'로 설정</span><span class="sxs-lookup"><span data-stu-id="eb5ad-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="eb5ad-137">사용자 계정 작업 항목 및 문서 업로드 기록을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="eb5ad-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="eb5ad-138">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5ad-138">Select **Delete**.</span></span>

    <span data-ttu-id="eb5ad-139">확인 대화 상자가 표시됩니다. "그러면 선택한 사용자의 모든 컨트롤 작업 항목 할당 및 문서 업로드 *기록이 제거됩니다. 이 작업은 영구적입니다. 계속하고 싶나요?*"</span><span class="sxs-lookup"><span data-stu-id="eb5ad-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="eb5ad-140">확인을 **계속하려면** 취소를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb5ad-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
