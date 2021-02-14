---
title: Office 365 서비스의 IPv6 지원
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: '요약: 365 구성 요소 및 Office 365 정부 Microsoft Office IPv6 지원에 대해 설명 합니다.'
ms.openlocfilehash: f671e8caf868ebbed628a155b73ce6fe413949a9
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235609"
---
# <a name="ipv6-support-in-office-365-services"></a>Office 365 서비스의 IPv6 지원

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Office 365는 IPv6과 IPv4를 모두 지원합니다. 그러나 일부 Office 365 기능은 IPv6을 통해 완전히 사용하도록 설정되지는 않습니다. 즉, IPv4와 IPv6을 모두 사용하여 Office 365에 연결해야 합니다. Office 365로의 아웃바운드 트래픽을 필터링하는 경우 Office 365에서 지원하는 IPv6 주소의 전체 목록은 [Office 365 URL](urls-and-ip-address-ranges.md)및 IP 주소 범위 문서에서 찾을 수 있습니다. 네트워크를 구성하고 적절한 IPv6 주소를 허용한 후 Microsoft 다운로드 센터에서 [Office 365 IPv6 테스트](https://go.microsoft.com/fwlink/?LinkId=293447) 계획을 다운로드할 수 있습니다.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Office 365 구독 서비스의 IPv6 지원

### <a name="exchange-online-and-ipv6"></a>Exchange Online 및 IPv6

Exchange Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 유선 네트워크와 무선 네트워크 모두에서 기본적으로 IPv6을 사용합니다. Exchange Online에 대한 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online 및 IPv6

 **Office 365 Government G1/G3/G4/K1** SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6을 사용하려고 합니다.
  
 **공용 다중 테넌트 클라우드** Microsoft는 요청 시 SharePoint Online IPv6을 사용할 수 있도록 합니다. 조직의 DNS 인프라에 대해 CIDR에서 고지된 IP 주소를 제공해야 합니다. 테넌트에 대해 IPv6을 사용하도록 설정하기 위해 다른 조직에서는 이 DNS 인프라를 공유할 수 없습니다. IPv6을 사용하도록 설정한 후 SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6이 사용됩니다.
  
SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 유선 네트워크와 무선 네트워크 모두에서 기본적으로 IPv6이 사용됩니다. SharePoint Online에 대한 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.
  
 **Office 365 Government G1/G3/G4/K1** SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6을 사용하려고 합니다.
  
### <a name="skype-for-business-and-ipv6"></a>비즈니스용 Skype 및 IPv6

IPv6은 비즈니스용 Skype에서 지원되지 않습니다. 더 이상 사용할 수 없습니다.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 및 IPV6

Microsoft Teams 직접 라우팅은 IPv4만 지원됩니다. Microsoft Teams 서비스 및 클라이언트는 IPv4와 IPv6을 둘 다 지원합니다. Microsoft Teams와의 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection 및 IPv6

전송 계층 보안 프로토콜을 통해 전송이 발생하는 경우 EOP(Exchange Online Protection)는 IPv6을 지원합니다. EOP 범위의 경우 [Office 365 URL 및 IP 주소 범위를 사용하세요.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Office 365 정부 제품용 IPv6 지원

정부 제공에 대한 Office 365 IPv6 지원은 행정부 및 기관의 최고 정보 책임자에 대한 OMB(관리 예산부) 양해와 IPv6(연방 정부의 IPv6( 인터넷 프로토콜 버전 6) 채택에 대한 양해를 준수합니다. [Microsoft Office 365 for Government는](https://go.microsoft.com/fwlink/p/?LinkId=325414) 미국 정부 데이터를 분계된 커뮤니티 클라우드에 저장하는 다중 테넌트 서비스입니다. 다른 Office 365 제품과 마찬가지로 Exchange Online, 비즈니스용 Skype, SharePoint Online 및 엔터프라이즈용 Microsoft 365 앱을 비롯한 생산성 및 공동 작업 서비스를 제공합니다. 

365 Microsoft Office 2013 이상에만 적용됩니다. Office 365 정부 제품 제공에 대한 자세한 내용은 [정부용 Office 365 발표:](https://go.microsoft.com/fwlink/p/?LinkId=325414)미국 정부 커뮤니티 클라우드를 참조하세요. ITAR(International Traffic in Arms [Regulations)는 미국 USML(MUNITIONS List)에서](https://go.microsoft.com/fwlink/p/?LinkId=325415)국방 관련 문서 및 서비스의 수출 및 가져오기 기능을 제어하는 미국 정부 규정 집합입니다. 

Microsoft Office 365 대기업은 FISMA(Federal Information Security Management) 인증 및 상업적 엔터티가 필요한 미국 연방 기관에 보안, 개인 정보 보호 및 규정 준수 요구 사항을 지원하는 Microsoft 생산성 솔루션에 대한 전용 호스팅 서비스를 제공합니다.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>IPv6 및 Office 365를 사용할 때 고려해야 할 것

IPv6을 사용하지 않도록 설정하지 않는 것이 좋습니다. 자세한 내용은 이 지침 문서를 [참조하세요.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) 네트워크에서 사용 되는 IP 버전을 확인 하는 다음을 고려 합니다.
  
- 명령 프롬프트의 **IPConfig** 명령 표시에 "IPv6 주소" 또는 "임시 IPv6 주소"라는 행이 포함되어 있는 경우 환경에 IPv6이 있습니다.

- 모든 IPv6 주소가 "fe80"으로 시작하고 "Link-Local IPv6 Address"라는 행에 해당하는 경우 환경에 IPv6이 없는 것입니다.

이러한 고려 사항이 네트워크에 적용될 수 있습니다.
  
- 공용 구독 서비스는 IPv6을 통해 신용 카드로 구매를 지원하지 않습니다. 이는 정부가 EA(정부 커뮤니티 클라우드) 라이선스를 기업계약 않습니다.

- IPv6에서는 일부 RMS(권한 관리 서비스) 시나리오를 지원하지 않습니다.

- BlackBerry는 IPv6을 지원하지 ® 때문에 IPv6은 BlackBerry를 지원하지 않습니다® Enterprise Server(BES)를 지원하지 않습니다.

- Office 365에서 AD FS(Active Directory Federation Services)를 사용하는 경우 IPv6을 사용하여 AD FS 네트워크 끝점을 Office 365에 광고할 수 없습니다. Exchange Online을 사용할 때 AD FS DNS 항목에 AAAA 레코드를 포함하면 안 됩니다. 

다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/o365ip6](https://aka.ms/o365ip6)
  
## <a name="see-also"></a>참고 항목

[IPv6 학습 로드맵](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 사용 가이드](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
