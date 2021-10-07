---
title: Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 전자 메일 Exchange Online 보안 Microsoft 365 TLS(전송 계층 보안) 및 FS(Forward Secrecy)를 사용하여 전자 메일 통신을 보호하는 방법을 알아보십시오. 또한 Microsoft에서 발급한 인증서에 대한 정보도 Exchange Online.
ms.openlocfilehash: 27b6022b421fce40935def19f614680b7196fd86
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177522"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법

전자 메일 Exchange Online 보안 Microsoft 365 TLS(전송 계층 보안) 및 FS(Forward Secrecy)를 사용하여 전자 메일 통신을 보호하는 방법을 알아보십시오. 또한 Exchange Online용으로 Microsoft에서 발급한 인증서에 대한 정보도 제공합니다.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>TLS 기본 Microsoft 365 및 Exchange Online

TLS(전송 계층 보안) 및 TLS 이전의 SSL은 보안 인증서를 사용하여 컴퓨터 간 연결을 암호화함으로써 네트워크를 통한 통신을 보호하는 암호화 프로토콜입니다. TLS는 SSL(Secure Sockets Layer)을 능가하며 SSL 3.1이라고도 합니다. Exchange Online TLS를 사용하여 Exchange 서버 간의 연결과 Exchange 서버와 다른 서버(예: Exchange Exchange 서버 또는 받는 사람의 메일 서버) 간의 연결을 암호화합니다. 연결이 암호화된 후 해당 연결을 통해 전송되는 모든 데이터는 암호화된 채널을 통해 전송됩니다. 그러나 TLS로 암호화된 연결을 통해 전송된 메시지를 전달하는 경우 해당 메시지가 반드시 암호화되지는 않습니다. 이는 간단한 용어로 TLS는 메시지를 암호화하지 않는 것이고 연결만 암호화하기 때문에 발생합니다.
  
메시지를 암호화하려는 경우 메시지 내용을 암호화하는 암호화 기술을 사용하여 메시지 암호화와 같은 Office 합니다. [OME(Office 365](email-encryption.md) 및 [Office 365 메시지 암호화)의](ome.md) 메시지 암호화 옵션에 대한 자세한 내용은 전자 메일 암호화를 Office 365. 
  
Microsoft와 프레미스 조직 또는 파트너와 같은 다른 조직 간에 보안 대응 채널을 설정하려는 경우 TLS를 사용하는 것이 좋습니다. Exchange Online 전자 메일 보안을 위해 먼저 TLS를 사용하려고 하지만 다른 사용자가 TLS 보안을 제공하지 않는 경우 이 작업을 항상 시도할 수 없습니다. 커넥터를 사용하여 모든 메일을 보호하는 방법 또는 중요한 파트너에 대한 정보를 계속 *읽어 보아야 합니다.* 

고객에게 동급 최고의 암호화를 제공하기 위해 Microsoft는 TLS(전송 계층 보안) 버전 1.0 및 1.1을 Office 365 및 [Office 365 GCC.](tls-1-2-in-office-365-gcc.md) [](tls-1.0-and-1.1-deprecation-for-office-365.md) 그러나 TLS 없이 암호화되지 않은 SMTP 연결을 계속 사용할 수 있습니다. 암호화 없이는 전자 메일 전송을 권장하지 않습니다.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>고객 Exchange Online 간에 TLS를 사용하는 Exchange Online 방법

Exchange Online 서버는 항상 TLS 1.2를 사용하여 데이터 센터의 Exchange Online 서버에 대한 연결을 암호화합니다. 조직 내에 있는 받는 사람에게 메일을 보내면 TLS를 사용하여 암호화된 연결을 통해 해당 전자 메일이 자동으로 전송됩니다. 또한 다른 고객에게 보내는 모든 전자 메일은 TLS를 사용하여 암호화되고 전달 보안 기능을 사용하여 보호된 연결을 통해 전송됩니다.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>신뢰할 Microsoft 365 파트너와 외부 Microsoft 365 간에 TLS를 사용하는 방법

