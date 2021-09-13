---
title: Office 365의 암호화에 대한 기술 관련 세부 정보
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Office 365 암호화에 사용되는 다양한 인증서, 기술 및 TLS(전송 계층 보안) 암호화 제품군에 대해 Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b2257338ab214ccdaa08f1aa8f322aad98d7c8b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212592"
---
# <a name="technical-reference-details-about-encryption"></a>Office 365의 암호화에 대한 기술 관련 세부 정보

이 문서를 참조하여 에서 암호화에 사용되는 인증서, 기술 및 TLS 암호화 [제품군에 대해 Office 365.](encryption.md) 이 문서에서는 계획된 사용 고지 사항의 세부 정보도 제공합니다.
  
- 개요 정보를 찾고 있는 경우 에서 [암호화를 Office 365.](encryption.md)
- 설정 정보를 찾고 있는 경우 에서 암호화 [설정을 Office 365 Enterprise.](set-up-encryption.md)
- 특정 버전의 Windows 지원되는 암호 제품군에 대한 자세한 내용은 [TLS/SSL(Schannel SSP)의](/windows/desktop/SecAuthN/cipher-suites-in-schannel)암호 제품군을 참조하세요.

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 인증서 소유권 및 관리

이 경우 인증서를 구입하거나 유지 관리하지 Office 365. 대신 Office 365 자체 인증서를 사용합니다.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>현재 암호화 표준 및 계획된 사용 고지

동급 최고의 암호화를 제공하기 위해 Office 365 암호화 표준을 정기적으로 검토합니다. 경우에 따라 오래된 표준은 오래되고 보안이 낮아지기만 하여 더는 사용이 불가능해지기도 합니다. 이 문서에서는 현재 지원되는 암호 제품군 및 기타 표준과 계획된 사용되지 않는 경우의 세부 정보를 제공합니다.

## <a name="fips-compliance-for-office-365"></a>OFFICE 365

