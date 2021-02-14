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
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 이 문서에서는 Microsoft 클라우드에서 고객 데이터를 안전하게 유지하는 데 사용되는 다양한 형태의 암호화에 대해 간략하게 살펴 읽습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e48cc4fc54f0bc4553bab655611900523e11bd4d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214276"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft 클라우드에서 암호화

Microsoft 엔터프라이즈 클라우드 서비스 내의 고객 데이터는 다양한 형식의 암호화를 포함하여 다양한 기술 및 프로세스로 보호됩니다. (이 문서의 고객 데이터에는 Exchange Online 사서함 콘텐츠, 전자 메일 본문, 일정 항목 및 전자 메일 첨부 파일의 콘텐츠와 해당하는 경우 비즈니스용 Skype 콘텐츠), SharePoint Online 사이트 콘텐츠 및 사이트에 저장된 파일, 비즈니스용 OneDrive 또는 비즈니스용 Skype에 업로드된 파일이 포함됩니다. Microsoft는 제품 및 서비스에서 여러 암호화 방법, 프로토콜 및 암호화를 사용하여 고객 데이터가 클라우드 서비스를 통과할 수 있는 안전한 경로를 제공하고 클라우드 서비스 내에 저장된 고객 데이터의 기밀성을 보호하는 데 도움이 됩니다. Microsoft는 고객 데이터에 대한 무단 액세스에 대한 장벽을 제공하기 위해 사용할 수 있는 가장 강력한 보안 암호화 프로토콜 중 일부를 사용합니다. 적절한 키 관리는 암호화 모범 사례의 필수 요소로도 사용되어 Microsoft에서 관리하는 모든 암호화 키가 제대로 보호되도록 합니다.

고객 구성에 관계없이 Microsoft의 엔터프라이즈 클라우드 서비스에 저장된 고객 데이터는 하나 이상의 암호화 형식을 사용하여 보호됩니다. (암호화 정책 및 적용에 대한 유효성 검사는 여러 타사 감사자에 의해 독립적으로 확인하며, 이러한 감사 보고서는 [Service Trust Portal에서 확인할 수 있습니다.)](https://aka.ms/stp)

Microsoft는 미사용 및 전송 중 고객 데이터를 암호화하는 서비스 쪽 기술을 제공합니다. 예를 들어 미사용 고객 데이터의 경우 Microsoft Azure는 [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) 및 [DM-Crypt를](https://en.wikipedia.org/wiki/Dm-crypt)사용하며, Microsoft [](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) 365는 BitLocker, [Azure Storage Service 암호화,](https://docs.microsoft.com/azure/)분산 키 관리자(DKM) 및 Microsoft 365 서비스 암호화를 사용합니다. 전송되는 고객 데이터의 경우 Azure, Office 365, Microsoft 상용 지원, Microsoft Dynamics 365, Microsoft Power BI 및 Visual Studio Team Services는 Microsoft 데이터 센터 간과 사용자 장치와 Microsoft 데이터 센터 간에 IPsec(인터넷 프로토콜 보안) 및 TLS(전송 계층 보안)와 같은 업계 표준 보안 전송 프로토콜을 사용합니다.

Microsoft에서 제공하는 암호화 보안의 기준 수준 외에도 클라우드 서비스에는 관리할 수 있는 추가 암호화 옵션도 포함되어 있습니다. 예를 들어 Azure VM(가상 컴퓨터)과 사용자 간의 트래픽에 대해 암호화를 사용하도록 설정할 수 있습니다. [Azure Virtual Networks를](https://azure.microsoft.com/services/virtual-network/)사용하면 업계 표준 IPsec 프로토콜을 사용하여 회사 VPN 게이트웨이와 Azure 간의 트래픽과 가상 네트워크에 있는 VM 간의 트래픽을 암호화할 수 있습니다. 또한 새로운 Office [365](set-up-new-message-encryption-capabilities.md) 메시지 암호화 기능을 사용하면 누구에게나 암호화된 메일을 보낼 수 있습니다.

Microsoft 보안 정책의 구성 요소인 공개 키 인프라 운영 보안 표준에 따라 [Microsoft는](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)미국 정부의 FIPS(Federal [Information Processing Standards)](https://csrc.nist.gov/publications/PubsFIPS.html) 140-2 표준을 충족하는 암호화 모듈 사용을 포함하는 인증서 및 인증 메커니즘에 Windows 운영 체제에 포함된 암호화 기능을 활용합니다. (Microsoft에 대한 관련 NIST 인증서 번호는 다음에서 찾을 수 있습니다. https://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [참고] 리소스로 Microsoft 보안 정책에 액세스하려면 직장 또는 학교 계정을 사용하여 로그인해야 합니다. 아직 구독이 없는 경우 무료 평가판에 [등록할 수 있습니다.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2는 암호화를 구현하는 제품 모듈의 유효성을 검사하기 위해 특별히 설계된 표준입니다. 서비스 내에서 구현된 암호화 모듈은 해시 강도, 키 관리에 대한 요구 사항을 충족하는 것으로 인증될 수 있습니다. Microsoft 클라우드 서비스에서 데이터의 기밀성, 무결성 또는 가용성을 보호하기 위해 암호화 기능을 사용할 경우 사용되는 모듈 및 암호는 FIPS 140-2 표준을 충족합니다.

Microsoft는 Windows 운영 체제의 각 새 릴리스를 사용하여 클라우드 서비스에서 사용되는 기반 암호화 모듈을 인증합니다.

- Azure 및 Azure U.S. Government
- Dynamics 365 및 Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense

보관된 고객 데이터 암호화는 BitLocker, DKM, Azure Storage Service 암호화, Exchange Online의 서비스 암호화, 비즈니스용 Skype, 비즈니스용 OneDrive 및 SharePoint Online의 서비스 암호화를 비롯한 여러 서비스 쪽 기술을 통해 제공됩니다. Office 365 서비스 암호화에는 Azure Key Vault에 저장된 고객 관리 암호화 키를 사용하는 옵션이 포함되어 있습니다. 고객 키라고 하는 이 [](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)고객 관리 키 옵션은 Exchange Online, SharePoint Online, 비즈니스용 Skype 및 비즈니스용 OneDrive에서 사용할 수 있습니다.

전송되는 고객 데이터의 경우 모든 Office 365 서버는 기본적으로 클라이언트 컴퓨터와 TLS를 사용하여 보안 세션을 협상하여 고객 데이터를 보호합니다.  이는 비즈니스용 Skype, Outlook, 웹용 Outlook, 모바일 클라이언트 및 웹 브라우저와 같은 클라이언트에서 사용하는 모든 장치의 프로토콜에 적용됩니다.

모든 고객 연결 서버는 기본적으로 TLS 1.2로 협상하지만 필요한 경우 하위 표준으로의 협상도 지원됩니다.

## <a name="related-links"></a>관련 링크

- [Azure의 암호화](office-365-azure-encryption.md)
- [암호화에 대한 BitLocker 및 분산 키 관리자(DKM)](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 서비스 암호화](office-365-service-encryption.md)
- [비즈니스용 Skype, 비즈니스용 OneDrive, SharePoint Online 및 Exchange Online용 Office 365 암호화](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [전송 중인 데이터 암호화](office-365-encryption-for-data-in-transit.md)
- [고객 관리 암호화 기능](office-365-customer-managed-encryption-features.md)
- [암호화 위험 및 보호](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365에서 암호화](office-365-encryption-in-microsoft-dynamics-365.md)