기본적으로 Exchange Online TLS를 항상 사용하게 됩니다. 즉, Exchange Online 가장 안전한 버전의 TLS를 사용하여 연결을 암호화한 다음 두 당사자가 모두 동의할 수 있는 암호를 찾을 때까지 TLS 암호화 목록을 아래로 진행합니다. 받는 사람에게 Exchange Online 보안 연결을 통해서만 전송되도록 구성하지 않은 경우 받는 사람 조직에서 TLS 암호화를 지원하지 않는 경우 기본적으로 메시지는 암호화되지 않은으로 전송됩니다. 대부분의 기업에서는 기회적 TLS로 충분합니다. 그러나 의료, 은행 또는 정부 조직과 같은 규정 준수 요구 사항이 있는 비즈니스의 경우 TLS를 Exchange Online 또는 강제로 구성할 수 있습니다. 자세한 내용은 [Configure mail flow using connectors in Office 365.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
  
조직과 신뢰할 수 있는 파트너 조직 간에 TLS를 구성하기로 결정한 경우 Exchange Online TLS를 사용하여 신뢰할 수 있는 통신 채널을 만들 수 있습니다. 강제 TLS를 사용하려면 파트너 조직에서 메일을 보내기 위해 Exchange Online 인증서로 인증해야 합니다. 파트너는 이를 위해 자체 인증서를 관리해야 합니다. 이 Exchange Online 커넥터를 사용하여 사용자가 받는 사람의 전자 메일 공급자에 도착하기 전에 무단 액세스로부터 보내는 메시지를 보호합니다. 커넥터를 사용하여 메일 흐름을 구성하는 데 대한 자세한 내용은 [Configure mail flow using connectors in Office 365.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 및 하이브리드 Exchange Server 배포

하이브리드 Exchange 배포를 관리하는 경우 사서함이 Exchange 있는 받는 사람에게 메일을 보내기 위해 Microsoft 365 인증서를 사용하여 Exchange 서버에서 인증해야 Office 365. 따라서 해당 서버에 대한 자체 보안 인증서를 관리해야 Exchange 있습니다. 또한 이러한 서버 인증서를 안전하게 저장하고 유지 관리해야 합니다. 하이브리드 배포에서 인증서를 관리하는 데 대한 자세한 내용은 하이브리드 배포에 대한 인증서 요구 [사항을 참조하세요.](/exchange/certificate-requirements)
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Exchange Online TLS를 설정하는 Office 365

Exchange Online 고객의 경우 강제로 TLS가 작동하여 보내고 받은 모든 전자 메일을 보호하려면 TLS가 필요한 커넥터를 두 개 이상 설정해야 합니다. 사용자 사서함으로 전송되는 전자 메일용 커넥터와 사용자 사서함에서 보낸 전자 메일용 커넥터가 필요합니다. 이러한 커넥터는 Exchange 관리 센터에서 Office 365. 자세한 내용은 [Configure mail flow using connectors in Office 365.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
  
## <a name="tls-certificate-information-for-exchange-online"></a>사용자에 대한 TLS 인증서 Exchange Online

다음 표에서는 Exchange Online 사용하는 인증서 정보를 제공합니다. 비즈니스 파트너가 전자 메일 서버에 강제 TLS를 설정하는 경우 이 정보를 제공해야 합니다. 보안상의 이유로 인증서는 수시로 변경됩니다. 데이터 센터 내에서 인증서에 대한 업데이트를 출시했습니다. 새 인증서는 2018년 9월 3일 이후의 유효합니다.
  
 **2018년 9월 3일 이후 유효한 현재 인증서 정보**
  
| 특성 | 값 |
|:-----|:-----|
|인증 기관 루트 발급자  <br/> |GlobalSign Root CA – R1 <br/> |
|인증서 이름  <br/> |mail.protection.outlook.com  <br/> |
|조직  <br/> |Microsoft Corporation  <br/> |
|조직 구성 단위  <br/> |  <br/> |
|인증서 키 강도  <br/> |2048  <br/> |
   
 **사용 불가능한 인증서 정보는 2018년 9월 3일까지 유효합니다.**
  
원활한 전환을 위해 앞으로도 참조를 위해 이전 인증서 정보를 계속 제공하겠지만, 지금부터는 현재 인증서 정보를 사용해야 합니다.
  
****

| 특성 | 값 |
|:-----|:-----|
|인증 기관 루트 발급자  <br/> |Baltimore CyberTrust Root  <br/> |
|인증서 이름  <br/> |mail.protection.outlook.com  <br/> |
|조직  <br/> |Microsoft Corporation  <br/> |
|조직 구성 단위  <br/> |Microsoft Corporation  <br/> |
|인증서 키 강도  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>새 인증서 Exchange Online 준비

새 인증서는 새 CA(인증 기관)에서 인증서에 사용된 이전 인증서와 Exchange Online. 따라서 새 인증서를 사용하려면 일부 작업을 수행해야 할 수 있습니다.

새 인증서를 사용하려면 인증서 유효성 검사의 일부로 새 CA의 끝점에 연결해야 합니다. 이렇게 하지 못하면 메일 흐름에 부정적인 영향을 줄 수 있습니다. 메일 서버가 특정 대상에 연결되는 방화벽으로 메일 서버를 보호하는 경우 서버가 새 인증서의 유효성을 검사할 수 있는지 확인해야 합니다. 서버에서 새 인증서를 사용할 수 있도록 확인을 위해 다음 단계를 완료합니다.

1. 커넥트 사용하여 로컬 Exchange Server Windows PowerShell 다음 명령을 실행합니다.  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. 창이 나타나면 검색을 **선택합니다.**

1. 유틸리티의 확인이 완료되면 상태가 반환됩니다. 상태가 확인으로 **표시될** 경우 메일 서버가 새 인증서의 유효성을 검사할 수 있습니다. 그렇지 않은 경우 연결이 실패하는 원인을 결정해야 합니다. 대부분의 경우 방화벽 설정을 업데이트해야 합니다. 액세스해야 하는 끝점의 전체 목록은 다음과 같습니다.
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

일반적으로 업데이트 업데이트를 통해 루트 인증서에 대한 Windows 수신합니다. 그러나 일부 배포에는 이러한 업데이트가 자동으로 발생하지 않도록 하는 추가 보안이 있습니다. Windows 업데이트에서 루트 인증서를 자동으로 업데이트할 수 없는 잠겨 있는 배포에서는 다음 단계를 완료하여 올바른 루트 CA 인증서가 설치되도록 해야 합니다.
1.  커넥트 사용하여 로컬 Exchange Server Windows PowerShell 다음 명령을 실행합니다.  
  `certmgr.msc`

2. 신뢰할 **수 있는 루트 인증 기관/인증서에서** 새 인증서가 나열되어 있는지 확인할 수 있습니다.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>TLS 및 사용자에 대한 자세한 Microsoft 365

지원되는 암호화 제품군 목록은 암호화에 대한 [기술 참조 세부 정보를 참조하세요.](technical-reference-details-about-encryption.md)
  
[파트너 조직과의 보안 메일 흐름을 위한 커넥터 설정](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[향상된 전자 메일 보안이 포함된 커넥터](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Microsoft 365의 암호화](encryption.md)
