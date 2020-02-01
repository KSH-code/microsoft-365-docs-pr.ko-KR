---
title: Exchange Online에서 오류 코드 5.7.7 xx에 해당 하는 전자 메일 배달 문제 수정
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online에서 오류 코드 5.7.7 xx의 전자 메일 문제를 해결 하는 방법에 대해 알아봅니다 (테 넌 트 차단 됨).
ms.openlocfilehash: e8e134793db946ddfc3ef09d0adc19b2a04df30b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599285"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Exchange Online에서 오류 코드 5.7.7 xx에 해당 하는 전자 메일 배달 문제 수정

이 항목에서는 배달 못 함 보고서 (NDR, 바운스 메시지, 배달 상태 알림 또는 DSN이 라고도 함)에 상태 코드 550 5.7.7 xx가 표시 되는 경우에 수행할 수 있는 작업에 대해 설명 합니다. 테 넌 트가 단방향 이나 다른 방법으로 전자 메일을 보낼 수 없도록 제한 되 면이 자동 알림을 볼 수 있습니다. 이러한 오류 코드는 대개 705 또는 750로 제공 됩니다.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: 테 넌 트가 임계값 제한을 초과 했습니다. 확인 해야 할 사항

사용자가 서비스를 통해 의심 스러운 전자 메일을 보내는 경우에는 문제가 해결 될 때까지 모든 사용자가 전자 메일을 보내지 못할 수 있습니다. 일반적으로 손상 (가장 일반적인)을 하거나 너무 많은 대량 메일을 보내는 경우이 결과가 발생 합니다. 사용자에 게 다음을 알리는 NDR이 수신 됩니다.

`550 5.7.705 Access denied, tenant has exceeded threshold`

드물지만 구독을 이미 만료 한 후 갱신 하는 경우에도 이러한 상황이 발생할 수 있습니다. 서비스가 새 구독 정보를 동기화 하는 데 시간이 걸리지만 (대개 하루 이상) 조직에서 전자 메일을 보낼 수 없도록 차단 될 수 있습니다. 이를 방지 하는 가장 좋은 방법은 구독이 만료 되지 않았는지 확인 하는 것입니다.

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: 등록 되지 않은 도메인 전자 메일 제한: 알아야 할 사항

Office 365을 사용 하면 테 넌 트에서 Exchange Online Protection (EOP)을 통해 일부 메시지를 릴레이할 수 있습니다. 예시는 다음과 같습니다:

- Office 365 사서함은 외부 보낸 사람 으로부터 전자 메일을 받습니다. 메일 전달은 Office 365 사서함에서 구성 되므로 메시지가 사용자의 외부 전자 메일 주소로 전달 됩니다. 이 시나리오는 학생 들이 자신의 개인 전자 메일 계정을 사용 하 여 학교 관련 메시지를 볼 수 있도록 하려는 교육 환경에서 가장 일반적입니다.

- EOP를 통해 보내는 메일을 보내는 온-프레미스 전자 메일 서버가 있는 하이브리드 환경

### <a name="problems-with-unregistered-domains"></a>등록 되지 않은 도메인 문제

문제는 온-프레미스 전자 메일 서버가 EOP를 통해 대용량의 스팸을 릴레이할 때 발생 합니다. 거의 모든 경우에 커넥터는 제대로 설정 되지만 등록 되지 않은 도메인 (구축 되지 않음)에서 전자 메일이 전송 됩니다. Office 365에서는 등록 되지 않은 도메인에서 적절 한 전자 메일을 받을 수 있지만, 전자 메일을 보내는 데 사용 하는 모든 도메인을 허용 도메인으로 구성 해야 합니다.

일단 손상 되 면 테 넌 트가 등록 되지 않은 도메인에서 아웃 바운드 전자 메일을 보낼 수 없게 됩니다. 사용자에 게 다음을 알리는 NDR이 수신 됩니다.

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="unblocking-tenant-in-order-to-send-again"></a>다시 보내기 위해 테 넌 트 차단 해제

테 넌 트가 전자 메일을 보내지 못하도록 차단 된 경우에는 몇 가지 작업을 수행 해야 합니다.

1. 관리자 계정의 암호를 변경 합니다. 테 넌 트가 보내지 못하도록 차단 된 경우에는 관리자 계정이 손상 되었을 가능성이 높습니다. 공격자가 더 이상 피해를 줄 수 없도록 암호를 변경 하는 것이 첫 번째 단계입니다.

2. Office 365 조 직의 모든 관리자에 대해 [MFA를 사용 하도록 설정](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 합니다.

3. 모든 전자 메일 도메인이 등록 되어 있는지 확인 합니다. 자세한 내용은 Exchange Online에서 [Office 365에 도메인 추가](https://docs.microsoft.com/office365/admin/setup/add-domain) 및 [허용 도메인 관리](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)를 참조 하세요.

4. 비정상적인 [커넥터](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)를 찾습니다. 악의적인 행위자는 종종 Office 365 조직에서 새 인바운드 커넥터를 만들어 스팸을 보냅니다. 기존 커넥터를 보려면 [Office 365에서 커넥터 유효성 검사](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)를 참조 하세요.

5. [Office 365에서 손상 된 전자 메일 계정에 응답 하는](responding-to-a-compromised-email-account.md)것으로 설명 되어 있는 사용자가 손상 되었는지 확인 합니다.

6. 온-프레미스 전자 메일 서버를 잠그고 해당 서버가 손상 되지 않았는지 확인 합니다.

   > [!TIP]
   > 특히 타사 서버를 사용 하는 경우에는 여러 가지 요인이 있습니다. 에 관계 없이 보내는 메일이 스팸을 포함 하지 않는지 확인 해야 합니다.

7. Microsoft 지원 서비스에 문의 하 여 전자 메일을 다시 보내기 위해 테 넌 트 차단 해제를 요청 합니다. 오류 코드가 도움이 되지만 사용자 환경에 대 한 보안이 유지 되 고 스팸 메일을 보낼 수 없다는 사실을 입증 해야 합니다. 지원 사례를 열려면 [비즈니스 제품에 대 한 지원 문의-관리자 도움말](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)을 참조 하세요.

## <a name="for-more-information"></a>자세한 내용

[Office 365의 전자 메일 스팸 방지 및 보호](anti-spam-protection.md)

[Exchange Online 서비스 설명의 보내는 제한 섹션에 있는 대량 메일 지침](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[Office 365의 전자 메일 배달 못 함 보고서(NDR)](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[사서함의 전자 메일 전달 구성](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Office 365를 사용하여 전자 메일을 보내도록 다기능 장치 또는 응용 프로그램을 설정하는 방법](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[Exchange Online에서 허용 도메인을 관리](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)합니다.
