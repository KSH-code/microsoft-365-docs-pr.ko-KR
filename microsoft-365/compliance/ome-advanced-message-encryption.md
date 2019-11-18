---
title: Office 365 고급 메시지 암호화
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
description: Advanced Message Encryption in Office 365에서는 보호 된 메시지를 사용 하 여 관리자가 더 많은 작업을 수행할 수 있도록 함으로써 조직이 준수 의무를 충족할 수 있습니다.
ms.openlocfilehash: 7594a6ed2226081e54af957268cf0ca3fe403767
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38687071"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 고급 메시지 암호화

Office 365 Advanced Message Encryption은 [microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (비영리 스태프 가격), Office 365 Enterprise E5 (비영리 스태프 가격) 및 Office 365 교육용 A5에 포함 되어 있습니다. 조직에서 Office 365 고급 메시지 암호화를 포함 하지 않는 구독을 사용 하는 경우 microsoft 365 E3, Microsoft 365 E3 (비영리 직원 가격) 또는 Office 365 Advanced 용 Microsoft 365 E5 준수 SKU 추가 기능을 통해 구매할 수 있습니다. Microsoft 365 E3, Microsoft 365 E3 (비영리 직원 가격) 또는 Office 365 Sku에 대 한 준수 SKU 추가 기능입니다.

Advanced Message Encryption in Office 365에서는 고객이 외부 받는 사람에 대 한 보다 유연한 제어 및 암호화 된 전자 메일 액세스를 필요로 하는 규정 준수 의무를 충족 하도록 지원 합니다. Office 365의 고급 메시지 암호화를 사용 하 여 조직 외부에서 공유 되는 중요 한 전자 메일을 자동 정책으로 제어할 수 있습니다. 이러한 정책을 구성 하 여 PII, 재무 또는 상태 Id와 같은 중요 한 정보 유형을 식별 하거나 키워드를 사용 하 여 보호 기능을 향상 시킬 수 있습니다. 정책을 구성한 후에는 사용자 지정 브랜드 전자 메일 서식 파일을 사용 하 여 정책을 변경한 다음 정책에 맞는 전자 메일에 대 한 추가 제어를 위해 만료 날짜를 추가 합니다. 또한 관리자는 언제 든 지 메일에 대 한 액세스를 취소 하 여 보안 웹 포털을 통해 외부에서 액세스 하는 암호화 된 전자 메일을 제어할 수 있습니다.

외부의 받는 사람에 게 전송 되는 전자 메일의 만료 날짜만 취소 하 고 설정할 수 있습니다.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption 시작

다음 문서에서는 고급 메시지 암호화를 설정 하 고 사용 하는 방법에 대해 설명 합니다.

조직에 Office 365 고급 메시지 암호화를 포함 하는 구독이 있어야 합니다. 지원 되는 구독에 대 한 자세한 내용은 [메시지 정책 및 규정 준수 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)참조 하세요.

아직 Office 365 메시지 암호화를 설정 하지 않은 경우에는 [새 Office 365 메시지 암호화 기능 설정을](set-up-new-message-encryption-capabilities.md)참조 하세요.

고급 메시지 암호화를 사용 하는 경우 단일 브랜딩 서식 파일로 제한 되지 않습니다. 대신 여러 브랜딩 서식 파일을 만들고 사용할 수 있습니다. 자세한 내용은 [암호화 된 메시지에 조직의 브랜드 추가](add-your-organization-brand-to-encrypted-messages.md)를 참조 하세요.

[Office 365 고급 메시지 암호화로 암호화 된 전자 메일의 만료 날짜를 설정](ome-advanced-expiration.md)합니다. 조직 외부에서 공유 되는 중요 한 전자 메일 제어 보안 웹 포털을 통해 암호화 된 전자 메일을 통해 액세스를 만료 하는 자동 정책으로 보호를 강화 합니다.

[Office 365 고급 메시지 암호화로 암호화 된 전자 메일을 해지](revoke-ome-encrypted-mail.md)합니다. 조직 외부에서 공유 되는 중요 한 전자 메일 제어 및 보안 웹 포털을 통한 암호화 된 전자 메일에 대 한 액세스를 해지 하 여 보호 기능 향상  

Office 365 고급 메시지 암호화를 사용 하 여 사용자 지정 브랜딩 템플릿을 적용할 때마다 Office 365에서 템플릿을 적용 한 메일 흐름 규칙에 맞는 전자 메일에 래퍼를 적용 합니다. 사용자가 포털을 통해 받은 메시지에만 메시지를 해지 하 고 만료 날짜를 적용할 수 있습니다. 즉, 사용자 지정 브랜딩 서식 파일이 적용 된 전자 메일입니다. 자세한 내용 및 예제는 [모든 외부 받는 사람이 OME 포털을 사용 하 여 암호화 된 메일 읽기 (Office 365 Advanced Message Encryption only)](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only)의 지침을 참조 하십시오.
