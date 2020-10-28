---
title: 암호화에 대 한 기술 참조 세부 정보
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
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Office 365에서 암호화에 사용 되는 다양 한 인증서, 기술 및 TLS 암호 제품군에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb45f325095143e6f66d9cd2bfa6f3875fb03043
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769178"
---
# <a name="technical-reference-details-about-encryption"></a>암호화에 대 한 기술 참조 세부 정보

이 문서를 참조 하 여 [Office 365에서 암호화](encryption.md)에 사용 되는 인증서, 기술 및 TLS 암호 제품군에 대해 알아봅니다. 이 문서에서는 계획 된 사용 중단에 대 한 세부 정보도 제공 합니다.

- 개요 정보를 찾으려면 [Encryption In Office 365](encryption.md)을 참조 하세요.
- 설치 정보를 찾으려면 [Set up encryption In Office 365 Enterprise](set-up-encryption.md)를 참조 하세요.
- 특정 Windows 버전에서 지원 되는 암호 그룹에 대 한 자세한 내용은 [TLS/SSL (SCHANNEL SSP)의 암호 그룹](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)을 참조 하십시오.

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 인증서 소유권 및 관리

Microsoft는 자체 인증서를 사용하므로 Office 365에 대한 인증서를 구입하거나 유지 관리할 필요가 없습니다.

## <a name="current-encryption-standards-and-planned-deprecations"></a>현재 암호화 표준 및 계획 된 사용 중단

Office 365에 대 한 모범 사례 암호화를 계속 해 서 제공 하기 위해 Microsoft는 지원 되는 암호화 표준을 정기적으로 검토 합니다. 경우에 따라 오래 된 표준을 유지 하 고 보안 수준이 더 낮은 경우에는 이전 표준과 사용 중지 야 합니다. 이 항목에서는 현재 지원 되는 암호 제품군 및 기타 표준과 계획 된 사용 중단에 대 한 세부 정보를 설명 합니다.

## <a name="fips-compliance-for-office-365"></a>Office 365에 대 한 FIPS 준수

Office 365에서 지 원하는 모든 암호화 제품군은 FIPS 140-2에서 허용 되는 알고리즘을 사용 합니다. Office 365은 Windows에서 FIPS 유효성 검사를 상속 합니다 (Schannel을 통해). Schannel에 대 한 자세한 내용은 [TLS/SSL (SCHANNEL SSP)의 암호 그룹](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)을 참조 하세요.

## <a name="versions-of-tls-supported-by-office-365"></a>Office 365에서 지원하는 TLS 버전

TLS(전송 계층 보안) 및 TLS 이전의 SSL은 보안 인증서를 사용하여 컴퓨터 간 연결을 암호화함으로써 네트워크를 통한 통신을 보호하는 암호화 프로토콜입니다. Office 365는 tls 버전 1.2 (TLS 1.2)를 지원 합니다.

TLS 버전 1.3 (TLS 1.3)은 현재 지원 되지 않습니다.

## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>TLS 1.0 및 1.1의 사용을 지원 하 고이에 대 한 지원을 제공 합니다.

2018는 Office 365에서 더 이상 TLS 1.0 및 1.1을 지원 하지 않으므로 10 월 31 일 이후로 발생 합니다. 즉 Microsoft는 TLS 1.0 및 1.1을 사용하여 Office 365와 연결되는 클라이언트, 장치 또는 서비스에서 발견된 새로운 문제를 수정하지 않을 것입니다. GCC High 및 DoD 환경에 대 한 공식적인 중단은 2020 년 1 월 15 일에 시작 됩니다. 전 세계 및 GCC 환경에 대 한 TLS 1.0 및 1.1의 중단은 2020 년 10 월 15 일에 시작 됩니다.

모든 클라이언트 서버와 브라우저 서버 조합에서 TLS 1.2 및 최신 암호 그룹을 사용 하 여 Office 365 및 Microsoft 365 서비스에 대 한 안전한 연결을 유지 하도록 해야 합니다. 특정 클라이언트-서버 및 브라우저-서버 조합을 업데이트해야 할 수 있습니다. 이를 통해 영향을 주는 방법에 대 한 자세한 내용은 [Office 365에서 TLS 1.2의 필수 사용 준비](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)를 참조 하세요.

