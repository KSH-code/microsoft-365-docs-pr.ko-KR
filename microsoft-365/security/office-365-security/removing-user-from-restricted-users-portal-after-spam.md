---
title: 제한된 사용자 포털에서 차단된 사용자 제거
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft 365 Defender 포털의 제한된 사용자 페이지에서 사용자를 제거하는 방법을 알아볼 수 있습니다. 사용자는 일반적으로 계정 손상의 결과로 아웃바운드 스팸 전송을 위해 제한된 사용자 포털에 추가됩니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 774f47c65f98a2e93ee6e50406afe897a315de12
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187379"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a>Microsoft 365의 제한된 사용자 포털에서 차단된 사용자 제거

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

사용자가 [서비스 제한](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 또는 [아웃바운드 스팸 정책](configure-the-outbound-spam-policy.md)에 지정된 아웃바운드 전송 제한 중 하나를 초과하는 경우 전자 메일 보내기가 제한되지만 계속 전자 메일을 받을 수 있습니다.

사용자는 Microsoft 365 Defender 포털의 **제한된 사용자** 페이지에 추가됩니다. 사용자가 전자 메일을 보내려고 하면 메시지가 오류 코드 [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 및 다음 텍스트와 함께 배달 못 함 보고서(NDR 또는 바운스 메시지라고도 함)로 반환됩니다.

> "유효한 보낸 사람으로 인식되지 않았기 때문에 메시지를 배달할 수 없습니다. 가장 일반적인 이유는 전자 메일 주소가 스팸 메일을 보내는 것으로 의심어서 더 이상 전자 메일을 보낼 수 없는 경우입니다.  도움이 필요하면 전자 메일 관리자에게 문의하세요. 원격 서버에서 '550 5.1.8 액세스가 거부되었습니다. 잘못된 아웃 바운드 보낸 사람"이 반환되었습니다.

관리자는 Microsoft 365 Defender 또는 Exchange Online PowerShell의 제한된 사용자 페이지에서 사용자를 제거할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. **제한된 사용자** 페이지로 직접 이동하려면 <https://security.microsoft.com/restrictedusers>를 사용합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 제한된 사용자 포털에서 사용자를 제거하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원이어야 합니다.
  - 제한된 사용자 포털에 읽기 전용으로 액세스하려면 **글로벌 리더** 또는 **보안 리더** 역할 그룹의 구성원이어야 합니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  > [!NOTE]
  >
  > - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹도 기능에 대한 읽기 전용 권한을 부여합니다.

- 아웃바운드 전자 메일 제한을 초과 하는 보낸 사람은 손상된 계정을 나타냅니다. 제한된 사용자 포털에서 사용자를 제거하기 전에 관련 계정을 다시 제어하기 위해 필요한 단계를 수행해야 합니다. 자세한 내용은 [Office 365에서 손상된 전자 메일 계정에 응답](responding-to-a-compromised-email-account.md)을 참조하세요.

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a>Microsoft 365 Defender 포털을 사용하여 제한된 사용자 목록에서 사용자 제거

1. Microsoft 365 Defender 포털에서 **Email & collaboration**(전자 메일 및 공동 작업) > **검토** > **제한된 사용자** 로 이동합니다.

2. **제한된 사용자** 페이지에서 사용자를 클릭하여 차단을 해제할 사용자를 찾아 선택합니다.

3. 표시되는 **차단 해제** 작업을 클릭합니다.

4. 표시되는 **사용자 차단 해제** 플라이아웃에서 제한된 계정에 대한 세부 정보를 읽습니다. 계정이 손상된 경우에 적절한 조치를 취하는지 확인하기 위해 권장 사항을 검토해야 합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 다음 화면에는 이후 손상을 방지하는 데 도움이 되는 권장 사항이 있습니다. MFA(다단계 인증)를 사용하도록 설정하고 암호를 재설정하는 것이 좋습니다.

   작업을 마쳤으면 **제출** 을 클릭합니다.

6. **예** 를 클릭하여 변경 내용을 확인합니다.

   > [!NOTE]
   > 모든 제한 사항을 사용자에게서 제거하는 데 최대 1시간이 걸릴 수 있습니다.

## <a name="verify-the-alert-settings-for-restricted-users"></a>제한된 사용자에 대한 경고 설정 확인

**전자 메일을 보내지 못하도록 제한된 사용자** 라는 기본 경고 정책은 사용자가 아웃바운드 메일을 보내지 못하도록 차단되었을 때 관리자에게 알립니다. 이러한 설정을 확인하고 알림을 보낼 사용자를 더 추가할 수 있습니다. 경고 정책에 대한 자세한 내용은 [Microsoft 365의 경고 정책](../../compliance/alert-policies.md)을 참조하세요.

> [!IMPORTANT]
> 경고가 작동하려면 감사 로그 검색이 설정되어 있어야 합니다. 자세한 내용은 [감사 로그 검색 설정 및 해제](../../compliance/turn-audit-log-search-on-or-off.md)를 참조하세요.

1. Microsoft 365 Defender 포털에서 **Email & collaboration**(전자 메일 및 공동 작업) \> **Policies & rules**(정책 및 규칙) \> **경고 정책** 으로 이동합니다.

2. **경고 정책** 페이지에서 **User restricted from sending email**(전자 메일 전송이 제한된 사용자)이라는 경고를 찾아 선택합니다. 이름을 기준으로 정책을 정렬하거나 **검색 상자** 를 사용하여 정책을 찾을 수 있습니다.

3. 표시되는 **User restricted from sending email**(전자 메일 전송이 제한된 사용자) 플라이아웃에서 다음 설정을 확인하거나 구성합니다.
   - **상태**: 경고가 ![토글 켬](../../media/scc-toggle-on.png)으로 설정되어 있는지 확인합니다.
   - **전자 메일 받는 사람**: **편집** 을 클릭하고 **받는 사람 편집** 플라이아웃이 나타나면 다음 설정을 확인하거나 구성합니다.
     - **전자 메일 알림 보내기**: 이 항목이 선택되었는지 확인합니다(**설정**).
     - **전자 메일 받는 사람**: 기본값은 **TenantAdmins**(즉, **전역 관리자** 구성원)입니다. 받는 사람을 더 추가하려면 상자의 빈 영역을 클릭합니다. 받는 사람 목록이 표시되면 이름을 입력하여 필터링하고 받는 사람을 선택할 수 있습니다. ![제거 아이콘](../../media/m365-cc-sc-remove-selection-icon.png)을 클릭하여 상자에서 기존 받는 사람을 제거할 수 있습니다. 이름 옆에 있습니다.
     - **일별 알림 제한**: 기본값은 **제한 없음** 이지만 일별 최대 알림 수에 대한 한도를 선택할 수 있습니다.

     작업을 마쳤으면 **저장** 을 클릭합니다.

4. **전자 메일을 보내지 못하도록 제한된 사용자** 플라이아웃으로 돌아가서 **닫기** 를 클릭합니다.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Exchange Online PowerShell을 사용하여 제한된 사용자 목록에서 사용자 보기 및 제거

전자 메일을 보내지 못하도록 제한된 사용자 목록을 보려면 다음 명령을 실행합니다.

```powershell
Get-BlockedSenderAddress
```

특정 사용자에 대한 세부 정보를 보려면 \<emailaddress\>를 그들의 전자 메일 주소로 바꾸고 다음 명령을 실행합니다.

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

자세한 구문 및 매개 변수 정보는 [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress)를 참조하세요.

제한된 사용자 목록에서 사용자를 제거하려면 \<emailaddress\>를 사용자의 전자 메일 주소로 바꾸고 다음 명령을 실행합니다.

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

자세한 구문 및 매개 변수 정보는 [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress)를 참조하세요.
