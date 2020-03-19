---
title: Microsoft 준수 점수 업데이트
f1.keywords:
- NOCSH
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
description: 향후 위험 평가를 간소화 하 고 자동화 하는 데 도움이 되는 Microsoft 준수 점수 (preview)에 대 한 이후 업데이트에 대 한 자세한 내용은 M365 준수 센터의 기능을 참조 하십시오.
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857781"
---
# <a name="microsoft-compliance-score-preview-updates"></a><span data-ttu-id="50bb6-103">Microsoft 준수 점수 (미리 보기) 업데이트</span><span class="sxs-lookup"><span data-stu-id="50bb6-103">Microsoft Compliance Score (Preview) updates</span></span>

 <span data-ttu-id="50bb6-104">이 문서에서는 향후 [Microsoft 규정 준수 점수](compliance-score.md) 및 [microsoft 준수 관리자](compliance-manager-overview.md)의 업데이트에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-104">This article provides details about future updates to [Microsoft Compliance Score](compliance-score.md) and [Microsoft Compliance Manager](compliance-manager-overview.md).</span></span> <span data-ttu-id="50bb6-105">해당 [관계](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="50bb6-105">Learn more about their [relationship](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).</span></span>

## <a name="improved-template-creation-and-update-processes"></a><span data-ttu-id="50bb6-106">향상 된 서식 파일 만들기 및 업데이트 프로세스</span><span class="sxs-lookup"><span data-stu-id="50bb6-106">Improved template creation and update processes</span></span>

<span data-ttu-id="50bb6-107">평가를 위해 템플릿을 가져오고, 내보내고, 수정 하는 프로세스를 단순화 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-107">We're simplifying the process for importing, exporting, and modifying templates for assessments.</span></span> <span data-ttu-id="50bb6-108">새로운 환경에서는 자체 평가를 준수 점수로 가져오고 업데이트 된 상태로 유지 하는 데 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-108">The new experience will make it easier for you to bring your own assessments into Compliance Score and keep them updated.</span></span>

### <a name="the-current-process"></a><span data-ttu-id="50bb6-109">현재 프로세스</span><span class="sxs-lookup"><span data-stu-id="50bb6-109">The current process</span></span>

