---
title: Microsoft 365의 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: 이 Office 365 사용할 수 있는 가장 강력한 암호화, 프로토콜 및 기술을 사용하여 미사용 및 전송 중 콘텐츠가 암호화됩니다. 암호화에 대한 개요를 Office 365.
ms.openlocfilehash: a1ee73d7ded7a02cd7851081412d2403e0ca8f1d
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587304"
---
# <a name="encryption"></a>암호화

암호화는 파일 보호 및 정보 보호 전략의 중요한 부분입니다. 이 문서에서는 암호화에 대한 개요를 Office 365. 조직의 암호화를 설정하는 방법 및 문서의 암호를 보호하는 방법과 같은 암호화 Office 도움이 됩니다.
  
- TLS와 같은 인증서 및 기술에 대한 자세한 내용은 에서 암호화에 대한 기술 참조 [세부 Office 365.](technical-reference-details-about-encryption.md)

- 조직의 암호화를 구성하거나 설정하는 방법에 대한 자세한 내용은 에서 암호화 [설정을 Office 365 Enterprise.](set-up-encryption.md)

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>암호화란 무엇일까요? 그리고 암호화가 암호화에서 어떻게 Office 365?

암호화 프로세스는 데이터를 암호 텍스트로 인코딩합니다(일반 텍스트). 일반 텍스트와 달리 암호 텍스트는 암호 텍스트가 해독될 때까지 사용자나 컴퓨터에서 사용할 수 없습니다. 암호 해독에는 권한이 부여된 사용자만 있는 암호화 키가 필요합니다. 암호화를 사용하면 권한이 부여된 받는 사람만 콘텐츠의 암호를 해독할 수 있습니다. 콘텐츠에는 파일, 전자 메일 메시지, 일정 항목 등이 포함됩니다.
  
암호화 자체는 콘텐츠 가로채기를 방지하지 않습니다. 암호화는 조직에 대한 보다 큰 정보 보호 전략의 일부입니다. 암호화를 사용하면 권한이 부여된 사용자만 암호화된 데이터를 사용할 수 있습니다.
  
여러 암호화 계층을 동시에 사용할 수 있습니다. 예를 들어 전자 메일 메시지와 전자 메일이 흐르는 통신 채널을 암호화할 수 있습니다. 이 Office 365 사용하여 데이터는 여러 가지 강력한 암호화 프로토콜 및 TLS/SSL(전송 계층 보안/SSL), IPSec(인터넷 프로토콜 보안) 및 AES(고급 암호화 표준)를 Secure Sockets Layer 사용하여 미사용 및 전송 중으로 암호화됩니다.
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>미사용 데이터 및 전송되는 데이터에 대한 암호화

  미사용 데이터의 예로는 SharePoint 라이브러리에 업로드한 파일, Project Online 데이터, 비즈니스용 Skype 모임에서 업로드한 문서, 사서함의 폴더에 저장한 전자 메일 메시지 및 첨부 파일, 비즈니스용 OneDrive.
  
 **전송되는 데이터의** 예로는 배달 중인 메일 메시지나 온라인 모임에서 진행되는 대화가 있습니다. Office 365 Microsoft 서버와 통신할 때마다 또는 Microsoft 서버가 다른 서버와 통신할 때마다 데이터가 전송됩니다.
  
이 Office 365 여러 계층과 종류의 암호화가 함께 작동하여 데이터를 보호합니다. 다음 표에는 추가 정보에 대한 링크가 포함된 몇 가지 예제가 포함되어 있습니다.
  
