---
title: 암호화에 대한 기술 관련 세부 정보
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
description: Office 365에서 암호화에 사용되는 다양한 인증서, 기술 및 TLS 암호화 제품군에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e4b2923d2b250e85efa7fdc50a995db397d670
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814370"
---
# <a name="technical-reference-details-about-encryption"></a>암호화에 대한 기술 관련 세부 정보

이 문서를 참조하여 Office 365에서 암호화에 사용되는 인증서, 기술 및 TLS [암호화 제품군에 대해 알아봅니다.](encryption.md) 이 문서에서는 미리 정해지는 계획된 제거에 대한 세부 정보도 제공합니다.
  
- 개요 정보를 보려면 [Office 365에서 암호화를 참조하세요.](encryption.md)
- 설정 정보를 찾고 있다면 [Office 365 Enterprise에서 암호화 설정을 참조하세요.](set-up-encryption.md)
- 특정 Windows 버전에서 지원되는 암호화 제품군에 대한 자세한 내용은 [TLS/SSL(Schannel SSP)의 암호화 제품군을 참조하세요.](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 인증서 소유권 및 관리

Microsoft는 자체 인증서를 사용하므로 Office 365에 대한 인증서를 구입하거나 유지 관리할 필요가 없습니다.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>현재 암호화 표준 및 이러한 사용 기간 제거

Office 365에 대해 최고의 암호화를 계속 제공하기 위해 Microsoft는 정기적으로 지원되는 암호화 표준을 검토합니다. 경우에 따라 이전 표준이 최신이 아닐 수 있어 서기가 더 안전하지않아지므로 사용하지 않아도 됩니다. 이 항목에서는 현재 지원되는 암호 그룹 및 기타 표준과 계획된 사용 기간에 대한 세부 정보를 설명합니다. 

## <a name="fips-compliance-for-office-365"></a>Office 365에 대한 FIPS 규정 준수

Office 365에서 지원되는 모든 암호화 제품군은 FIPS 140-2에서 허용되는 사용 알고리즘입니다. Office 365는 Windows에서(Schannel을 통해) FIPS 유효성 검사를 상속합니다. Schannel에 대한 자세한 내용은 [TLS/SSL(Schannel SSP)의 암호화 제품군을 참조하세요.](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365에서 지원하는 TLS 버전

TLS(전송 계층 보안) 및 TLS 이전의 SSL은 보안 인증서를 사용하여 컴퓨터 간 연결을 암호화함으로써 네트워크를 통한 통신을 보호하는 암호화 프로토콜입니다. Office 365에서는 TLS 버전 1.2(TLS 1.2)를 지원합니다.

현재 TLS 버전 1.3(TLS 1.3)은 지원되지 않습니다.
  
## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>TLS 1.0 및 1.1 사용 상각 도상 및 이것의 의미

2018년 10월 31일부터 Office 365는 더 이상 TLS 1.0 및 1.1을 지원하지 않습니다. 즉 Microsoft는 TLS 1.0 및 1.1을 사용하여 Office 365와 연결되는 클라이언트, 장치 또는 서비스에서 발견된 새로운 문제를 수정하지 않을 것입니다. GCC High 및 DoD 환경에서 공식 감가 상각은 2020년 1월 15일까지 시작되었습니다. 전 세계에서 TLS 1.0 및 1.1의 사용 기간이 2020년 10월 15일에 시작됩니다. 

모든 클라이언트 서버와 브라우저-서버 조합이 TLS 1.2 및 최신 암호화 제품군을 사용하여 Office 365 및 Microsoft 365 서비스에 대한 보안 연결을 유지하는지 확인해야 합니다. 특정 클라이언트-서버 및 브라우저-서버 조합을 업데이트해야 할 수 있습니다. 이에 미치는 영향에 대한 자세한 내용은 [Office 365에서 TLS 1.2를 필수적으로 사용하도록 준비를 참조하세요.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>3DES에 대한 지원 사용되지 않는 3DES

2018년 10월 31일부터 Office 365에서는 더 이상 Office 365와 통신하기 위해 3DES 암호화 제품군을 사용할 수 없습니다. 더욱 구체적으로, Office 365에서는 사용자 암호화 TLS_RSA_WITH_3DES_EDE_CBC_SHA 지원하지 않습니다. 2019년 2월 28일부터 Office 365에서 이 암호 제품군이 비활성화되었습니다. 이 날짜 이후 Office 365와 통신하는 클라이언트와 서버는 이 항목에 나열된 보다 안전한 암호화 중 하나 이상을 지원해야 [합니다(Office 365에서 지원하는 TLS](#tls-cipher-suites-supported-by-office-365)암호화 제품군 참조).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365에서 SHA-1 인증서를 지원하지 않음

2016년 6월 부상으로Office 365에서는 아웃바운드 또는 인바운드 연결에 대해 SHA-1 인증서를 더 이상 수락하지 않습니다. 현재 인증서 체인에 SHA-1이 포함된 인증서를 사용 중이면 SHA-2(Secure Hash Algorithm 2) 또는 강력한 해시 알고리즘을 사용하도록 체인을 업데이트해야 합니다.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365에서 지원되는 TLS 암호화 제품군

암호화 제품군은 TLS에서 보안 연결을 설정하는 데 사용되는 암호화 알고리즘 모음입니다. Office 365에서 지원하는 암호화 제품군은 강력한 암호화 제품군의 순서대로 제일 강력한 제품군부터 먼저 다음 표에 나열됩니다. Office 365에서 연결 요청을 받으면 Office 365는 제일 먼저 최상위 암호화 제품군을 사용하여 연결하려고 합니다. 그러면, 성공적으로, Office 365에서는 목록에서 두 번째 암호화 제품군을 시도하고 Office 365에서 다른 서버 또는 클라이언트에 연결 요청을 보낼 때 암호화 제품군을 선택하거나 적어도 TLS를 사용할지는 받는 서버 또는 클라이언트에 달려 있습니다.

> [!IMPORTANT]
> TLS 버전은 더 이상 사용되지 않습니다. 새 버전을 사용할 수 *should not be used* 있는 경우에는 더 이상 사용되지 않는 버전을 사용하면 안 됩니다. TLS 1.3은 현재 지원되지 않습니다. 레거시 서비스에 TLS 1.0 또는 1.1이 필요하지 않으면 사용하지 않도록 설정해야 합니다.

| 암호화 제품군 | 키 교환 알고리즘/강도 | PB(Forward Secrecy) | 암호화/강도 | 인증 알고리즘 |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|예 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|예 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |아니요 <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |아니요 <br/> |AES/256 <br/>|RSA/112 <br/> |

이러한 다음 암호 그룹은 사용 기간까지 여전히 TLS 1.0 및 1.1 프로토콜을 지원합니다. 사용 이전 날짜가 2020년 10월 15일이면, 2020년 10월 15일 경제적이었고, 이전 에는 3월 15일 및 GCC 환경이 사요됩니다.

| 프로토콜 | 암호 그룹 이름 | 키 교환 알고리즘/강도 | PC(Forward Secrecy) 지원 | 인증 알고리즘/강도 | 암호화/강도 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |예  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |예  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |아니요  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |아니요  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |아니요   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |아니요   <br/> |RSA/112  <br/> |AES/256  <br/> |
   
## <a name="related-topics"></a>관련 항목
[Windows 10 v1903의 TLS 암호화 제품군](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365의 암호화](encryption.md)
  
[Office 365 Enterprise의 암호화 설정](set-up-encryption.md)
  
[Windows에서 TLS 1.0의 Schannel 구현 보안 상태 업데이트 2015년 11월 24일](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 암호화 향상 기능(Windows IT 센터)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Office 365 및 Office 365 GCC에서 TLS 1.2 준비](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
