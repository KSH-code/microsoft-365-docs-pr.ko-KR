---
title: Microsoft Threat Protection에서 고급 헌팅 쿼리 결과에 대한 작업 수행
description: 고급 헌팅 쿼리 결과에서 위협 및 영향을 받는 자산을 빠르게 해결
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, 시간 제한 방지, 명령줄, 프로세스 ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075452"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="48867-104">고급 헌팅 쿼리 결과에 대한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="48867-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="48867-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="48867-105">**Applies to:**</span></span>
- [<span data-ttu-id="48867-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="48867-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="48867-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="48867-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48867-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="48867-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="48867-109">강력하고 포괄적인 작업 옵션을 사용하여 고급 헌팅에서 발견한 위협을 빠르게 포함하거나 손상된 자산을 해결할 수 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="48867-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="48867-110">이러한 옵션을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48867-110">With these options, you can:</span></span>

- <span data-ttu-id="48867-111">디바이스에서 다양한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="48867-111">Take various actions on devices</span></span>
- <span data-ttu-id="48867-112">파일 Quarantine files</span><span class="sxs-lookup"><span data-stu-id="48867-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="48867-113">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="48867-113">Required permissions</span></span>

<span data-ttu-id="48867-114">고급 헌팅을 통해 조치를 취하려면 장치에서 수정 작업을 제출할 수 있는 권한이 있는 끝점용 Defender의 역할이 [필요합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="48867-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="48867-115">조치를 취할 수 없는 경우 전역 관리자에게 문의하여 다음 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="48867-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="48867-116">*위협 및 > 관리에 대한 활성 수정 작업 - 수정 처리*</span><span class="sxs-lookup"><span data-stu-id="48867-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="48867-117">디바이스에서 다양한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="48867-117">Take various actions on devices</span></span>

<span data-ttu-id="48867-118">쿼리 결과의 열로 식별된 장치에 대해 다음 `DeviceId` 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48867-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="48867-119">감염을 포함하거나 공격이 후방으로 이동하지 않도록 영향을 받는 장치를 격리</span><span class="sxs-lookup"><span data-stu-id="48867-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="48867-120">조사 패키지를 수집하여 추가 포렌식 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="48867-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="48867-121">바이러스 백신 검사 실행을 통해 최신 보안 인텔리전스 업데이트를 사용하여 위협 찾기 및 제거</span><span class="sxs-lookup"><span data-stu-id="48867-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="48867-122">자동화된 조사를 시작하여 장치 및 기타 영향을 받는 장치에 대한 위협을 확인하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="48867-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="48867-123">앱 실행을 Microsoft 서명된 실행 파일로만 제한하여 맬웨어 또는 기타 트러블되지 않은 실행 파일을 통한 후속 위협 활동 방지</span><span class="sxs-lookup"><span data-stu-id="48867-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="48867-124">끝점용 Defender를 통해 이러한 응답 작업이 수행되는 방법에 대한 자세한 내용은 장치의 응답 [작업에 대해 읽어 보아야 합니다.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="48867-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="48867-125">파일 Quarantine files</span><span class="sxs-lookup"><span data-stu-id="48867-125">Quarantine files</span></span>

<span data-ttu-id="48867-126">발생할 때  자동으로 검리될 수 있도록 파일에 대한 검지 작업을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48867-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="48867-127">이 작업을 선택할 때 다음 열 중 선택하여 쿼리 결과에서 검사할 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48867-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="48867-128">`SHA1` - 대부분의 고급 헌팅 테이블에서 기록된 작업의 영향을 받은 파일의 SHA-1입니다.</span><span class="sxs-lookup"><span data-stu-id="48867-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="48867-129">예를 들어 파일을 복사한 경우 복사된 파일이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48867-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="48867-130">`InitiatingProcessSHA1` — 대부분의 고급 헌팅 테이블에서 이 파일은 기록된 작업을 시작하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48867-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="48867-131">예를 들어 자식 프로세스가 시작된 경우 이는 상위 프로세스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48867-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="48867-132">`SHA256` — 열로 식별된 파일의 SHA-256에 해당하는 `SHA1` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="48867-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="48867-133">`InitiatingProcessSHA256` — 열로 식별된 파일의 SHA-256에 해당하는 `InitiatingProcessSHA1` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="48867-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="48867-134">검사 작업을 수행 하는 방법 및 파일을 복원 하는 방법에 대 한 자세한 내용은 파일에 대 한 [응답 작업에 대 한 읽기.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="48867-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="48867-135">파일을 찾아서 이를 검지하려면 쿼리 결과에 장치 식별자 `DeviceId` 값도 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48867-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="48867-136">작업 수행</span><span class="sxs-lookup"><span data-stu-id="48867-136">Take action</span></span>

<span data-ttu-id="48867-137">설명된 작업을 수행하려면 쿼리 결과에서 하나 이상의 레코드를 선택한 다음 작업 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="48867-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="48867-138">마법사가 기본 작업을 선택한 다음 제출하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="48867-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![레코드를 검사하기 위한 패널이 있는 선택한 레코드의 이미지](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="48867-140">수행한 작업 검토</span><span class="sxs-lookup"><span data-stu-id="48867-140">Review actions taken</span></span>

<span data-ttu-id="48867-141">각 작업은 각 작업 센터의 작업 센터 기록( 또는  >   [)에 security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="48867-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="48867-142">작업 센터로 이동하여 각 작업의 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="48867-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="48867-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="48867-143">Related topics</span></span>

- [<span data-ttu-id="48867-144">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="48867-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="48867-145">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="48867-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="48867-146">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="48867-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="48867-147">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="48867-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="48867-148">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="48867-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="48867-149">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="48867-149">Custom detections overview</span></span>](overview-custom-detections.md)