<span data-ttu-id="50bb6-110">두 가지 방법으로 준수 관리자에서 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-110">There are two ways to create a template in Compliance Manager.</span></span> <span data-ttu-id="50bb6-111">기존 서식 파일을 복사 하거나 Excel 스프레드시트의 템플릿 데이터를 새 서식 파일로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-111">You can copy an existing template, or you can import template data from an Excel spreadsheet into a new template.</span></span> <span data-ttu-id="50bb6-112">**서식** 파일 페이지에서 **+ 서식 파일** 을 선택 하 여 새 서식 파일을 만들려면 이름을 입력 하 고, 차원을 선택 하 고, 특정 서식 및 스키마를 사용 하 여 Excel 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-112">From your **Templates** page, you select **+ Add template** to create a brand new template by entering a name, selecting dimensions, and uploading an Excel file with a specific format and schema.</span></span> <span data-ttu-id="50bb6-113">또는 아래 이미지에 나와 있는 것 처럼, **기존 서식 파일에서 복사본** 을 선택 하 고 복사할 서식 파일을 선택한 다음 차원을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-113">Or you can check the **Copy from an existing template** box, select a template to copy, and verify dimensions, as shown in the image below.</span></span> <span data-ttu-id="50bb6-114">서식 파일을 사용자 지정 하려면 먼저 서식 파일을 만든 후 **사용자 지정 컨트롤 추가** 를 선택 하 여 시작 되는 [다중 단계 프로세스가](working-with-compliance-manager.md#templates) 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-114">Customizing your template requires a [multi-step process](working-with-compliance-manager.md#templates) that begins by selecting **Add custom control** after creating your template.</span></span>

<span data-ttu-id="50bb6-115">![준수 점수-대시보드](../media/compliance-score-template-update-old.png "현재 서식 파일 복사 프로세스")</span><span class="sxs-lookup"><span data-stu-id="50bb6-115">![Compliance Score - dashboard](../media/compliance-score-template-update-old.png "Current template copy process")</span></span>

### <a name="whats-changing"></a><span data-ttu-id="50bb6-116">변경 된 기능</span><span class="sxs-lookup"><span data-stu-id="50bb6-116">What's changing</span></span>

<span data-ttu-id="50bb6-117">새 템플릿을 쉽게 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-117">We're making it easier for you to create new templates.</span></span> <span data-ttu-id="50bb6-118">1 단계 **확장** 프로세스에서는 현재 Microsoft 서식 파일에 작업 및 컨트롤이 포함 된 스프레드시트를 추가 하 여 고유한 사용자 지정 버전을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-118">In a one-step **extension** process, you can add a spreadsheet with your actions and controls to an existing Microsoft template to make your own customized version.</span></span> <span data-ttu-id="50bb6-119">**서식 파일** 플라이 아웃 창에서 아래 이미지와 같이 **전역 템플릿에서 확장명 만들기** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-119">On the **Template** flyout pane, select the **Create extension from global template** checkbox, as shown in the image below.</span></span> <span data-ttu-id="50bb6-120">그런 다음 새 Excel 형식을 사용 하 여 현재 보다 덜 복잡 한 사용자 지정 내용을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-120">You'll then add customizations using a new Excel format that is less complex than the current one.</span></span> <span data-ttu-id="50bb6-121">이 새 프로세스는 **기존 서식 파일에서 현재 복사본** 을 대체 하 고 **사용자 지정 컨트롤** 함수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-121">This new process replaces the current **Copy from an existing template** and **Add custom control** functions.</span></span>

<span data-ttu-id="50bb6-122">아래에 나와 있는 버전 관리 프로세스를 통해 원래 평가를 업데이트할 때마다 사용자 지정 된 평가는 이러한 업데이트를 상속 하 고 사용자 정의 컨트롤을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-122">Each time the original assessment is updated through the versioning process outlined below, your customized assessment will inherit those updates and keep your custom controls.</span></span>

<span data-ttu-id="50bb6-123">또한 기존 템플릿을 쉽게 수정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-123">We're also making it easier to modify your own existing templates.</span></span> <span data-ttu-id="50bb6-124">서식 파일을 내보내고, 같은 통합 문서를 변경한 다음, 편집한 내용이 저장 된 상태로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-124">You can export your template, make changes in the same workbook, then import it with your edits saved.</span></span>

<span data-ttu-id="50bb6-125">![준수 점수-대시보드](../media/compliance-score-template-update-new.png "새 서식 파일 만들기 프로세스")</span><span class="sxs-lookup"><span data-stu-id="50bb6-125">![Compliance Score - dashboard](../media/compliance-score-template-update-new.png "New template creation process")</span></span>

## <a name="versioning-notice-and-control"></a><span data-ttu-id="50bb6-126">버전 관리 알림 및 제어</span><span class="sxs-lookup"><span data-stu-id="50bb6-126">Versioning notice and control</span></span>

<span data-ttu-id="50bb6-127">조직의 준수 점수 및 규정 준수 관리자에 게 업데이트 된 평가를 수신 하 여 인증 및 규제 업데이트를 맞추는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-127">Your organization will receive updated assessments in the next release of Compliance Score and Compliance Manager to help you align with certification and regulation updates.</span></span>

<span data-ttu-id="50bb6-128">향후에는 평가의 템플릿이나 개선 작업에 대 한 업데이트를 사용할 수 있을 때마다 알림 아이콘에 업데이트가 준비 되었음을 알리는 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-128">Going forward, whenever an update is available for an assessment's template or an improvement action, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="50bb6-129">해당 아이콘을 클릭 하면 팝업 창에서 업데이트에 대해 설명 하 고 사용자에 게 수락을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-129">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="50bb6-130">다음은 평가에 대 한 버전 관리 경고의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-130">Below is an example of the versioning alert for an assessment:</span></span>

<span data-ttu-id="50bb6-131">![준수 점수-버전 관리 경고](../media/compliance-score-assessment-version.png "평가 버전 업데이트 경고")</span><span class="sxs-lookup"><span data-stu-id="50bb6-131">![Compliance Score - versioning alert](../media/compliance-score-assessment-version.png "Assessment version update alert")</span></span>

<span data-ttu-id="50bb6-132">알림 아이콘을 선택 하면 업데이트 및 수락 여부를 설명 하는 플라이 아웃 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-132">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept:</span></span>

<span data-ttu-id="50bb6-133">![준수 점수-버전 지정 플라이 아웃](../media/compliance-score-assessment-version-accept.png "평가 업데이트 확인 창")</span><span class="sxs-lookup"><span data-stu-id="50bb6-133">![Compliance Score - versioning flyout](../media/compliance-score-assessment-version-accept.png "Assessment update confirmation pane")</span></span>

## <a name="common-actions-will-synch-status-across-groups"></a><span data-ttu-id="50bb6-134">일반 작업을 통해 여러 그룹의 상태가 동기화 됨</span><span class="sxs-lookup"><span data-stu-id="50bb6-134">Common actions will synch status across groups</span></span>

<span data-ttu-id="50bb6-135">조직에 여러 평가 그룹이 있는 경우 **기술** 작업의 동작 (즉, 전체 조직에 영향을 주는 작업)이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-135">If your organization has multiple groups of assessments, the behavior of **Technical** actions (that is, actions affecting your entire organization) will change.</span></span> <span data-ttu-id="50bb6-136">그룹 간 중복 된 작업은 하나의 단일 작업으로 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-136">Any duplicate actions across groups will be combined into one single action.</span></span> <span data-ttu-id="50bb6-137">이 단일 작업은 중복 버전에서 업로드 된 모든 메모 및 증거를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-137">That single action will contain all uploaded notes and evidence from the duplicate versions.</span></span> <span data-ttu-id="50bb6-138">이렇게 변경 하면 기술적 작업이 같은 그룹에 속해 있을 때 현재 수행 중인 것 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-138">With this change, technical actions will behave as they currently do when they belong to the same group.</span></span> <span data-ttu-id="50bb6-139">이제 하나의 그룹 또는 평가에서 작업에 대 한 변경 내용이 모든 인스턴스에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-139">Any change made to the action in one group or assessment will now be reflected in all instances.</span></span> <span data-ttu-id="50bb6-140"> *\*구현 상태*\*, *\*구현 Dat*\*, *\*테스트 상태*\*및 *\*테스트 날짜** 에는 최신 업데이트가 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-140">The **Implementation Status**, **Implementation Dat**, **Test Status**, and **Test Date** will reflect the most recent updates.</span></span>

## <a name="language-support"></a><span data-ttu-id="50bb6-141">언어 지원</span><span class="sxs-lookup"><span data-stu-id="50bb6-141">Language support</span></span>

<span data-ttu-id="50bb6-142">이제 준수 점수가 영어, 중국어 (간체), 중국어 (번체), 프랑스어, 독일어, 이탈리아어, 일본어, 한국어, 포르투갈어 (브라질), 러시아어, 스페인어 등의 언어로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50bb6-142">Compliance Score will now be available in the following languages in addition to English: Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), Russian, and Spanish.</span></span>
