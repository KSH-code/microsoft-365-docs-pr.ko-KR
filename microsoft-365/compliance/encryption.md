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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: Office 365를 사용하는 경우 사용 가능한 가장 강력한 암호화, 프로토콜 및 기술을 사용하여 미사용 및 전송 중 콘텐츠가 암호화됩니다. Office 365의 암호화 개요를 참조하세요.
ms.openlocfilehash: 0cd440549cd038ec9b5f69233e7faa18d9bcee1e
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663013"
---
# <a name="encryption"></a>암호화

암호화는 파일 보호 및 정보 보호 전략의 중요한 부분입니다. 이 문서에서는 Office 365의 암호화에 대한 개요를 제공합니다. 조직의 암호화 설정 방법 및 Office 문서를 암호로 보호하는 방법과 같은 암호화 작업에 대한 도움말을 얻습니다.
  
- TLS와 같은 인증서 및 기술에 대한 자세한 내용은 [Office 365의](technical-reference-details-about-encryption.md)암호화에 대한 기술 참조 세부 정보를 참조하세요.

- 조직에 대한 암호화를 구성하거나 설정하는 방법에 대한 자세한 내용은 [Office 365 Enterprise에서 암호화 설정을 참조하세요.](set-up-encryption.md)

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>암호화란 무엇일까요? Office 365에서는 암호화가 어떻게 작동하나요?

암호화 프로세스는 데이터를 암호 텍스트로 인코딩합니다(일반 텍스트). 일반 텍스트와 달리 암호 텍스트는 암호 텍스트가 해독될 때까지 사용자나 컴퓨터에서 사용할 수 없습니다. 암호 해독에는 인증된 사용자만 사용할 수 있는 암호화 키가 필요합니다. 암호화를 사용하면 권한이 부여된 받는 사람만 콘텐츠의 암호를 해독할 수 있습니다. 콘텐츠에는 파일, 전자 메일 메시지, 일정 항목 등이 포함됩니다.
  
암호화 자체는 콘텐츠 가로채기를 방지하지 않습니다. 암호화는 조직을 위한 보다 큰 정보 보호 전략의 일부입니다. 암호화를 사용하면 권한이 부여된 사용자만 암호화된 데이터를 사용할 수 있습니다.
  
여러 계층의 암호화를 동시에 사용할 수 있습니다. 예를 들어 전자 메일 메시지와 전자 메일이 흐르는 통신 채널을 암호화할 수 있습니다. Office 365를 사용하는 경우 몇 가지 강력한 암호화 프로토콜과 TLS/SSL(전송 계층 보안), IPSec(인터넷 프로토콜 보안) 및 AES(Advanced Encryption Standard)를 Secure Sockets Layer 기술을 사용하여 미사용 및 전송 중 데이터가 암호화됩니다.
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>미사용 데이터 및 전송되는 데이터에 대한 암호화

  미사용 데이터의 예로는 SharePoint 라이브러리에 업로드한 파일, Project Online 데이터, 비즈니스용 Skype 모임에서 업로드한 문서, 사서함의 폴더에 저장한 전자 메일 메시지 및 첨부 파일, 비즈니스용 OneDrive에 업로드한 파일이 있습니다.
  
 **전송되는 데이터의 예로는** 배달되는 메일 메시지 또는 온라인 모임에서 진행되는 대화가 있습니다. Office 365에서는 사용자의 장치가 Microsoft 서버와 통신하거나 Microsoft 서버가 다른 서버와 통신할 때마다 데이터가 전송됩니다.
  
Office 365를 사용하는 경우 여러 계층과 종류의 암호화가 함께 작동하여 데이터를 보호합니다. 다음 표에는 추가 정보에 대한 링크가 포함된 몇 가지 예제가 포함되어 있습니다.
  