FIPS 140-Office 365 허용되는 알고리즘을 사용하는 모든 암호화 제품군 Office 365 Schannel을 통해 WINDOWS FIPS 유효성 검사를 상속합니다. Schannel에 대한 자세한 내용은 [TLS/SSL(Schannel SSP)의 Cipher Suites를 참조하세요.](/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365에서 지원하는 TLS 버전

TLS 및 TLS 이전의 SSL은 보안 인증서를 사용하여 컴퓨터 간 연결을 암호화하여 네트워크를 통해 통신을 보호하는 암호화 프로토콜입니다. Office 365 TLS 버전 1.2(TLS 1.2)를 지원할 수 있습니다.

TLS 버전 1.3(TLS 1.3)은 현재 지원되지 않습니다.

> [!IMPORTANT]
> TLS 버전은 더 이상 사용되지 않습니다. 더  이상 사용되지 않는 버전은 최신 버전을 사용할 수 있는 경우 사용되지 않습니다. 레거시 서비스에 TLS 1.0 또는 1.1이 필요하지 않은 경우 사용하지 않도록 설정해야 합니다.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>TLS 1.0 및 1.1 사용되지 않는 지원

Office 365 2018년 10월 31일 TLS 1.0 및 1.1 지원이 중지되었습니다. High 및 DoD 환경에서 TLS 1.0 및 1.1을 GCC 완료했습니다. 2020년 10월 15일부터 전 세계 및 GCC 환경에 대해 TLS 1.0 및 1.1을 사용할 수 없습니다. 다음 주 및 몇 개월에 대해 롤아웃을 계속할 예정입니다.

모든 클라이언트 및 Office 365 Microsoft 365 연결 유지 관리하기 위해 모든 클라이언트-서버 및 브라우저-서버 조합은 TLS 1.2 및 최신 암호 제품군을 사용합니다. 특정 클라이언트-서버 및 브라우저-서버 조합을 업데이트해야 할 수 있습니다. 이 변경이 미치는 영향에 대한 자세한 내용은 에서 [TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 Office 365.
  
## <a name="deprecating-support-for-3des"></a>3DES 지원 사용 안

2018년 10월 31일 이후로 Office 365 통신에 3DES 암호 제품군을 더 이상 사용할 수 Office 365. 특히, Office 365 더 이상 TLS_RSA_WITH_3DES_EDE_CBC_SHA 지원하지 않습니다. 2019년 2월 28일부터 이 암호 제품군은 2019년 2월 28일부터 Office 365. 클라이언트 및 서버와 통신하는 Office 365 지원되는 암호 중 하나 이상을 지원해야 합니다. 지원되는 암호 목록은 에서 지원하는 TLS 암호 제품군을 [Office 365.](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365에서 SHA-1 인증서를 지원하지 않음

2016년 6월부터는 Office 365 연결에 대한 SHA-1 인증서를 더 이상 수락하지 않습니다. 인증서 체인에서 SHA-2(보안 해시 알고리즘 2) 또는 더 강력한 해시 알고리즘을 사용합니다.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>지원되는 TLS 암호 Office 365

TLS는 암호화 알고리즘 모음인 암호화 제품군을 사용하여 보안 연결을 설정합니다. Office 365 표에 나열된 암호 제품군을 지원할 수 있습니다. 이 표에는 가장 강력한 암호 제품군이 먼저 나열되어 있는 강도순으로 암호 제품군이 나열되어 있습니다.

Office 365 가장 안전한 암호 제품군을 사용하여 먼저 연결을 시도하여 연결 요청에 응답합니다. 연결이 작동하지 않는 경우 Office 365 가장 안전한 두 번째 암호 제품군을 계속 사용하게 됩니다. 연결이 수락될 때까지 서비스가 목록 아래로 계속됩니다. 마찬가지로, Office 365 요청하는 경우 수신 서비스는 TLS를 사용할지 여부와 사용할 암호 제품군을 선택합니다.

| 암호 그룹 이름 | 키 교환 알고리즘/강도 | 전방 secrecy | 암호/강도 | 인증 알고리즘/강도 |
|:-----|:-----|:-----|:-----|:-----|
| TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> | ECDH/192  <br/> | 예  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> | ECDH/128  <br/> | 예  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384  <br/> | ECDH/192  <br/> | 예  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256  <br/> | ECDH/128  <br/> | 예  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA     <br/> | ECDH/192  <br/> | 예  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA     <br/> | ECDH/128  <br/> | 예  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_256_GCM_SHA384        <br/> | RSA/112   <br/> | 아니요   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_128_GCM_SHA256        <br/> | RSA/112   <br/> | 아니요   <br/> | AES/256  <br/> | RSA/112  <br/> |

다음 암호 제품군은 사용되지 않는 날짜까지 TLS 1.0 및 1.1 프로토콜을 지원했습니다. 사용 GCC 2020년 1월 15일인 High 및 DoD 환경의 경우 전 세계 및 GCC 환경의 경우 2020년 10월 15일입니다.

| 프로토콜 | 암호 그룹 이름 | 키 교환 알고리즘/강도 | 전방 secrecy | 암호/강도 | 인증 알고리즘/강도 | 
|:-----|:-----|:-----|:-----|:-----|:-----|
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> | ECDH/192  <br/> | 예  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> | ECDH/128  <br/> | 예  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA        <br/> | RSA/112   <br/> | 아니요   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA        <br/> | RSA/112   <br/> | 아니요   <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> | RSA/112   <br/> | 아니요   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> | RSA/112   <br/> | 아니요   <br/> | AES/256  <br/> | RSA/112  <br/> |

특정 Office 365(Microsoft Teams 포함)는 Azure [Front Door를](/azure/frontdoor/front-door-overview) 사용하여 TLS 연결을 종료하고 네트워크 트래픽을 효율적으로 라우팅합니다. 이러한 제품에 연결하려면 [Azure Front Door over TLS 1.2에서](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-) 지원하는 암호 제품군 중 하나 이상을 사용하도록 설정해야 합니다. 이 Windows 10 이상의 경우 더 나은 보안을 위해 ECDHE 암호 제품군 중 하나 또는 둘 다를 사용하도록 설정하는 것이 좋습니다. Windows 7, 8 및 8.1은 Azure Front Door의 ECDHE 암호 제품군과 호환되지 않고 해당 운영 체제와의 호환성을 위해 DHE 암호 제품군이 제공되었습니다.

## <a name="related-articles"></a>관련 문서

[v1903의 TLS Windows 10 제품군](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365의 암호화](encryption.md)
  
[Office 365 Enterprise의 암호화 설정](set-up-encryption.md)
  
[Windows 보안 상태 업데이트에서 TLS 1.0의 Schannel 구현: 2015년 11월 24일](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 암호화 개선 사항(IT Windows)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Office 365 및 Office 365 GCC에서 TLS 1.2 준비](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

[Azure Front Door에서 지원하는 현재 암호 제품군은 무엇입니까?](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)
