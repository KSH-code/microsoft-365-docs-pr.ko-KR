---
title: 암호화 위험 및 보호
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
ms.custom:
- seo-marvel-mar2020
description: 이 문서에서는 보호에 사용할 수 있는 암호화 Office 365 위험에 대해 학습합니다.
ms.openlocfilehash: 6bb0e705095b4f31c730a21921985131785dc3f0
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216695"
---
# <a name="encryption-risks-and-protections"></a>암호화 위험 및 보호

Microsoft는 Microsoft 365 및 고객 데이터에 대한 위험에 중점을 두는 제어 및 규정 준수 프레임워크를 준수합니다. Microsoft는 이러한 위험을 완화하기 위해 대규모 기술 및 프로세스 기반 방법(제어라고도 합니다.)을 구현합니다. 컨트롤을 통한 위험 식별, 평가 및 완화는 지속적인 프로세스입니다. 

시설, 네트워크, 서버, 응용 프로그램, 사용자(예: Microsoft 관리자) 및 데이터와 같은 클라우드 서비스의 다양한 계층 내에서 제어를 구현하는 것이 심층 방어 전략을 형성합니다. 이 전략의 핵심은 동일하거나 유사한 위험 시나리오로부터 보호하기 위해 여러 계층에서 다양한 컨트롤이 구현되는 것입니다. 이러한 다계층 접근 방식은 어떤 이유로 인해 컨트롤이 실패할 경우 안전하지 않습니다.

일부 위험 시나리오 및 이러한 위험을 완화하는 현재 사용 가능한 암호화 기술은 아래에 나와 있습니다. 이러한 시나리오는 대부분의 경우 해당 시나리오에서 구현된 다른 컨트롤을 통해 Office 365.

| 암호화 기술 | 서비스 | 키 관리 | 위험 시나리오 | 값 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online, SharePoint Online 및 비즈니스용 Skype | Microsoft | 디스크나 서버가 도난당하거나 잘못 재생됩니다. | BitLocker는 도난되거나 부적절하게 재활용된 하드웨어(서버/디스크)로 인한 데이터 손실을 방지하는 장애 조치(fail-safe) 접근 방식을 제공합니다. |
| 서비스 암호화 | SharePoint 온라인, 비즈니스용 Skype 및 비즈니스용 OneDrive; Exchange Online(로드맵 사용) | Microsoft | 내부 또는 외부 해커가 개별 파일/데이터에 Blob으로 액세스합니다. | 암호화된 데이터는 키에 액세스하지 않고는 암호를 해독할 수 없습니다. 해커가 데이터에 액세스하는 위험을 완화하는 데 도움이 됩니다. |
| 고객 키 | SharePoint 온라인, 비즈니스용 OneDrive, Exchange Online 및 비즈니스용 Skype | 고객 | N/A(이 기능은 모든 위험을 완화하는 것이 아니라 규정 준수 기능으로 설계됩니다.) | 고객이 내부 규정 및 규정 준수 의무를 충족하고 서비스를 떠나 Microsoft의 데이터에 대한 액세스를 해지할 수 있도록 지원 |
| 클라이언트와 Microsoft 365 간의 TLS | Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Teams 및 Yammer | Microsoft, 고객 | 인터넷을 통해 클라이언트 컴퓨터와 클라이언트 컴퓨터 Microsoft 365 데이터 흐름을 탭하는 중간 또는 기타 공격 | 이 구현은 Microsoft와 고객 모두에게 가치를 제공하며 데이터 무결성을 보장하며, 데이터 무결성이 Microsoft 365 보장합니다. |
| Microsoft 데이터 센터 간의 TLS | Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 비즈니스용 Skype | Microsoft | 다른 Microsoft 데이터 센터에 있는 Microsoft 365 서버 간의 고객 데이터 흐름을 탭하기 위한 중간 또는 기타 공격 | 이 구현은 Microsoft 데이터 센터 간의 공격으로부터 데이터를 보호하는 또 다른 방법입니다. |
| Azure 권한 관리(Microsoft 365 또는 Azure Information Protection에 포함) | Exchange Online, SharePoint Online 및 비즈니스용 OneDrive | 고객 | 데이터는 데이터에 액세스할 수 없는 사람의 손에 들어 있습니다. | Azure Information Protection은 암호화, ID 및 권한 부여 정책을 사용하여 고객에게 가치를 제공하는 Azure RMS를 사용하여 여러 장치에서 파일 및 전자 메일을 보호합니다. Azure RMS는 특정 기준(즉, 특정 주소의 모든 전자 메일)과 일치하는 모든 전자 메일이 다른 받는 사람에게 전송되기 전에 자동으로 암호화될 수 있는 Microsoft 365 고객에게 가치를 제공합니다. |
| S/MIME | Exchange Online | 고객 | 전자 메일은 받는 사람이 아닌 사람의 손에 들어 있습니다. | S/MIME은 S/MIME으로 암호화된 전자 메일이 전자 메일을 직접 받는 사람만 해독할 수 있도록 하여 고객에게 가치를 제공합니다. |
| Office 365 메시지 암호화 | Exchange Online, SharePoint Online | 고객 | 보호된 첨부 파일을 포함한 전자 메일은 전자 메일의 받는 사람이 아닌 Microsoft 365 또는 외부에 있는 사람을 수락합니다. | OME는 특정 조건과 일치하는 Microsoft 365(즉, 특정 주소의 모든 전자 메일)가 다른 내부 또는 외부 받는 사람에게 전송되기 전에 자동으로 암호화되는 고객에게 가치를 제공합니다. |
| 파트너 조직과의 SMTP TLS | Exchange Online | 고객 | 전자 메일은 테넌트에서 다른 파트너 조직으로 전송되는 동안 중간 또는 기타 공격을 통해 Microsoft 365 가로채기됩니다. | 이 시나리오는 고객이 암호화된 SMTP 채널 내에서 Microsoft 365 테넌트와 파트너의 전자 메일 조직 간에 모든 전자 메일을 보내고 받을 수 있도록 고객에게 가치를 제공합니다. |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>다중 테넌트 환경에서 사용할 수 있는 암호화 기술

