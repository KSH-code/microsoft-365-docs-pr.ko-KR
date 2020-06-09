---
title: 제한된 사용자 포털에서 차단된 사용자 제거
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 관리자는 Office 365의 제한된 사용자 포털에서 사용자를 제거 하는 방법을 알아볼 수 있습니다. 사용자는 일반적으로 계정 손상의 결과로 아웃바운드 스팸 전송을 위해 제한된 사용자 포털에 추가됩니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9e28550c67e20466b18b17d8b49fb1b68997cc4
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617365"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Office 365의 제한된 사용자 포털에서 차단된 사용자 제거

사용자가 [서비스 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 또는 [아웃바운드 스팸 정책](configure-the-outbound-spam-policy.md)에 지정된 아웃바운드 전송 제한 중 하나를 초과하는 경우 전자 메일 보내기가 제한되지만 계속 전자 메일을 받을 수 있습니다.

보안 및 규정 준수 센터의 제한된 사용자 포털에 사용자가 추가됩니다. 사용자가 전자 메일을 보내려고 하면 메시지가 오류 코드 [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 및 다음 텍스트와 함께 배달 못 함 보고서(NDR 또는 바운스 메시지라고도 함)로 반환됩니다.

> "유효한 보낸 사람으로 인식되지 않았기 때문에 메시지를 배달할 수 없습니다. 가장 일반적인 이유는 전자 메일 주소가 스팸 메일을 보내는 것으로 의심어서 더 이상 전자 메일을 보낼 수 없는 경우입니다.  도움이 필요하면 전자 메일 관리자에게 문의하세요. 원격 서버에서 '550 5.1.8 액세스가 거부되었습니다. 잘못된 아웃 바운드 보낸 사람"이 반환되었습니다.

관리자는 보안 및 규정 준수 센터 또는 Exchange Online PowerShell에서 제한된 보낸 사람 포털의 사용자를 제거할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다. **제한된 사용자** 페이지로 직접 이동하려면 <https://protection.office.com/restrictedusers>를 사용합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 제한된 사용자 포털에서 사용자를 제거하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원이어야 합니다. 제한된 사용자 포털에 대한 읽기 전용 액세스를 위해서는 **보안 읽기 권한자** 역할 그룹의 구성원이어야 합니다. 보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

- 아웃바운드 전자 메일 제한을 초과 하는 보낸 사람은 손상된 계정을 나타냅니다. 제한된 사용자 포털에서 사용자를 제거하기 전에 해당 계정을 다시 제어하기 위해 필요한 단계를 수행해야 합니다. 자세한 내용은 [Office 365에서 손상된 전자 메일 계정에 응답](responding-to-a-compromised-email-account.md)을 참조하세요.

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>보안 및 규정 준수 센터를 사용하여 제한 된 사용자 목록에서 사용자 제거

1. 보안 및 규정 준수 센터에서 **위협 관리** \> **검토** \> **제한된 사용자**로 이동합니다.

2. 차단을 해제하려는 사용자를 찾아 선택합니다. **동작** 열에서 **차단 해제**를 클릭합니다.

3. 플라이아웃하면 전송이 제한된 계정에 대한 세부 정보로 이동합니다. 계정이 실제로 손상될 경우에 적절한 조치를 취하는지 확인하기 위해 권장 사항을 검토해야 합니다. 완료되면 **다음**을 선택합니다.

4. 다음 화면에는 이후 손상을 방지하는 데 도움이 되는 권장 사항이 있습니다. MFA(다단계 인증)를 사용하도록 설정하고 암호를 변경하는 것이 좋습니다. 작업이 완료되면 **사용자 차단 해제**를 클릭합니다.

5. **예**를 클릭하여 변경 내용을 확인합니다.

   > [!NOTE]
   > 제한이 제거되기까지 30분 정도 걸릴 수 있습니다.

## <a name="verify-the-alert-settings-for-restricted-users"></a>제한된 사용자에 대한 경고 설정 확인

**전자 메일을 보내지 못하도록 제한된 사용자**라는 기본 경고 정책은 사용자가 아웃바운드 메일을 보내지 못하도록 차단되었을 때 관리자에게 알립니다. 이러한 설정을 확인하고 알림을 보낼 사용자를 더 추가할 수 있습니다. 경고 정책에 대한 자세한 내용은 [보안 및 규정 준수 센터의 경고 정책](../../compliance/alert-policies.md)을 참조하세요.

> [!IMPORTANT]
> 경고가 작동하려면 감사 로그 검색이 설정되어 있어야 합니다. 자세한 내용은 [감사 로그 검색 설정 및 해제](../../compliance/turn-audit-log-search-on-or-off.md)를 참조하세요.

1. 보안 및 규정 준수 센터에서 **경고** \> **경고 정책**으로 이동합니다.

2. **전자 메일을 보내지 못하도록 제한된 사용자** 경고를 찾아 선택합니다.

3. 플라이아웃이 나타나면 다음 설정을 확인하거나 구성합니다.

   - **상태**: 경고가 ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)으로 설정되어 있는지 확인합니다.

   - **전자 메일 받는 사람**: **편집**을 클릭하고 **받는 사람 편집** 플라이아웃이 나타나면 다음 설정을 확인하거나 구성합니다.

     - **전자 메일 알림 보내기**: 확인란이 선택(**설정**)되어 있는지 확인합니다.

     - **전자 메일 받는 사람**: 기본값은 **TenantAdmins**(즉, **전역 관리자** 구성원)입니다. 받는 사람을 더 추가하려면 상자의 빈 영역을 클릭합니다. 받는 사람 목록이 표시되면 이름을 입력하여 필터링하고 받는 사람을 선택할 수 있습니다. 해당 이름 옆의 ![제거 아이콘](../../media/scc-remove-icon.png)을 클릭하여 상자에서 기존의 받는 사람을 제거할 수 있습니다.

     - **일별 알림 제한**: 기본값은 **제한 없음**이지만 일별 최대 알림 수에 대한 한도를 선택할 수 있습니다.

     작업을 마쳤으면 **저장**을 클릭합니다.

4. **전자 메일을 보내지 못하도록 제한된 사용자** 플라이아웃으로 돌아가서 **닫기**를 클릭합니다.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Exchange Online PowerShell을 사용하여 제한된 사용자 목록에서 사용자 보기 및 제거

전자 메일을 보내지 못하도록 제한된 사용자 목록을 보려면 다음 명령을 실행합니다.

```powershell
Get-BlockedSenderAddress
```

특정 사용자에 대한 세부 정보를 보려면 \<emailaddress\>를 그들의 전자 메일 주소로 바꾸고 다음 명령을 실행합니다.

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

자세한 구문 및 매개 변수 정보는 [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress)를 참조하세요.

제한된 사용자 목록에서 사용자를 제거하려면 \<emailaddress\>를 그들의 전자 메일 주소로 바꾸고 다음 명령을 실행합니다.

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

자세한 구문 및 매개 변수 정보는 [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress)를 참조하세요.
