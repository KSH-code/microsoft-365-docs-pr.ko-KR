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
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225486"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="5e6c8-104">Microsoft Threat Protection의 자동화 된 조사 및 응답 기능의 수정 작업</span><span class="sxs-lookup"><span data-stu-id="5e6c8-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="5e6c8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5e6c8-105">**Applies to:**</span></span>
- <span data-ttu-id="5e6c8-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="5e6c8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5e6c8-107">Microsoft Threat Protection의 자동화 된 조사 및 응답 기능은 특정 수정 작업을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c8-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="5e6c8-108">일부 유형의 재구성 작업은 끝점이 라고도 하는 장치에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c8-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="5e6c8-109">전자 메일 콘텐츠에 대 한 기타 수정 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c8-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="5e6c8-110">다음 표에서는 현재 Microsoft Threat Protection에서 지원 되는 수정 작업을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c8-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="5e6c8-111">끝점 수정 작업</span><span class="sxs-lookup"><span data-stu-id="5e6c8-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="5e6c8-112">전자 메일 수정 작업</span><span class="sxs-lookup"><span data-stu-id="5e6c8-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="5e6c8-113">파일 격리</span><span class="sxs-lookup"><span data-stu-id="5e6c8-113">Quarantine file</span></span><br/><span data-ttu-id="5e6c8-114">레지스트리 키 추가</span><span class="sxs-lookup"><span data-stu-id="5e6c8-114">Remove registry key</span></span><br/><span data-ttu-id="5e6c8-115">프로세스 중단</span><span class="sxs-lookup"><span data-stu-id="5e6c8-115">Kill process</span></span> <br/><span data-ttu-id="5e6c8-116">서비스 중지</span><span class="sxs-lookup"><span data-stu-id="5e6c8-116">Stop service</span></span> <br/><span data-ttu-id="5e6c8-117">드라이버 해제</span><span class="sxs-lookup"><span data-stu-id="5e6c8-117">Disable driver</span></span> <br/><span data-ttu-id="5e6c8-118">예약된 작업 제거</span><span class="sxs-lookup"><span data-stu-id="5e6c8-118">Remove scheduled task</span></span>      |<span data-ttu-id="5e6c8-119">전자 메일 메시지 또는 클러스터의 일시 삭제</span><span class="sxs-lookup"><span data-stu-id="5e6c8-119">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="5e6c8-120">차단 URL(클릭 시간)</span><span class="sxs-lookup"><span data-stu-id="5e6c8-120">Block URL (time-of-click)</span></span><br/><span data-ttu-id="5e6c8-121">외부 메일 전달 해제</span><span class="sxs-lookup"><span data-stu-id="5e6c8-121">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="5e6c8-122">승인 보류 중 이거나 이미 완료 되었는지 여부에 관계 없이 수정 작업은 [알림 센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c8-122">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e6c8-123">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5e6c8-123">Next steps</span></span>

- [<span data-ttu-id="5e6c8-124">자동화된 조사 및 대응과 관련된 조치 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="5e6c8-124">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="5e6c8-125">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="5e6c8-125">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
