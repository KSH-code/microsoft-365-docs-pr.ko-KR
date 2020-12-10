---
title: Microsoft 365의 정보 장벽
description: Microsoft 365에서 정보 장벽을 구성하는 방법을 학습합니다.
keywords: Microsoft 365, 내부자 위험, 규정 준수
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 74a5b557ae610f8d008ad9d43bd2ccac43179131
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613846"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="34b90-104">Microsoft 365의 정보 장벽</span><span class="sxs-lookup"><span data-stu-id="34b90-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="34b90-105">Microsoft 365를 사용하면 그룹과 조직 전체에서 통신 및 공동 작업을 할 수 있으며, 필요한 경우 특정 사용자 그룹 간 통신 및 공동 작업을 제한하는 방법을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="34b90-106">여기에는 조직에서 이해 관계가 충돌하지 않도록 두 그룹 간의 통신 및 공동 작업을 제한하려는 상황이나 시나리오가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="34b90-107">여기에는 내부 정보를 보호하기 위해 조직 내부의 특정 사용자 간의 통신 및 공동 작업을 제한해야 하는 상황도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="34b90-108">정보 장벽은 Microsoft Teams, SharePoint Online 및 비즈니스용 OneDrive에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="34b90-109">준수 관리자 또는 정보 장벽 관리자는 Microsoft Teams에서 사용자 그룹 간의 통신을 허용하거나 차단하는 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="34b90-110">정보 장벽 정책은 다음 상황에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="34b90-111">일의 거래자 그룹 사용자는 마케팅 팀과 커뮤니케이션하거나 파일을 공유하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="34b90-112">기밀 회사 정보를 작업하는 재무 직원은 조직 내의 특정 그룹과 파일을 전달하거나 파일을 공유하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="34b90-113">거래 비밀 자료가 있는 내부 팀은 조직 내의 특정 그룹의 사용자와 온라인으로 전화를 걸거나 채팅하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="34b90-114">연구 팀은 제품 개발 팀과만 전화하거나 온라인으로 채팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="34b90-115">Microsoft 365에 대한 정보 장벽 구성</span><span class="sxs-lookup"><span data-stu-id="34b90-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="34b90-116">다음 단계를 사용하여 조직에 대한 정보 장벽을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="34b90-116">Use the following steps to configure information barriers for your organization:</span></span>

![내부자 위험 솔루션 정보 장벽 단계](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="34b90-118">Microsoft [](information-barriers.md) 365의 정보 장벽에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="34b90-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="34b90-119">선행 [구성 및 사용 권한 구성](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="34b90-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="34b90-120">조직의 [사용자 세그먼트화](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="34b90-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="34b90-121">정보 장벽 [정책 만들기 및 구성](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="34b90-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="34b90-122">정보 [장벽 정책 적용](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="34b90-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="34b90-123">정보 장벽에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="34b90-123">More information about information barriers</span></span>

- [<span data-ttu-id="34b90-124">정보 장벽 정책의 속성</span><span class="sxs-lookup"><span data-stu-id="34b90-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="34b90-125">정보 장벽 정책 편집 또는 제거</span><span class="sxs-lookup"><span data-stu-id="34b90-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)