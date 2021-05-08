---
title: 검사에 대한 제외 Microsoft Defender 바이러스 백신 설정
description: 파일(지정된 프로세스에서 수정한 파일 포함) 및 폴더가 해당 폴더에서 검색되지 Microsoft Defender 바이러스 백신. PowerShell을 사용하여 제외의 유효성을 검사합니다.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275123"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="8ba3a-104">검사에 대한 제외 Microsoft Defender 바이러스 백신 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8ba3a-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8ba3a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8ba3a-105">**Applies to:**</span></span>

- [<span data-ttu-id="8ba3a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ba3a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8ba3a-107">특정 파일, 폴더, 프로세스 및 프로세스에서 연 파일은 검사에서 제외할 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="8ba3a-108">이러한 제외는 예약된 [검사,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)요구 [](run-scan-microsoft-defender-antivirus.md)시 검사 및 항상 실시간 보호 및 모니터링에 [적용됩니다.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8ba3a-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="8ba3a-109">처리된 파일에 대한 제외는 실시간 보호에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="8ba3a-110">제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8ba3a-110">Configure and validate exclusions</span></span>

<span data-ttu-id="8ba3a-111">제외를 구성하고 유효성을 검사하기 위해 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="8ba3a-112">파일 이름, 확장명 및 폴더 위치에 따라 제외를 [구성하고 유효성을 검사합니다.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8ba3a-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="8ba3a-113">파일 확장명Microsoft Defender 바이러스 백신 이름 또는 위치에 따라 파일 검색에서 파일을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="8ba3a-114">프로세스에서 연 파일에 대한 제외를 [구성하고 유효성을 검사합니다.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8ba3a-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="8ba3a-115">특정 프로세스에서 연 검사에서 파일을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="8ba3a-116">권장 사항 정의하는 데 사용할 수 있는 예</span><span class="sxs-lookup"><span data-stu-id="8ba3a-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ba3a-117">Microsoft Defender 바이러스 백신 운영 체제 동작 및 일반적인 관리 파일(예: 엔터프라이즈 관리, 데이터베이스 관리 및 기타 엔터프라이즈 시나리오 및 상황에 사용되는 파일)을 기반으로 하는 많은 자동 제외가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="8ba3a-118">제외를 정의하면 제외가 제공하는 보호가 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="8ba3a-119">제외 구현과 관련된 위험을 항상 평가해야 합니다. 또한 악의적이지 않다고 확신하는 파일만 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="8ba3a-120">제외를 정의할 때 다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="8ba3a-121">제외는 기술적으로 보호 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="8ba3a-122">제외를 정의할 때 항상 완화를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="8ba3a-123">다른 완화는 제외된 위치에 적절한 ACL(액세스 제어 목록), 감사 정책, 최신 소프트웨어 등을 통해 처리하도록 하는 것만큼 간단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="8ba3a-124">제외를 주기적으로 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-124">Review the exclusions periodically.</span></span> <span data-ttu-id="8ba3a-125">검토 프로세스의 일부로 완화를 다시 검토하고 다시 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="8ba3a-126">사전 예방적이면 제외를 정의하지 않는 것이 가장 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="8ba3a-127">예를 들어 향후에는 문제가 될 수 있기 때문에 제외하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="8ba3a-128">제외를 완화할 수 있는 성능 또는 응용 프로그램 호환성과 관련한 문제와 같은 특정 문제에만 제외를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="8ba3a-129">제외 목록 변경 내용을 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="8ba3a-130">보안 관리자는 특정 제외가 추가된 이유와 관련한 충분한 컨텍스트를 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="8ba3a-131">특정 경로가 제외된 이유에 대한 특정 이유에 대한 답변을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ba3a-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8ba3a-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="8ba3a-132">Related articles</span></span>

- [<span data-ttu-id="8ba3a-133">Microsoft Defender 바이러스 백신 제외 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8ba3a-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8ba3a-134">제외 정의 시 피해야 하는 일반적인 실수</span><span class="sxs-lookup"><span data-stu-id="8ba3a-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
