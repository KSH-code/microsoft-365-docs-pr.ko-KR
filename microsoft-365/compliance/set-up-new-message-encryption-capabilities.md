---
title: 새 메시지 암호화 기능 설정하기
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 조직 내부나 조직 외부의 사람과 보호된 전자 메일을 사용하여 통신할 수 있게 하는 새 Office 365 메시지 암호화 기능에 대해 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
ms.openlocfilehash: d76b350736ead1620f2dc52bfed607ec2c9f7893
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188100"
---
# <a name="set-up-new-message-encryption-capabilities"></a>새 메시지 암호화 기능 설정하기

새 Office 365 메시지 암호화(OME) 기능을 사용하면 조직은 모든 장치에 있는 모든 사용자와 보호된 전자 메일을 공유할 수 있습니다. 사용자는 다른 Microsoft 365 조직은 물론, Outlook.com, Gmail 및 기타 전자 메일 서비스를 사용하지만, 고객이 아닌 사용자와도 보호된 메시지를 주고받을 수 있습니다.

조직에서 새 OME 기능을 사용할 수 있는지 여부는 아래 단계를 실시하여 확인하세요.

## <a name="verify-that-azure-rights-management-is-active"></a>Azure 권한 관리의 활성화 여부 확인

새 OME 기능은 암호화 및 액세스 제어를 통한 전자 메일 및 문서 보호를 위해 [Azure Information Protection](/azure/information-protection/what-is-azure-rms)이 사용하는 기술인 [Azure 권한 관리 서비스(Azure RMS)](/azure/information-protection/what-is-information-protection)에 있는 보호 기능을 활용합니다.

새 OME 기능을 사용하기 위해서는 조직의 테넌트에서 [Azure 권한 관리](/azure/information-protection/what-is-azure-rms)가 활성화되어 있기만 하면 됩니다. 활성화된 경우에는 Microsoft 365가 새 OME 기능을 자동으로 활성화하므로 다른 작업이 필요 없습니다.

또한 Azure RMS는 대부분의 적격 계획에 대해 자동으로 활성화되므로 이와 관련하여 아무 작업도 수행하지 않아도 됩니다. 자세한 내용은 [Azure Rights Management 활성화](/azure/information-protection/activate-service)를 참조하세요.

> [!IMPORTANT]
> Exchange Online에서 AD RMS(Active Directory Rights Management)를 사용하는 경우 새 OME 기능을 사용하려면 먼저 [Azure Information Protection으로 마이그레이션](/azure/information-protection/migrate-from-ad-rms-to-azure-rms)해야 합니다. OME는 AD RMS와 호환되지 않습니다.

자세한 내용은 다음을 참조하세요.

- 현재의 구독에 Azure Information Protection이 포함되었는지 여부를 확인하려면 [새 OME 기능을 사용하기 위해서는 어떤 구독이 필요한가요?](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-)를 참조하세요.
- 적절한 구독을 구입하기 위해서는 [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)에서 자세한 내용을 참조하세요.

### <a name="manually-activating-azure-rights-management"></a>Azure AD Rights Management 수동 활성화

Azure RMS를 비활성화로 설정한 경우나, 어떤 이유에서 자동으로 활성화되지 못한 경우에는 수동으로 활성화할 수 있습니다.

- **Microsoft 365 관리 센터**: [관리 센터에서 Azure 권한 관리 활성화 방법](/azure/information-protection/activate-office365)을 확인하세요.
- **Azure Portal**: [Azure Portal에서 Azure 권한 관리 활성화 방법](/azure/information-protection/activate-azure)을 확인하세요.

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Azure Information Protection 테넌트 키 관리 구성

이 단계는 선택 사항입니다. 기본 설정은 Azure Information Protection용 루트 키를 Microsoft가 관리하도록 구성하는 것이고, 대부분의 조직에 권장되는 모범 사례입니다. 이렇게 설정된 경우에는 별도의 작업이 필요 없습니다.

