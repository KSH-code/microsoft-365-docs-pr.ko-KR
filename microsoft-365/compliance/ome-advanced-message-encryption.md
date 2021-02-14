---
title: 고급 메시지 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 고급 메시지 암호화는 관리자가 보호된 메시지로 더 많은 작업을 할 수 있도록 하여 조직이 규정 준수 의무를 충족하는 데 도움이 됩니다.
ms.openlocfilehash: 0e28bd283b6a7d1666d5db9b71040d2f377adffe
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626896"
---
# <a name="advanced-message-encryption"></a>고급 메시지 암호화

Office 365 고급 메시지 암호화는 [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5(비영리 직원 가격), Office 365 Enterprise E5(비영리 직원 가격 책정) 및 Office 365 Education A5에 포함되어 있습니다. 조직에 Office 365 고급 메시지 암호화가 포함되어 있지 않은 구독이 있는 경우 Microsoft 365 E3용 Microsoft 365 E5 준수 SKU 추가 기능으로 구매할 수 있습니다. Microsoft 365 E3(비영리 직원 가격 책정) 또는 Microsoft 365 E3, Microsoft 365 E3(비영리 직원 가격), Office 365 SKU 또는 Microsoft 365 E5/A5 정보 보호 및 거버넌스 SKU 추가 기능용 Office 365 고급 준수 SKU 추가 기능

고급 메시지 암호화는 고객이 외부 받는 사람에 대한 보다 유연한 제어 및 암호화된 전자 메일에 대한 액세스가 필요한 준수 의무를 충족하는 데 도움이 됩니다. Office 365의 고급 메시지 암호화를 사용하면 자동 정책을 사용하여 조직 외부에서 공유되는 중요한 전자 메일을 제어할 수 있습니다. 이러한 정책을 구성하여 PII, 재무 또는 상태 식별과 같은 중요한 정보 유형을 식별하거나 키워드를 사용하여 보호를 강화할 수 있습니다. 정책을 구성한 후 정책을 사용자 지정 브랜드 전자 메일 서식 파일과 페어링한 다음 정책에 맞는 전자 메일에 대한 추가 제어를 위한 만료 날짜를 추가합니다. 또한 관리자는 보안 웹 포털을 통해 외부에서 액세스하는 암호화된 전자 메일에 대한 액세스 권한을 제한할 수 있습니다.

외부 받는 사람에게 보낸 전자 메일의 만료 날짜만 해지하고 설정할 수 있습니다.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Office 365 고급 메시지 암호화 시작

다음 문서에서는 고급 메시지 암호화를 설정하고 사용하는 방법을 설명하고 있습니다.

조직에 Office 365 고급 메시지 암호화가 포함된 구독이 있어야 합니다. 지원되는 구독에 대한 자세한 내용은 메시지 정책 및 규정 준수 서비스 [설명을 참조하십시오.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

Office 365 메시지 암호화를 아직 설정하지 않은 경우 새 [Office 365](set-up-new-message-encryption-capabilities.md)메시지 암호화 기능 설정을 참조하세요.

고급 메시지 암호화를 사용하는 경우 단일 브랜랜드 템플릿으로 제한되지 않습니다. 대신 여러 브랜드 템플릿을 만들고 사용할 수 있습니다. 자세한 내용은 암호화된 메시지에 조직의 브랜드 [추가를 참조하세요.](add-your-organization-brand-to-encrypted-messages.md)

[Office 365 고급](ome-advanced-expiration.md)메시지 암호화로 암호화된 전자 메일의 만료 날짜를 설정합니다. 보안 웹 포털을 통해 암호화된 전자 메일에 대한 액세스를 만료하여 보호를 강화하는 자동 정책으로 조직 외부에서 공유되는 중요한 전자 메일을 제어합니다.

[Office 365 고급](revoke-ome-encrypted-mail.md)메시지 암호화로 암호화된 전자 메일을 해지합니다. 조직 외부에서 공유되는 중요한 전자 메일을 제어하고 암호화된 전자 메일로 보안 웹 포털을 통해 액세스를 해지하여 보호 기능을 향상합니다.  

Office 365 고급 메시지 암호화를 사용하면 사용자 지정 브랜드 템플릿을 적용할 때 언제든지 Microsoft는 서식 파일을 적용하는 메일 흐름 규칙에 맞는 래퍼를 전자 메일에 적용합니다. 사용자는 포털을 통해 받는 메시지에만 메시지를 해지하고 만료 날짜를 적용할 수 있습니다. 즉, 사용자 지정 브랜드 템플릿이 적용된 전자 메일입니다. 자세한 정보 및 예제는 모든 외부 받는 사람이 OME 포털을 사용하여 암호화된 메일을 [읽는지 확인의 지침을 참조하세요.](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)
