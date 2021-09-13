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
ms.openlocfilehash: eb842a3d5add719338773f088b07dcf4c32ede53
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216555"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 유지 잠금 사용

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

유지 잠금은 전역 관리자를 비롯하여 누구도 정책을 해제하거나 삭제하거나 덜 제한적으로 만들 수 없도록 보존 정책 또는 보존 레이블 정책을 잠급니다. 해당 구성은 규정 요구 사항에 필요할 수 있으며 로그 관리자로부터의 안전 보호를 지원할 수 있습니다.

보존 정책이 잠기는 경우:

- 누구도 정책을 사용하지 않도록 설정하거나 삭제할 수 없습니다.
- 위치는 추가할 수 있지만 제거할 수는 없습니다.
- 보존 기간을 연장할 수 있지만 줄일 수는 없습니다.

보존 레이블 정책이 잠기는 경우:

- 누구도 정책을 사용하지 않도록 설정하거나 삭제할 수 없습니다.
- 위치는 추가할 수 있지만 제거할 수는 없습니다.
- 레이블은 추가할 수 있지만 제거할 수는 없습니다.

요약하면 잠긴 정책은 늘리거나 확장할 수 있지만 줄이거나 해제할 수 없습니다.

> [!IMPORTANT]
> 보존 정책 또는 보존 레이블 정책을 잠그기 전에 해당 정책의 영향을 이해하고 조직에 해당 정책이 필요한지 여부를 확인하는 것이 중요합니다. 예를 들어 규정 요구 사항을 충족해야 할 수 있습니다. 유지 잠금이 적용된 후에는 관리자가 해당 정책을 사용하지 않도록 설정하거나 삭제할 수 없습니다.

[게시](create-apply-retention-labels.md)하거나 [자동 적용](apply-retention-labels-automatically.md)하는 [보존 정책](create-retention-policies.md) 또는 보존 레이블 정책을 생성한 후에 유지 잠금을 구성합니다. 

> [!NOTE]
> 레이블 정책을 잠그더라도 관리자는 잠긴 정책에 포함된 레이블의 보존 기간을 단축할 수 없습니다. 이 요구 사항은 다른 제한 사항과 함께 항목을 [규제 기록](records-management.md#records)으로 표시하도록 레이블을 구성할 때 충족될 수 있습니다.

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>보존 정책 또는 보존 레이블 정책을 잠그는 방법

유지 잠금을 사용해야 하는 경우 PowerShell을 사용해야 합니다. 유지 잠금이 적용된 후에는 관리자가 보존 정책을 사용하지 않도록 설정하거나 삭제할 수 없으므로 우발적인 구성으로부터의 안전 보호를 위해 UI에서 해당 기능을 활성화할 수 없습니다.

모든 보존 정책 및 모든 구성 관련 정책은 유지 잠금을 지원합니다.

1. [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)합니다.

2. [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy)를 실행하여 잠그려는 정책의 이름을 찾습니다. 예를 들어,
    
   ![PowerShell의 보존 정책 목록.](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. 사용자의 정책에 유지 잠금을 설정하려면 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet을 해당 정책 이름으로 실행하고 *RestrictiveRetention* 매개 변수를 True로 설정합니다.
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    예시:
    
    ![PowerShell의 RestrictiveRetention 매개 변수.](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     메시지가 표시되면 이 구성과 함께 제공되는 제한 사항을 읽고 **Y** 를 입력하여 승인합니다.
    
   ![PowerShell에서 보존 정책 잠금을 원하는지 확인하는 메시지.](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

이제 해당 정책에 유지 잠금이 적용됩니다. 확인하기 위해 `Get-RetentionCompliancePolicy`을(를) 다시 실행하지만 해당 정책 이름을 지정하고 정책 매개변수를 표시합니다.

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

**RestrictiveRetention** 이 **True** 로 설정되어 있는지 확인해야 합니다. 예를 들어,

![PowerShell에 모든 매개 변수와 함께 표시된 잠긴 정책.](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>참고 항목

[정보 거버넌스 및 레코드 관리를 위해 규정 요구 사항을 충족할 수 있도록 도움이 되는 리소스](retention-regulatory-requirements.md)