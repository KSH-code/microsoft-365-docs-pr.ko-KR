---
title: Microsoft 준수 점수 릴리스 정보
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 위험 평가를 간소화 하 고 자동화 하는 데 도움이 되는 M365 준수 센터의 기능인 Microsoft 준수 점수 (미리 보기)에 대 한 릴리스 정보 및 알려진 문제
ms.openlocfilehash: 192519e323f9d23420f82a603979b50f4581ac4f
ms.sourcegitcommit: e2ed110c4c3a8434f9fcc9d610069bc77bc39220
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "38687159"
---
# <a name="microsoft-compliance-score-release-notes-preview"></a><span data-ttu-id="838ed-103">Microsoft 준수 점수 릴리스 정보 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="838ed-103">Microsoft Compliance Score release notes (Preview)</span></span>

<span data-ttu-id="838ed-104">Microsoft 준수 점수가 공개 미리 보기를 통해 예정 된 기능 및 업데이트에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-104">The public preview of Microsoft Compliance Score provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="838ed-105">준수 점수는 위험 기반 점수를 계산 하 여 준수 위험을 줄이는 데 도움이 되는 권장 작업을 완료 하는 과정을 측정 하는 [Microsoft 365 준수 센터](microsoft-365-compliance-center.md) 의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-105">Compliance Score is a new feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that calculates a risk-based score, measuring your progress towards completing recommended actions that help reduce compliance risks.</span></span>

## <a name="compliance-score-and-compliance-manager-relationship"></a><span data-ttu-id="838ed-106">준수 점수 및 준수 관리자 관계</span><span class="sxs-lookup"><span data-stu-id="838ed-106">Compliance Score and Compliance Manager relationship</span></span>

<span data-ttu-id="838ed-107">준수 관리자에서 처리 되는 대부분의 준수 기능은 이제 규정 준수 점수를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-107">Many of the compliance functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="838ed-108">그러나 일부 기능은 여전히 준수 관리자 에게만 존재 하며, 공용 미리 보기 기간 동안 준수 관리자의 일부 이전 기능은 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-108">However some functionality still resides only in Compliance Manager, and some previous functionality in Compliance Manager is altered during the public preview period.</span></span> 

<span data-ttu-id="838ed-109">공개 미리 보기 동안 준수 점수 및 준수 관리자를 사용할 때는 다음 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-109">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