|**콘텐츠 종류**|**암호화 기술**|**자세한 정보를 알아볼 수 있는 리소스**|
|:-----|:-----|:-----|
|디바이스의 파일. 이러한 파일에는 폴더에 저장된 전자 메일 메시지, Office, 태블릿 또는 휴대폰에 저장된 문서 또는 Microsoft 클라우드에 저장된 데이터가 포함됩니다.  <br/> |Microsoft 데이터 센터의 BitLocker. BitLocker는 컴퓨터 및 태블릿과 같은 클라이언트 Windows 사용할 수도 있습니다.  <br/> Microsoft 데이터 센터의 분산 키 관리자(DKM)  <br/> 고객용 Microsoft 365  <br/> |[Windows IT 센터: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft 보안 센터: 암호화](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [클라우드 보안 제어 시리즈: 미사용 데이터 암호화](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online이 전자 메일 암호를 보호하는 방법](exchange-online-secures-email-secrets.md) <br/> [고객 키를 사용한 서비스 암호화](customer-key-overview.md) <br/> |
|사용자 간에 전송되는 파일입니다. 이러한 파일에는 사용자 Office 공유되는 SharePoint 목록 항목이 포함됩니다.  <br/> |전송되는 파일에 대한 TLS  <br/> |[비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화](data-encryption-in-odb-and-spo.md) <br/> [비즈니스용 Skype 온라인: 보안 및 보관](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|받는 사람 간에 전송된 전자 메일입니다. 이 전자 메일에는 전자 메일이 Exchange Online.  <br/> |Office 365 메시지 암호화 전자 메일에 대한 Azure 권한 관리, S/MIME 및 TLS를 사용하여 관리  <br/> |[OME(Office 365 메시지 암호화)](ome.md) <br/> [Office 365의 전자 메일 암호화](email-encryption.md) <br/> [Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|받는 사람 간에 전송되는 채팅, 메시지 및 Microsoft Teams. <br/> |Teams TLS 및 MTLS를 사용하여 인스턴트 메시지를 암호화합니다. 미디어 트래픽은 SRTP(Secure RTP)를 사용하여 암호화됩니다. Teams 암호화 키 교환에 FIPS(Federal Information Processing Standard) 호환 알고리즘을 사용합니다. <br/> |[암호화를 Teams](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>보안 및 규정 준수 요구 사항을 충족하기 위해 암호화에 대한 더 많은 제어가 필요한 경우 어떻게 하나요?

Microsoft 365 볼륨 암호화, 파일 암호화 및 사서함 암호화에 대한 Microsoft 관리 솔루션을 Office 365. 또한 Microsoft는 관리 및 제어할 수 있는 암호화 솔루션을 제공합니다. 이러한 암호화 솔루션은 Azure를 통해 구축됩니다.
  
자세한 내용은 다음 리소스를 참조하세요.
  
- [Azure 권한 관리란?](/information-protection/understand-explore/what-is-azure-rms)

- [관리 센터에서 권한 관리 활성화](../enterprise/activate-rms-in-microsoft-365.md)

- [SharePoint Online 관리 센터에서 IRM(정보 권한 관리)을 설정](set-up-irm-in-sp-admin-center.md)

- [Office 365의 고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [이중 키 암호화 Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>방법

|**이 작업을 수행하기 위해**|**다음 리소스를 참조합니다.**|
|:-----|:-----|
|조직에 대한 암호화 설정|[Office 365 Enterprise의 암호화 설정](set-up-encryption.md)|
|인증서, 기술 및 TLS 암호 제품군에 대한 세부 정보 보기|[암호화에 대한 기술 세부 정보](technical-reference-details-about-encryption.md)|
|모바일 장치에서 암호화된 메시지 사용|[Android 장치에서](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)암호화된 메시지 보기 암호화된 메시지 보기 iPhone[또는](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) iPad|
|암호 보호를 사용하여 문서를 암호화합니다. (암호 보호는 브라우저에서 지원되지 않습니다. 암호 보호를 위해 Word, Excel PowerPoint 데스크톱 버전을 사용하세요.) |문서, 통합 문서 또는 프레젠테이션에 보호를 [추가하거나 제거합니다.](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) 보호 추가 **섹션을** 선택한 다음 암호로 **암호화를 참조하세요.**|
|문서에서 암호화 제거|문서, 통합 문서 또는 프레젠테이션에 보호를 [추가하거나 제거합니다.](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) 보호 **제거 섹션을** 선택한 다음 암호 암호화 **제거를 참조하세요.**  |

## <a name="related-topics"></a>관련 항목

[보안 Microsoft 365 보호 기능 계획](plan-for-security-and-compliance.md)

[비즈니스용 요금제의 보안 Microsoft 365 10가지 방법](/office365/admin/security-and-compliance/secure-your-business-data)

[Microsoft Stream 비디오 수준 암호화 및 재생 흐름](/stream/network-overview#video-level-encryption-and-playback-flow)