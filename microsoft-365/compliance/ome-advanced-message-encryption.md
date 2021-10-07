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
ms.localizationpriority: medium
ms.date: 08/11/2021
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 고급 메시지 암호화는 관리자가 보호된 메시지로 더 많은 작업을 할 수 있도록 하여 조직이 규정 준수 의무를 충족하는 데 도움이 됩니다.
ms.openlocfilehash: 9e0f1933d68ba696e6446b321857eb3f6836f378
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197560"
---
# <a name="advanced-message-encryption"></a>고급 메시지 암호화

Office 365 고급 메시지 암호화 [E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5(비영리 직원 가격), Office 365 Enterprise E5(비영리 직원 가격 책정)에 포함되어 있습니다 Microsoft 365 Enterprise. 및 Office 365 Education A5. 조직에 Office 365 고급 메시지 암호화 없는 구독이 있는 경우 Microsoft 365 E3, Microsoft 365 E3(비영리 직원 가격) 또는 Microsoft 365 E3 Microsoft 365 E3(비영리 직원 가격), Office 365 SKU 또는 Microsoft 365 E5/A5 정보 보호 및 거버넌스 SKU 추가 기능용 Office 365 Advanced Compliance SKU 추가 기능으로 구매할 수 있습니다 Microsoft 365 E5 Compliance. Microsoft 365 A3/E3.

고급 메시지 암호화는 고객이 외부 받는 사람에 대한 보다 유연한 제어 및 암호화된 전자 메일에 대한 액세스가 필요한 규정 준수 의무를 충족하는 데 도움이 됩니다. 고급 메시지 암호화를 사용하여 Office 365 정책을 사용하여 조직 외부에서 공유되는 중요한 전자 메일을 제어할 수 있습니다. 이러한 정책을 구성하여 PII, 재무 또는 상태 식별과 같은 중요한 정보 유형을 식별하거나 키워드를 사용하여 보호를 강화할 수 있습니다. 정책을 구성한 후 사용자 지정 브랜드 전자 메일 서식 파일과 정책을 페어링한 다음 정책에 맞는 전자 메일에 대한 추가 제어를 위한 만료 날짜를 추가합니다. 또한 관리자는 보안 웹 포털을 통해 외부에 액세스하는 암호화된 전자 메일에 대한 액세스를 해지하여 해당 메일에 대한 액세스 권한을 추가로 제어할 수 있습니다.

외부 받는 사람에게 보낸 전자 메일의 만료 날짜만 해지하고 설정할 수 있습니다.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>시작 Office 365 고급 메시지 암호화

다음 문서에서는 고급 메시지 암호화를 설정하고 사용하는 방법에 대해 설명하고 있습니다.

조직에 구독이 포함되어 있어야 Office 365 고급 메시지 암호화. 지원되는 구독에 대한 자세한 내용은 메시지 정책 및 규정 준수 서비스 [설명 을 참조하세요.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

아직 설정하지 Office 365 메시지 암호화 경우 [Set up new Office 365 메시지 암호화 capabilities을 참조합니다.](set-up-new-message-encryption-capabilities.md)

고급 메시지 암호화를 사용하면 단일 브랜드 템플릿으로 제한되지 않습니다. 대신 여러 브랜드 템플릿을 만들고 사용할 수 있습니다. 자세한 내용은 암호화된 메시지에 조직의 브랜드 [추가를 참조하세요.](add-your-organization-brand-to-encrypted-messages.md) 사용자 지정 브랜드를 사용하는 경우 외부 받는 사람은 OME 포털에 대한 링크가 포함된 알림 전자 메일을 받게 됩니다. 메일 흐름 규칙은 알림 전자 메일 및 OME 포털에서 사용할 브랜드 템플릿을 결정합니다. 이렇게 하면 보안 콘텐츠가 조직 외부로 전송되지 않습니다.

사용자는 포털을 통해 받는 메시지에만 메시지를 해지하고 만료 날짜를 적용할 수 있습니다. 즉, 사용자 지정 브랜징 템플릿이 적용된 전자 메일입니다. 자세한 정보 및 예제는 모든 외부 받는 사람이 OME 포털을 사용하여 암호화된 메일을 [읽는지 확인의 지침을 참조하세요.](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)

[에서 암호화된 전자 메일의 만료 날짜를 Office 365 고급 메시지 암호화.](ome-advanced-expiration.md) 보안 웹 포털을 통해 암호화된 전자 메일에 대한 액세스를 만료하여 보호를 강화하는 자동 정책으로 조직 외부에서 공유되는 중요한 전자 메일을 제어합니다.

[에서 암호화된](revoke-ome-encrypted-mail.md)전자 메일을 Office 365 고급 메시지 암호화. 보안 웹 포털을 통해 암호화된 전자 메일에 대한 액세스를 해지하여 조직 외부에서 공유되는 중요한 전자 메일을 제어하고 보호를 강화합니다.  
