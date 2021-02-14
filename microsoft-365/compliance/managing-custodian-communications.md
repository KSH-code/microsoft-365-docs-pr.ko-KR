---
title: Advanced eDiscovery에서 통신 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery를 사용하면 법적 조사에서 보유자에게 알리기 위한 법적 보유 알림 워크플로를 쉽게 관리할 수 있습니다.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551247"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="6a9f2-103">Advanced eDiscovery에서 통신 사용</span><span class="sxs-lookup"><span data-stu-id="6a9f2-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="6a9f2-104">고급 eDiscovery를 사용하면 법률 부서에서 법적 보유 알림을 추적하고 배포하는 프로세스를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="6a9f2-105">보유자 커뮤니케이션 도구를 사용하면 법률 부서가 초기 알림에서 미리 알림, 미리 알림 및 에스컬레이터에 대한 전체 법적 보유 프로세스를 한 위치에서 관리하고 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="6a9f2-106">법적 보유 알림이란?</span><span class="sxs-lookup"><span data-stu-id="6a9f2-106">What is a legal hold notification?</span></span>

<span data-ttu-id="6a9f2-107">법적 보유(소송 자료 보호라고도 *하는)* 알림은 법률 조사와 관련이 있을 수 있는 데이터의 직원, 사건 대응 직원 또는 보유자에게 조직의 법률 부서에서 전송되는 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="6a9f2-108">이러한 알림은 보류자가 전자적으로 저장된 정보와 활성 또는 임박한 법적 문제와 관련이 있을 수 있는 모든 콘텐츠를 보존하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="6a9f2-109">법률 팀은 각 보호자로부터 받은, 읽기, 이해 및 제공된 지침을 준수하기로 합의한 것을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="6a9f2-110">법적 보유 알림 프로세스</span><span class="sxs-lookup"><span data-stu-id="6a9f2-110">The legal hold notification process</span></span>

<span data-ttu-id="6a9f2-111">조직은 임박한 소송 또는 규제 조사에 대해 학습할 때 관련 정보를 보존할 의무가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="6a9f2-112">조사의 보존 요구 사항을 준수하기 위해 조직은 잠재적 관리인에게 관련 정보를 보존해야 할 의무를 즉시 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="6a9f2-113">Advanced eDiscovery를 사용하여 법률 팀에서 법적 보유 알림 워크플로를 만들고 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="6a9f2-114">양도자 커뮤니케이션 도구를 사용하면 법률 팀에서 다음 알림 및 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="6a9f2-115">**발행 알림:** 법적 보유 고지는 법률 부서에서 사례 관련 정보가 있을 수 있는 보유자에 대한 알림을 통해 발급(또는 시작)됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="6a9f2-116">이 알림은 보호자에게 검색에 필요할 수 있는 정보를 보존할 것 을 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="6a9f2-117">**다시 발행 알림:** 이 경우 이전에 요청한 것보다 추가 콘텐츠(또는 적은 콘텐츠)를 보존해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="6a9f2-118">이 시나리오에서는 기존 보류 통지를 업데이트하고 보유자에 다시 발급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="6a9f2-119">**릴리스 알림:** 문제가 해결된 후 보호자에 대한 보존 요구 사항이 더 이상 적용되지 않으면 해당 사례에서 보호권이 해지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="6a9f2-120">또한 보호자에게 더 이상 콘텐츠를 보존할 필요 없음을 알리고 데이터와 관련하여 정상적인 작업 활동을 다시 시작하는 방법에 대한 지침을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="6a9f2-121">미리 알림 및 **에스컬레이터:** 경우에 따라 알림만 발행하면 법적 검색 요구 사항을 충족하기에 충분하지 않은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="6a9f2-122">각 알림을 통해 법률 팀은 응답하지 않는 보호자에 대해 자동으로 후속 작업을 수행하기 위해 미리 알림 및 에스컬레이터 워크플로 집합을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="6a9f2-123">**미리 알림:** 법적 보류 알림이 발급되거나 보유자 집합에 다시 발급된 후 조직은 응답하지 않는 보유자에 대해 경고할 미리 알림을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="6a9f2-124">**에스컬레이터:** 경우에 따라, 특정 기간 동안 미리 알림 집합이 설정된 후에도 보호자에게 응답하지 않는 경우 법률 팀은 응답하지 않는 보호자 및 관리자에게 알리는 에스컬레이터 워크플로를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="6a9f2-125">보호자 통신 프로세스 관리에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="6a9f2-126">법적 보유 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="6a9f2-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="6a9f2-127">커뮤니케이션 편집기 사용</span><span class="sxs-lookup"><span data-stu-id="6a9f2-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="6a9f2-128">보류 알림 관리</span><span class="sxs-lookup"><span data-stu-id="6a9f2-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="6a9f2-129">보류 알림 승인</span><span class="sxs-lookup"><span data-stu-id="6a9f2-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)