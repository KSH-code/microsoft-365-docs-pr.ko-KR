---
title: 사용자 지원 Microsoft Managed Desktop
description: 사용자가 서비스 및 장치에 대한 도움말을 얻을 수 있는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362609"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="f1921-104">사용자를 위한 도움말</span><span class="sxs-lookup"><span data-stu-id="f1921-104">Getting help for users</span></span>

<span data-ttu-id="f1921-105">Microsoft에 대한 상승된 장치 [](../service-description/user-support.md) 액세스 또는 에스컬레이터를 요청해야 하는 워크플로 지점에 도달한 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="f1921-106">테스트 그룹의 디바이스에서는 이러한 지원 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="f1921-107">권한 상승 요청</span><span class="sxs-lookup"><span data-stu-id="f1921-107">Elevation requests</span></span>

<span data-ttu-id="f1921-108">장치에 대한 높은 액세스 권한을 요청하기 전에 가장 적합한 작업을 검토하는 것이 가장 좋은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="f1921-109">**일반적인 작업은** 이 프로세스가 의도한 작업으로, 장치와의 문제를 해결하는 동안 Microsoft Managed Desktop 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f1921-110">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-110">Examples include:</span></span>
    - <span data-ttu-id="f1921-111">기본 제공 시스템 문제 해결사, 명령 프롬프트 또는 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1921-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="f1921-112">업무용 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f1921-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="f1921-113">해결 방법을 사용하여 디자인에 따라 작동해야 하는 기능 수정(예: BitLocker 정품 인증 또는 업데이트되지 않는 시스템 시간)</span><span class="sxs-lookup"><span data-stu-id="f1921-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="f1921-114">업데이트 드라이버, 장치 제거 또는 새 변경 내용 검색과 같은 작업을 위해 장치 관리자 권한 상승</span><span class="sxs-lookup"><span data-stu-id="f1921-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="f1921-115">**권장되지 않는 작업은** 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="f1921-116">소프트웨어 또는 브라우저 설치</span><span class="sxs-lookup"><span data-stu-id="f1921-116">Installing software or browsers</span></span>
    - <span data-ttu-id="f1921-117">주변 장치용 드라이버를 Windows 설정 외부에 드라이버 설치</span><span class="sxs-lookup"><span data-stu-id="f1921-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="f1921-118">파일 .msi 또는 .exe 설치</span><span class="sxs-lookup"><span data-stu-id="f1921-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="f1921-119">Windows 기능 설치</span><span class="sxs-lookup"><span data-stu-id="f1921-119">Installing Windows features</span></span>

- <span data-ttu-id="f1921-120">**지원되지 않는 작업은** 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="f1921-121">보안 또는 관리 기능과 충돌하는 소프트웨어 또는 Microsoft Managed Desktop 기능 설치</span><span class="sxs-lookup"><span data-stu-id="f1921-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="f1921-122">BitLocker와 같은 Windows 필요한 Microsoft Managed Desktop 기능을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="f1921-123">관리되는 설정 수정</span><span class="sxs-lookup"><span data-stu-id="f1921-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="f1921-124">권한 상승을 요청하는 경우</span><span class="sxs-lookup"><span data-stu-id="f1921-124">To request elevation</span></span>

1. <span data-ttu-id="f1921-125">의 포털로 이동한 후 사용자 자격 증명으로 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) Azure Active Directory 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="f1921-126">새 **권한 상승 요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1921-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="f1921-127">다음 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-127">Provide these details:</span></span>
    - <span data-ttu-id="f1921-128">**자체 지원 티켓** 시스템에서 티켓 ID를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="f1921-129">**장치 이름:** 장치 일련 번호를 입력한 다음 메뉴에서 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="f1921-130">**범주:** 문제와 가장 잘 맞는 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="f1921-131">옵션이 닫히는 것  같은 경우 기타를  선택하고 제목 및 작업 계획 **필드에** 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="f1921-132">가능한 경우 범주를 선택하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="f1921-133">**하위 목록**: 이슈에 가장 잘 맞는 하위 목록 선택</span><span class="sxs-lookup"><span data-stu-id="f1921-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="f1921-134">옵션이 닫히는 것  같은 경우 기타를 선택하고 제목에 간단한 설명을 **제공합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1921-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="f1921-135">작업 **계획에서** 권한 상승이 부여된 후 수행하기로 계획한 문제 해결 단계를 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="f1921-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="f1921-136">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="f1921-137">에스컬레이터 요청</span><span class="sxs-lookup"><span data-stu-id="f1921-137">Escalation requests</span></span>


<span data-ttu-id="f1921-138">Microsoft로 [문제를 에스컬레이터해야](../service-description/user-support.md#escalation-portal) 하는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="f1921-139">의 포털로 이동한 후 사용자 자격 증명으로 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) Azure Active Directory 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="f1921-140">**에스컬ation 요청 을** 선택한 다음 새 **에스컬ation 요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1921-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="f1921-141">다음 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-141">Provide these details:</span></span>
    - <span data-ttu-id="f1921-142">**범주:** 문제와 가장 잘 맞는 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="f1921-143">**제목:** 간단한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="f1921-144">**설명:** 팀에서 문제를 이해하는 데 도움이 될 수 있는 세부 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="f1921-145">파일을 첨부해야 하는 경우 파일을 제출한 후 요청으로 돌아와서 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="f1921-146">**기본 연락처 정보:** 팀과 함께 작업하는 주 담당자에게 연락하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="f1921-147">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-147">Select **Submit**.</span></span>
5. <span data-ttu-id="f1921-148">팀과 상호 작용하기 위해 동일한 포털에서 티켓을 다시 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="f1921-149">이 경로를 통해 심각도 C 문제만 에스컬레이터할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="f1921-150">다른 문제가 있는 경우 IT 관리자에게 문의하여 관리 포털을 통해 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="f1921-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>