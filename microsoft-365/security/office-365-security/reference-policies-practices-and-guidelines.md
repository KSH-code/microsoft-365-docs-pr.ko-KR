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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft는 원치 않는 메일, 휴의적이거나 악성적인 메일로부터 사용자를 보호하는 데 도움이 되는 여러 가지 업체 모범 사례를 개발하고 채택해 주시어다양한 정책과 절차를 개발하고 채택해 주어주세요.
ms.openlocfilehash: 13bc62f8be25a21f5ed2d1c2c2f4208a56d28bf0
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826520"
---
# <a name="reference-policies-practices-and-guidelines"></a>참조: 정책, 사례 및 지침

Microsoft는 웹에서 가장 신뢰할 수 있는 사용자 환경을 제공하기 위해 최선을 다하고 있습니다. 따라서 Microsoft는 해가, 원하지 않는 메일 또는 악의적인 메일로부터 사용자를 보호하는 데 도움이 되는 여러 가지 업체 모범 사례를 개발하고 채택해 주어 주시기 바가 다양한 정책 과정을 개발하고 채택해 주시기 바가 제시되었습니다. 사용자에게 전자 메일을 보내는 보낸 사람은 해당 노란을 완전히 이해하고 이 문서의 지침을 따라 잠재적인 배달 문제를 방지하는 데 도와줍니다.

이러한 정책 및 지침을 준수하지 않는 경우 지원 팀에서 지원을 제공할 수 없습니다. 이 문서에 나와 있는 지침, 관행 및 정책을 준수하고 보내는 IP 주소를 기준으로 배달 문제가 여전히 발생하는 경우 단계에 따라 목록 지정 요청을 제출하세요. 지침은 목록 [삭제 포털을 사용하여 수신 거부 목록에서 본인 제거를 참조하세요.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="general-microsoft-policies"></a>일반 Microsoft 정책

Microsoft 365 사용자에게 보낸 전자 메일은 전자 메일 전송 및 Microsoft 365를 사용하는 모든 Microsoft 정책을 준수해야 합니다.

- Microsoft 365에 적용하는 서비스 약관 특히 서비스를 사용하여 스팸을 만들거나 맬웨어를 배포하는 것은 금지됩니다.

- [Microsoft 서비스 계약](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>정부 기당 데이터 처리

Microsoft 365 사용자에게 보낸 전자 메일은 해당 확인 대상의 전자 메일 통신을 통제하는 모든 관련 법률 및 규정을 준수해야 합니다.

- [CAN-SPAM Act: 비즈니스용 준수 가이드](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["내 제거" 응답 및 책임: 전자 메일 마케팅 업체는 "구독 취소" 클레임](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>기술 지침

Microsoft 365로 보낸 전자 메일은 아래 문서에 나열된 해당 권장 사항을 준수해야 합니다. 일부 링크는 영어로만 제공될 수 있습니다.

- [RFC 2505: SMTP MTA에 대한 스팸 방지 권장 사항](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: 명령 파이프라이프로운에 대한 SMTP 서비스 확장](https://www.ietf.org/rfc/rfc2920.txt)

또한 Microsoft 365에 연결하는 전자 메일 서버는 다음 요구 사항을 준수해야 합니다.

- 보낸 사람은 RFC 5321, RFC 5322 등을 포함하여 IETF(Internet Society의 Internet Engineering Task Force)를 통해 게시된 인터넷 전자 메일 전송에 대한 모든 기술 표준을 준수해야 합니다.

- 500에서 599(영구적 배달 못 함 응답 또는 NDR이라고도 함) 사이의 숫자 SMTP 오류 응답 코드가 제공된 후 보낸 사람은 해당 메시지를 받는 사람에게 다시 보내려고 시도하지 않아아서는 안 됩니다.

- 배달 못 함 응답이 여러 개이며 보낸 사람은 해당 받는 사람에게 전자 메일을 보내기 위해 추가로 시도해야 합니다.

- 메시지는 보안이 없는 이메일 릴레이 또는 프록시 서버를 통해 전송되지 않습니다.

- 개별 목록 또는 보낸 사람이 호스팅하는 모든 목록에서 구독 해제 메커니즘은 명확하게 문서화하여 받는 사람이 찾고 사용할 수 있도록 명확하게 문서화해야 합니다.

- 동적 IP 공간으로의 연결이 허용되지 않을 수도 있습니다.

- 전자 메일 서버에는 유효한 역방향 DNS 레코드가 있어야 합니다.

## <a name="reputation-management"></a>신뢰도 관리

보낸 사람, ISP 및 기타 서비스 공급자는 아웃바운드 IP 주소의 신뢰도를 적소식으로 관리해야 합니다.

## <a name="microsoft-365-limits"></a>Microsoft 365 제한

보낸 사람이 Exchange Online Protection 제한에 나열된 Microsoft 365 [제한을 준수해야 합니다.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>전자 메일 배달 리소스 및 조직

Microsoft는 인터넷 및 전자 메일 에코시스템을 개선하기 위해 산업 기업 및 서비스 공정업체와 정식을 제공합니다. 이러한 조직에서는 지원할 모범 사례 문서를 게시하여 보낸 사람을 적응할 것을 권장합니다. 이렇게 하면 전 세계 여러 전자 메일 서비스 공급자에게 전자 메일을 전달할 수 있습니다.

- [메시징 맬웨어 모바일 오프 서비스 방지 작업 그룹](https://www.m3aawg.org/)

- [온라인 트러스트 설정](https://www.otalliance.org/resources)

- [전자 메일을 보낸 사람 & 공급자 연습](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>절사용 및 스팸 보고

어려운, 악용도가 없거나 원치 않는 전자 메일을 보고하려면 [Microsoft에 보고 메시지 및 파일을 참조하십시오.](report-junk-email-messages-to-microsoft.md) 이러한 유형의 통신을 보내는 것은 Microsoft 정책 위임이며 확인된 보고서에 대해 적절한 조치가 수행됩니다.

## <a name="law-enforcement"></a>법 적용

법 집행 기관의 소속으로 Office 365와 관련하여 법적 문서가 포함된 Microsoft Corporation을 제공하고자 하는 경우 또는 Microsoft에 제출한 법적 설명서에 대한 질문이 있는 경우 (1) 722-1299로 문의하십시오.
