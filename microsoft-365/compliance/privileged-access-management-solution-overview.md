---
title: Microsoft 365의 권한 있는 액세스 관리
description: Microsoft 365에서 내부자 위험 기능을 구성하는 방법을 알아보고,
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
ms.openlocfilehash: 7fecfd7088f65effd6addddc51c1236c7b2af191
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613872"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="4e224-104">Microsoft 365의 권한 있는 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="4e224-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="4e224-105">일부 사용자가 중요한 정보 또는 중요한 네트워크 구성 설정에 Microsoft Exchange Online 액세스하는 것은 손상된 계정 또는 내부 위협 활동에 대한 잠재적인 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4e224-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="4e224-106">권한이 부여된 액세스 관리는 위반으로부터 조직을 보호하고 중요한 데이터 또는 중요한 구성 설정에 대한 액세스를 제한하여 규정 준수 모범 사례를 충족하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e224-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="4e224-107">관리자가 지속적으로 액세스하는 대신 관리자 권한 상승이 필요한 작업에 대해 Just-In-Time 액세스 규칙이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e224-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="4e224-108">Microsoft 365에서 Exchange Online에 대한 권한 있는 액세스 관리를 사용하도록 설정하면 조직이 제로 스위딩 권한으로 작동하고 관리 액세스 취약성에 대한 방어 계층을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e224-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="4e224-109">Microsoft 365에 대한 권한 있는 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="4e224-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="4e224-110">다음 단계를 사용하여 조직에 대해 권한이 부여된 액세스 관리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e224-110">Use the following steps to configure privileged access management for your organization:</span></span>

![내부자 위험 솔루션 권한이 부여된 액세스 관리 단계](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="4e224-112">Microsoft 365의 권한 [있는 액세스](privileged-access-management-overview.md) 관리에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="4e224-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="4e224-113">승인자 [그룹 만들기](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="4e224-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="4e224-114">권한이 [부여된 액세스 관리 사용](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="4e224-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="4e224-115">액세스 [정책 만들기](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="4e224-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="4e224-116">권한이 [부여된 액세스 요청 제출/승인](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="4e224-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="4e224-117">권한이 부여된 액세스 관리에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="4e224-117">More information about privileged access management</span></span>

- [<span data-ttu-id="4e224-118">권한이 부여된 액세스 관리에 대한 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="4e224-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)