|**콘텐츠 종류**|**암호화 기술**|**자세한 정보를 알아볼 수 있는 리소스**|
|:-----|:-----|:-----|
|디바이스의 파일. 이러한 파일에는 폴더에 저장된 전자 메일 메시지, 컴퓨터, 태블릿 또는 휴대폰에 저장된 Office 문서 또는 Microsoft 클라우드에 저장된 데이터가 포함됩니다.  <br/> |Microsoft 데이터 센터의 BitLocker. Windows 컴퓨터 및 태블릿과 같은 클라이언트 컴퓨터에서도 BitLocker를 사용할 수 있습니다.  <br/> Microsoft 데이터 센터의 DKM(분산 키 관리자)  <br/> Microsoft 365 고객 키  <br/> |[Windows IT 센터: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft 보안 센터: 암호화](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [클라우드 보안 제어 시리즈: 미사용 데이터 암호화](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online이 전자 메일 암호를 보호하는 방법](exchange-online-secures-email-secrets.md) <br/> [고객 키를 사용한 서비스 암호화](customer-key-overview.md) <br/> |
|사용자 간에 전송되는 파일입니다. 이러한 파일에는 사용자 간에 공유되는 Office 문서 또는 SharePoint 목록 항목이 포함됩니다.  <br/> |전송되는 파일에 대한 TLS  <br/> |[비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화](data-encryption-in-odb-and-spo.md) <br/> [비즈니스용 Skype Online: 보안 및 보관](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|받는 사람 간에 전송된 전자 메일입니다. 이 전자 메일에는 Exchange Online에서 호스팅하는 전자 메일이 포함됩니다.  <br/> |전송 중 전자 메일에 대한 Azure 권한 관리, S/MIME 및 TLS를 사용하는 Office 365 메시지 암호화  <br/> |[OME(Office 365 메시지 암호화)](ome.md) <br/> [Office 365의 전자 메일 암호화](email-encryption.md) <br/> [Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Microsoft Teams를 사용하는 받는 사람 간에 채팅, 메시지 및 전송되는 파일 <br/> |Teams는 TLS 및 MTLS를 사용하여 인스턴트 메시지를 암호화합니다. 미디어 트래픽은 SRTP(Secure RTP)를 사용하여 암호화됩니다. Teams는 암호화 키 교환에 FIPS(Federal Information Processing Standard) 규격 알고리즘을 사용합니다. <br/> |[Teams용 암호화](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>보안 및 규정 준수 요구 사항을 충족하기 위해 암호화에 대한 더 많은 제어가 필요한 경우 어떻게 해야 하나요?

Microsoft 365는 Office 365의 볼륨 암호화, 파일 암호화 및 사서함 암호화에 대한 Microsoft 관리 솔루션을 제공합니다. 또한 Microsoft는 관리 및 제어할 수 있는 암호화 솔루션을 제공합니다. 이러한 암호화 솔루션은 Azure를 통해 구축됩니다.
  
자세한 내용은 다음 리소스를 참조하세요.
  
- [Azure 권한 관리란?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [관리 센터에서 권한 관리 활성화](https://docs.microsoft.com/microsoft-365/enterprise/activate-rms-in-microsoft-365)

- [SharePoint Online 관리 센터에서 IRM(정보 권한 관리)을 설정](set-up-irm-in-sp-admin-center.md)

- [Office 365의 고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [Microsoft 365용 이중 키 암호화](double-key-encryption.md)

## <a name="how-do-i"></a>방법

|**이 작업을 수행하기 위해**|**다음 리소스 참조**|
|:-----|:-----|
|조직에 대한 암호화 설정  <br/> |[Office 365 Enterprise의 암호화 설정](set-up-encryption.md) <br/> |
|인증서, 기술 및 TLS 암호 제품군에 대한 세부 정보 보기 <br/> |[암호화에 대한 기술 세부 정보](technical-reference-details-about-encryption.md) <br/> |
|모바일 장치에서 암호화된 메시지 작업  <br/> |[Android 장치에서 암호화된 메시지 보기](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [iPhone 또는 iPad에서 암호화된 메시지 보기](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|암호 보호를 사용하여 문서 암호화  <br/><br/>  암호 보호는 브라우저에서 지원되지 않습니다. 암호 보호를 위해 데스크톱 버전의 Word, Excel 및 PowerPoint를 사용하세요. |[문서, 통합 문서 또는 프레젠테이션에서 보호 추가 또는 제거](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> 보호 추가 **섹션을** 선택한 다음 암호로 **암호화를 참조하세요.**  |
|문서에서 암호화 제거  <br/> |[문서, 통합 문서 또는 프레젠테이션에서 보호 추가 또는 제거](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> 보호 제거 **섹션을** 선택한 다음 암호 제거 **암호화를 참조하세요.**  |


## <a name="related-topics"></a>관련 항목

[Microsoft 365 보안 및 정보 보호 기능 계획](plan-for-security-and-compliance.md)

[비즈니스용 Microsoft 365 계획을 보호하는 상위 10가지 방법](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide)

[Microsoft Stream 비디오 수준 암호화 및 재생 흐름](https://docs.microsoft.com/stream/network-overview#video-level-encryption-and-playback-flow)
