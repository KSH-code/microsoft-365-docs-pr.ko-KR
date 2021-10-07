---
title: 고급 메시지 암호화로 암호화된 전자 메일 해지
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 관리자 및 메시지 보낸 사람은 관리자 권한으로 암호화된 특정 전자 메일을 해지할 Office 365 고급 메시지 암호화.
ms.openlocfilehash: 86231857b01cc4f505f19063fe59cd58b75e263b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201820"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>고급 메시지 암호화로 암호화된 전자 메일 해지

전자 메일 해지는 전자 메일 해지의 일부로 Office 365 고급 메시지 암호화. Office 365 고급 메시지 암호화 [E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5(비영리 직원 가격), Office 365 Enterprise E5(비영리 직원 가격 책정)에 포함되어 있습니다 Microsoft 365 Enterprise. 및 Office 365 Education A5. 조직에 Office 365 고급 메시지 암호화 없는 구독이 있는 경우 Microsoft 365 E3, Microsoft 365 E3 Microsoft 365 E5 Compliance(비영리 직원 가격) 또는 Microsoft 365 E3(비영리 직원 가격) 또는 Microsoft 365 E3(비영리 직원 가격) 또는 Office 365 SKU용 Office 365 Advanced Compliance SKU 추가 기능을 사용하여 구입할 수 있습니다.

이 문서는 에 대한 보다 큰 문서 [시리즈의 Office 365 메시지 암호화.](ome.md)

메시지를 Office 365 고급 메시지 암호화 암호화한 경우 Microsoft 365 관리자 또는 메시지를 보낸 사람인 경우 특정 조건에서 메시지를 해지할 수 있습니다. 관리자는 PowerShell을 사용하여 메시지를 해지합니다. 보낸 사람이 사용자로부터 직접 보낸 메시지를 해지할 수 웹용 Outlook. 이 문서에서는 해지가 가능한 상황과 해지 방법을 설명합니다.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>해지할 수 있는 암호화된 전자 메일

받는 사람이 링크 기반의 브랜드가 있는 암호화된 전자 메일을 받은 경우 관리자와 메시지 보낸 사람은 암호화된 전자 메일을 해지할 수 있습니다. 받는 사람이 지원되는 Outlook 클라이언트에서 기본 인라인 환경을 받은 경우 메시지를 해지할 수 없습니다.

받는 사람이 링크 기반 환경 또는 인라인 환경을 받는지 여부는 받는 사람 ID 유형에 따라 다릅니다. Office 365 및 Microsoft 계정 받는 사람(예: outlook.com 사용자)은 지원되는 Outlook 클라이언트에서 인라인 환경을 사용할 수 있습니다. Gmail 및 Yahoo 받는 사람과 같은 다른 모든 받는 사람 유형은 링크 기반 환경을 제공합니다.

관리자와 메시지 보낸 사람이 해당 메시지에서 직접 적용한 암호화를 사용하여 암호화된 메시지를 해지할 웹용 Outlook. 예를 들어 암호화 전용 옵션을 사용하여 암호화된 메시지입니다.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot showing Encrypt Only option in 웹용 Outlook.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>해지된 암호화된 전자 메일의 받는 사람 환경

전자 메일이 해지된 후 받는 사람은 Office 365 메시지 암호화 포털을 통해 암호화된 전자 메일에 액세스할 때 "보낸 사람이 메시지를 해지했습니다."라는 오류가 표시됩니다.

![해지된 암호화된 전자 메일을 보여 주는 스크린샷](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>전송한 암호화된 메시지를 해지하는 방법

공유 계정(예: gmail.com 또는 공유 계정)을 사용하는 단일 받는 사람에게 보낸 메일을 yahoo.com. 즉, 링크 기반 환경을 수신한 단일 받는 사람에게 보낸 전자 메일을 해지할 수 있습니다.

Office 365 또는 학교 계정을 사용하는 받는 사람 또는 Microsoft 계정을 사용하는 사용자(예: Office 365 Microsoft 365 계정)에게 보낸 메일을 해지할 outlook.com 없습니다. 

전송한 암호화된 메시지를 해지하기 위해 다음 단계를 완료합니다.

1. 보낸 웹용 Outlook 보낸 메시지 **폴더에서** 해지할 메시지를 찾아 이동합니다.

   메일이 해지될 수 있는 경우 메시지 맨 위에 "외부 액세스 제거" 링크가 표시됩니다.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="2013에서 해지하려는 암호화된 메일을 보여 웹용 Outlook.":::

2. 외부 **액세스 제거를 클릭하여** 메시지를 취소합니다.

   메시지에 해당 상태가 해지된 것으로 표시됩니다.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="해지된 암호화된 메시지를 보여 웹용 Outlook.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>관리자 권한으로 암호화된 메시지를 해지하는 방법

Microsoft 365 관리자는 다음과 같은 일반적인 단계에 따라 적합한 암호화된 전자 메일을 해지합니다.

- 전자 메일의 메시지 ID를 얻습니다.
- 메시지를 해지할 수 있는지 확인
- 메일을 해지합니다.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>1단계. 전자 메일의 메시지 ID 얻기

암호화된 메일을 해지하기 전에 메일의 메시지 ID를 수집합니다. MessageId는 일반적으로 다음 형식입니다.

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

해지할 전자 메일의 메시지 ID를 찾는 방법에는 여러 가지가 있습니다. 이 섹션에서는 두 가지 옵션에 대해 설명하지만 ID를 제공하는 모든 메서드를 사용할 수 있습니다.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>보안 및 준수 센터의 메시지 추적을 사용하여 해지하려는 전자 메일의 메시지 ID를 &amp; 식별하려는 경우

1. 보안 및 준수 센터에서 새 메시지 추적을 사용하여 보낸 [& 검색합니다.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)

2. 전자 메일을 들은 후 메시지를 선택하여 메시지 추적 세부 **정보** 창을 표시 합니다. 추가 **정보를 확장하여** 메시지 ID를 찾습니다.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>보안 및 준수 센터의 메시지 암호화 보고서를 사용하여 Office 전자 메일의 메시지 ID를 &amp; 식별합니다.

1. 보안 및 &amp; 준수 센터에서 메시지 암호화 **보고서로 이동합니다.** 이 보고서에 대한 자세한 내용은 보안 및 준수 센터에서 전자 메일 [보안 보고서 &amp; 보기를 참조하세요.](../security/office-365-security/view-email-security-reports.md)

2. 세부 **정보 보기 테이블을** 선택하고 해지할 메시지를 식별합니다.

3. 메시지를 두 번 클릭하여 메시지 ID가 포함된 세부 정보를 볼 수 있습니다.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>2단계. 메일이 해지 가능한지 확인

메시지를 해지할 수 있는지 확인을 위해 보안 및 준수 센터의 세부 정보 표에  있는 암호화 보고서에 해지 상태 필드가 표시되는지 &amp; 여부를 확인해야 합니다.

전자 메일 메시지를 사용하여 특정 전자 메일 메시지를 해지할 수 Windows PowerShell 다음 단계를 완료합니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. 다음과 Get-OMEMessageStatus cmdlet을 실행합니다.

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   이 명령은 메시지의 제목과 메시지를 취소할 수 있는지 여부를 반환합니다. 예를 들면 다음과 같습니다.

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>3단계. 메일 해지

해지할 전자 메일의 메시지 ID를 알고 메시지가 해지가 가능한지 확인한 후 보안 및 준수 센터를 사용하여 전자 메일을 해지하거나 &amp; Windows PowerShell.

보안 및 준수 센터를 사용하여 메시지를 &amp; 해지

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 보안 및 준수 & 연결합니다.

2. 암호화 **보고서의** 메시지에 대한 **세부** 정보 표에서 메시지 **취소를 선택하십시오.**

전자 메일을 사용하여 전자 메일을 Windows PowerShell cmdlet을 Set-OMEMessageRevocation.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell)커넥트 Exchange Online 합니다.

2. 다음과 Set-OMEMessageRevocation cmdlet을 실행합니다.

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 전자 메일이 해지 지 여부를 확인 하 고 다음과 같이 Get-OMEMessageStatus cmdlet을 실행 합니다.

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    해지에 성공하면 cmdlet은 다음 결과를 반환합니다.  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>자세한 내용은 Office 365 고급 메시지 암호화

- [Office 365 고급 메시지 암호화](ome-advanced-message-encryption.md)

- [Office 365 고급 메시지 암호화 - 전자 메일 만료](ome-advanced-expiration.md)

- [메시지 정책 및 규정 준수 서비스 설명](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)