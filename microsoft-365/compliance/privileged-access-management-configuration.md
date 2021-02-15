---
title: 권한이 부여된 액세스 관리 시작
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: 이 문서를 사용하여 Office 365에서 권한이 부여된 액세스 관리를 사용하도록 설정하고 구성하는 방법을 자세히 알아보는 방법을 사용할 수 있습니다.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126535"
---
# <a name="get-started-with-privileged-access-management"></a>권한이 부여된 액세스 관리 시작

이 항목에서는 조직에서 권한이 부여된 액세스 관리를 사용하도록 설정하고 구성하는 방법을 안내합니다. Microsoft 365 관리 센터 또는 Exchange 관리 PowerShell을 사용하여 권한 있는 액세스를 관리하고 사용할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

권한이 부여된 액세스 관리를 시작하기 전에 Microsoft [365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 구독 및 추가 기능을 확인해야 합니다. 권한이 부여된 액세스 관리에 액세스하고 사용하려면 조직에 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.

- Microsoft 365 E5 구독(유료 또는 평가판)
- Microsoft 365 E3 구독(또는 Office 365 E3 구독 + Enterprise Mobility and Security E3 구독) + Microsoft 365 E5 규정 준수 추가 기능
- 모든 Microsoft 365, Office 365, Exchange, SharePoint 또는 비즈니스용 OneDrive 구독 + Microsoft 365 E5 내부자 위험 관리 추가 기능  
- Microsoft 365 A5 구독(유료 또는 평가판)
- Microsoft 365 A3 구독(또는 Office 365 A3 구독 + Enterprise Mobility and Security A3 구독) + Microsoft A5 준수 추가 기능
- 모든 Microsoft 365, Office 365, Exchange, SharePoint 또는 OneDrive for Education 구독 + Microsoft 365 A5 내부자 위험 관리 추가 기능
- Office 365 Enterprise E5 구독(유료 또는 평가판)
- Office 365 Enterprise E3 구독 + Office 365 고급 준수 추가 기능(더 이상 새 구독에 사용할 수 없음, 참고 참조)

권한이 부여된 액세스 관리 요청을 제출하고 응답하는 사용자에게 위의 라이선스 중 하나를 할당해야 합니다.

>[!IMPORTANT]
>Office 365 Advanced Compliance는 더 이상 독립 실행형 구독으로 판매하지 않습니다. 현재 구독이 만료되면 고객은 동일한 또는 추가 규정 준수 기능을 포함하는 위의 구독 중 하나로 전환해야 합니다.

기존 Office 365 Enterprise E5 요금제가 없는 경우 권한 있는 액세스 관리를 시도하려는 경우 기존 Office 365 [](https://www.microsoft.com/microsoft-365/enterprise) 구독에 [Microsoft 365를](/office365/admin/try-or-buy-microsoft-365) 추가하거나 Microsoft 365 Enterprise E5 평가판을 등록할 수 있습니다.

## <a name="enable-and-configure-privileged-access-management"></a>권한이 부여된 액세스 관리 사용 및 구성

다음 단계에 따라 조직에서 권한이 부여된 액세스를 설정하고 사용하세요.

- [1단계: 승인자 그룹 만들기](privileged-access-management-configuration.md#step1)

    권한 액세스 사용을 시작하기 전에 권한 상승 및 권한 있는 작업에 대한 액세스에 대한 들어오는 요청에 대해 승인 기관이 필요한 사용자를 결정하십시오. 승인자 그룹의 일부인 사용자는 액세스 요청을 승인할 수 있습니다. 이 그룹은 Office 365에서 메일 사용이 가능한 보안 그룹을 만들어 사용하도록 설정합니다.

- [2단계: 권한 있는 액세스 사용](privileged-access-management-configuration.md#step2)

    권한 있는 액세스는 권한 있는 액세스 관리 액세스 제어에서 제외하려는 시스템 계정 집합을 포함하여 기본 승인자 그룹을 사용하여 Office 365에서 명시적으로 사용하도록 설정해야 합니다.

- [3단계: 액세스 정책 만들기](privileged-access-management-configuration.md#step3)

    승인 정책을 만들면 개별 작업에서 범위가 지정되는 특정 승인 요구 사항을 정의할 수 있습니다. 승인 유형 옵션은 자동 또는 **수동입니다.** 

- [4단계: 권한 있는 액세스 요청 제출/승인](privileged-access-management-configuration.md#step4)

    권한이 부여된 액세스에는 연결된 승인 정책이 정의된 작업에 대한 승인이 필요합니다. 승인 정책에 포함된 작업의 경우 사용자는 작업을 실행하는 데 필요한 사용 권한을 가지기 위해 액세스 승인을 요청하고 부여해야 합니다.

승인이 부여된 후 요청하는 사용자는 의도한 작업을 실행할 수 있으며 권한이 부여된 액세스는 사용자를 대신하여 작업을 승인하고 실행합니다. 승인은 요청한 기간(기본 기간은 4시간)에 대해 유효하게 유지되어 요청자에서 의도한 작업을 여러 번 실행할 수 있습니다. 이러한 모든 실행은 기록되어 보안 및 규정 준수 감사에 사용할 수 있습니다. 

>[!NOTE]
>Exchange 관리 PowerShell을 사용하여 권한 있는 액세스를 사용하도록 설정하고 구성하려면 다단계 인증을 사용하여 [Exchange Online PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) 연결의 단계를 수행하여 Office 365 자격 증명을 사용하여 Exchange Online PowerShell에 연결합니다. Exchange Online PowerShell에 연결하는 동안 권한이 부여된 액세스를 사용하도록 설정하는 단계를 조직에 대해 다단계 인증을 사용하도록 설정할 필요는 없습니다. 다단계 인증을 사용하여 연결하면 요청에 서명하는 데 권한이 부여된 액세스에 사용되는 OAuth 토큰이 생성됩니다.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>1단계: 승인자 그룹 만들기

1. 조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 그룹 **추가**  >  **그룹으로 이동하세요.**

3. 메일 **사용이 가능한 보안** 그룹을 선택한 다음 새 그룹의 이름, 그룹 전자 메일 주소 및 **설명** 필드를 입력합니다.  

4. 그룹을 저장합니다. 그룹을 완전히 구성하고 Microsoft 365 관리 센터에 표시하는 데 몇 분 정도 걸릴 수 있습니다.

5. 새 승인자 그룹을 선택하고 편집을 **선택하여** 그룹에 사용자를 추가합니다.

6. 그룹을 저장합니다.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>2단계: 권한 있는 액세스 사용

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서

1. 조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**

3. 권한 있는 **작업 컨트롤에 대한 승인 필요를 사용하도록** 설정

4. 1단계에서 만든 승인자 그룹을 기본 승인자 그룹으로 **할당합니다.**

5. **저장** 및 **닫기.**

### <a name="in-exchange-management-powershell"></a>Exchange 관리 PowerShell에서

권한 있는 액세스를 사용하도록 설정하고 승인자 그룹을 할당하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

예제:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>조직 내의 특정 자동화가 권한 있는 액세스에 종속되지 않고도 작동할 수 있도록 시스템 계정 기능을 사용할 수 있습니다. 그러나 이러한 제외는 예외적인 것이 며 허용되는 제외는 정기적으로 승인 및 감사해야 합니다.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>3단계: 액세스 정책 만들기

조직에 대해 최대 30개까지 권한 있는 액세스 정책을 만들고 구성할 수 있습니다.

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서

1. 조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**

3. 액세스 **정책 및 요청 관리 선택.**

4. 정책 **구성을** 선택하고 정책 **추가를 선택합니다.**

5. 드롭다운 필드에서 조직에 적합한 값을 선택합니다.
    
    **정책 유형:** 작업, 역할 또는 역할 그룹

    **정책 범위**: Exchange

    **정책 이름:** 사용 가능한 정책에서 선택

    **승인 유형:** 수동 또는 자동

    **승인 그룹:** 1단계에서 만든 승인자 그룹 선택

6. **Create(만들기)를** 선택한 다음 **닫기(닫기)를 선택합니다.** 정책을 완전히 구성하고 사용하도록 설정하는 데 몇 분 정도 걸릴 수 있습니다.

### <a name="in-exchange-management-powershell"></a>Exchange 관리 PowerShell에서

승인 정책을 만들고 정의하기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

예제:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>4단계: 권한 있는 액세스 요청 제출/승인

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>권한 있는 작업 실행을 위한 권한 상승 권한 부여 요청

권한 있는 액세스 요청은 요청이 제출된 후 최대 24시간 동안 유효합니다. 승인되거나 거부되지 않은 경우 요청이 만료되고 액세스가 승인되지 않습니다.

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서

1. 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**

3. 액세스 **정책 및 요청 관리 선택.**

4. 새 **요청을 선택합니다.** 드롭다운 필드에서 조직에 적합한 값을 선택합니다.

    **요청 유형**: 작업, 역할 또는 역할 그룹

    **요청 범위**: Exchange

    **요청:** 사용 가능한 정책에서 선택

    **기간(시간)**: 요청된 액세스의 시간입니다. 요청할 수 있는 시간 수에는 제한이 없습니다.

    **설명:** 액세스 요청과 관련된 설명의 텍스트 필드

5. 저장을 **선택한** 다음 **닫습니다.** 요청은 전자 메일을 통해 승인자 그룹으로 전송됩니다.

#### <a name="in-exchange-management-powershell"></a>Exchange 관리 PowerShell에서

Exchange Online PowerShell에서 다음 명령을 실행하여 승인자 그룹에 승인 요청을 만들고 제출합니다.

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

예제:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>권한 상승 요청 상태 보기

승인 요청이 만들어진 후 권한 상승 요청 상태는 요청 ID와 연결된 Exchange 관리 PowerShell 또는 관리 센터에서 검토할 수 있습니다.

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서

1. 자격 증명으로 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **권한으로 & 설정**  >  **보안으로 이동합니다.**

3. 액세스 **정책 및 요청 관리 선택.**

4. 보류 **중,** 승인됨, 거부됨 또는  **고객 Lockbox** 상태를 사용하여 제출된 요청을 필터링하려면 보기를 선택합니다.  

#### <a name="in-exchange-management-powershell"></a>Exchange 관리 PowerShell에서

Exchange Online PowerShell에서 다음 명령을 실행하여 특정 요청 ID에 대한 승인 요청 상태를 볼 수 있습니다.

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

예제:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>권한 상승 권한 부여 요청 승인

승인 요청이 생성되면 관련 승인자 그룹의 구성원이 전자 메일 알림을 받고 요청 ID와 관련된 요청을 승인할 수 있습니다. 요청자에 전자 메일 메시지를 통해 요청 승인 또는 거부에 대한 알림이 제공됩니다.

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서

1. 자격 증명으로 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호 권한 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**

3. 액세스 **정책 및 요청 관리 선택.**

4. 나열된 요청을 선택하여 세부 정보를 보고 요청에 대한 작업을 수행합니다.

5. 요청을 **승인하려면** 승인을  선택하거나 거부를 선택하여 요청을 거부합니다. 이전에 승인된 요청은 해지를 선택하여 액세스가 해지될 **수 있습니다.**

#### <a name="in-exchange-management-powershell"></a>Exchange 관리 PowerShell에서

권한 상승 권한 부여 요청을 승인하기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

예제:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

권한 상승 권한 부여 요청을 거부하기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

예제:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Office 365에서 권한 있는 액세스 정책 삭제

조직에서 더 이상 필요하지 않는 경우 권한이 부여된 액세스 정책을 삭제할 수 있습니다.

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서

1. 조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **권한으로 & 설정**  >  **보안으로 이동합니다.**

3. 액세스 **정책 및 요청 관리 선택.**

4. 정책 **구성을 선택합니다.**

5. 삭제할 정책을 선택한 다음 정책 **제거를 선택합니다.**

6. **닫기** 를 선택합니다.

### <a name="in-exchange-management-powershell"></a>Exchange 관리 PowerShell에서

권한 있는 액세스 정책을 삭제하려면 Exchange Online Powershell에서 다음 명령을 실행합니다.

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Office 365에서 권한 있는 액세스를 사용하지 않도록 설정

필요한 경우 조직에 대해 권한이 부여된 액세스 관리를 사용하지 않도록 설정할 수 있습니다. 권한이 부여된 액세스를 사용할 수 없는 경우 연결된 승인 정책 또는 승인자 그룹은 삭제되지 않습니다.

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서

1. 조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**

3. 권한이 **부여된 액세스 제어에 대한 승인 필요를 사용하도록** 설정

### <a name="in-exchange-management-powershell"></a>Exchange 관리 PowerShell에서

권한 있는 액세스를 사용하지 않도록 설정하기 위해 Exchange Online Powershell에서 다음 명령을 실행합니다.

```PowerShell
Disable-ElevatedAccessControl
```
