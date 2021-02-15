---
title: Microsoft 365의 내부자 위험 관리
description: Microsoft 365에서 내부자 위험 관리를 구성하는 방법을 학습합니다.
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
ms.openlocfilehash: 3919523c703cb64ac443b3f0f73484efe9cea670
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613924"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="2767b-104">Microsoft 365의 내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="2767b-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="2767b-105">점점 더 많은 직원이 광범위한 플랫폼 및 서비스에서 데이터를 만들고 관리하고 공유할 수 있는 더 많은 액세스 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2767b-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="2767b-106">대부분의 경우 조직은 규정 준수 요구 사항 및 직원 개인 정보 보호 표준을 충족하면서 조직 전체의 위험을 식별하고 완화하는 데 필요한 리소스와 도구가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="2767b-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="2767b-107">이러한 위험에는 실수로 과도하게 공유하거나 악의적인 의도를 하여 직원을 퇴사하는 데이터 도용 및 조직 외부의 정보 누출이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2767b-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="2767b-108">Microsoft 365의 내부자 위험 관리는 모든 서비스 및 제3자 지표를 사용하여 위험한 사용자 활동을 신속하게 식별, 평가 및 대응하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2767b-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="2767b-109">Microsoft 365 및 Microsoft Graph의 로그를 사용하여 내부자 위험 관리를 사용하면 특정 정책을 정의하여 위험 지표를 식별하고 이러한 위험을 완화하기 위한 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2767b-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="2767b-110">Microsoft 365에 대한 내부자 위험 관리 구성</span><span class="sxs-lookup"><span data-stu-id="2767b-110">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="2767b-111">다음 단계를 사용하여 조직에 대한 내부자 위험 관리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2767b-111">Use the following steps to configure insider risk management for your organization:</span></span>

![내부자 위험 솔루션 내부자 위험 관리 단계](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="2767b-113">Microsoft 365의 [내부자](insider-risk-management.md) 위험 관리에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="2767b-113">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="2767b-114">내부자 [위험 관리 계획 및 라이선스 확인](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="2767b-114">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="2767b-115">내부자 [위험 관리 설정 구성](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2767b-115">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="2767b-116">커넥터에 대한 사용 권한 및 정책 [& 구성](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates) [](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)</span><span class="sxs-lookup"><span data-stu-id="2767b-116">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)</span></span>
5. <span data-ttu-id="2767b-117">내부자 위험 [관리 정책 만들기 및 구성](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="2767b-117">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="2767b-118">내부자 위험 관리에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="2767b-118">More information about insider risk management</span></span>

- [<span data-ttu-id="2767b-119">내부자 위험 정책 관리</span><span class="sxs-lookup"><span data-stu-id="2767b-119">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="2767b-120">내부자 위험 경고 조사</span><span class="sxs-lookup"><span data-stu-id="2767b-120">Investigate insider risk alerts</span></span>](insider-risk-management-alerts.md)
- [<span data-ttu-id="2767b-121">내부자 위험 사례에 대한 행동</span><span class="sxs-lookup"><span data-stu-id="2767b-121">Act on insider risk cases</span></span>](insider-risk-management-cases.md)