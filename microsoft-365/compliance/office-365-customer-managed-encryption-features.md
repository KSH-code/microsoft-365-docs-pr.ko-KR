---
title: 고객 관리 암호화 기능
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
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: 이 문서에서는 Microsoft 365에서 관리 및 구성할 수 있는 암호화 기술에 대해 알아보고 있습니다.
ms.openlocfilehash: bb6f9fedf915fd261266a9ed5d0c561d1352ea09
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921558"
---
# <a name="customer-managed-encryption-features"></a>고객 관리 암호화 기능

Microsoft에서 관리하는 Microsoft 365의 암호화 기술과 함께 Microsoft 365는 다음을 관리하고 구성할 수 있는 추가 암호화 기술도 작동합니다.

- [Azure 권한 관리](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [보안 다용도 인터넷 메일 확장](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365 메시지 암호화](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [파트너 조직과의 메일 흐름 보안](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

이러한 기술에 대한 자세한 내용은 [Microsoft 365 서비스 설명을 참조하세요.](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)

## <a name="azure-rights-management"></a>Azure 권한 관리

[Azure RMS(Azure 권한](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) 관리)는 [Azure Information Protection에서](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)사용하는 보호 기술입니다. 암호화, ID 및 권한 부여 정책을 사용하여 휴대폰, 태블릿 및 PC 등 여러 플랫폼과 장치에서 파일 및 전자 메일을 보호합니다. 보호는 데이터와 함께 유지될 수 있기 때문에 조직 내부 및 외부 모두에서 정보를 보호할 수 있습니다. Azure RMS는 모든 파일 형식을 영구적으로 보호하고, 어디서나 파일을 보호하고, 비즈니스 대 비즈니스 공동 작업을 지원하며, 광범위한 Windows 및 비 Windows 장치를 지원합니다. Azure RMS 보호는 [DLP(데이터](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)손실 방지) 정책을 강화할 수 있습니다. Azure Information Protection의 Azure 권한 관리 서비스를 사용할 수 있는 응용 프로그램 및 서비스에 대한 자세한 내용은 응용 프로그램이 Azure 권한 관리 서비스를 지원하는 [방법을 참조하세요.](https://docs.microsoft.com/information-protection/understand-explore/applications-support)

Azure RMS는 Microsoft 365와 통합되어 있으며 모든 고객이 사용할 수 있습니다. Azure RMS를 사용하도록 Microsoft 365를 구성하려면 SharePoint 관리 센터에서 Azure 권한 관리를 사용하도록 IRM 구성 및 [IRM(정보 권한 관리) 설정을 참조하세요.](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx) 프레미스 AD(Active Directory) RMS 서버를 사용하는 경우 IRM을 구성하여온-프레미스 [AD RMS](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)서버를 사용할 수도 있지만, 다른 조직과의 보안 공동 작업과 같은 새로운 기능을 사용하도록 [Azure RMS로](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) 마이그레이션하는 것이 좋습니다.

Azure RMS를 사용하여 고객 데이터를 보호하는 경우 Azure RMS는 무결성을 위해 SHA-256 해시 알고리즘이 있는 2048비트 RSA 비대칭 키를 사용하여 데이터를 암호화합니다. Office 문서 및 전자 메일의 대칭 키는 AES 128비트입니다. Azure RMS로 보호되는 각 문서 또는 전자 메일에 대해 Azure RMS는 단일 AES 키("콘텐츠 키")를 만들고 해당 키는 문서에 포함되고 문서의 에디션을 통해 지속됩니다. 콘텐츠 키는 문서의 정책의 일부로 조직의 RSA 키("Azure Information Protection 테넌트 키")로 보호됩니다. 또한 정책은 문서 작성자가 서명합니다. 이 테넌트 키는 조직의 Azure RMS에서 보호되는 모든 문서 및 전자 메일에 공통적으로 사용하며, 조직이 고객이 관리하는 테넌트 키를 사용하는 경우 Azure Information Protection 관리자가 이 키를 변경할 수만 있습니다. Azure RMS에서 사용되는 암호화 컨트롤에 대한 자세한 내용은 [Azure RMS 작동 방식 참조 Under the hood](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work).

기본 Azure RMS 구현에서 Microsoft는 각 테넌트에 고유한 루트 키를 생성하고 관리합니다. 고객은 BYOK(Bring Your Own Key)라는 키 관리 방법을 사용하여 Azure RMS에서 루트 키의 수명 주기를 관리할 수 있습니다. [BYOK(Bring Your Own Key)라는](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) 키 관리 방법을 사용하면 Microsoft의 FIPS 140-2 수준 2 유효성이 검사된 HSM으로 전송한 후 이 키를 제어할 수 있습니다. 루트 키에 대한 액세스는 직원에게 부여되지 않습니다. 키를 보호하는 HSM에서 키를 내보내거나 추출할 수 없습니다. 또한 루트 키에 대한 모든 액세스를 표시하는 거의 실시간 로그에 액세스할 수 있습니다. 자세한 내용은 Azure 권한 관리 사용 현황 로깅 및 [분석을 참조하세요.](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)

Azure 권한 관리는 전선 탭, 중간에서 만인 공격, 데이터 도용, 조직 공유 정책의 의도하지 않은 위반과 같은 위협을 완화하는 데 도움이 됩니다. 이와 동시에 적절한 권한이 없는 사용자에 의해 전송 중 또는 휴지통에 있는 고객 데이터에 대한 무단 액세스는 해당 데이터를 따르는 정책을 통해 금지되므로 고의로 또는 알지 못하게 해당 데이터가 잘못된 손으로 떨어질 위험을 완화하고 데이터 손실 방지 기능을 제공합니다. Azure Information Protection의 일부로 사용되는 경우 Azure RMS는 데이터 분류 및 레이블 지정 기능, 콘텐츠 표시, 문서 액세스 추적 및 액세스 해지 기능도 제공합니다. 이러한 기능에 대한 자세한 내용은 [Azure Information Protection, Azure Information](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) [Protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)배포 로드맵 및 Azure Information Protection에 대한 빠른 시작 자습서를 [참조하세요.](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)

## <a name="secure-multipurpose-internet-mail-extension"></a>보안 다용도 인터넷 메일 확장

S/MIME(Secure/Multipurpose Internet Mail Extensions)은 MIME 데이터의 공개 키 암호화 및 디지털 서명을 위한 표준입니다. S/MIME는 RFCs 3369, 3370, 3850, 3851 등에서 정의됩니다. 이를 통해 사용자는 전자 메일을 암호화하고 전자 메일에 디지털 서명할 수 있습니다. S/MIME을 사용하여 암호화된 전자 메일은 해당 받는 사람만 개인 키를 사용하여 암호를 해독할 수 있습니다. 이 암호는 해당 받는 사람만 사용할 수 있습니다. 따라서 전자 메일의 받는 사람이 아니라 다른 사람이 전자 메일의 암호를 해독할 수 없습니다.

[Microsoft는 S/MIME을 지원합니다.](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx) 공용 인증서는 고객의 프레미스 Active Directory에 배포되고 Microsoft 365 테넌트로 복제할 수 있는 특성에 저장됩니다. 공개 키에 해당하는 개인 키는 계속 On-premises로 유지되어 Office 365로 전송되지 않습니다. 사용자는 Outlook, 웹용 Outlook 및 웹용 Outlook 클라이언트를 사용하여 조직의 두 사용자 간에 전자 메일을 작성, 암호화, 암호 해독, 읽기 및 디지털 서명할 Exchange ActiveSync 있습니다. 자세한 내용은 [Office 365에서 S/MIME](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)암호화를 참조하세요.

## <a name="office-365-message-encryption"></a>Office 365 메시지 암호화

AIP(Azure [Information Protection)를](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) 바탕으로 구축된 [OME(Office 365](https://products.office.com/exchange/office-365-message-encryption) 메시지 암호화)를 사용하면 암호화되고 권한으로 보호된 메일을 누구에게나 보낼 수 있습니다. OME는 적절한 권한이 없는 사용자의 무단 데이터 액세스와 같은 기타 위협(예: 전선 탭 및 중간에 있는 관리 공격)과 같은 위협을 완화합니다. Azure Information Protection을 토대하여 보다 간단하고 직관적인 보안 전자 메일 환경을 제공하는 투자를 제공했습니다. Microsoft 365에서 조직 내부 또는 외부의 모든 사용자로 보낸 메시지를 보호할 수 있습니다. 이러한 메시지는 Azure Active Directory, Microsoft 계정 및 Google ID를 비롯한 모든 ID를 사용하여 다양한 메일 클라이언트 집합에서 볼 수 있습니다. 조직에서 암호화된 메시지를 사용하는 방법에 대한 자세한 내용은 [Office 365 메시지 암호화를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/ome)

## <a name="transport-layer-security"></a>전송 계층 보안   

파트너와의 보안 통신을 보장하려는 경우 인바운드 및 아웃바운드 커넥터를 사용하여 보안 및 메시지 무결성을 제공할 수 있습니다. 인증서를 사용하여 각 커넥터에 대해 강제 인바운드 및 아웃바운드 TLS를 구성할 수 있습니다. 암호화된 SMTP 채널을 사용하는 경우 중간에 있는 메시지 차단 공격을 통해 데이터가 도난되는 것을 방지할 수 있습니다. 자세한 내용은 [Exchange Online에서 TLS를](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)사용하여 전자 메일 연결을 보호하는 방법을 참조하세요.

## <a name="domain-keys-identified-mail"></a>확인된 도메인 키 메일

EOP(Exchange Online Protection) 및 Exchange Online은 DKIM(Domain Keys Identified Mail) 메시지의 인바운드 유효성 검사를 지원합니다. DKIM은 메시지가 보낸 도메인에서 보낸 메시지와 다른 사람이 스푸핑되지 않았다는 것을 유효성을 검사하는 방법입니다. 전자 메일 메시지를 전송하는 조직에 링크하며, 보다 큰 전자 메일 암호화 패러다임의 일부분입니다. 이 패러다임의 세 부분에 대한 자세한 내용은 다음을 참조하세요.

- [스푸핑을 방지할 수 있도록 SPF 설정](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [DKIM을 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [DMARC를 사용하여 전자 메일의 유효성 검사](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