| 암호화 기술 | 구현한 경우 | 주요 Exchange 알고리즘 및 강도 | 키 관리\* | FIPS 140-2 유효성 검사 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256비트 | AES 외부 키는 비밀 금고 서버의 레지스트리에 Exchange 저장됩니다. 비밀 금고 액세스하려면 높은 수준의 권한 상승 및 승인이 필요한 보안 저장소입니다. Lockbox라는 내부 도구를 사용하여 액세스 권한을 요청하고 승인할 수 있습니다. AES 외부 키도 서버의 신뢰할 수 있는 플랫폼 모듈에 저장됩니다. 48자리 숫자 암호는 Active Directory에 저장되고 Lockbox에 의해 보호됩니다. | 예 |
|  | SharePoint Online | AES 256비트 | AES 외부 키는 비밀 키에 금고. 비밀 금고 액세스하려면 높은 수준의 권한 상승 및 승인이 필요한 보안 저장소입니다. Lockbox라는 내부 도구를 사용하여 액세스 권한을 요청하고 승인할 수 있습니다. AES 외부 키도 서버의 신뢰할 수 있는 플랫폼 모듈에 저장됩니다. 48자리 숫자 암호는 Active Directory에 저장되고 Lockbox에 의해 보호됩니다. | 예 |
|  | 비즈니스용 Skype | AES 256비트 | AES 외부 키는 비밀 키에 금고. 비밀 금고 액세스하려면 높은 수준의 권한 상승 및 승인이 필요한 보안 저장소입니다. Lockbox라는 내부 도구를 사용하여 액세스 권한을 요청하고 승인할 수 있습니다. AES 외부 키도 서버의 신뢰할 수 있는 플랫폼 모듈에 저장됩니다. 48자리 숫자 암호는 Active Directory에 저장되고 Lockbox에 의해 보호됩니다. | 예 |
| 서비스 암호화 | SharePoint Online | AES 256비트 | Blob을 암호화하는 데 사용되는 키는 온라인 콘텐츠 SharePoint 저장됩니다. 온라인 SharePoint 데이터베이스는 미사용 데이터베이스 액세스 제어 및 암호화로 보호됩니다. 암호화는 암호화에서 TDE를 사용하여 Azure SQL Database. 이러한 비밀은 테넌트 수준이 아닌 SharePoint Online의 서비스 수준에 있습니다. 이러한 비밀(마스터 키라고도 불리며)은 키 저장소라는 별도의 보안 저장소에 저장됩니다. TDE는 활성 데이터베이스와 데이터베이스 백업 및 트랜잭션 로그 모두에 대해 미사용 보안을 제공합니다. 고객이 선택적 키를 제공하는 경우 고객 키는 Azure Key Vault에 저장되고 서비스에서는 키로 테넌트 키를 암호화합니다. 이 키는 사이트 키를 암호화하는 데 사용되며, 이 키는 파일 수준 키를 암호화하는 데 사용됩니다. 기본적으로 고객이 키를 제공하면 새 키 계층 구조가 도입됩니다. | 예 |
|  | 비즈니스용 Skype | AES 256비트 | 각 데이터는 임의로 생성된 256비트 키를 사용하여 암호화됩니다. 암호화 키는 해당 메타데이터 XML 파일에 저장되며, 회의당 마스터 키로도 암호화됩니다. 또한 마스터 키는 회의당 한 번씩 임의로 생성됩니다. | 예 |
|  | Exchange Online | AES 256비트 | 각 사서함은 Microsoft(로드맵 사용) 또는 고객이 제어하는 암호화 키를 사용하는 데이터 암호화 정책을 사용하여 암호화됩니다(고객 키 사용 시). | 예 |
| Microsoft 365 및 클라이언트/파트너 간의 TLS | Exchange Online | [여러 암호 제품군을 지원하는 기회적 TLS](./exchange-online-uses-tls-to-secure-email-connections.md) | Exchange Online(outlook.office.com)에 대한 TLS 인증서는 Baltimore CyberTrust Root에서 발급한 2048비트 SHA256RSA 인증서입니다. <br> <br> Exchange Online TLS 루트 인증서는 Baltimore CyberTrust 루트에서 발급한 2048비트 SHA1RSA 인증서입니다. | 예, 256비트 암호 강도를 사용하는 TLS 1.2가 사용되는 경우 |
|  | SharePoint Online | TLS 1.2 with AES 256 <br> <br> [비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화](./data-encryption-in-odb-and-spo.md) | SharePoint Online(*.sharepoint.com)에 대한 TLS 인증서는 Baltimore CyberTrust Root에서 발급한 2048비트 SHA256RSA 인증서입니다. <br> <br> SharePoint Online용 TLS 루트 인증서는 Baltimore CyberTrust 루트에서 발급한 2048비트 SHA1RSA 인증서입니다. | 예 |
|  | 비즈니스용 Skype | [SIP 통신 및 PSOM 데이터 공유 세션에 대한 TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | 비즈니스용 Skype(*.lync.com)에 대한 TLS 인증서는 Baltimore CyberTrust Root에서 발급한 2048비트 SHA256RSA 인증서입니다. <br> <br> 비즈니스용 Skype TLS 루트 인증서는 Baltimore CyberTrust 루트에서 발급한 2048비트 SHA256RSA 인증서입니다. | 예 |
|  | Microsoft Teams | TLS 1.2 with AES 256 <br> <br> [사용자에 대한 질문과 Microsoft Teams - 관리자 도움말](/MicrosoftTeams/teams-overview) | Microsoft Teams(teams.microsoft.com, edge.skype.com)에 대한 TLS 인증서는 Baltimore CyberTrust Root에서 발급한 2048비트 SHA256RSA 인증서입니다. <br> <br> Microsoft Teams TLS 루트 인증서는 Baltimore CyberTrust 루트에서 발급한 2048비트 SHA256RSA 인증서입니다. | 예 |
| Microsoft 데이터 센터 간의 TLS | 모든 Microsoft 365 서비스 | TLS 1.2 with AES 256 <br> <br> SRTP(Secure Real-time Transport Protocol) | Microsoft는 Microsoft 데이터 센터 간의 서버 간 통신에 내부적으로 관리되고 배포된 인증 기관을 사용 합니다. | 예 |
| Azure 권한 관리(Microsoft 365 또는 Azure Information Protection에 포함) | Exchange Online | 업데이트 및 향상된 RMS 암호화 구현인 암호화 모드 [2를](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))지원합니다. 서명 및 암호화를 위해 RSA 2048을 지원하고 서명의 해시에는 SHA-256을 지원합니다. | [Microsoft에서 관리합니다.](/azure/information-protection/plan-implement-tenant-key) | 예 |
|  | SharePoint Online | 업데이트 및 향상된 RMS 암호화 구현인 암호화 모드 [2를](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))지원합니다. 서명 및 암호화를 위한 RSA 2048과 서명에 대해 SHA-256을 지원합니다. | [기본 설정인 Microsoft에서](/azure/information-protection/plan-implement-tenant-key)관리합니다. 또는 <br> <br> Microsoft에서 관리하는 키 대신 사용할 수 있는 고객 관리 IT 관리 Azure 구독이 있는 조직은 BYOK를 사용하여 추가 비용 없는 사용 현황을 기록할 수 있습니다. 자세한 내용은 자체 키 [구현을 참조하세요.](/azure/information-protection/plan-implement-tenant-key) 이 구성에서 nCipher HSM은 키를 보호하는 데 사용됩니다. 자세한 내용은 [nCipher HSM 및 Azure RMS를 참조하세요.](https://www.thales-esecurity.com/msrms/cloud) | 예 |
| S/MIME | Exchange Online | 암호화 메시지 구문 Standard 1.5(PKCS #7) | 배포된 고객 관리 공개 키 인프라에 따라 다를 수 있습니다. 키 관리는 고객이 수행하며 Microsoft는 서명 및 암호 해독에 사용되는 개인 키에 액세스할 수 없습니다. | 예, 3DES 또는 AES256을 사용하여 발신 메시지를 암호화하도록 구성된 경우 |
| Office 365 메시지 암호화 | Exchange Online | Azure RMS(서명 및 암호화용 암호화용 암호화 모드[2](./technical-reference-details-about-encryption.md) - RSA 2048 및 서명용 SHA-256)와 동일 | Azure Information Protection을 암호화 인프라로 사용합니다. 사용되는 암호화 방식은 메시지 암호화 및 암호 해독에 사용되는 RMS 키를 얻은 위치에 따라 다릅니다. | 예 |
| 파트너 조직과의 SMTP TLS | Exchange Online | TLS 1.2 with AES 256 | Exchange Online(outlook.office.com)에 대한 TLS 인증서는 DigiCert Cloud Services CA-1에서 발급한 RSA 암호화 인증서가 있는 2048비트 SHA-256입니다. <br> <br> Exchange Online TLS 루트 인증서는 GlobalSign Root CA - R1에서 발급한 RSA 암호화 인증서가 있는 2048비트 [SHA-1입니다.](./exchange-online-uses-tls-to-secure-email-connections.md#tls-certificate-information-for-exchange-online) <br> <br> 보안상의 이유로 인증서는 수시로 변경됩니다. | 예, 256비트 암호 강도를 사용하는 TLS 1.2가 사용되는 경우 |

*\*이 표에서 참조되는 TLS 인증서는 미국 데이터 센터용입니다. 미국이 아닌 데이터 센터도 2048비트 SHA256RSA 인증서를 사용 합니다.*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>정부 클라우드 커뮤니티 환경에서 사용할 수 있는 암호화 기술

| 암호화 기술 | 구현한 경우 | 주요 Exchange 알고리즘 및 강도 | 키 관리\* | FIPS 140-2 유효성 검사 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256비트 | AES 외부 키는 비밀 금고 서버의 레지스트리에 Exchange 저장됩니다. 비밀 금고 액세스하려면 높은 수준의 권한 상승 및 승인이 필요한 보안 저장소입니다. Lockbox라는 내부 도구를 사용하여 액세스 권한을 요청하고 승인할 수 있습니다. AES 외부 키도 서버의 신뢰할 수 있는 플랫폼 모듈에 저장됩니다. 48자리 숫자 암호는 Active Directory에 저장되고 Lockbox에 의해 보호됩니다. | 예 |
|  | SharePoint Online | AES 256비트 | AES 외부 키는 비밀 키에 금고. 비밀 금고 액세스하려면 높은 수준의 권한 상승 및 승인이 필요한 보안 저장소입니다. Lockbox라는 내부 도구를 사용하여 액세스 권한을 요청하고 승인할 수 있습니다. AES 외부 키도 서버의 신뢰할 수 있는 플랫폼 모듈에 저장됩니다. 48자리 숫자 암호는 Active Directory에 저장되고 Lockbox에 의해 보호됩니다. | 예 |
|  | 비즈니스용 Skype | AES 256비트 | AES 외부 키는 비밀 키에 금고. 비밀 금고 액세스하려면 높은 수준의 권한 상승 및 승인이 필요한 보안 저장소입니다. Lockbox라는 내부 도구를 사용하여 액세스 권한을 요청하고 승인할 수 있습니다. AES 외부 키도 서버의 신뢰할 수 있는 플랫폼 모듈에 저장됩니다. 48자리 숫자 암호는 Active Directory에 저장되고 Lockbox에 의해 보호됩니다. | 예 |
| 서비스 암호화 | SharePoint Online | AES 256비트 | Blob을 암호화하는 데 사용되는 키는 온라인 콘텐츠 SharePoint 저장됩니다. 온라인 SharePoint 데이터베이스는 미사용 데이터베이스 액세스 제어 및 암호화로 보호됩니다. 암호화는 암호화에서 TDE를 사용하여 Azure SQL Database. 이러한 비밀은 테넌트 수준이 아닌 SharePoint Online의 서비스 수준에 있습니다. 이러한 비밀(마스터 키라고도 불리며)은 키 저장소라는 별도의 보안 저장소에 저장됩니다. TDE는 활성 데이터베이스와 데이터베이스 백업 및 트랜잭션 로그 모두에 대해 미사용 보안을 제공합니다. 고객이 선택적 키를 제공하는 경우 고객 키는 Azure Key Vault에 저장되고 서비스에서는 키로 테넌트 키를 암호화하며, 이 키는 사이트 키를 암호화하는 데 사용되며, 이 키는 파일 수준 키를 암호화하는 데 사용됩니다. 기본적으로 고객이 키를 제공하면 새 키 계층 구조가 도입됩니다. | 예 |
|  | 비즈니스용 Skype | AES 256비트 | 각 데이터는 임의로 생성된 256비트 키를 사용하여 암호화됩니다. 암호화 키는 해당 메타데이터 XML 파일에 저장되며, 회의당 마스터 키로도 암호화됩니다. 또한 마스터 키는 회의당 한 번씩 임의로 생성됩니다. | 예 |
|  | Exchange Online | AES 256비트 | 각 사서함은 Microsoft 또는 고객이 제어하는 암호화 키를 사용하는 데이터 암호화 정책을 사용하여 암호화됩니다(고객 키 사용 시). | 예 |
| Microsoft 365 및 클라이언트/파트너 간의 TLS | Exchange Online | [여러 암호 제품군을 지원하는 기회적 TLS](./exchange-online-uses-tls-to-secure-email-connections.md) | Exchange Online(outlook.office.com)에 대한 TLS 인증서는 Baltimore CyberTrust Root에서 발급한 2048비트 SHA256RSA 인증서입니다. <br> <br> Exchange Online TLS 루트 인증서는 Baltimore CyberTrust 루트에서 발급한 2048비트 SHA1RSA 인증서입니다. | 예, 256비트 암호 강도를 사용하는 TLS 1.2가 사용되는 경우 |
|  | SharePoint Online | TLS 1.2 with AES 256 | SharePoint Online(*.sharepoint.com)에 대한 TLS 인증서는 Baltimore CyberTrust Root에서 발급한 2048비트 SHA256RSA 인증서입니다. <br> <br> SharePoint Online용 TLS 루트 인증서는 Baltimore CyberTrust 루트에서 발급한 2048비트 SHA1RSA 인증서입니다. | 예 |
|  | 비즈니스용 Skype | SIP 통신 및 PSOM 데이터 공유 세션에 대한 TLS | 비즈니스용 Skype(*.lync.com)에 대한 TLS 인증서는 Baltimore CyberTrust Root에서 발급한 2048비트 SHA256RSA 인증서입니다. <br> <br> 비즈니스용 Skype TLS 루트 인증서는 Baltimore CyberTrust 루트에서 발급한 2048비트 SHA256RSA 인증서입니다. | 예 |
|  | Microsoft Teams | [사용자에 대한 질문과 Microsoft Teams - 관리자 도움말](/MicrosoftTeams/teams-overview) | Microsoft Teams(teams.microsoft.com; edge.skype.com)에 대한 TLS 인증서는 Baltimore CyberTrust Root에서 발급한 2048비트 SHA256RSA 인증서입니다. <br> <br> Microsoft Teams TLS 루트 인증서는 Baltimore CyberTrust 루트에서 발급한 2048비트 SHA256RSA 인증서입니다. | 예 |
| Microsoft 데이터 센터 간의 TLS | Exchange Online, SharePoint Online, 비즈니스용 Skype | TLS 1.2 with AES 256 | Microsoft는 Microsoft 데이터 센터 간의 서버 간 통신에 내부적으로 관리되고 배포된 인증 기관을 사용 합니다. | 예 |
|  |  | SRTP(Secure Real-time Transport Protocol) |  |  |
| Azure 권한 관리 서비스 | Exchange Online | 업데이트 및 향상된 RMS 암호화 구현인 암호화 모드 [2를](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))지원합니다. 서명 및 암호화를 위해 RSA 2048을 지원하고 서명의 해시에는 SHA-256을 지원합니다. | [Microsoft에서 관리합니다.](/azure/information-protection/plan-implement-tenant-key) | 예 |
|  | SharePoint Online | 업데이트 및 향상된 RMS 암호화 구현인 암호화 모드 [2를](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))지원합니다. 서명 및 암호화를 위해 RSA 2048을 지원하고 서명의 해시에는 SHA-256을 지원합니다. | [기본 설정인 Microsoft에서](/azure/information-protection/plan-implement-tenant-key)관리합니다. 또는 <br> <br> Microsoft에서 관리하는 키 대신 사용할 수 있는 BYOK(고객 관리 키)입니다. IT 관리 Azure 구독이 있는 조직은 BYOK를 사용하여 추가 비용 없는 사용 현황을 기록할 수 있습니다. 자세한 내용은 자체 키 [구현을 참조하세요.](/azure/information-protection/plan-implement-tenant-key) <br> <br> BYOK 시나리오에서 nCipher HSM은 키를 보호하는 데 사용됩니다. 자세한 내용은 [nCipher HSM 및 Azure RMS를 참조하세요.](https://www.thales-esecurity.com/msrms/cloud) | 예 |
| S/MIME | Exchange Online | 암호화 메시지 구문 Standard 1.5(PKCS #7) | 배포된 공개 키 인프라에 따라 다를 수 있습니다. | 예, 3DES 또는 AES-256을 사용하여 발신 메시지를 암호화하도록 구성된 경우입니다. |
| Office 365 메시지 암호화 | Exchange Online | Azure RMS(서명 및 암호화용 암호화용 암호화 모드[2](./technical-reference-details-about-encryption.md) - RSA 2048, 서명의 해시용 SHA-256)와 동일 | Azure RMS를 암호화 인프라로 사용합니다. 사용되는 암호화 방식은 메시지 암호화 및 암호 해독에 사용되는 RMS 키를 얻은 위치에 따라 다릅니다. <br> <br> RMS를 사용하여 Microsoft Azure 경우 암호화 모드 2가 사용됩니다. AD(Active Directory) RMS를 사용하여 키를 얻는 경우 암호화 모드 1 또는 암호화 모드 2가 사용됩니다. 사용되는 방법은 사내 AD RMS 배포에 따라 다를 수 있습니다. 암호화 모드 1은 원래 AD RMS 암호화 구현입니다. 서명 및 암호화를 위해 RSA 1024를 지원하고 서명에 대해 SHA-1을 지원합니다. 이 모드는 HSM을 사용하는 BYOK 구성을 제외하고 모든 현재 버전의 RMS에서 계속 지원됩니다. | 예 |
| 파트너 조직과의 SMTP TLS | Exchange Online | TLS 1.2 with AES 256 | Exchange Online(outlook.office.com)에 대한 TLS 인증서는 DigiCert Cloud Services CA-1에서 발급한 RSA 암호화 인증서가 있는 2048비트 SHA-256입니다. <br> <br> Exchange Online TLS 루트 인증서는 GlobalSign Root CA - R1에서 발급한 RSA 암호화 인증서가 있는 2048비트 [SHA-1입니다.](./exchange-online-uses-tls-to-secure-email-connections.md#tls-certificate-information-for-exchange-online) <br> <br> 보안상의 이유로 인증서는 수시로 변경됩니다. | 예, 256비트 암호 강도를 사용하는 TLS 1.2가 사용되는 경우 |

*\*이 표에서 참조되는 TLS 인증서는 미국 데이터 센터용입니다. 미국이 아닌 데이터 센터도 2048비트 SHA256RSA 인증서를 사용 합니다.*