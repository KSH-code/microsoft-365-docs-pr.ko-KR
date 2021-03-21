---
title: Office 365 고급 메시지 암호화로 암호화 된 전자 메일의 만료 날짜 설정
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 고급 메시지 암호화를 사용하여 사용자 지정 브랜드 템플릿을 통해 전자 메일의 만료 날짜를 설정하여 전자 메일 보안을 확장합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927788"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Office 365 고급 메시지 암호화로 암호화 된 전자 메일의 만료 날짜 설정

Office 365 고급 메시지 암호화는 [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5(비영리 직원 가격), Office 365 Enterprise E5(비영리 직원 가격 책정) 및 Office 365 Education A5에 포함되어 있습니다. 조직에 Office 365 고급 메시지 암호화를 포함하지 않는 구독이 있는 경우 Microsoft 365 E3, Microsoft 365 E3(비영리 직원 가격) 또는 Microsoft 365 E3, Microsoft 365 E3(비영리 직원 가격 책정) 또는 Office 365 SKU용 Office 365 고급 준수 SKU 추가 기능으로 구매할 수 있습니다.

사용자가 OME 포털을 사용하여 암호화된 전자 메일에 액세스하는 외부 받는 사람에게 보내는 전자 메일에 메시지 만료를 사용할 수 있습니다. 받는 사람이 OME 포털을 사용하여 조직의 만료 날짜를 지정하는 사용자 지정 브랜드 템플릿을 사용하여 조직에서 보낸 암호화된 전자 메일을 보고 회신하게 Windows PowerShell.

Office 365 전역 관리자는 조직의 전자 메일 메시지 모양을 사용자 지정하기 위해 회사 브랜드를 적용할 때 이러한 전자 메일 메시지의 만료를 지정할 수도 있습니다. Office 365 고급 메시지 암호화를 사용하면 조직에서 보낸 암호화된 전자 메일에 대해 여러 템플릿을 만들 수 있습니다. 템플릿을 사용하여 받는 사람이 사용자가 보낸 메일에 액세스할 수 있는 기간을 제어할 수 있습니다.

최종 사용자가 만료 날짜가 설정된 메일을 받으면 래퍼 전자 메일에 만료 날짜가 표시됩니다. 사용자가 만료된 메일을 열려고 하는 경우 OME 포털에 오류가 나타납니다.

외부 받는 사람에게만 전자 메일의 만료 날짜를 설정할 수 있습니다.

Office 365 고급 메시지 암호화를 사용하면 사용자 지정 브랜드를 적용할 때 언제든지 Office 365에서 템플릿을 적용하는 메일 흐름 규칙에 맞는 전자 메일에 래퍼를 적용합니다. 또한 사용자 지정 브랜드를 사용하는 경우 만료만 사용할 수 있습니다.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>PowerShell을 사용하여 메일 만료를 강제로 하는 사용자 지정 브랜징 템플릿 만들기

1. 조직에서 전역 관리자 권한이 있는 계정을 사용하여 [Exchange Online PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) 연결합니다.

2. cmdlet을 New-OMEConfiguration 실행합니다.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

여기서,

- `Identity` 은 사용자 지정 서식 파일 이름입니다.

- `ExternalMailExpiryInDays` 메일이 만료되기 전에 받는 사람이 메일을 유지할 수 있는 기간(일)을 식별합니다. 1~730일 사이의 값을 사용할 수 있습니다.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Office 365 고급 메시지 암호화에 대한 자세한 정보

- [Office 365 고급 메시지 암호화](ome-advanced-message-encryption.md)

- [Office 365 고급 메시지 암호화로 암호화된 전자 메일 취소](revoke-ome-encrypted-mail.md)

- [메시지 정책 및 규정 준수 서비스 설명](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)