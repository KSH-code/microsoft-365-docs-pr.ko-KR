---
title: 웹용 Outlook에서 정크 및 피싱 전자 메일 보고
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online의 Outlook 웹 (Outlook Web App)에서 기본 제공 정크 메일, 정크 메일이 아닌 피싱 메일로 보고 옵션, 사용자를 위해 이러한 보고 옵션을 사용 하지 않도록 설정 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 1ec226259ccb3dac9a01ee8d4c5fc635c0fc5702
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206481"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Exchange Online의 웹용 Outlook에서 정크 메일 및 피싱 메일로 신고

Exchange Online의 사서함이 있는 Microsoft 365 조 직에서는 웹에서 Outlook (이전의 Outlook Web App)의 기본 제공 보고 옵션을 사용 하 여 가양성 (스팸으로 표시 된 전자 메일), 거짓 네거티브 (잘못 된 전자 메일 허용) 및 EOP (Exchange Online Protection)에 대 한 피싱 메시지를 제출할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- Exchange Online 사서함을 사용 하는 조직의 관리자 인 경우 보안 & 준수 센터에서 전송 포털을 사용 하는 것이 좋습니다. 자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.

- 관리자는 사용자가 웹용 Outlook에서 Microsoft에 메시지를 보고 하는 기능을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 자세한 내용은이 항목 뒷부분에 나오는 [웹용 Outlook에서 정크 메일 보고 사용 안 함 또는 사용](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 섹션을 참조 하십시오.

- 보고 된 메시지가 사용자가 지정한 사서함으로 복사 되거나 리디렉션되도록 구성할 수 있습니다. 자세한 내용은 [Exchange Online의 스팸 및 피싱 메시지에 대 한 사용자 제출을 위한 사서함 지정](user-submission.md)을 참조 하세요.

- Microsoft에 메시지를 보고 하는 방법에 대 한 자세한 내용은 [microsoft에 메시지 및 파일 보고서](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>웹용 Outlook에서 스팸 및 피싱 메시지 보고

1. 정크 메일을 제외한 받은 편지함 또는 다른 모든 전자 메일 폴더의 메시지에 대해 다음 방법 중 하나를 사용 하 여 스팸 및 피싱 메시지를 보고 합니다.

   - 메시지를 선택 하 고 도구 모음에서 **정크 메일** 을 클릭 한 다음 **정크** 또는 **피싱**을 선택 합니다.

     ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/owa-report-junk.png)

   - 하나 이상의 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크 메일로 표시**를 선택 합니다.

2. 대화 상자가 나타나면 **보고서**를 클릭 합니다. 생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.

   ![정크 메일로 신고 대화 상자](../../media/owa-report-as-junk-dialog.png)

   ![피싱 메일로 신고 대화 상자](../../media/owa-report-as-phishing-dialog.png)

3. 선택한 메시지가 분석을 위해 Microsoft로 전송 됩니다. 메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>웹용 Outlook의 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지가 보고 되도록 합니다.

1. 정크 메일 폴더에서 다음 방법 중 하나를 사용 하 여 스팸 가양성 또는 피싱 메시지를 보고 합니다.

   - 메시지를 선택 하 고 도구 모음에서 **정크 메일** 아님으로 클릭 한 다음 **정크** 또는 **피싱**아님을 선택 합니다.

     ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/owa-report-not-junk.png)

   - 하나 이상의 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크 메일 아님으로 표시**를 선택 합니다.

2. 대화 상자가 나타나면 정보를 읽고 **보고서**를 클릭 합니다. 생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.

   ![정크 메일 아님으로 보고 대화 상자](../../media/owa-report-as-not-junk-dialog.png)

   ![피싱 메일로 신고 대화 상자](../../media/owa-report-as-phishing-dialog.png)

3. 선택한 메시지가 분석을 위해 Microsoft로 전송 됩니다. 메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>웹용 Outlook에서 정크 메일 보고를 사용 하지 않도록 설정 하거나 사용

기본적으로 사용자는 웹용 Outlook에서 분석을 위해 Microsoft에 가짜 긍정, 거짓 네거티브 및 피싱 메시지를 보고할 수 있습니다. 관리자는 Exchange Online PowerShell에서 웹 사서함 정책에 대 한 Outlook을 구성 하 여 사용자가 스팸 가양성 및 스팸 거짓 네거티브를 Microsoft에 보고 하지 못하도록 할 수 있습니다. 사용자가 피싱 메시지를 Microsoft에 보고 하는 기능을 사용 하지 않도록 설정할 수 없습니다.