- <span data-ttu-id="838ed-110">**평가 관리**: 사용자는 준수 점수에 평가 및 해당 상태 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-110">**Managing assessments**: users can view assessments and their status details in Compliance Score.</span></span> <span data-ttu-id="838ed-111">그러나 사용자는 준수 관리자의 평가 관리 작업 ([지침 보기](working-with-compliance-manager.md#assessments)) 및 작업을 수행할 수 있으며 다음으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-111">However users can only perform assessment management tasks in Compliance Manager ([view instructions](working-with-compliance-manager.md#assessments)), and tasks and are limited to the following:</span></span>
    - <span data-ttu-id="838ed-112">새 평가를 업로드 하지만 기존 평가는 수정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-112">Upload new assessments, but not modify existing assessments.</span></span> <span data-ttu-id="838ed-113">기존 평가를 수정 해야 하는 경우 새 템플릿을 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-113">If you need to modify an existing assessment, you will need to upload a new template.</span></span>
    - <span data-ttu-id="838ed-114">평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="838ed-114">Export assessments</span></span>
    - <span data-ttu-id="838ed-115">보관 평가</span><span class="sxs-lookup"><span data-stu-id="838ed-115">Archive assessments</span></span>
    - <span data-ttu-id="838ed-116">보관 된 평가 보기</span><span class="sxs-lookup"><span data-stu-id="838ed-116">View archived assessments</span></span>
 - <span data-ttu-id="838ed-117">**평가를 위한 템플릿 만들기**:</span><span class="sxs-lookup"><span data-stu-id="838ed-117">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="838ed-118">사용자는 준수 관리자를 방문 하 여 새 템플릿을 만들고 기존 템플릿을 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-118">Users must go to Compliance Manager to create new templates and export existing templates.</span></span> 
   - <span data-ttu-id="838ed-119">기존 템플릿은 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-119">Existing templates cannot be customized.</span></span> <span data-ttu-id="838ed-120">[준수 관리자의 서식 파일 관리](working-with-compliance-manager.md#templates)에 대 한 지침을 읽으십시오.</span><span class="sxs-lookup"><span data-stu-id="838ed-120">Read instructions for [managing templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="838ed-121">서식 파일을 만들 때는 **제품** 및 **인증** 에 대 한 차원을 모두 포함 하 여 서식 파일이 준수 점수에 표시 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-121">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
 - <span data-ttu-id="838ed-122">**사용 권한 설정**: 규정 준수 점수 준수 관리자에서 이전에 사용 권한을 부여 받지 않은 사용자는 Microsoft 365 준수 센터에서 사용 권한을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-122">**Setting permissions**: Compliance Score users who were not previously granted permissions in Compliance Manager must have their permissions set in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="838ed-123">규정 준수 관리자에서 역할이 이전에 설정 된 사용자는 준수 점수 작업을 할 때 같은 수준의 액세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-123">Users whose roles were previously set in Compliance Manager can use that same level of access when working in Compliance Score.</span></span>
- <span data-ttu-id="838ed-124">**데이터 전송**: 규정 준수 관리자에 데이터가 있는 조직은 규정 준수 점수에 해당 하는 데이터를 확인 하 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-124">**Transfer of data**: organizations with data residing in Compliance Manger will see that data in Compliance Score, and vice-versa.</span></span>
- <span data-ttu-id="838ed-125">준수 **관리자에 게 준수 점수**에 로그인: 사용자가 준수 점수에 로그인 되어 있고 준수 관리자에 게 연결 되는 링크를 선택 하는 경우 사용자가 다시 로그인 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-125">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user will not have to sign in again.</span></span> <span data-ttu-id="838ed-126">링크를 클릭 하면 브라우저에서 대화 상자를 표시 하는 새 탭이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-126">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="838ed-127">머리글이 "이미 Microsoft 클라우드 서비스 고객" 인 최상위 섹션에서</span><span class="sxs-lookup"><span data-stu-id="838ed-127">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="838ed-128">계정에 로그인 하 여 준수 관리자에 게 자동으로 로그인 하는 **로그인** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-128">Sign in to your account,” select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="838ed-129">준수 점수에 알려진 문제 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="838ed-129">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="838ed-130">다음 섹션에서는 향후 준수 점수에서 해결 해야 할 알려진 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-130">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="launch-now-links-in-certain-improvement-actions"></a><span data-ttu-id="838ed-131">특정 개선 작업의 지금 시작 링크</span><span class="sxs-lookup"><span data-stu-id="838ed-131">Launch Now links in certain improvement actions</span></span>

<span data-ttu-id="838ed-132">특정 개선 작업에서 구현 명령 아래에 표시 되는 **지금 시작** 링크를 선택 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-132">In certain improvement actions, selecting the **Launch Now** link that appears underneath the implementation instructions gives an error.</span></span> <span data-ttu-id="838ed-133">SharePoint 관리 센터에 적합 한 대상에 액세스 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-133">To access the proper destination, which is the the SharePoint admin center, follow these steps:</span></span>

1. <span data-ttu-id="838ed-134">[Microsoft 365 관리 센터로](https://admin.microsoft.com)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-134">Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="838ed-135">왼쪽 탐색 메뉴에서 **모두 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-135">On the left navigation menu, select **Show all**.</span></span>
3. <span data-ttu-id="838ed-136">**관리 센터** 에서 **SharePoint**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-136">Under **Admin centers,** select **SharePoint**.</span></span>

<span data-ttu-id="838ed-137">다음은 모두 **보호 정보** 범주에 상주 하는 영향을 받는 향상 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-137">Below are the affected improvement actions, which all reside in the **Protect information** category:</span></span>
  - <span data-ttu-id="838ed-138">SharePoint 라이브러리에 암호화 적용</span><span class="sxs-lookup"><span data-stu-id="838ed-138">Apply encryption to SharePoint Library</span></span>
  - <span data-ttu-id="838ed-139">SharePoint Online의 데이터 분류</span><span class="sxs-lookup"><span data-stu-id="838ed-139">Classify Data in SharePoint Online</span></span>
  - <span data-ttu-id="838ed-140">만료 되도록 외부 공유 링크 구성</span><span class="sxs-lookup"><span data-stu-id="838ed-140">Configure External Sharing Links to Expire</span></span>
  - <span data-ttu-id="838ed-141">문서 라이브러리에 대 한 버전 관리 사용</span><span class="sxs-lookup"><span data-stu-id="838ed-141">Enable Versioning for Document Libraries</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="838ed-142">관리자가 아닌 사용자에 대 한 긴 로드 시간</span><span class="sxs-lookup"><span data-stu-id="838ed-142">Long load times for non-admin users</span></span>
<span data-ttu-id="838ed-143">준수 점수 관리자 역할 이외의 역할을 보유 하는 사용자는 로그인을 시도할 때 로드 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-143">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="838ed-144">브라우저를 새로 고치면이 문제가 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-144">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="838ed-145">( [규정 준수 점수 역할](compliance-score-setup.md#set-user-permissions-and-assign-roles)에 대해 자세히 알아보세요.)</span><span class="sxs-lookup"><span data-stu-id="838ed-145">(Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="838ed-146">지원되는 브라우저</span><span class="sxs-lookup"><span data-stu-id="838ed-146">Supported browsers</span></span>

- <span data-ttu-id="838ed-147">최신 버전의 Microsoft Edge, Chrome 및 Safari가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-147">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="838ed-148">브라우저를 새로 고칠 때까지 업데이트 된 데이터가 표시 되지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-148">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="838ed-149">Microsoft Edge의 preview 버전은 지원 되지 않지만 알려진 문제는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-149">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="838ed-150">Internet Explorer가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-150">Internet Explorer is not supported.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="838ed-151">언어 지원</span><span class="sxs-lookup"><span data-stu-id="838ed-151">Language support</span></span>

- <span data-ttu-id="838ed-152">준수 점수는 미국 영어로만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="838ed-152">Compliance Score is only available in U.S. English.</span></span>