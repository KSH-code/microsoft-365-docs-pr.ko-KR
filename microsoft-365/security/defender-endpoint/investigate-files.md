---
title: 끝점 파일에 대한 Microsoft Defender 조사
description: 조사 옵션을 사용하여 경고, 동작 또는 이벤트와 관련된 파일에 대한 세부 정보를 얻을 수 있습니다.
keywords: 조사, 조사, 파일, 악의적인 활동, 공격 동기 부여, 심층 분석, 심층 분석 보고서
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a801b6153cf3f273290721756440cfe974103e92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072607"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="ffeca-104">끝점 경고에 대한 Microsoft Defender와 관련된 파일 조사</span><span class="sxs-lookup"><span data-stu-id="ffeca-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ffeca-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ffeca-105">**Applies to:**</span></span>
- [<span data-ttu-id="ffeca-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ffeca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ffeca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffeca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="ffeca-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ffeca-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ffeca-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="ffeca-110">특정 경고, 동작 또는 이벤트와 관련된 파일의 세부 정보를 조사하여 파일에 악의적인 활동이 있는지 확인하고 공격 동기를 식별하고 잠재적인 위반 범위를 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="ffeca-111">특정 파일의 자세한 프로필 페이지에 액세스하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="ffeca-112">예를 들어 검색 기능을 사용하여 경고 프로세스 **트리,** 인시던트 **그래프,** 아티팩트 타임라인의 링크를 클릭하거나 장치 타임라인 에 나열된 이벤트를 선택할 **수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="ffeca-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="ffeca-113">자세한 프로필 페이지에서 새 파일 페이지를 전환하여 새 페이지 레이아웃과 이전 페이지 레이아웃 간에 전환할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="ffeca-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="ffeca-114">이 문서의 나머지에서는 새로운 페이지 레이아웃에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="ffeca-115">파일 보기의 다음 섹션에서 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="ffeca-116">파일 세부 정보, 맬웨어 검색, 파일 보전</span><span class="sxs-lookup"><span data-stu-id="ffeca-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="ffeca-117">심층 분석</span><span class="sxs-lookup"><span data-stu-id="ffeca-117">Deep analysis</span></span>
- <span data-ttu-id="ffeca-118">경고</span><span class="sxs-lookup"><span data-stu-id="ffeca-118">Alerts</span></span>
- <span data-ttu-id="ffeca-119">조직에서 관찰</span><span class="sxs-lookup"><span data-stu-id="ffeca-119">Observed in organization</span></span>
- <span data-ttu-id="ffeca-120">심층 분석</span><span class="sxs-lookup"><span data-stu-id="ffeca-120">Deep analysis</span></span>
- <span data-ttu-id="ffeca-121">파일 이름</span><span class="sxs-lookup"><span data-stu-id="ffeca-121">File names</span></span>

<span data-ttu-id="ffeca-122">이 페이지에서 파일에 대한 작업을 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="ffeca-123">파일 작업</span><span class="sxs-lookup"><span data-stu-id="ffeca-123">File actions</span></span>

<span data-ttu-id="ffeca-124">프로필 페이지 위쪽의 파일 정보 카드 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="ffeca-125">여기에 수행할 수 있는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="ffeca-126">중지 및 검사</span><span class="sxs-lookup"><span data-stu-id="ffeca-126">Stop and quarantine</span></span>
- <span data-ttu-id="ffeca-127">표시기 추가/편집</span><span class="sxs-lookup"><span data-stu-id="ffeca-127">Add/edit indicator</span></span>
- <span data-ttu-id="ffeca-128">파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="ffeca-128">Download file</span></span>
- <span data-ttu-id="ffeca-129">위협 전문가에게 문의</span><span class="sxs-lookup"><span data-stu-id="ffeca-129">Consult a threat expert</span></span>
- <span data-ttu-id="ffeca-130">작업 센터</span><span class="sxs-lookup"><span data-stu-id="ffeca-130">Action center</span></span>

<span data-ttu-id="ffeca-131">이러한 작업에 대한 자세한 내용은 파일에 대한 응답 [작업 수행을 참조하세요.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="ffeca-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="ffeca-132">파일 세부 정보, 맬웨어 검색 및 파일 보전</span><span class="sxs-lookup"><span data-stu-id="ffeca-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="ffeca-133">파일 세부 정보, 인시던트, 맬웨어 검색 및 파일 보전 카드에는 파일에 대한 다양한 특성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="ffeca-134">파일의 MD5, 바이러스 총 검색 비율, Microsoft Defender AV 검색(사용 가능한 경우) 및 파일의 보전과 같은 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="ffeca-135">파일 보전 카드는 파일이 조직 및 전 세계 디바이스에서 어디에서 표시 봤는가를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="ffeca-136">다른 사용자는 파일 보충 카드의 조직 섹션에 있는 디바이스에서 *서로* 다른 값을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="ffeca-137">이는 카드에 사용자가 있는 RBAC 범위에 따라 정보가 표시하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="ffeca-138">즉, 사용자에게 특정 장치 집합에 대한 표시 권한이 부여된 경우 해당 디바이스에 대한 파일 조직 보전만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![파일 정보의 이미지](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="ffeca-140">경고</span><span class="sxs-lookup"><span data-stu-id="ffeca-140">Alerts</span></span>

<span data-ttu-id="ffeca-141">경고 **탭은** 파일과 연결된 경고 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="ffeca-142">이 목록에는 장치 그룹(있는 경우)을 제외하고 경고 큐와 동일한 정보가 다수 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="ffeca-143">열 머리그 위에 있는 도구 모음에서 열 사용자 지정을 선택하여 표시되는 정보의 종류를 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="ffeca-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![파일 섹션과 관련된 경고 이미지](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="ffeca-145">조직에서 관찰</span><span class="sxs-lookup"><span data-stu-id="ffeca-145">Observed in organization</span></span>

<span data-ttu-id="ffeca-146">조직에서 **관찰 탭을** 사용하면 날짜 범위를 지정하여 파일로 관찰된 장치를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="ffeca-147">이 탭에는 최대 100대의 디바이스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="ffeca-148">파일이 _있는_ 모든 장치를 표시하려면 탭의 열 헤더 위에  있는 작업 메뉴에서 내보내기를 선택하여 탭을 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![파일이 있는 가장 최근에 관찰된 장치의 이미지](images/atp-observed-machines.png)

<span data-ttu-id="ffeca-150">슬라이더 또는 범위 선택기에서 파일 관련 이벤트를 확인할 기간을 빠르게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="ffeca-151">시간 창을 하루만큼 작게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="ffeca-152">이렇게 하면 해당 IP 주소와 통신한 파일만 볼 수 있으며 불필요한 스크롤 및 검색을 크게 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="ffeca-153">심층 분석</span><span class="sxs-lookup"><span data-stu-id="ffeca-153">Deep analysis</span></span>

<span data-ttu-id="ffeca-154">심층 **분석** 탭을 [](respond-file-alerts.md#deep-analysis)사용하면 파일을 심층 분석을 위해 제출하여 파일 동작에 대한 세부 정보 및 조직 내에서 파일에 어떤 영향을 미치고 있는지 쉽게 확인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="ffeca-155">파일을 제출한 후 결과를 사용할 수 있는 경우 심층 분석 보고서가 이 탭에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="ffeca-156">심층 분석에서 아무것도 찾지 못하면 보고서는 비어 있으며 결과 공간은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![심층 분석 탭의 이미지](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="ffeca-158">파일 이름</span><span class="sxs-lookup"><span data-stu-id="ffeca-158">File names</span></span>

<span data-ttu-id="ffeca-159">파일 **이름 탭에는** 조직 내에서 파일이 사용이 관찰된 모든 이름이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeca-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![파일 이름 탭의 이미지](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="ffeca-161">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ffeca-161">Related topics</span></span>

- [<span data-ttu-id="ffeca-162">끝점 큐에 대한 Microsoft Defender 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="ffeca-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="ffeca-163">끝점 경고에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="ffeca-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="ffeca-164">끝점 경고에 대한 Microsoft Defender 조사</span><span class="sxs-lookup"><span data-stu-id="ffeca-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="ffeca-165">Microsoft Defender for Endpoint Devices 목록에서 장치 조사</span><span class="sxs-lookup"><span data-stu-id="ffeca-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="ffeca-166">끝점 경고에 대한 Microsoft Defender와 연결된 IP 주소 조사</span><span class="sxs-lookup"><span data-stu-id="ffeca-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="ffeca-167">끝점 경고에 대한 Microsoft Defender와 연결된 도메인 조사</span><span class="sxs-lookup"><span data-stu-id="ffeca-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="ffeca-168">끝점용 Microsoft Defender에서 사용자 계정 조사</span><span class="sxs-lookup"><span data-stu-id="ffeca-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="ffeca-169">파일에 대한 응답 작업 수행</span><span class="sxs-lookup"><span data-stu-id="ffeca-169">Take response actions on a file</span></span>](respond-file-alerts.md)