여러 가지 이유에서 직접 사용자 고유 루트 키(BYOK(Bring Your Own Key)라고도 함)를 생성하고 관리해야 할 필요가 있는 경우가 있습니다. 예를 들면, 규정 준수 요구 사항을 충족하기 위한 경우입니다. 이러한 경우에는 새 OME 기능을 설정하기 전에 필수 단계를 먼저 완료하는 것을 권장합니다. 자세한 내용은 [Azure Information Protection 테넌트 키 계획 및 구현](/information-protection/plan-design/plan-implement-tenant-key)을 참조하세요.

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Exchange Online PowerShell에서 새 OME 구성 확인

[Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)에서 새 OME 기능을 사용할 수 있도록 Microsoft 365 테넌트가 올바르게 구성되었는지 확인할 수 있습니다.

1. Microsoft 365 테넌트에서 전역 관리자 권한을 사용하여 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)합니다.

2. Get-IRMConfiguration cmdlet을 실행합니다.

     AzureRMSLicensingEnabled 매개 변수의 값이 $True인지 확인합니다. 이 값은 테넌트에서 OME가 구성되었음을 나타냅니다. 그렇지 않은 경우에는 AzureRMSLicensingEnabled의 값을 $True으로 설정하여 OME을 사용할 수 있도록 설정합니다.

3. 다음 구문을 사용하여 Test-IRMConfiguration cmdlet을 실행합니다.

   ```powershell
   Test-IRMConfiguration [-Sender <email address> -Recipient <email address>]
   ```

   **예제**:

   ```powershell
   Test-IRMConfiguration -Sender securityadmin@contoso.com -Recipient securityadmin@contoso.com
   ```

   - 보낸 사람 및 받는 사람의 경우 Microsoft 365 테넌트 사용자의 전자 메일 주소를 사용합니다.

     결과는 다음과 같이 표시됩니다.

     ```console
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - *Contoso* 자리에 조직 이름이 표시됩니다.

   - 기본 템플릿 이름은 위에 표시된 이름과 다를 수 있습니다. 자세한 내용은 [Azure Information Protection의 템플릿 구성 및 관리](/azure/information-protection/configure-policy-templates)를 참조하세요.

4. Remove-PSSession cmdle을 실행하여 권한 관리 서비스와의 연결을 해제합니다.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>다음 단계: 새 OME 기능을 사용하기 위한 메일 흐름 규칙 정의

조직에서 전자 메일을 암호화하기 위한 사전 구성 메일 흐름 규칙이 있는 경우에는 새 OME 기능을 사용할 수 있도록 기존 규칙을 업데이트해야 합니다. 새 배포의 경우 새 메일 흐름 규칙을 만들어야 합니다.

> [!IMPORTANT]
> 기존의 메일 흐름 규칙을 업데이트하지 않으면 사용자는 계속해서 새 OME 환경이 아닌 이전의 HTML 첨부 파일 형식의 암호화된 메일을 받게 됩니다.

메일 흐름 규칙은 어떤 전자 메일을 암호화하고, 어떤 메시지의 암호화를 제거할지에 대한 조건을 결정합니다. 규칙에 대한 동작을 설정하면 규칙 조건에 일치하는 모든 메시지가 전송 시에 암호화됩니다.

OME에 대한 메일 흐름 규칙을 만드는 단계에 대한 내용은 [Office 365에서 전자 메일 메시지를 암호화하기 위한 메일 흐름 규칙 정의](define-mail-flow-rules-to-encrypt-email.md)를 참조하세요.

기존 규칙을 업데이트하여 새 OME 기능을 사용하려면 다음을 실행합니다.

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339)에서 **관리 센터 > Exchange** 로 이동합니다.
2. Exchange 관리 센터에서 **메일 흐름 > 규칙** 으로 이동합니다.
3. 각 규칙에 대해 **다음** 을 실행합니다.
    - **메시지 보안 수정** 을 선택합니다.
    - **365 메시지 암호화 및 권한 보호 적용** 을 선택합니다.
    - 목록에서 RMS 템플릿을 선택합니다.
    - **저장** 을 선택합니다.
    - **확인** 을 선택합니다.
