---
title: Microsoft Defender AV 검사에 대한 제외 설정
description: 파일(지정된 프로세스에서 수정한 파일 포함) 및 폴더를 Microsoft Defender AV에서 검사하지 못하게 제외할 수 있습니다. PowerShell을 사용하여 제외의 유효성을 검사합니다.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691505"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="4913c-104">Microsoft Defender 바이러스 백신 검사에 대한 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4913c-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4913c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4913c-105">**Applies to:**</span></span>

- <span data-ttu-id="4913c-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="4913c-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="4913c-107">Microsoft Defender 바이러스 백신 검사에서 특정 파일, 폴더, 프로세스 및 프로세스에서 연 파일을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="4913c-108">이러한 제외는 예약된 [검사,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)요구 [](run-scan-microsoft-defender-antivirus.md)시 검사 및 항상 실시간 보호 및 모니터링에 [적용됩니다.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4913c-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="4913c-109">처리된 파일에 대한 제외는 실시간 보호에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="4913c-110">제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4913c-110">Configure and validate exclusions</span></span>

<span data-ttu-id="4913c-111">제외를 구성하고 유효성을 검사하기 위해 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="4913c-112">파일 이름, 확장명 및 폴더 위치에 따라 제외를 [구성하고 유효성을 검사합니다.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4913c-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="4913c-113">이렇게 하면 파일 확장명, 파일 이름 또는 위치에 따라 Microsoft Defender 바이러스 백신 검사에서 파일을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="4913c-114">프로세스에서 연 파일에 대한 제외를 [구성하고 유효성을 검사합니다.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4913c-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="4913c-115">이렇게 하면 특정 프로세스에서 연 검사에서 파일을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="4913c-116">제외를 정의하기 위한 권장 사항</span><span class="sxs-lookup"><span data-stu-id="4913c-116">Recommendations for defining exclusions</span></span>

<span data-ttu-id="4913c-117">제외를 정의할 경우 Microsoft Defender 바이러스 백신에서 제공하는 보호가 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-117">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="4913c-118">제외 구현과 관련된 위험을 항상 평가해야 합니다. 또한 악의적이지 않다고 확신하는 파일만 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="4913c-119">다음은 제외를 정의할 때 유의해야 하는 권장 사항 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-119">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="4913c-120">제외는 기술적으로 보호 간격입니다. 제외를 정의할 때 항상 추가 완화를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-120">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="4913c-121">추가 완화는 제외된 위치에 적절한 ACL(액세스 제어 목록), 감사 정책, 최신 소프트웨어 등을 통해 처리하도록 하는 것만큼 간단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-121">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="4913c-122">제외를 주기적으로 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-122">Review the exclusions periodically.</span></span> <span data-ttu-id="4913c-123">검토 프로세스의 일부로 완화를 다시 확인하고 다시 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-123">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="4913c-124">사전 제외를 정의하지 않는 것이 가장 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-124">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="4913c-125">예를 들어 향후에는 문제가 될 수 있기 때문에 제외하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-125">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="4913c-126">성능 관련 문제 또는 제외가 완화될 수 있는 응용 프로그램 호환성과 관련한 특정 문제에만 제외를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="4913c-126">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="4913c-127">제외 목록 변경 내용을 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-127">Audit the exclusion list changes.</span></span> <span data-ttu-id="4913c-128">보안 관리자는 특정 제외가 추가된 이유와 관련한 충분한 컨텍스트를 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-128">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="4913c-129">특정 경로가 제외된 이유에 대한 특정 이유에 대한 답변을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4913c-129">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4913c-130">관련 문서</span><span class="sxs-lookup"><span data-stu-id="4913c-130">Related articles</span></span>

- [<span data-ttu-id="4913c-131">Windows Server 2016에서 Microsoft Defender 바이러스 백신 제외</span><span class="sxs-lookup"><span data-stu-id="4913c-131">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4913c-132">제외를 정의할 때 피해야 하는 일반적인 실수</span><span class="sxs-lookup"><span data-stu-id="4913c-132">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)