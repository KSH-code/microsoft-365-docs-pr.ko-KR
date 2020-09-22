---
title: 고급 구하기 스키마의 DeviceFileCertificateInfo 테이블
description: 고급 구하기 스키마의 DeviceFileCertificateInfo 테이블에 있는 파일 서명 정보에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, 디지털 서명, 인증서, 파일 서명, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 69669366f4f4d79f7c9ec7f28c8ccf1336e96adc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198229"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

`DeviceFileCertificateInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 파일 서명 인증서에 대 한 정보가 포함 되어 있습니다. 이 테이블은 끝점에서 파일에 대해 정기적으로 수행 되는 인증서 확인 작업에서 얻은 데이터를 사용 합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `IsSigned` | 부울 | 파일 서명 여부를 나타냅니다. |
| `SignatureType` | 문자열 | 서명 정보가 파일 자체에 포함 된 콘텐츠 인지 아니면 외부 카탈로그 파일에서 읽 었는 지를 나타냅니다. |
| `Signer` | 문자열 | 파일의 서명자에 대 한 정보 |
| `SignerHash` | 문자열 | 서명자를 식별 하는 고유한 해시 값 |
| `Issuer` | 문자열 | 발급 CA (인증 기관)에 대 한 정보 |
| `IssuerHash` | 문자열 | 발급 CA (인증 기관)를 식별 하는 고유한 해시 값 |
| `CertificateSerialNumber` | 문자열 | 발급 CA (인증 기관)에 고유한 인증서의 식별자입니다. |
| `CrlDistributionPointUrls` | 문자열 |  인증서 및 Crl (인증서 해지 목록)이 포함 된 네트워크 공유의 Url을 나열 하는 JSON 배열 |
| `CertificateCreationTime` | datetime | 인증서를 만든 날짜 및 시간입니다. |
| `CertificateExpirationTime` | datetime | 인증서가 만료 되도록 설정 된 날짜 및 시간 |
| `CertificateCountersignatureTime` | datetime | 인증서가 연대 된 날짜 및 시간 |
| `IsTrusted` | 부울 | 알 수 없는 루트 인증서 정보, 유효 하지 않은 서명, 해지 된 인증서 및 기타 불확실 한 특성이 있는지 확인 하는 WinVerifyTrust 함수 결과에 따라 파일을 신뢰할 수 있는지 여부를 나타냅니다. |
| `IsRootSignerMicrosoft` | 부울 | 루트 인증서의 서명자가 Microsoft 인지 여부를 나타냅니다. |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다. | 

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
