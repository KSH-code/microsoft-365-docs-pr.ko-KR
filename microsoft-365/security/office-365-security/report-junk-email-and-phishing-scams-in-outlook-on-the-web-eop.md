---
title: 웹에서 정크 메일 및 피싱 Outlook 보고
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 관리자는 Outlook(Outlook Web App)의 기본 제공 정크 메일 및 정크 메일이 아닌 기본 제공 정크 및 피싱 전자 메일 보고 옵션에 대해 Exchange Online 사용자에 대해 이러한 보고 옵션을 사용하지 않도록 설정하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788310"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>웹 사이트에서 Outlook 메일로 정크 및 피싱 전자 메일을 Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

하이브리드 Microsoft 365 인증을 사용하는 Exchange Online 사서함이 있는 조직에서 가음성(스팸으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 전자 메일 허용) 및 피싱 메시지를 EOP(Exchange Online Protection)에 제출할 수 있습니다. [](../../enterprise/hybrid-modern-auth-overview.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

> [!IMPORTANT]
> 사용자 제출에 대해 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 권장하는 것이 좋습니다. 자세한 내용은 보고서 메시지 또는 피싱 보고 추가 기능 사용 을 [참조하세요.](./enable-the-report-message-add-in.md) 사용자 제출 정책을 사용할 수 Outlook 기본 제공 보고 환경은 사용하지 [않는 것이 좋습니다.](./user-submission.md)

- 사서함이 있는 조직의 관리자인 Exchange Online 보안 및 준수 센터의 제출 포털을 & 좋습니다. 자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)

- 관리자는 사용자가 웹에서 Microsoft에 메시지를 보고하는 기능을 사용하지 않도록 설정하거나 Outlook 수 있습니다. 자세한 내용은 이 문서 2부의 웹에서 정크 [Outlook](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 사용 안 하도록 설정 또는 사용 섹션을 참조하십시오.

- 보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다. 자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)

- Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>웹에서 정크 메일 Outlook 사용 안 하도록 설정

기본적으로 사용자는 웹에서 스팸 오판정, 거짓 부정 및 피싱 메시지를 분석하기 위해 Microsoft에 Outlook 수 있습니다. 관리자는 Outlook PowerShell의 웹 사서함 정책에 대한 사용자 Exchange Online 구성하여 사용자가 Microsoft에 스팸 가음성 및 스팸 거짓 부정을 보고하지 못하도록 할 수 있습니다. 사용자가 Microsoft에 피싱 메시지를 보고하는 기능을 사용하지 않도록 설정할 수 없습니다.

### <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 Exchange Online 사용 권한을 할당해야 합니다. 특히 조직 관리 및 받는 사람 관리 역할 그룹에 기본적으로  할당되는  받는 사람 정책 또는 **메일** 받는 사람 역할이 필요합니다.  Exchange Online 역할 그룹에 대한 자세한 내용은 Exchange Online [](/exchange/permissions-exo/permissions-exo) 및 에서 역할 그룹 수정을 [Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)

- 모든 조직에는 OwaMailboxPolicy-Default라는 기본 정책이 있지만 사용자 지정 정책을 만들 수 있습니다. 사용자 지정 정책은 기본 정책 전에 범위가 지정한 사용자에게 적용됩니다. 웹 사서함 정책의 Outlook 대한 자세한 내용은 Outlook 웹 사서함 정책의 [Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- 정크 메일 보고를 사용할 수 없는 경우 웹에서 메시지를 정크 메일로 표시하거나 정크 메일 아님으로 표시하는 Outlook 제거되지는 않습니다. 정크 메일 폴더에서 메시지를 선택하고 정크 메일 아님을 클릭하면 메시지가 받은 편지함으로 다시  \>  이동합니다. 다른 전자 메일 폴더에서 메시지를 선택하고  정크 정크를 클릭하면 메시지가 여전히 정크 메일 \>  폴더로 이동합니다. 더 이상 사용할 수 없는 것은 메시지를 Microsoft에 보고하는 옵션입니다.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>PowerShell Exchange Online 사용하여 웹에서 정크 메일 보고를 사용하지 않도록 설정하거나 Outlook 수 있습니다.

1. 기존 Outlook 사서함 정책 및 정크 메일 보고 상태를 찾으면 다음 명령을 실행합니다.

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. 웹 사이트에서 정크 메일 보고를 Outlook 사용하려면 다음 구문을 사용하세요.

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   이 예에서는 기본 정책에서 정크 메일 보고를 사용하지 않도록 설정합니다.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   이 예에서는 Contoso Managers라는 사용자 지정 정책에서 정크 메일 보고를 사용할 수 있습니다.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

구문과 매개 변수에 대한 자세한 내용은 [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) 및 [Set-OwaMailboxPolicy를 참조하십시오.](/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

웹용 전자 메일에서 정크 메일 보고를 사용하도록 설정하거나 사용하지 않도록 설정 Outlook 다음 단계를 사용하세요.

- PowerShell을 Exchange Online 다음 명령을 실행하고 **ReportJunkEmailEnabled** 속성 값을 검증합니다.

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 영향을 받는 사용자의 사서함을 웹용 Outlook 열고 받은 편지함에서 메시지를 선택하고  정크 정크를 클릭한 다음 메시지를 Microsoft에 보고하라는 메시지가 표시되거나 표시되지 않는지 \>  확인해야 합니다.<sup>\*</sup>

- 영향을 받는 사용자의 사서함을 웹 Outlook 열고, 정크 메일 폴더에서 메시지를 선택하고, 정크 정크를 클릭하고, 메시지를 Microsoft에 보고하라는 메시지가 Microsoft에 보고되어 있는지 또는 표시되지 않는지  \>  확인합니다.<sup>\*</sup>

<sup>\*</sup> 사용자는 메시지를 보고하는 동안 메시지를 보고하라는 메시지를 숨길 수 있습니다. 이 설정을 웹용 웹 Outlook 확인:

1. 웹 **설정** Outlook 아이콘 모든 Outlook ![ ](../../media/owa-settings-icon.png) \> **정크 메일 보기** \> **를 클릭합니다.**
2. 보고 **섹션에서** 값을 확인 합니다. **보고서를 보내기 전에 요청 합니다.**

   ![Outlook 정크 메일 보고 설정에 대한 정보](../../media/owa-junk-email-reporting-options.png)
