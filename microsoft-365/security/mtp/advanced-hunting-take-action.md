---
title: Microsoft Threat Protection의 고급 구하기 쿼리 결과에 대해 작업 수행
description: 고급 구하기 쿼리 결과에서 위협과 영향을 받는 자산에 빠르게 주소 만들기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, search, query, 원격 분석, 작업 수행
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7250feffa69cc1a6cc37908a599dff0fab6c5e6c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429659"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="794c8-104">고급 구하기 쿼리 결과에 대해 작업 수행</span><span class="sxs-lookup"><span data-stu-id="794c8-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="794c8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="794c8-105">**Applies to:**</span></span>
- <span data-ttu-id="794c8-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="794c8-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="794c8-107">강력 하 고 종합적인 작업 옵션을 사용 하 여 [고급 구하기](advanced-hunting-overview.md) 에서 찾은 위협과 공격에 노출 된 자산을 빠르게 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="794c8-108">이러한 옵션을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-108">With these options, you can:</span></span>

- <span data-ttu-id="794c8-109">장치에서 다양 한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="794c8-109">Take various actions on devices</span></span>
- <span data-ttu-id="794c8-110">파일 격리</span><span class="sxs-lookup"><span data-stu-id="794c8-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="794c8-111">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="794c8-111">Required permissions</span></span>
<span data-ttu-id="794c8-112">고급 구하기를 통해 조치를 취할 수 있으려면 [장치에 대 한 재구성 작업을 제출할](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)수 있는 권한이 있는 MICROSOFT Defender ATP 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="794c8-113">작업을 수행할 수 없는 경우 전역 관리자에 게 다음 사용 권한을 부여 하는 것에 대해 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="794c8-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="794c8-114">*활성 수정 작업 > 위협 및 취약성 관리-업데이트 관리 처리*</span><span class="sxs-lookup"><span data-stu-id="794c8-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="794c8-115">장치에서 다양 한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="794c8-115">Take various actions on devices</span></span>
<span data-ttu-id="794c8-116">쿼리 결과에서 열로 식별 되는 장치에 대해 다음 작업을 수행할 수 있습니다 `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="794c8-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="794c8-117">영향을 받는 장치를 감염을 포함 하거나 공격을 이동 하지 못하도록 차단 laterally</span><span class="sxs-lookup"><span data-stu-id="794c8-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="794c8-118">자세한 법적 정보를 얻기 위한 조사 패키지 수집</span><span class="sxs-lookup"><span data-stu-id="794c8-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="794c8-119">최신 보안 인텔리전스 업데이트를 사용 하 여 위협 검색 및 제거를 위한 바이러스 검사 실행</span><span class="sxs-lookup"><span data-stu-id="794c8-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="794c8-120">장치 및 기타 영향을 받는 장치에서 위협을 확인 하 고 수정 하는 자동화 된 조사 시작</span><span class="sxs-lookup"><span data-stu-id="794c8-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="794c8-121">앱 실행을 Microsoft 서명 된 실행 파일로 제한 하 여 맬웨어 또는 기타 신뢰할 수 없는 실행 파일을 통한 위협 작업을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="794c8-122">이러한 응답 작업을 Microsoft Defender ATP를 통해 수행 하는 방법에 대 한 자세한 내용은 [장치에 대 한 응답 작업 정보를 참조](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)하세요.</span><span class="sxs-lookup"><span data-stu-id="794c8-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="794c8-123">파일 격리</span><span class="sxs-lookup"><span data-stu-id="794c8-123">Quarantine files</span></span>
<span data-ttu-id="794c8-124">파일에 *격리* 작업을 배포 하 여 오류가 발생 하면 자동으로 격리 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="794c8-125">이 작업을 선택할 때 다음 열 중에서 선택 하 여 쿼리 결과에서 격리 될 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="794c8-126">`SHA1` — 대부분의 고급 구하기 테이블에서이는 기록 된 작업의 영향을 받은 파일의 SHA-1입니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="794c8-127">예를 들어 파일을 복사한 경우 복사한 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="794c8-128">`InitiatingProcessSHA1` — 대부분의 고급 구하기 테이블에서 기록 된 작업 시작을 담당 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="794c8-129">예를 들어 하위 프로세스가 시작 된 경우 상위 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="794c8-130">`SHA256` -열로 식별 되는 파일에 해당 하는 SHA-256입니다 `SHA1` .</span><span class="sxs-lookup"><span data-stu-id="794c8-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="794c8-131">`InitiatingProcessSHA256` -열로 식별 되는 파일에 해당 하는 SHA-256입니다 `InitiatingProcessSHA1` .</span><span class="sxs-lookup"><span data-stu-id="794c8-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="794c8-132">격리 작업을 수행 하는 방법과 파일을 복원 하는 방법에 대 한 자세한 내용은 [파일에 대 한 응답 작업 정보를 참조](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)하세요.</span><span class="sxs-lookup"><span data-stu-id="794c8-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="794c8-133">파일을 찾아 격리 하기 위해 쿼리 결과에 `DeviceId` 장치 식별자로 값도 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="794c8-134">작업 수행</span><span class="sxs-lookup"><span data-stu-id="794c8-134">Take action</span></span>
<span data-ttu-id="794c8-135">설명 된 작업을 수행 하려면 쿼리 결과에서 하나 이상의 레코드를 선택 하 고 **작업 수행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="794c8-136">마법사는 원하는 작업을 선택 하 여 전송 하는 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![레코드를 검사 하기 위한 패널이 있는 선택한 레코드의 이미지](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="794c8-138">수행한 작업 검토</span><span class="sxs-lookup"><span data-stu-id="794c8-138">Review actions taken</span></span>
<span data-ttu-id="794c8-139">각 작업은 action **center** [action center](mtp-action-center.md)  >  **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history))의 작업 센터에 개별적으로 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="794c8-140">작업 센터로 이동 하 여 각 작업의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="794c8-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="794c8-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="794c8-141">Related topics</span></span>
- [<span data-ttu-id="794c8-142">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="794c8-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="794c8-143">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="794c8-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="794c8-144">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="794c8-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="794c8-145">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="794c8-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="794c8-146">알림 센터 개요</span><span class="sxs-lookup"><span data-stu-id="794c8-146">Action center overview</span></span>](mtp-action-center.md)
