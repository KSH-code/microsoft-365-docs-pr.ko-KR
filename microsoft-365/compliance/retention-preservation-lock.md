---
title: 보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 유지 잠금 사용
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 보존 정책 및 보존 레이블 정책과 함께 유지 잠금을 사용하여 규정 요구 사항을 충족하고 로그 관리자로부터의 안전 보호를 지원합니다.
ms.openlocfilehash: 6f6cfc5bef9b93af08fcc9b703b29facb9a7c576
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920718"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="b461d-103">보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 유지 잠금 사용</span><span class="sxs-lookup"><span data-stu-id="b461d-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="b461d-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="b461d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="b461d-105">유지 잠금은 전역 관리자를 비롯하여 누구도 정책을 해제하거나 삭제하거나 덜 제한적으로 만들 수 없도록 보존 정책 또는 보존 레이블 정책을 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="b461d-106">해당 구성은 규정 요구 사항에 필요할 수 있으며 로그 관리자로부터의 안전 보호를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="b461d-107">보존 정책을 잠근 경우:</span><span class="sxs-lookup"><span data-stu-id="b461d-107">When a policy for retention is locked:</span></span>

- <span data-ttu-id="b461d-108">아무도 끌 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-108">No one can turn it off</span></span>
- <span data-ttu-id="b461d-109">위치는 추가할 수 있지만 제거할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="b461d-110">보존 기간을 연장할 수 있지만 줄일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-110">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="b461d-111">요약하면 잠긴 정책은 늘리거나 확장할 수 있지만 줄이거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-111">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b461d-112">보존 정책 또는 보존 레이블 정책을 잠그기 전에 해당 정책의 영향을 이해하고 조직에 해당 정책이 필요한지 여부를 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-112">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="b461d-113">예를 들어 규정 요구 사항을 충족해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-113">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="b461d-114">유지 잠금이 적용된 후에는 관리자가 해당 정책을 사용하지 않도록 설정하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-114">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="b461d-115">[게시](create-apply-retention-labels.md)하거나 [자동 적용](apply-retention-labels-automatically.md)하는 [보존 정책](create-retention-policies.md) 또는 보존 레이블 정책을 생성한 후에 유지 잠금을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-115">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="b461d-116">보존 정책 또는 보존 레이블 정책을 잠그는 방법</span><span class="sxs-lookup"><span data-stu-id="b461d-116">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="b461d-117">유지 잠금을 사용해야 하는 경우 PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-117">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="b461d-118">유지 잠금이 적용된 후에는 관리자가 보존 정책을 사용하지 않도록 설정하거나 삭제할 수 없으므로 우발적인 구성으로부터의 안전 보호를 위해 UI에서 해당 기능을 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-118">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="b461d-119">모든 보존 정책 및 모든 구성 관련 정책은 유지 잠금을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-119">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="b461d-120">[보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-120">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="b461d-121">[Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)를 실행하여 잠그려는 정책의 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-121">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="b461d-122">예제:</span><span class="sxs-lookup"><span data-stu-id="b461d-122">For example:</span></span>
    
   ![PowerShell의 보존 정책 목록](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="b461d-124">사용자의 정책에 유지 잠금을 설정하려면 [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet을 해당 정책 이름으로 실행하고 *RestrictiveRetention* 매개 변수를 True로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-124">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="b461d-125">예제:</span><span class="sxs-lookup"><span data-stu-id="b461d-125">For example:</span></span>
    
    ![PowerShell의 RestrictiveRetention 매개 변수](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="b461d-127">메시지가 표시되면 이 구성과 함께 제공되는 제한 사항을 읽고 **Y** 를 입력하여 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-127">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y** :</span></span>
    
   ![PowerShell에서 보존 정책 잠금을 원하는지 확인하는 메시지](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="b461d-129">이제 해당 정책에 유지 잠금이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-129">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="b461d-130">확인하기 위해 `Get-RetentionCompliancePolicy`을(를) 다시 실행하지만 해당 정책 이름을 지정하고 정책 매개변수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-130">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="b461d-131">**RestrictiveRetention** 이 **True** 로 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b461d-131">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="b461d-132">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="b461d-132">For example:</span></span>

![PowerShell에 모든 매개 변수와 함께 표시된 잠긴 정책](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="b461d-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b461d-134">See also</span></span>

[<span data-ttu-id="b461d-135">정보 거버넌스 및 레코드 관리를 위해 규정 요구 사항을 충족할 수 있도록 도움이 되는 리소스</span><span class="sxs-lookup"><span data-stu-id="b461d-135">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)