## <a name="deprecating-support-for-3des"></a>3DES에 대 한 방식 지원

2018 년 10 월 31 일 이후로 office 365에서는 Office 365로의 통신에 3DES 암호 제품군을 사용 하는 것을 더 이상 지원 하지 않습니다. 보다 구체적으로 말하면 Office 365에서는 TLS_RSA_WITH_3DES_EDE_CBC_SHA 암호 제품군을 더 이상 지원 하지 않습니다. 2019 년 2 월 28 일부 터이 암호 제품군은 Office 365에서 사용 하지 않도록 설정 되었습니다. 이 날짜 후에 Office 365와 통신 하는 클라이언트 및 서버는이 항목에 나열 된 보안 암호 중 하나 이상을 지원 해야 합니다 ( [Office 365에서 지 원하는 TLS 암호 제품군](#tls-cipher-suites-supported-by-office-365)참조).

## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365에서 SHA-1 인증서를 지원하지 않음

6 월 2016 일에 Office 365에서는 아웃 바운드 또는 인바운드 연결에 대 한 SHA-1 인증서를 더 이상 받아들이지 않습니다. 현재 인증서 체인에서 s h a-1이 포함 된 인증서를 사용 하는 경우에는 SHA-2 (보안 해시 알고리즘 2) 또는 보다 강력한 해싱 알고리즘을 사용 하도록 체인을 업데이트 해야 합니다.

## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365에서 지원 되는 TLS 암호 그룹

암호화 제품군은 TLS에서 보안 연결을 설정하는 데 사용되는 암호화 알고리즘 모음입니다. Office 365에서 지원하는 암호화 제품군은 강력한 암호화 제품군의 순서대로 제일 강력한 제품군부터 먼저 다음 표에 나열됩니다. Office 365에서 연결 요청을 받으면 먼저 Office 365에서 맨 위의 암호 제품군을 사용 하 여 연결을 시도 합니다. 그런 다음 실패 하면 Office 365에서 목록의 두 번째 암호 그룹을 시도 하 고 목록에서 아래로 이동 합니다. Office 365에서 다른 서버 또는 클라이언트에 연결 요청을 보낼 때 암호화 제품군을 선택하거나 적어도 TLS를 사용할지는 받는 서버 또는 클라이언트에 달려 있습니다.

> [!IMPORTANT]
> TLS 버전은 사용 중지, 더 이상 사용 되지 않는 버전은 최신 버전을 사용할 수 있는 경우 *사용 하지 않도록 해야* 합니다. TLS 1.3은 현재 지원 되지 않습니다. 레거시 서비스에 TLS 1.0 또는 1.1가 필요 하지 않은 경우에는 사용 하지 않도록 설정 해야 합니다.

| 암호 제품군 | 키 교환 알고리즘/강도 | 전달 완전 보안 | 암호화/강도 | 인증 알고리즘 |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |아니요 <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |아니요 <br/> |AES/256 <br/>|RSA/112 <br/> |

이러한 암호 제품군은 여전히 해당 기간 동안 TLS 1.0 및 1.1 프로토콜을 지원 합니다. 해당 출시 날짜가 1 월 15 일, 2020, 그리고 해당 날짜가 10 월 15 2020 일에 해당 하는 전 세계 및 GCC 환경에 해당 하는 GCC High 및 DoD 환경의 경우

| 프로토콜 | 암호 그룹 이름 | 키 교환 알고리즘/강도 | 전달 완전 완벽 지원 | 인증 알고리즘/강도 | 암호화/강도 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |예  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |예  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |아니요  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |아니요  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |아니요   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |아니요   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-topics"></a>관련 항목
[Windows 10 v1903의 TLS 암호 그룹](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365의 암호화](encryption.md)

[Office 365 Enterprise의 암호화 설정](set-up-encryption.md)

[암호화 위험 및 보호](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections?view=o365-worldwide)

[Windows 보안 상태 업데이트에서 TLS 1.0의 Schannel 구현: 2015 년 11 월 24 일](https://support.microsoft.com/kb/3117336)

[TLS/SSL 암호화 향상 (Windows IT 센터)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)

[Office 365 및 Office 365 GCC에서 TLS 1.2 준비](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
