---
title: 참조 정책, 사례 및 지침
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft는 다양한 정책, 절차를 개발하고 사용자를 악의적, 원치 않는 또는 악의적인 전자 메일로부터 보호하기 위해 여러 업계 모범 사례를 채택했습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f53b1c36417b15e366b527dd1c12e4f23c06f632
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406599"
---
# <a name="reference-policies-practices-and-guidelines"></a>참조: 정책, 사례 및 지침

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft는 웹에서 가장 신뢰할 수 있는 사용자 환경을 제공하기 위해 전념하고 있습니다. 따라서 Microsoft는 다양한 정책, 절차를 개발하고, 악의적, 원치 않는 또는 악의적인 전자 메일로부터 사용자를 보호하기 위해 몇 가지 업계 모범 사례를 채택했습니다. 사용자에게 전자 메일을 보내고자 하는 보낸 사람은 이 노력에 도움을 주며 잠재적인 배달 문제를 방지하는 데 도움이 되도록 이 문서의 지침을 완전히 이해하고 준수해야 합니다.

이러한 정책 및 지침을 준수하지 않는 경우 지원 팀에서 지원을 받지 못하게 될 수 있습니다. 이 문서에 제시된 지침, 사례 및 정책을 준수하고 여전히 보내는 IP 주소에 따라 배달 문제가 발생하는 경우 단계에 따라 목록에서 요청을 제출하세요. 자세한 내용은 목록 제거 포털을 사용하여 수신 차단된 보낸 사람 목록에서 자신을 [제거를 참조하세요.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="general-microsoft-policies"></a>일반 Microsoft 정책

Microsoft 365 사용자에게 전송되는 전자 메일은 Microsoft 365의 전자 메일 전송 및 사용을 규정하는 모든 Microsoft 정책을 준수해야 합니다.

- Microsoft 365에 적용되는 서비스 약관 특히 서비스를 사용하여 스팸을 방지하거나 맬웨어를 배포하는 금지입니다.

- [Microsoft 서비스 계약](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>정부 규정

Microsoft 365 사용자에게 전송되는 전자 메일은 해당 관할권의 전자 메일 통신을 규정하는 모든 관련 법률 및 규정을 준수해야 합니다.

- [CAN-SPAM Act: A Compliance Guide for Business](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["제거" 응답 및 책임: 전자 메일 시장은 "구독 취소" 클레임의 수호해야 합니다.](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>기술 지침

Microsoft 365로 전송되는 전자 메일은 아래 문서에 나열된 해당 권장 사항을 준수해야 합니다(일부 링크는 영어로만 제공).

- [RFC 2505: SMTP MTAS에 대한 스팸 방지 권장 사항](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: 명령 파이프라이너용 SMTP 서비스 확장](https://www.ietf.org/rfc/rfc2920.txt)

또한 Microsoft 365에 연결하는 전자 메일 서버는 다음 요구 사항을 준수해야 합니다.

- 보낸 사람이 RFC 5321, RFC 5322 등을 포함하여 인터넷 사회의 IETF(Internet Engineering Task Force)에서 게시한 인터넷 전자 메일 전송에 대한 모든 기술 표준을 준수해야 합니다.

- 500에서 599 사이의 숫자 SMTP 오류 응답 코드(영구적 배달 못지 않은 응답 또는 NDR)를 제공한 후 보낸 사람은 해당 메시지를 해당 받는 사람에게 다시 전송하지 말아야 합니다.

- 배달되지 않은 응답이 여러 개 있는 경우 보낸 사람은 해당 받는 사람에게 전자 메일을 보내기 더 이상 시도하지 말아야 합니다.

- 비보안 전자 메일 릴레이 또는 프록시 서버를 통해 메시지를 전송하면 안 됩니다.

- 개별 목록 또는 보낸 사람이 호스팅하는 모든 목록에서 수신을 제출하지 않는 메커니즘을 명확하게 문서화해야 받는 사람이 쉽게 찾아 사용할 수 있습니다.

- 동적 IP 공간의 연결이 수락되지 않을 수 있습니다.

- 전자 메일 서버에 유효한 역방향 DNS 레코드가 있어야 합니다.

## <a name="reputation-management"></a>신뢰도 관리

보낸 사람, ISP 및 기타 서비스 공급자는 아웃바운드 IP 주소의 신뢰도를 적극적으로 관리해야 합니다.

## <a name="microsoft-365-limits"></a>Microsoft 365 제한

보낸 사람이 Exchange Online Protection 제한에 나열된 Microsoft 365 [제한을 준수해야 합니다.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>전자 메일 배달 리소스 및 조직

Microsoft는 인터넷 및 전자 메일 에코시스템을 개선하기 위해 산업 기관 및 서비스 공급자와 적극적으로 작업하고 있습니다. 이러한 조직은 보낸 사람이 준수할 수 있는 모범 사례 문서를 게시했습니다. 이를 통해 전 세계 여러 전자 메일 서비스 공급자가 전자 메일을 배달할 수 있습니다.

- [메시징 맬웨어 모바일 남용 방지 작업 그룹](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.internetsociety.org/ota/)

- [전자 메일 보낸 & 공급자 연대](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>남용 및 스팸 보고

위조, 악의적, 원치 않는 또는 악성 전자 메일을 보고하려면 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md) 이러한 유형의 통신을 보내는 것은 Microsoft 정책을 위반하며 확인된 보고서에 대해 적절한 조치를 취합니다.

## <a name="law-enforcement"></a>사법 기관

사법 기관의 구성원이자 Office 365에 관한 법적 문서를 Microsoft Corporation에 지원하고자 하는 경우 또는 Microsoft에 제출한 법적 문서에 대한 질문이 있는 경우 (1) (425) 722-1299로 전화하세요.
