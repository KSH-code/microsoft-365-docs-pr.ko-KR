---
title: 고급 헌팅 schema의 DeviceFileCertificateInfo 테이블
description: 고급 헌팅스키마의 DeviceFileCertificateInfo 표에 있는 파일 서명 정보에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 디지털 서명, 인증서, 파일 서명, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072420"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

고급 `DeviceFileCertificateInfo` 헌팅 [Schema의](advanced-hunting-overview.md) 표에는 파일 서명 인증서에 대한 정보가 포함되어 있습니다. 이 표에서는 끝점의 파일에 대해 정기적으로 수행되는 인증서 확인 활동에서 얻은 데이터를 사용 합니다.

고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `IsSigned` | 부울 | 파일에 서명이 있는지 여부를 나타냅니다. |
| `SignatureType` | 문자열 | 서명 정보가 파일 자체에 포함된 콘텐츠로 읽혀지거나 외부 카탈로그 파일에서 읽어들이는지 여부를 나타냅니다. |
| `Signer` | 문자열 | 파일의 서명자에 대한 정보 |
| `SignerHash` | 문자열 | 서명자를 식별하는 고유 해시 값 |
| `Issuer` | 문자열 | 발급 CA(인증 기관)에 대한 정보 |
| `IssuerHash` | 문자열 | 발급 CA(인증 기관)를 식별하는 고유 해시 값 |
| `CertificateSerialNumber` | 문자열 | 발급 CA(인증 기관)에 고유한 인증서의 식별자 |
| `CrlDistributionPointUrls` | 문자열 |  인증서 및 CRL(인증서 해지 목록)이 포함된 네트워크 공유의 URL을 나열하는 JSON 배열 |
| `CertificateCreationTime` | datetime | 인증서를 만든 날짜 및 시간 |
| `CertificateExpirationTime` | datetime | 인증서가 만료되는 날짜 및 시간 |
| `CertificateCountersignatureTime` | datetime | 인증서가 연대 서명된 날짜 및 시간 |
| `IsTrusted` | 부울 | 알 수 없는 루트 인증서 정보, 잘못된 서명, 해지된 인증서 및 기타 의심되는 특성을 검사하는 WinVerifyTrust 함수의 결과에 따라 파일을 신뢰할 수 있는지 여부를 나타냅니다. |
| `IsRootSignerMicrosoft` | 부울 | 루트 인증서의 서명자인지 여부를 나타냅니다. |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |


## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)
