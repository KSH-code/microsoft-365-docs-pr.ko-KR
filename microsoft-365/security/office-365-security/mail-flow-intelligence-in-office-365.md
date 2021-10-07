---
title: 메일 흐름 인텔리전스
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 관리자는 커넥터를 사용하여 메시지 배달과 연결된 오류 코드(메일 흐름 인텔리전스라고도 알려지기)에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84029f2f3387913b810c6886a2ac546e587aaca7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169494"
---
# <a name="mail-flow-intelligence-in-eop"></a>EOP의 메일 흐름 인텔리전스

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 Exchange Online 조직에서는 일반적으로 커넥터를 사용하여 EOP에서 전자 메일 환경으로 전자 메일 메시지를 라우팅합니다. 커넥터를 사용하여 조직의 메시지를 파트너 Microsoft 365 라우팅할 수도 있습니다. 커넥터를 Microsoft 365 배달할 수 없는 경우 이러한 메시지는 커넥터에서 Microsoft 365. Microsoft 365 24시간 동안 각 메시지에 대해 배달을 계속 다시 시도합니다. 24시간이 지난 후 큐에 대기된 메시지가 만료되고 메시지가 배달되지 않는 보고서(NDR 또는 반송 메시지라고도 알려지음)에서 원래 보낸 사람으로 반환됩니다.

Microsoft 365 사용하여 메시지를 배달할 수 없는 경우 오류가 발생합니다. 가장 일반적인 오류와 해당 해결 방법도 이 문서에 설명되어 있습니다. 커넥터를 통해 전송된 확인할 수 없는 메시지에 대한 큐 및 알림 오류를 총체적으로 메일 흐름 인텔리전스라고 _합니다._

## <a name="error-code-450-44312-dns-query-failed"></a>오류 코드: 450 4.4.312 DNS 쿼리 실패

일반적으로 이 Microsoft 365 커넥터에 지정된 스마트 호스트에 연결하려고 했지만 스마트 호스트의 IP 주소를 찾기 위한 DNS 쿼리가 실패했다는 의미입니다. 이 오류의 가능한 원인은 다음과 같습니다.

- 도메인의 DNS 호스팅 서비스(도메인에 대한 권한이 있는 이름 서버를 유지 관리하는 사용자)에 문제가 있습니다.

- 도메인이 최근에 만료되었습니다. 따라서 MX 레코드를 검색할 수 없습니다.

- 도메인의 MX 레코드가 최근에 변경된 경우 DNS 서버는 이전에 도메인에 대한 DNS 정보를 캐시했습니다.

### <a name="how-do-i-fix-error-code-450-44312"></a>오류 코드 450 4.4.312를 수정하는 방법

- DNS 호스팅 서비스에서 도메인 문제를 식별하고 해결합니다.

- 파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결합니다.

## <a name="error-code-450-44315-connection-timed-out"></a>오류 코드: 450 4.4.315 연결 시간

일반적으로 이 Microsoft 365 대상 전자 메일 서버에 연결할 수 없습니다. 오류 세부 정보에서 문제를 설명합니다. 예:

- On-premises email server is down.

- 커넥터의 스마트 호스트 설정에 오류가 있으므로 Microsoft 365 IP 주소에 연결하려고 합니다.

### <a name="how-do-i-fix-error-code-450-44315"></a>오류 코드 450 4.4.315를 수정하는 방법

- 어떤 시나리오가 적용되는지 확인하여 필요한 수정을 합니다. 예를 들어 메일 흐름이 올바르게 작동하고 커넥터 설정을 변경하지 않은 경우, 서버가 다운되어 있는 경우 또는 네트워크 인프라가 변경된 경우(예: 인터넷 서비스 공급자를 변경했기 때문에 IP 주소가 다를 수 있습니다)를 확인하려면 사내 전자 메일 환경을 검사해야 합니다.

- 파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결합니다.

## <a name="error-code-450-44316-connection-refused"></a>오류 코드: 450 4.4.316 연결 거부

일반적으로 이 오류는 Microsoft 365 서버에 연결하려고 할 때 연결 오류가 발생했다는 의미입니다. 이 오류의 원인으로는 방화벽이 IP 주소의 연결을 Microsoft 365 있습니다. 또는, 이 오류는 완전히 마이그레이션한 경우의 계획적인 오류일 수 있습니다. Microsoft 365 전자 메일 환경을 종료해야 합니다.

### <a name="how-do-i-fix-error-code-450-44316"></a>오류 코드 450 4.4.316을 수정하는 방법

- 사내 환경에 사서함이 있는 경우 TCP 포트 25의 Microsoft 365 IP 주소에서 사내 전자 메일 서버로의 연결을 허용하도록 방화벽 설정을 수정해야 합니다. IP 주소 Microsoft 365 URL 및 IP 주소 Microsoft 365 을 [참조하세요.](../../enterprise/urls-and-ip-address-ranges.md)

