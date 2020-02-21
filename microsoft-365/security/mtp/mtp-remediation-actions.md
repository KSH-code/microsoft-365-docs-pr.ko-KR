---
title: Microsoft Threat Protection의 자동화 된 조사 및 응답 기능의 수정 작업
description: Microsoft Threat Protection의 자동화된 조사 및 대응 기능에 대한 개요를 확인하세요.
keywords: 자동화된, 조사, 경고, 트리거, 작업, 수정
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175951"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="5212d-104">Microsoft Threat Protection의 자동화 된 조사 및 응답 기능의 수정 작업</span><span class="sxs-lookup"><span data-stu-id="5212d-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="5212d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5212d-105">**Applies to:**</span></span>
- <span data-ttu-id="5212d-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="5212d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5212d-107">Microsoft Threat Protection의 자동화 된 조사 및 응답 기능은 특정 수정 작업을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5212d-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="5212d-108">일부 유형의 재구성 작업은 끝점이 라고도 하는 장치에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5212d-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="5212d-109">전자 메일 콘텐츠에 대 한 기타 수정 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5212d-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="5212d-110">다음 표에서는 현재 Microsoft Threat Protection에서 지원 되는 수정 작업을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5212d-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="5212d-111">끝점 수정 작업</span><span class="sxs-lookup"><span data-stu-id="5212d-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="5212d-112">전자 메일 수정 작업</span><span class="sxs-lookup"><span data-stu-id="5212d-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="5212d-113">파일 격리</span><span class="sxs-lookup"><span data-stu-id="5212d-113">Quarantine file</span></span><br/><span data-ttu-id="5212d-114">레지스트리 키 추가</span><span class="sxs-lookup"><span data-stu-id="5212d-114">Remove registry key</span></span><br/><span data-ttu-id="5212d-115">프로세스 중단</span><span class="sxs-lookup"><span data-stu-id="5212d-115">Kill process</span></span> <br/><span data-ttu-id="5212d-116">서비스 중지</span><span class="sxs-lookup"><span data-stu-id="5212d-116">Stop service</span></span> <br/><span data-ttu-id="5212d-117">레지스트리 키 추가</span><span class="sxs-lookup"><span data-stu-id="5212d-117">Remove registry key</span></span> <br/><span data-ttu-id="5212d-118">드라이버 해제</span><span class="sxs-lookup"><span data-stu-id="5212d-118">Disable driver</span></span> <br/><span data-ttu-id="5212d-119">예약된 작업 제거</span><span class="sxs-lookup"><span data-stu-id="5212d-119">Remove scheduled task</span></span>      |<span data-ttu-id="5212d-120">전자 메일 메시지 또는 클러스터의 일시 삭제</span><span class="sxs-lookup"><span data-stu-id="5212d-120">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="5212d-121">차단 URL(클릭 시간)</span><span class="sxs-lookup"><span data-stu-id="5212d-121">Block URL (time-of-click)</span></span><br/><span data-ttu-id="5212d-122">외부 메일 전달 해제</span><span class="sxs-lookup"><span data-stu-id="5212d-122">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="5212d-123">승인 보류 중 이거나 이미 완료 되었는지 여부에 관계 없이 수정 작업은 [알림 센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5212d-123">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5212d-124">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5212d-124">Next steps</span></span>

- [<span data-ttu-id="5212d-125">자동화된 조사 및 대응과 관련된 조치 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="5212d-125">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="5212d-126">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="5212d-126">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
