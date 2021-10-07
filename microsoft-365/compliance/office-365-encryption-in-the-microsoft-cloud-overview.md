---
title: Microsoft 클라우드에서 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 이 문서에서는 Microsoft 클라우드에서 고객 데이터를 안전하게 유지하는 데 사용되는 다양한 형태의 암호화에 대한 개요를 읽어 읽습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c888c1958eb5265c31ae981e42a96eeeeb57f3ef
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194384"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft 클라우드에서 암호화

Microsoft 엔터프라이즈 클라우드 서비스 내의 고객 데이터는 다양한 형식의 암호화를 포함하여 여러 기술 및 프로세스에 의해 보호됩니다. 이 문서의 고객 데이터에는 Exchange Online 사서함 콘텐츠, 전자 메일 본문, 일정 항목 및 전자 메일 첨부 파일의 콘텐츠, 해당하는 경우 비즈니스용 Skype 콘텐츠), SharePoint Online 사이트 콘텐츠 및 사이트에 저장된 파일, 비즈니스용 OneDrive 또는 비즈니스용 Skype.) Microsoft는 제품 및 서비스 전체에서 여러 암호화 방법, 프로토콜 및 암호화를 사용하여 고객 데이터가 클라우드 서비스를 통과하는 안전한 경로를 제공하고 클라우드 서비스 내에 저장된 고객 데이터의 기밀성을 보호하는 데 도움이 됩니다. Microsoft는 고객 데이터에 대한 무단 액세스에 대한 장벽을 제공하기 위해 사용할 수 있는 가장 강력한 보안 암호화 프로토콜 중 일부를 사용합니다. 적절한 키 관리는 암호화 모범 사례의 필수 요소로도 사용되어 Microsoft는 모든 Microsoft에서 관리하는 암호화 키의 보안을 적절히 유지하도록 합니다.

Microsoft의 엔터프라이즈 클라우드 서비스에 저장된 고객 데이터는 하나 이상의 암호화 형식을 사용하여 보호됩니다. (암호화 정책의 유효성 검사 및 적용은 여러 타사 감사자에 의해 독립적으로 확인하며, 이러한 감사에 대한 보고서는 [Service Trust Portal에서 확인할 수 있습니다.)](https://aka.ms/stp)

Microsoft는 미사용 및 전송 중 고객 데이터를 암호화하는 서비스 쪽 기술을 제공합니다. 예를 들어 미사용 고객 데이터의 경우 Microsoft Azure [및](/windows/device-security/bitlocker/bitlocker-overview) [DM-Crypt를](https://en.wikipedia.org/wiki/Dm-crypt)사용하며 Microsoft 365 BitLocker, Azure Storage 서비스 암호화, DKM(분산 키 관리자) 및 Microsoft 365 서비스 암호화를 사용합니다. [](/azure/) [](./exchange-online-secures-email-secrets.md) 전송되는 고객 데이터의 경우 Azure, Office 365, Microsoft 상용 지원, Microsoft Dynamics 365, Microsoft Power BI 및 Visual Studio Team Services Microsoft 데이터 센터 간에 Microsoft 데이터 센터와 사용자 장치 간에 IPsec(인터넷 프로토콜 보안) 및 TLS(전송 계층 보안)와 같은 업계 표준 보안 전송 프로토콜을 사용합니다. datacenters.

Microsoft에서 제공하는 기본 수준의 암호화 보안 외에도 클라우드 서비스에는 관리할 수 있는 암호화 옵션도 포함되어 있습니다. 예를 들어 Azure VM(가상 컴퓨터)과 사용자 간의 트래픽에 대해 암호화를 사용하도록 설정할 수 있습니다. [Azure Virtual Networks를](https://azure.microsoft.com/services/virtual-network/)사용하면 업계 표준 IPsec 프로토콜을 사용하여 회사 VPN 게이트웨이와 Azure 간의 트래픽을 암호화할 수 있습니다. 가상 네트워크의 VM 간 트래픽을 암호화할 수도 있습니다. 또한 새로운 Office 365 메시지 암호화 [기능을](set-up-new-message-encryption-capabilities.md) 통해 암호화된 메일을 누구에게나 보낼 수 있습니다.

Microsoft 보안 정책의 구성 요소인 공개 키 인프라 운영 보안 표준에 따라 [Microsoft는](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)인증서 및 인증 메커니즘에 Windows 운영 체제에 포함된 암호화 기능을 사용 합니다. 이러한 메커니즘에는 미국 정부의 FIPS(Federal [Information Processing Standards)](https://csrc.nist.gov/publications/PubsFIPS.html) 140-2 표준을 충족하는 암호화 모듈의 사용이 포함됩니다. 암호화 모듈 유효성 검사 프로그램 [CMVP를](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)사용하여 Microsoft에 대한 관련 NIST 인증서 번호를 검색할 수 있습니다.

> [참고] 리소스로 Microsoft 보안 정책에 액세스하려면 직장 또는 학교 계정을 사용하여 로그인해야 합니다. 아직 구독이 없는 경우 무료 평가판에 [등록할 수 있습니다.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2는 암호화를 구현하는 제품 모듈의 유효성을 검사하기 위해 특별히 설계된 표준입니다. 서비스 내에서 구현된 암호화 모듈은 해시 강도, 키 관리 등 요구 사항을 충족하는 것으로 인증될 수 있습니다. Microsoft 클라우드 서비스의 데이터 기밀성, 무결성 또는 가용성을 보호하는 데 사용되는 암호화 모듈 및 암호는 FIPS 140-2 표준을 충족합니다.

Microsoft는 클라우드 서비스에서 사용되는 기반 암호화 모듈을 새로운 Windows 인증합니다.

- Azure 및 Azure 미국 정부
- Dynamics 365 및 Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense

미사용 고객 데이터 암호화는 BitLocker, DKM, Azure Storage Service Encryption 및 Exchange Online, 비즈니스용 Skype, 비즈니스용 OneDrive 및 SharePoint Online의 서비스 암호화를 비롯한 여러 서비스 쪽 기술을 통해 제공됩니다. Office 365 서비스 암호화에는 Azure Key Vault에 저장된 고객 관리 암호화 키를 사용하는 옵션이 포함되어 있습니다. 고객 키라고 하는 이 [](./customer-key-overview.md)고객 관리 키 옵션은 Exchange Online, SharePoint Online, 비즈니스용 Skype 및 비즈니스용 OneDrive.

전송되는 고객 데이터의 경우 모든 Office 365 서버는 기본적으로 클라이언트 컴퓨터와 TLS를 사용하여 보안 세션을 협상하여 고객 데이터를 보호합니다. 예를 들어 Office 365 보안 세션을 비즈니스용 Skype, Outlook 및 웹용 Outlook, 모바일 클라이언트 및 웹 브라우저에 대해 협상합니다.

(모든 고객 연결 서버는 기본적으로 TLS 1.2로 협상합니다.)

## <a name="related-links"></a>관련 링크

- [Azure의 암호화](office-365-azure-encryption.md)
- [암호화에 대한 BitLocker 및 분산 키 관리자(DKM)](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 서비스 암호화](office-365-service-encryption.md)
- [Office 365 비즈니스용 Skype, 비즈니스용 OneDrive, SharePoint Online 및 Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [전송 중인 데이터 암호화](/compliance/assurance/assurance-encryption-in-transit)
- [고객 관리 암호화 기능](office-365-customer-managed-encryption-features.md)
- [암호화 위험 및 보호](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365에서 암호화](office-365-encryption-in-microsoft-dynamics-365.md)