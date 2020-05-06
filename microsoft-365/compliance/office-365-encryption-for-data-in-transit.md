---
title: 전송 중인 데이터 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 이 문서에서는 Microsoft 365 고객 데이터를 전송 중에 암호화 하는 방법에 대 한 간략 한 설명을 찾습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ee869308549398a9df00ed42975b4aeedb666a4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033606"
---
# <a name="encryption-for-data-in-transit"></a>전송 중인 데이터 암호화

Microsoft는 휴지 지는 고객 데이터를 보호 하는 것 외에도 암호화 기술을 사용 하 여 전송 중인 고객 데이터를 보호 합니다. 

전송 중인 데이터:

- 클라이언트 컴퓨터가 Microsoft 서버와 통신 하는 경우
- Microsoft 서버가 다른 Microsoft 서버와 통신 하는 경우 한
- Microsoft 서버가 Microsoft가 아닌 서버와 통신 하는 경우 (예: Exchange Online에서 타사 전자 메일 서버로 전자 메일을 배달 하는 경우)

Microsoft 서버 간의 데이터 센터 간 통신은 TLS 또는 IPsec을 통해 수행 되며, 모든 고객 연결 서버가 클라이언트 컴퓨터와 TLS를 사용 하 여 보안 세션을 협상 합니다 (예: Exchange Online은 256 비트 암호화 강도의 TLS 1.2을 사용 합니다 (FIPS 140-2 수준 2-유효성 검사 됨). (Office 365에서 지원 되는 TLS 암호 제품군 목록의 [암호화에 대 한 기술 참조 세부 정보](technical-reference-details-about-encryption.md) 를 참조 하세요.) 이는 Outlook, 비즈니스용 Skype, Microsoft 팀, 웹에서 Outlook과 같은 클라이언트에서 사용 하는 프로토콜에 적용 됩니다 (예: HTTP, POP3 등).

공용 인증서는 전송 되는 정보의 기밀성을 보호 하기 위한 내부 Microsoft 도구인 SSLAdmin을 사용 하 여 Microsoft IT SSL에서 발급 합니다. Microsoft IT에서 발급 한 모든 인증서의 길이는 최소 2048 비트 이며 Webtrust 준수를 사용 하려면 인증서가 Microsoft에서 소유한 공용 IP 주소에만 발급 되도록 해야 합니다. 이 조건을 충족 하지 못하는 모든 IP 주소는 예외 프로세스를 통해 라우팅됩니다.

사용 중인 TLS 버전, 즉 정방향 보안 (FS)을 사용할 수 있는지 여부와 같은 모든 구현 세부 정보를 공개적으로 사용할 수 있습니다. 이러한 세부 정보를 확인 하는 한 가지 방법은 [QUALYS SSL Labs](https://www.ssllabs.com)와 같은 타사 웹 사이트를 사용 하는 것입니다. 다음 서비스에 대 한 정보를 표시 하는 Qualys의 자동화 된 테스트 페이지에 대 한 링크는 다음과 같습니다.

- [Office 365 포털](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [비즈니스용 Skype (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [비즈니스용 Skype (웹)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Exchange Online Protection의 경우 Url은 테 넌 트 이름에 따라 다릅니다. 그러나 모든 고객은 **microsoft-com.mail.protection.outlook.com**을 사용 하 여 Microsoft 365을 테스트할 수 있습니다.
