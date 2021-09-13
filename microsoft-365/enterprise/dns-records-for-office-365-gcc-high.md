---
title: Office 365 GCC High용 DNS 레코드
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: '요약: 높은 Office 365 GCC DNS 레코드'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189652"
---
# <a name="dns-records-for-office-365-gcc-high"></a>Office 365 GCC High용 DNS 레코드

*이 문서는 High 및 Office 365 GCC 높음 Microsoft 365 GCC 적용됩니다.*

High를 등록하는 Office 365 GCC 온라인 서비스 테넌트에 SMTP 및 SIP 도메인을 추가해야 합니다.  Azure AD PowerShell의 New-MsolDomain cmdlet을 사용하여 이 작업을 진행하거나 [Azure Government Portal을](https://portal.azure.us) 사용하여 도메인 추가 및 소유권 확인 프로세스를 시작할 수 있습니다.

테넌트에 도메인을 추가하고 유효성을 검사한 후 다음 지침을 사용하여 서비스에 적합한 DNS 레코드를 추가합니다.  인바운드 MX 레코드 및 기존 자동 Exchange 조직 요구에 맞게 아래 표를 수정해야 할 수 있습니다.  이러한 DNS 레코드를 메시징 팀과 조정하여 전자 메일이 잘못 배달되지 않도록 하는 것이 좋습니다.

## <a name="exchange-online"></a>Exchange Online

| 종류 | 우선 순위 | 호스트 이름 | 주소 또는 값을 가리킴 | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us(자세한 내용은 아래 참조) | 1 Hour |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1시간 |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Exchange Autodiscover 레코드

모든 Exchange Server 있는 경우 마이그레이션할 때 기존 레코드를 현재 Exchange Online 레코드를 업데이트하고 마이그레이션을 완료한 후 해당 레코드를 업데이트하는 것이 좋습니다. 

### <a name="exchange-online-mx-record"></a>Exchange Online MX 레코드

허용 도메인의 MX 레코드 값은 위에서 언급한 표준 형식(테넌트 .mail.protection.office365.us)을  따르며, 테넌트는 기본 테넌트 이름의 첫 번째 부분으로 바됩니다. 

예를 들어 테넌트 이름이 contoso.onmicrosoft.us MX 레코드의  값으로 contoso.mail.protection.office365.us 사용할 수 있습니다.

## <a name="skype-for-business-online"></a>비즈니스용 Skype Online

### <a name="cname-records"></a>CNAME 레코드

| 형식 | 호스트 이름 | 주소 또는 값을 가리킴 | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1시간 |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 Hour |

### <a name="srv-records"></a>SRV 레코드

| 형식 | 서비스 | Protocol(프로토콜) | 포트 | 가중치 | 우선 순위 | 이름 | 대상 | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1시간 |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>추가 DNS 레코드

> [!IMPORTANT]
> DNS 영역의 기존 *msoid* CNAME 레코드가 있는  경우 지금 DNS에서 레코드를 제거해야 합니다.  msoid 레코드는 Microsoft 365 Enterprise 앱(이전의 앱)과 Office 365 ProPlus *정품* 인증이 성공하지 못합니다.