- 더 이상 메시지가 배달되지 않은 경우 잘못된 받는  사람이 있는 메시지를 즉시 거부할 수 있도록 경고에서 지금 수정을 Microsoft 365 클릭합니다. 이렇게 하면 잘못된 받는 사람에 대한 조직의 할당량 초과 위험이 줄어들어 정상적인 메시지 배달에 영향을 줄 수 있습니다. 또는 다음 지침을 사용하여 문제를 수동으로 해결할 수 있습니다.

  - [EAC(Exchange](/Exchange/exchange-admin-center)관리 센터)에서 전자 메일을 전자 메일 Microsoft 365 커넥터를 사용하지 않도록 설정하거나 삭제합니다.

    1. EAC에서 메일 **흐름** \> **커넥터로 이동하십시오.**

    2. From 값과 Office 365  조직의 전자 메일  서버를  값으로 설정하는 커넥터를 선택하고 다음 단계 중 하나를 수행합니다. 
       - 제거 제거 아이콘을  클릭하여 ![ 커넥터를 삭제합니다.](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)
       - 편집 편집 아이콘을  클릭하여 ![ 커넥터를 사용하지 않도록 설정합니다.](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 를 선택 **취소합니다.**

  - 내부 릴레이에서 Microsoft 365 전자 메일 환경과 연결된 허용 도메인을 **내부** 릴레이에서 권한이 있는 도메인으로 **변경합니다.** 자세한 내용은 [에서 허용 도메인 관리를 Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **참고:** 일반적으로 이러한 변경 내용은 적용하는 데 30분에서 1시간 정도 걸립니다. 1시간이 지나면 오류가 더 이상 수신되지 않습니다.

- 파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>오류 코드: 450 4.4.317 원격 서버에 연결할 수 없습니다.

일반적으로 이 오류는 Microsoft 365 전자 메일 서버에 연결되지만 서버가 즉시 오류로 응답했거나 연결 요구 사항을 충족하지 않는다는 의미입니다. 오류 세부 정보에서 문제를 설명합니다. 예:

- 대상 전자 메일 서버가 "서비스를 사용할 수 없습니다." 오류로 응답했습니다. 이 오류는 서버가 서버와 통신을 유지 관리할 수 Microsoft 365.
- 커넥터가 TLS를 요구하도록 구성되지만 대상 전자 메일 서버는 TLS를 지원하지 않습니다.

### <a name="how-do-i-fix-error-code-450-44317"></a>오류 코드 450 4.4.317을 수정하는 방법

- 커넥터의 TLS 설정 및 인증서와, 커넥터의 TLS 설정을 확인합니다.
- 파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>오류 코드: 450 4.4.318 연결이 중단되었습니다.

일반적으로 이 오류는 Microsoft 365 전자 메일 환경과 통신하는 데 문제가 있으므로 연결이 끊어졌다는 의미입니다. 이 오류의 가능한 원인은 다음과 같습니다.

- 방화벽에서 SMTP 패킷 검사 규칙을 사용하며 이러한 규칙이 제대로 작동하지 않습니다.
- 서비스 중단, 크래시 또는 시스템 리소스가 부족한 경우와 같은 사내 전자 메일 서버가 제대로 작동하지 않습니다. 이로 인해 서버의 시간이 종료되어 서버가 중단될 수 Microsoft 365.
- 사내 환경과 프레미스 환경 간에 네트워크 문제가 Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>오류 코드 450 4.4.318을 수정하는 방법

- 어떤 시나리오가 적용되는지 확인하여 필요한 수정을 합니다.
- 문제가 사내 환경과 프레미스 환경 간의 네트워크 문제로 Microsoft 365 네트워크 팀에 문의하여 문제를 해결합니다.
- 파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.

## <a name="error-code-450-47320-certificate-validation-failed"></a>오류 코드: 450 4.7.320 인증서 유효성 검사 실패

일반적으로 이 오류는 Microsoft 365 서버의 인증서 유효성을 검사하는 동안 오류가 발생했다는 의미입니다. 오류 세부 정보에서 오류를 설명합니다. 예:

- 인증서 만료
- 인증서 주체 불일치
- 인증서가 더 이상 유효하지 않습니다.

### <a name="how-do-i-fix-error-code-450-47320"></a>오류 코드 450 4.7.320을 수정하는 방법

- 커넥터에서 큐에 대기 중인 메시지를 배달할 수 있도록 커넥터의 Microsoft 365 수정합니다.
- 파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.

## <a name="other-error-codes"></a>기타 오류 코드

Microsoft 365 또는 파트너 전자 메일 서버로 메시지를 배달하는 데 어려움이 있습니다. 오류의 **대상** 서버 정보를 사용하여 환경의 문제를 검사하거나 구성 오류가 있는 경우 커넥터를 수정합니다.

파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.
