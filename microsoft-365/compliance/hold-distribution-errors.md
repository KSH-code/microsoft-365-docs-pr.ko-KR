---
title: eDiscovery 보류 오류 문제 해결
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Core eDiscovery에서 보유자 및 비관리 데이터 원본에 적용된 법적 보유와 관련된 오류를 해결합니다.
ms.openlocfilehash: 3e5cc6351d5026feda560bee646a1e6a03475ee2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191412"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a>eDiscovery 보류 오류 문제 해결

이 문서에서는 eDiscovery 보류에서 발생할 수 있는 일반적인 문제와 이러한 문제를 해결하는 방법에 대해 논의합니다. 이 문서에는 이러한 문제를 완화하거나 방지하는 데 도움이 되는 권장 사례도 포함되어 있습니다.

## <a name="recommended-practices"></a>권장 사례

eDiscovery 보류와 관련된 오류 수를 줄이면 다음과 같은 모범 사례가 권장됩니다.

- 보류 배포가 계속 보류 중인 경우 상태 또는 는 보류 배포가 완료될 때까지 기다렸다가 추가 업데이트를 `On (Pending)` `Off (Pending)` 합니다.

- 보류 정책을 추가로 업데이트하기 전에 보류 중인지 확인합니다. 다음 명령을 실행하거나 PowerShell 스크립트에 저장합니다.

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> -DistributionDetail
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- 각 트랜잭션에 대해 보류 정책을 반복적으로 업데이트하는 대신 단일 대량 요청으로 업데이트를 eDiscovery 보류에 병합합니다. 예를 들어 [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet을 사용하여 기존 보류 정책에 여러 사용자 사서함을 추가하기 위해 여러 사용자를 추가하기 위해 한 번만 실행하도록 명령을 실행(또는 스크립트에 코드 블록으로 추가)합니다.

  **올바른 예**

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **잘못된 예**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   이전의 잘못된 예에서 cmdlet은 작업을 완료하기 위해 5번 별도로 실행됩니다. 보류 정책에 사용자를 추가하는 권장 사례에 대한 자세한 내용은 추가 정보 [섹션을 참조하세요.](#more-information)

- eDiscovery 보류 문제에 대해 Microsoft 지원에 문의하기 전에 [오류/문제:](#errorissue-holds-dont-sync) 보류가 동기화되지 않습니다 섹션의 단계를 수행하여 보류 배포를 다시 시도합니다. 이 프로세스에서는 내부 서버 오류를 비롯한 일시적인 문제를 해결하는 경우가 종종 있습니다.

## <a name="errorissue-holds-dont-sync"></a>오류/문제: 보류가 동기화되지 않습니다.

보유자 및 데이터 원본을 보류할 때 다음 오류 메시지가 표시되어 있는 경우 해결 단계를 사용하여 문제를 해결합니다.

> 리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다. 최종 배포 상태를 업데이트하는 데 추가 2시간이 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다.

> 일시적인 데이터 센터 문제로 인해 콘텐츠 원본에 정책을 Office 365 수 없습니다. 현재 정책은 원본의 콘텐츠에 적용되지 않습니다. 따라서 차단된 배포에는 영향이 없습니다. 이 문제를 해결하려는 경우 정책을 다시 재배포해 하시기 바랍니다.

> 죄송합니다. 일시적인 내부 서버 오류로 인해 요청된 정책 변경을 수행할 수 없습니다. 30분 후 다시 시도하세요.

### <a name="resolution"></a>해결 방법

1. 커넥트 보안 & [센터 PowerShell에](/powershell/exchange/connect-to-scc-powershell) 대한 정보를 보고 eDiscovery 보류에 대해 다음 명령을 실행합니다.

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. *DistributionDetail* 매개 변수의 값을 검사합니다. 다음과 같은 오류를 찾아야 합니다.

   > 오류: 리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다. 최종 배포 상태를 업데이트하는 데 추가 2시간이 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다.

3. 문제의 보류 정책에서 **Set-CaseHoldPolicy -RetryDistribution** 명령을 실행합니다. 예를 들어:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a>오류: SharePoint 사이트가 읽기 전용 또는 액세스 가능하지 않습니다.

보유자 및 데이터 원본을 보류할 때 다음 오류 [메시지가](/sharepoint/sharepoint-admin-role) 표시될 경우 조직의 전역 관리자 또는 SharePoint 사이트가 잠겨 있는 것입니다. 잠긴 사이트는 eDiscovery가 사이트에 보류를 설정하지 않습니다.

> 사이트 SharePoint 읽기 전용 또는 액세스할 수 없습니다. 사이트 관리자에게 문의하여 사이트를 필기할 수 있도록 설정한 다음 이 정책을 다시 재배포하세요.

### <a name="resolution"></a>해결 방법

이 문제를 해결하려면 사이트의 잠금을 해제합니다(또는 관리자에게 잠금 해제 요청). 사이트의 잠금 상태를 변경하는 방법에 대한 자세한 내용은 사이트 잠금 및 잠금 [해제를 참조하세요.](/sharepoint/manage-lock-status)

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a>오류: 사서함 또는 SharePoint 사이트가 존재하지 않을 수 있습니다.

보유자 및 데이터 원본을 보류할 때 다음 오류 메시지가 표시되어 있는 경우 해결 단계를 사용하여 문제를 해결합니다.

> 사서함 또는 SharePoint 사이트가 존재하지 않을 수 있습니다.  이 문제가 올바르지 않은 경우 Microsoft 지원에 문의하시기 바랍니다.  그렇지 않은 경우 해당 정책에서 제거합니다.

### <a name="resolution"></a>해결 방법

- 조직에 사용자 사서함이 Exchange Online PowerShell에서 [Get-Mailbox를](/powershell/module/exchange/get-mailbox) 실행합니다.

- 조직에 사이트가 SharePoint PowerShell에서 [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet을 실행하여 사이트가 조직에 존재하는지 확인할 수 있습니다.

- 사이트 URL이 변경된지 확인합니다.

## <a name="more-information"></a>추가 정보

"권장 사례" 섹션에서 여러 사용자에 대한 보류 정책을 업데이트하는 지침은 시스템이 보류 정책에 대한 동시 업데이트를 차단하는 사실에서 비로소 제공됩니다. 즉, 업데이트된 보류 정책이 새 콘텐츠 위치에 적용되고 보류 정책이 보류 중인 상태이면 보류 정책에 추가 콘텐츠 위치를 추가할 수 없습니다. 다음은 이 문제를 완화하는 데 도움이 있도록 유의해야 할 몇 가지 사항입니다.
  
- 보류가 업데이트될 때마다 즉시 보류 상태가 됩니다. 보류 상태는 보류가 콘텐츠 위치에 적용되고 있는 것을 의미합니다.
  
- 루프를 실행하고 정책을 하나씩 추가하는 스크립트가 있는 경우("권장 사례" 섹션에 표시된 잘못된 예와 유사함) 첫 번째 콘텐츠 위치(예: 사용자 사서함)는 보류 중인 상태를 트리거하는 동기화 프로세스를 시작됩니다. 즉, 후속 루프에서 정책에 추가된 다른 사용자는 오류가 발생합니다.
  
- 조직에서 루프를 실행하여 보류 정책의 콘텐츠 위치를 업데이트하는 스크립트를 사용하는 경우 "권장 사례" 섹션의 올바른 예와 같이 단일 대량 작업에서 위치를 업데이트할 수 있도록 스크립트를 업데이트해야 합니다.
