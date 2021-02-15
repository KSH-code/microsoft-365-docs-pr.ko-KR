---
title: Office 365의 암호화에 대한 기술 관련 세부 정보
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 06/15/2020
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
description: Office 365 및 Microsoft 365의 암호화에 사용되는 다양한 인증서, 기술 및 TLS(전송 계층 보안) 암호화 제품군에 대해 자세히 알아보십시오.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 244d7a6cef6d77322475245435dafb6c89ab5353
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663431"
---
# <a name="technical-reference-details-about-encryption"></a>Office 365의 암호화에 대한 기술 관련 세부 정보

이 문서를 참조하여 [Office 365의](encryption.md)암호화에 사용되는 인증서, 기술 및 TLS 암호화 제품군을 참조하세요. 이 문서에서는 계획된 사용 금지에 대한 세부 정보도 제공합니다.
  
- 개요 정보를 찾고 있는 경우 [Office 365의 암호화를 참조하세요.](encryption.md)
- 설치 정보를 찾고 있는 경우 [Office 365 Enterprise에서 암호화 설정을 참조하세요.](set-up-encryption.md)
- 특정 버전의 Windows에서 지원되는 암호 제품군에 대한 자세한 내용은 [TLS/SSL(Schannel SSP)의](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)암호 제품군을 참조하세요.

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 인증서 소유권 및 관리

Office 365용 인증서를 구입하거나 유지 관리하지는 않습니다. 대신 Office 365는 자체 인증서를 사용합니다.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>현재 암호화 표준 및 계획된 사용 현안

동급 최고의 암호화를 제공하기 위해 Office 365는 지원되는 암호화 표준을 정기적으로 검토합니다. 오래된 표준이 오래되고 보안이 낮아질 때 더는 사용 안 되는 경우도 있습니다. 이 문서에서는 현재 지원되는 암호 제품군과 기타 표준 및 계획된 사용되지 않는 경우의 세부 정보를 설명합니다.

## <a name="fips-compliance-for-office-365"></a>Office 365에 대한 FIPS 규정 준수

Office 365에서 지원하는 모든 암호화 제품군은 FIPS 140-2에서 허용되는 알고리즘을 사용합니다. Office 365는 Windows(Schannel을 통해)에서 FIPS 유효성 검사를 상속합니다. Schannel에 대한 자세한 내용은 [TLS/SSL(Schannel SSP)의 암호 제품군을 참조하세요.](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365에서 지원하는 TLS 버전

TLS 및 TLS 전에 나온 SSL은 보안 인증서를 사용하여 컴퓨터 간 연결을 암호화하여 네트워크를 통해 통신을 보호하는 암호화 프로토콜입니다. Office 365는 TLS 버전 1.2(TLS 1.2)를 지원합니다.

TLS 버전 1.3(TLS 1.3)은 현재 지원되지 않습니다.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>TLS 1.0 및 1.1 사용되지 않는 지원

Office 365는 2018년 10월 31일 TLS 1.0 및 1.1 지원을 중지했습니다. TLS 1.0 및 1.1을 통해 Office 365에 연결하는 클라이언트, 장치 또는 서비스에서 발견된 새로운 문제는 해결되지 않습니다. GCC High 및 DoD 환경에 대한 공식적인 사용이 2020년 1월 15일로 시작되었습니다. 전 세계 및 GCC 환경에서는 TLS 1.0 및 1.1이 사용되지 않는 2020년 10월 15일이 되었습니다.

Office 365 및 Microsoft 365 서비스에 대한 보안 연결을 유지 관리하기 위해 모든 클라이언트-서버 및 브라우저 서버 조합은 TLS 1.2 및 최신 암호 제품군을 사용합니다. 특정 클라이언트-서버 및 브라우저-서버 조합을 업데이트해야 할 수 있습니다. 이 변경이 미치는 영향에 대한 자세한 내용은 [Office 365에서 TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 참조하세요.
  
## <a name="deprecating-support-for-3des"></a>3DES 지원 사용 안

2018년 10월 31일 이후로 Office 365는 더 이상 Office 365와의 통신을 위해 3DES 암호 제품군 사용을 지원하지 않습니다. 특히 Office 365는 더 이상 TLS_RSA_WITH_3DES_EDE_CBC_SHA 지원하지 않습니다. 2019년 2월 28일부터 이 암호 제품군은 Office 365에서 사용하지 않도록 설정되어 있습니다. Office 365와 통신하는 클라이언트 및 서버는 지원되는 암호 중 하나 이상을 지원해야 합니다. 지원되는 암호 목록은 Office [365에서](#tls-cipher-suites-supported-by-office-365)지원하는 TLS 암호 제품군을 참조하세요.
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365에서 SHA-1 인증서를 지원하지 않음

2016년 6월부터 Office 365는 아웃바운드 또는 인바운드 연결에 대한 SHA-1 인증서를 더 이상 수락하지 않습니다. 인증서 체인에서 SHA-2(보안 해시 알고리즘 2) 또는 더 강력한 해시 알고리즘을 사용합니다.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365에서 지원하는 TLS 암호 제품군

TLS는 암호화 알고리즘 모음인 암호화 제품군을 사용하여 보안 연결을 설정합니다. Office 365는 다음 표에 나열된 암호 제품군을 지원합니다. 이 표에는 가장 강력한 암호 제품군이 먼저 나열되어 있는 강도순으로 암호 제품군이 나열되어 있습니다.

Office 365는 가장 안전한 암호 제품군을 사용하여 먼저 연결을 시도하여 연결 요청에 응답합니다. 연결이 작동하지 않는 경우 Office 365는 목록에서 두 번째로 보안이 유지된 암호 제품군을 사용하게 됩니다. 연결이 수락될 때까지 서비스가 목록 아래로 계속됩니다. 마찬가지로 Office 365에서 연결을 요청하면 수신 서비스에서 TLS를 사용할지 여부와 사용할 암호 제품군을 선택합니다.

> [!IMPORTANT]
> TLS 버전은 더 이상 사용되지 않습니다. 최신  버전을 사용할 수 있는 경우 더 이상 사용되지 않는 버전을 사용하면 안 됩니다. TLS 1.3은 현재 지원되지 않습니다. 레거시 서비스에 TLS 1.0 또는 1.1이 필요하지 않은 경우 사용하지 않도록 설정해야 합니다.

| 암호 제품군 | 키 교환 알고리즘/강도 | 완벽한 앞으로의 Secrecy | 암호/강도 | 인증 알고리즘 |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |아니요 <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |아니요 <br/> |AES/256 <br/>|RSA/112 <br/> |

이러한 암호 제품군은 사용되지 않는 날짜까지 TLS 1.0 및 1.1 프로토콜을 지원했습니다. 사용이 2020년 1월 15일인 GCC High 및 DoD 환경과 전 세계 및 GCC 환경의 경우 2020년 10월 15일입니다.

| 프로토콜 | 암호 그룹 이름 | 키 교환 알고리즘/강도 | 완벽한 정방형 Secrecy 지원 | 인증 알고리즘/강도 | 암호/강도 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |예  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |예  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |아니요  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |아니요  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |아니요   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |아니요   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>관련 문서

[Windows 10 v1903의 TLS 암호 제품군](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365의 암호화](encryption.md)
  
[Office 365 Enterprise의 암호화 설정](set-up-encryption.md)
  
[Windows 보안 상태 업데이트에서 TLS 1.0의 Schannel 구현: 2015년 11월 24일](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 암호화 개선 사항(Windows IT 센터)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Office 365 및 Office 365 GCC에서 TLS 1.2 준비](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