### <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.

- 이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 특히 **조직 관리** 및 **받는 사람 관리** 역할 그룹에 기본적으로 할당 되는 **받는 사람 정책** 또는 **메일 받는 사람** 역할이 Exchange Online에 있어야 합니다. Exchange Online의 역할 그룹에 대 한 자세한 내용은 [Exchange online에서 역할 그룹 수정을](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)참조 하십시오.

- 모든 조직에는 Set-owamailboxpolicy 라는 기본 정책이 있지만 사용자 지정 정책을 만들 수 있습니다. 사용자 지정 정책은 기본 정책 이전의 범위 사용자에 게 적용 됩니다. 웹 사서함 정책의 Outlook에 대 한 자세한 내용은 [Exchange Online의 웹 사서함 정책에서 outlook](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)을 참조 하십시오.

- 정크 메일 보고를 사용 하지 않도록 설정 해도 해당 메시지를 웹용 Outlook에서 정크 메일로 표시 하는 기능이 제거 되지 않습니다. 정크 메일 폴더에서 메시지를 선택 하는 경우 **정크 메일이** 아닌 정크 메일이 아닌 클릭 \> **Not junk** 해도 메시지를 다시 받은 편지 함으로 이동 합니다. 다른 전자 메일 폴더에서 메시지를 선택 하 고 **정크** \> **정크** 을 클릭 해도 메시지가 정크 메일 폴더로 이동 됩니다. 더 이상 사용할 수 없는 작업은 Microsoft에 메시지를 보고 하는 옵션입니다.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>웹에서 Outlook에서 정크 메일 보고를 사용 하지 않도록 설정 하거나 사용 하도록 설정 하려면 Exchange Online PowerShell을 사용 합니다.

1. 웹 사서함 정책 및 정크 메일 보고 상태에 대 한 기존 Outlook을 찾으려면 다음 명령을 실행 합니다.

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. 웹용 Outlook에서 정크 메일 보고를 사용 하지 않도록 설정 하거나 사용 하도록 설정 하려면 다음 구문을 사용 합니다.

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   이 예에서는 기본 정책에서 정크 메일 보고를 사용 하지 않도록 설정 합니다.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   이 예에서는 Contoso 관리자 라는 사용자 지정 정책에서 정크 메일 보고를 사용 하도록 설정 합니다.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

구문과 매개 변수에 대 한 자세한 내용은 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) 및 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)를 참조 하십시오.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

웹용 Outlook에서 정크 메일 보고를 사용 하거나 사용 하지 않도록 설정 했는지 확인 하려면 다음 단계 중 하나를 사용 합니다.

- Exchange Online PowerShell에서 다음 명령을 실행 하 고 **ReportJunkEmailEnabled** 속성 값을 확인 합니다.

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 영향 받는 사용자의 사서함을 웹에서 열고, 받은 편지함에서 메시지를 선택 하 고, **정크** \> **메일** 을 클릭 하 고, Microsoft에 게 메시지를 보고할지 묻는 메시지가 표시 되는지 확인 합니다.<sup>\*</sup>

- 영향을 받는 사용자의 사서함을 웹에서 열고 정크 메일 폴더에서 메시지를 선택 하 고 **정크** 메일로 확인을 클릭 하 \> **Junk** 고 Microsoft에 게 메시지를 보고할지 여부를 묻는 메시지가 표시 되는지 여부를 결정 합니다.<sup>\*</sup>

<sup>\*</sup>사용자는 메시지를 보고 하는 동안 메시지를 보고 하 라는 메시지가 표시 되지 않도록 숨길 수 있습니다. 웹용 Outlook에서이 설정을 확인 하려면:

1. **Settings** ![ 웹 설정 아이콘의 outlook 설정을 클릭 하 여 ](../../media/owa-settings-icon.png) \> **모든 outlook 설정** \> **정크 메일**을 봅니다.
2. **보고** 섹션 **에서 다음 값**을 확인 합니다.

   ![웹용 Outlook 정크 메일 보고 설정](../../media/owa-junk-email-reporting-options.png)
