---
title: Office 앱에서 민감도 레이블 작동 방식
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 민감도 레이블을 사용하여 사용자의 생산성 및 공동 작업 능력이 저하되지 않도록 하면서 중요한 콘텐츠를 분류 및 보호할 수 있습니다. 민감도 레이블을 사용하여 레이블이 지정된 콘텐츠에 대해 암호화 또는 워터마크와 같은 보호 설정을 적용할 수 있습니다.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417567"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="7618e-104">Office 앱에서 민감도 레이블 작동 방식</span><span class="sxs-lookup"><span data-stu-id="7618e-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="7618e-105">Office 응용 프로그램에서 민감도 레이블을 사용하는 데 필요한 필수 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="7618e-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="7618e-106">일반적인 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7618e-106">Common requirements</span></span> 

- <span data-ttu-id="7618e-107">통합 민감도 레이블은 [보안 및 준수 센터에서 구성되고 게시](https://aka.ms/managemip)되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="7618e-108">사용자는 회사 계정으로 Office에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="7618e-109">사용자에게는 Office 365 E3 이상의 라이선스가 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="7618e-110">Windows용 Office에 대한 추가 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7618e-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="7618e-111">Azure Information Protection 클라이언트가 Office에서 실행되고 있지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="7618e-112">참고 항목: [Windows용 Office에서 민감도 레이블을 Azure Information Protection 클라이언트와 함께 실행할 수 있나요?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)</span><span class="sxs-lookup"><span data-stu-id="7618e-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="7618e-113">모든 플랫폼에서 Outlook에 대한 추가 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7618e-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="7618e-114">레이블 구성에서 콘텐츠 표시를 설정하는 경우에는 Exchange Online을 사용하여 전송에 콘텐츠 표시를 삽입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="7618e-115">현재 Office에서는 어떤 민감도 레이블 기능이 지원되나요?</span><span class="sxs-lookup"><span data-stu-id="7618e-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="7618e-116"><font size="-1">기능</span><span class="sxs-lookup"><span data-stu-id="7618e-116"><font size="-1">Capability</span></span><th><span data-ttu-id="7618e-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="7618e-117"><font size="-1">Windows</span></span><th><span data-ttu-id="7618e-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="7618e-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="7618e-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7618e-119"><font size="-1"> Word</span></span><br>
<span data-ttu-id="7618e-120">Excel</span><span class="sxs-lookup"><span data-stu-id="7618e-120">Excel</span></span><br>
<span data-ttu-id="7618e-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7618e-121">PowerPoint</span></span><br>
<span data-ttu-id="7618e-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="7618e-122">Outlook</span></span>


<td><span data-ttu-id="7618e-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7618e-123"><font size="-1"> Word</span></span><br>
<span data-ttu-id="7618e-124">Excel</span><span class="sxs-lookup"><span data-stu-id="7618e-124">Excel</span></span><br>
<span data-ttu-id="7618e-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7618e-125">PowerPoint</span></span><br>
<span data-ttu-id="7618e-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="7618e-126">Outlook</span></span>

<td><span data-ttu-id="7618e-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7618e-127"><font size="-1"> Word</span></span><br>
<span data-ttu-id="7618e-128">Excel</span><span class="sxs-lookup"><span data-stu-id="7618e-128">Excel</span></span><br>
<span data-ttu-id="7618e-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7618e-129">PowerPoint</span></span>
<td><span data-ttu-id="7618e-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="7618e-130"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="7618e-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7618e-131"><font size="-1"> Word</span></span><br>
<span data-ttu-id="7618e-132">Excel</span><span class="sxs-lookup"><span data-stu-id="7618e-132">Excel</span></span><br>
<span data-ttu-id="7618e-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7618e-133">PowerPoint</span></span>
<td><span data-ttu-id="7618e-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="7618e-134"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="7618e-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7618e-135"><font size="-1"> Word</span></span><br>
<span data-ttu-id="7618e-136">Excel</span><span class="sxs-lookup"><span data-stu-id="7618e-136">Excel</span></span><br>
<span data-ttu-id="7618e-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7618e-137">PowerPoint</span></span>
<td><span data-ttu-id="7618e-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="7618e-138"><font size="-1"> Outlook </b>
</span></span></tr>

<tr>
<td><span data-ttu-id="7618e-139"><font size="-1">수동으로 레이블 적용, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="7618e-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="7618e-140"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-140"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7618e-142"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-142"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7618e-144"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-144"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7618e-146"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-147"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-147"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7618e-149"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-150"><font size="-1">출시 예정<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="7618e-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="7618e-151"><font size="-1">출시 예정<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7618e-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="7618e-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">기본 레이블 적용</a>
</span><span class="sxs-lookup"><span data-stu-id="7618e-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="7618e-153"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-153"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7618e-155"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-155"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7618e-157"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-157"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7618e-159"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-160"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-160"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7618e-162"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-163"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-164"><font size="-1">출시 예정<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7618e-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7618e-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">레이블을 변경하는 데 사유 요구</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="7618e-166"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-166"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7618e-168"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-168"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7618e-170"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-170"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7618e-172"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-173"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-173"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7618e-175"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-176"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-177"><font size="-1">출시 예정<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7618e-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7618e-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">사용자 지정 도움말 페이지에 도움말 링크 제공</a>
</span><span class="sxs-lookup"><span data-stu-id="7618e-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="7618e-179"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-179"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7618e-181"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-181"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7618e-183"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-183"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7618e-185"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-186"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-186"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7618e-188"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-189"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-190"><font size="-1">출시 예정<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7618e-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7618e-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">콘텐츠 표시</a>
</span><span class="sxs-lookup"><span data-stu-id="7618e-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="7618e-192"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-192"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7618e-194"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-194"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7618e-196"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-196"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7618e-198"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-199"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-199"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="7618e-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="7618e-201"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-202"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-203"><font size="-1">출시 예정<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7618e-203"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7618e-204"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">사전 정의된 사용 권한 할당</a>
</span><span class="sxs-lookup"><span data-stu-id="7618e-204"><font size="-1">Assign pre-defined permissions</span></span><td><span data-ttu-id="7618e-205"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-205"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7618e-207"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-207"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7618e-209"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-209"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7618e-211"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-212"><font size="-1"><b>예</b></span><span class="sxs-lookup"><span data-stu-id="7618e-212"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="7618e-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="7618e-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7618e-214"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-215"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-216"><font size="-1">출시 예정<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7618e-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7618e-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">사용자가 권한을 할당하도록 허용</a>
</span><span class="sxs-lookup"><span data-stu-id="7618e-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Let users assign permissions</a>
</span></span><td><span data-ttu-id="7618e-218"><font size="-1"><b>예</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7618e-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="7618e-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="7618e-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7618e-220"><font size="-1"><b>예</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7618e-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="7618e-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="7618e-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="7618e-222"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-223"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-224"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="7618e-225"><font size="-1">출시 예정<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7618e-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7618e-226"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-227"><font size="-1">출시 예정<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="7618e-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="7618e-228"><font size="-1">관리자를 위한 <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">레이블 분석</a> 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="7618e-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="7618e-229"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7618e-230"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7618e-231"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-232"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-233"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-234"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-235"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-236"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="7618e-237"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">사용자가 전자 메일 및 문서에 레이블을 적용하도록 요구</a>
</span><span class="sxs-lookup"><span data-stu-id="7618e-237"><font size="-1">Require users to apply a label to their email and documents</span></span><td><span data-ttu-id="7618e-238"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7618e-239"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7618e-240"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-241"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-242"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-243"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-244"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-245"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="7618e-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">민감도 레이블을 콘텐츠에 자동으로 적용</a>
</span><span class="sxs-lookup"><span data-stu-id="7618e-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Apply a sensitivity label to content automatically</a>
</span></span><td><span data-ttu-id="7618e-247"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7618e-248"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7618e-249"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-250"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-251"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-252"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-253"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7618e-254"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7618e-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="7618e-255"><sup>1</sup>구성된 경우 사용자에게 레이블 다운그레이드를 정당화하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="7618e-256">그러나 아직 관리자는 사유 데이터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="7618e-257">"관리자를 위한 레이블 분석 데이터 보내기" 기능이 지원 되는 경우 이 기능을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="7618e-258"><sup>2</sup>사용자가 권한을 할당하도록 허용은 현재 Windows 및 Mac용 Outlook에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="7618e-259">Word, Excel 및 PowerPoint의 사용 가능성은 TBD입니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="7618e-260"><sup>3</sup>2019년 4분기 예상</span><span class="sxs-lookup"><span data-stu-id="7618e-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="7618e-261">콘텐츠에 민감도 레이블이 지정된 후 콘텐츠 표시 또는 암호화가 적용되는 시점은 언제인가요?</span><span class="sxs-lookup"><span data-stu-id="7618e-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="7618e-262">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="7618e-262">Application</span></span> | <span data-ttu-id="7618e-263">콘텐츠 표시</span><span class="sxs-lookup"><span data-stu-id="7618e-263">Content marking</span></span> | <span data-ttu-id="7618e-264">암호화</span><span class="sxs-lookup"><span data-stu-id="7618e-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="7618e-265">모든 플랫폼의 Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7618e-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="7618e-266">즉시</span><span class="sxs-lookup"><span data-stu-id="7618e-266">Immediately</span></span> | <span data-ttu-id="7618e-267">즉시</span><span class="sxs-lookup"><span data-stu-id="7618e-267">Immediately</span></span> |
| <span data-ttu-id="7618e-268">PC 및 Mac용 Outlook</span><span class="sxs-lookup"><span data-stu-id="7618e-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="7618e-269">Exchange Online에서 전자 메일을 보낸 후</span><span class="sxs-lookup"><span data-stu-id="7618e-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="7618e-270">즉시</span><span class="sxs-lookup"><span data-stu-id="7618e-270">Immediately</span></span> |
| <span data-ttu-id="7618e-271">Mac, iOS 및 Android용 Outlook</span><span class="sxs-lookup"><span data-stu-id="7618e-271">Outlook on the web, iOS, and Android</span></span> | <span data-ttu-id="7618e-272">Exchange Online에서 전자 메일을 보낸 후</span><span class="sxs-lookup"><span data-stu-id="7618e-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="7618e-273">Exchange Online에서 전자 메일을 보낸 후</span><span class="sxs-lookup"><span data-stu-id="7618e-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="7618e-274">Windows용 Office에서 민감도 레이블을 Azure Information Protection 클라이언트와 함께 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7618e-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="7618e-275">아니요.</span><span class="sxs-lookup"><span data-stu-id="7618e-275">No.</span></span> <span data-ttu-id="7618e-276">Windows용 Office에서 Azure Information Protection 클라이언트를 로드하면 민감도 레이블이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="7618e-277">Azure Information Protection 클라이언트가 설치되어있지만 대신 민감도 레이블을 사용하려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="7618e-278"> *\*Office에서 민감도 기능을 사용하여 민감도 레이블을 적용하고 보도록** 그룹 정책 설정을 구성합니다. 이 설정은 *\*사용자 구성/관리 템플릿/Microsoft Office 2016/보안 설정*\*에 있습니다. </span><span class="sxs-lookup"><span data-stu-id="7618e-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="7618e-279">참고: 이 설정은 기존 그룹 정책 배포 메커니즘 또는 [Office 클라우드 정책 서비스](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)를 통해 배포될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="7618e-280">또는 Azure Information Protection 클라이언트를 제거하거나  [사용지 않도록](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="7618e-281">모든 Office 응용 프로그램을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="7618e-282">Office 2016 또는 Office 2019와 같은 비구독 버전의 Office에서 민감도 레이블이 지원되나요?</span><span class="sxs-lookup"><span data-stu-id="7618e-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="7618e-283">아니요.</span><span class="sxs-lookup"><span data-stu-id="7618e-283">No.</span></span> <span data-ttu-id="7618e-284">민감도 레이블은 Office 365 구독에서만 지원되고 비구독 버전에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="7618e-285">그러나 Azure Information Protection 통합 레이블 클라이언트는 비등록 버전의 Office에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="7618e-286">민감도 레이블을 설정하기 전에 이전에 보호 템플릿을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="7618e-287">어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="7618e-287">Where did they go?</span></span>

<span data-ttu-id="7618e-288">관리자 정의 [보호 템플릿](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)은 민감도 레이블이 사용되는 경우 암호화가 설정된 민감도 레이블과 중복되므로 Office 사용자 환경에서 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="7618e-289">파일 또는 전자 메일에 분류가 여러 개 있을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7618e-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="7618e-290">아니요.</span><span class="sxs-lookup"><span data-stu-id="7618e-290">No.</span></span> <span data-ttu-id="7618e-291">사용자는 각 문서 또는 전자 메일에 대해 한 번에 하나의 레이블만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-291">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="7618e-292">전자 메일에 레이블을 지정하면 모든 첨부 파일에 자동으로 같은 레이블이 지정되나요?</span><span class="sxs-lookup"><span data-stu-id="7618e-292">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="7618e-293">아니요.</span><span class="sxs-lookup"><span data-stu-id="7618e-293">No.</span></span> <span data-ttu-id="7618e-294">첨부 파일이 포함된 전자 메일 메시지에 레이블을 지정하는 경우 해당 첨부 파일은 같은 레이블을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-294">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="7618e-295">첨부 파일은 레이블이 없는 상태로 유지되거나 따로 적용된 레이블이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-295">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="7618e-296">그러나 전자 메일에 대한 레이블이 보호를 적용하는 경우 해당 보호는 Office 첨부 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7618e-296">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7618e-297">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="7618e-297">Additional resources</span></span>

[<span data-ttu-id="7618e-298">Azure Information Protection의 분류 및 레이블링에 대한 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="7618e-298">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="7618e-299">Office 내의 문서 및 전자 메일에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="7618e-299">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
