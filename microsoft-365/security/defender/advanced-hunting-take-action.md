---
title: Defender에서 고급 헌팅 쿼리 결과에 Microsoft 365 수행
description: 고급 헌팅 쿼리 결과에서 위협 및 영향을 받는 자산을 빠르게 해결
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 작업 수행
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952611"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="d4663-104">고급 헌팅 쿼리 결과에 대한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="d4663-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4663-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d4663-105">**Applies to:**</span></span>
- <span data-ttu-id="d4663-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4663-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d4663-107">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d4663-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d4663-108">강력하고 포괄적인 작업 옵션을 사용하여 고급 헌팅에서 발견한 위협을 빠르게 포함하거나 손상된 자산을 해결할 수 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d4663-108">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="d4663-109">이러한 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-109">With these options, you can:</span></span>

- <span data-ttu-id="d4663-110">디바이스에서 다양한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="d4663-110">Take various actions on devices</span></span>
- <span data-ttu-id="d4663-111">파일 Quarantine files</span><span class="sxs-lookup"><span data-stu-id="d4663-111">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="d4663-112">필수 권한</span><span class="sxs-lookup"><span data-stu-id="d4663-112">Required permissions</span></span>
<span data-ttu-id="d4663-113">고급 헌팅을 통해 조치를 취하려면 장치에서 수정 작업을 제출할 수 있는 권한이 있는 끝점용 Microsoft [Defender의 역할이 필요합니다.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="d4663-113">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="d4663-114">조치를 취할 수 없는 경우 전역 관리자에게 문의하여 다음 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-114">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="d4663-115">*위협 및 > 조치 취약성 관리 - 수정 처리*</span><span class="sxs-lookup"><span data-stu-id="d4663-115">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="d4663-116">디바이스에서 다양한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="d4663-116">Take various actions on devices</span></span>
<span data-ttu-id="d4663-117">쿼리 결과의 열로 식별된 장치에 대해 다음 `DeviceId` 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-117">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="d4663-118">감염을 포함하거나 공격이 후방으로 이동하지 않도록 영향을 받는 장치를 격리</span><span class="sxs-lookup"><span data-stu-id="d4663-118">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="d4663-119">조사 패키지를 수집하여 추가 포렌식 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="d4663-119">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="d4663-120">바이러스 백신 검사 실행을 통해 최신 보안 인텔리전스 업데이트를 사용하여 위협 찾기 및 제거</span><span class="sxs-lookup"><span data-stu-id="d4663-120">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="d4663-121">자동화된 조사를 시작하여 장치 및 기타 영향을 받는 장치에 대한 위협을 확인하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-121">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="d4663-122">앱 실행을 Microsoft 서명된 실행 파일로만 제한하여 맬웨어 또는 기타 트러블되지 않은 실행 파일을 통한 후속 위협 활동 방지</span><span class="sxs-lookup"><span data-stu-id="d4663-122">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="d4663-123">끝점용 Microsoft Defender를 통해 이러한 응답 작업이 수행되는 방법에 대한 자세한 내용은 장치의 응답 [작업에 대해 읽어 보아야 합니다.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="d4663-123">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="d4663-124">파일 Quarantine files</span><span class="sxs-lookup"><span data-stu-id="d4663-124">Quarantine files</span></span>
<span data-ttu-id="d4663-125">발생할 때  자동으로 검리될 수 있도록 파일에 대한 검지 작업을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-125">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="d4663-126">이 작업을 선택할 때 다음 열 중 선택하여 쿼리 결과에서 검사할 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-126">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="d4663-127">`SHA1` - 대부분의 고급 헌팅 테이블에서 기록된 작업의 영향을 받은 파일의 SHA-1입니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-127">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="d4663-128">예를 들어 파일을 복사한 경우 복사된 파일이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-128">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="d4663-129">`InitiatingProcessSHA1` — 대부분의 고급 헌팅 테이블에서 이 파일은 기록된 작업을 시작하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-129">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="d4663-130">예를 들어 자식 프로세스가 시작된 경우 이는 상위 프로세스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-130">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="d4663-131">`SHA256` — 열로 식별된 파일의 SHA-256에 해당하는 `SHA1` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-131">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="d4663-132">`InitiatingProcessSHA256` — 열로 식별된 파일의 SHA-256에 해당하는 `InitiatingProcessSHA1` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-132">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="d4663-133">검사 작업을 수행 하는 방법 및 파일을 복원 하는 방법에 대 한 자세한 내용은 파일에 대 한 [응답 작업에 대 한 읽기.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)</span><span class="sxs-lookup"><span data-stu-id="d4663-133">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="d4663-134">파일을 찾아서 이를 검지하려면 쿼리 결과에 장치 식별자 `DeviceId` 값도 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-134">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="d4663-135">작업 수행</span><span class="sxs-lookup"><span data-stu-id="d4663-135">Take action</span></span>
<span data-ttu-id="d4663-136">설명된 작업을 수행하려면 쿼리 결과에서 하나 이상의 레코드를 선택한 다음 작업 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d4663-136">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="d4663-137">마법사가 기본 작업을 선택한 다음 제출하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-137">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![레코드를 검사하기 위한 패널이 있는 선택한 레코드의 이미지](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="d4663-139">수행한 작업 검토</span><span class="sxs-lookup"><span data-stu-id="d4663-139">Review actions taken</span></span>
<span data-ttu-id="d4663-140">각 작업은 각각 동작 센터 [](m365d-action-center.md) 기록( 또는 )의 security.microsoft.com/action-center/history  >   기록됩니다.[](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="d4663-140">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="d4663-141">작업 센터로 이동하여 각 작업의 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-141">Go to the action center to check the status of each action.</span></span>
 
>[!NOTE]
><span data-ttu-id="d4663-142">이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-142">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d4663-143">[Defender를 Microsoft 365 더](m365d-enable.md) 많은 데이터 원본을 사용하여 위협을 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-143">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="d4663-144">Endpoint용 Microsoft Defender에서 고급 헌팅 Microsoft 365 마이그레이션의 단계에 따라 [Endpoint용 Microsoft Defender에서](advanced-hunting-migrate-from-mde.md)고급 헌팅 워크플로를 Microsoft 365 Defender로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4663-144">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d4663-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d4663-145">Related topics</span></span>
- [<span data-ttu-id="d4663-146">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="d4663-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d4663-147">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="d4663-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d4663-148">쿼리 결과로 작업</span><span class="sxs-lookup"><span data-stu-id="d4663-148">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d4663-149">스키마에 대한 이해</span><span class="sxs-lookup"><span data-stu-id="d4663-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d4663-150">Action Center 개요</span><span class="sxs-lookup"><span data-stu-id="d4663-150">Action center overview</span></span>](m365d-action-center.md)
