---
title: 자동화된 조사 및 응답에서 보류 중인 수정 작업 검토 및 승인
keywords: AIR, autoIR, ATP, 자동화된, 조사, 대응, 수정, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 계획 2의 자동화된 조사 및 응답 기능의 수정 작업에 대해 자세히 알아보습니다.
ms.openlocfilehash: 9a1fdb4bec5168dfcd816dbce7da01f930e38ae1
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615195"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="cab92-104">Office 365에서 자동화된 조사 후 보류 중 또는 완료된 수정 작업 보기</span><span class="sxs-lookup"><span data-stu-id="cab92-104">View pending or completed remediation actions following an automated investigation in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]



![AIR 조사 작업 페이지](../../media/air-investigationactionspage.png)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="cab92-106">보류 중인 작업 승인(또는 거부)</span><span class="sxs-lookup"><span data-stu-id="cab92-106">Approve (or reject) pending actions</span></span>

<span data-ttu-id="cab92-107">조사의 [세부](air-view-investigation-results.md)정보를 보는 동안 보류 중인 수정 작업을 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-107">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="cab92-108">자동화된 조사가 완료될 수 있도록 가능한 한 빨리 이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-108">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cab92-109">재구성 작업을 승인하거나 거부하려면 적절한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-109">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="cab92-110">[AIR 기능을 사용하려면 필요한 사용 권한을 참조합니다.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="cab92-110">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="cab92-111"><https://protection.office.com>으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-111">Go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="cab92-112">이렇게하면 보안 및 준수 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-112">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="cab92-113">위협 **Threat management** 관리 \> **조사로 이동.**</span><span class="sxs-lookup"><span data-stu-id="cab92-113">Go to **Threat management** \> **Investigations**.</span></span>

3. <span data-ttu-id="cab92-114">조사 목록에서 ID 열의 **항목을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-114">In the list of investigations, select an item in the **ID** column.</span></span>

4. <span data-ttu-id="cab92-115">작업 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-115">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="cab92-116">목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-116">Select an item in the list.</span></span> <span data-ttu-id="cab92-117">(승인 및 거부 단추가 활성화됩니다.)</span><span class="sxs-lookup"><span data-stu-id="cab92-117">(This activates the Approve and Reject buttons.)</span></span>

6. <span data-ttu-id="cab92-118">선택한 항목에 대해 사용 가능한 정보를 검토한 다음 작업을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-118">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span>
   - <span data-ttu-id="cab92-119">**승인을** 통해 수정을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-119">**Approve** allows remediation to begin.</span></span>
   - <span data-ttu-id="cab92-120">**거부는** 추가 작업을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cab92-120">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="cab92-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cab92-121">Next steps</span></span>

- [<span data-ttu-id="cab92-122">Office 365의 자동화된 조사 세부 정보 및 결과</span><span class="sxs-lookup"><span data-stu-id="cab92-122">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

- [<span data-ttu-id="cab92-123">위협 탐색기 사용</span><span class="sxs-lookup"><span data-stu-id="cab92-123">Use Threat Explorer</span></span>](threat-explorer.md)
