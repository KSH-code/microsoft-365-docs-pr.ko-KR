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
description: '요약: Microsoft Office 365 구성 요소 및 Office 365 정부 제품에서 IPv6 지원을 설명하는 문서입니다.'
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028910"
---
# <a name="ipv6-support-in-office-365-services"></a>Office 365 서비스의 IPv6 지원

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Office 365는 IPv6 및 IPv4를 모두 지원합니다. 그러나 일부 Office 365 기능은 IPv6에서 완전히 사용하도록 설정되지는 않습니다. 즉, IPv4 및 IPv6을 모두 사용하여 Office 365에 연결해야 합니다. Office 365로의 아웃바운드 트래픽을 필터링하는 경우 Office 365에서 지원하는 IPv6 주소의 전체 목록은 [Office 365 URL](urls-and-ip-address-ranges.md)및 IP 주소 범위 문서에서 찾을 수 있습니다. 네트워크를 구성하고 적절한 IPv6 주소를 허용한 후 Microsoft 다운로드 센터에서 [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) 테스트 계획을 다운로드할 수 있습니다.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Office 365 구독 서비스의 IPv6 지원

### <a name="exchange-online-and-ipv6"></a>Exchange Online 및 IPv6

Exchange Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 유선 네트워크와 무선 네트워크 모두에서 기본적으로 IPv6을 사용합니다. Exchange Online에 대한 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online 및 IPv6

 **Office 365 Government G1/G3/G4/K1** SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6을 사용하려고 합니다.
  
 **공용 다중 테넌트 클라우드** Microsoft는 요청 시 SharePoint Online IPv6을 사용할 수 있도록 합니다. 조직의 DNS 인프라에 대해 CIDR에서 고지된 IP 주소를 제공해야 합니다. 테넌트에 대해 IPv6을 사용하도록 설정하기 위해 다른 조직에서는 이 DNS 인프라를 공유할 수 없습니다. IPv6을 사용하도록 설정한 후 SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6이 사용됩니다.
  
SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 유선 네트워크와 무선 네트워크 모두에서 기본적으로 IPv6을 사용합니다. SharePoint Online에 대한 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.
  
 
  
### <a name="skype-for-business-and-ipv6"></a>비즈니스용 Skype 및 IPv6

IPv6은 비즈니스용 Skype에서 지원되지 않습니다. 더 이상 사용할 수 없습니다.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 및 IPV6

Microsoft Teams 직접 라우팅은 IPv4만 지원됩니다. Microsoft Teams 서비스 및 클라이언트는 IPv4 및 IPv6을 모두 지원합니다. Microsoft Teams와의 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection 및 IPv6

전송 계층 보안 프로토콜을 통해 전송이 발생하는 경우 EOP(Exchange Online Protection)는 IPv6을 지원합니다. EOP 범위의 경우 [Office 365 URL 및 IP 주소 범위를 사용하세요.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Office 365 정부 제품용 IPv6 지원

정부 제공에 대한 Office 365 IPv6 지원은 행정부 및 기관의 최고 정보 책임자에 대한 OMB(관리 및 예산국) 양해 및 IPv6(Federal Government의 IPv6) 도입에 대한 양해를 준수합니다. [Microsoft Office 365 for Government는](https://go.microsoft.com/fwlink/p/?LinkId=325414) 미국 정부 데이터를 분계된 커뮤니티 클라우드에 저장하는 다중 테넌트 서비스입니다. 다른 Office 365 서비스와 마찬가지로 Exchange Online, 비즈니스용 Skype, SharePoint Online 및 엔터프라이즈용 Microsoft 365 앱을 비롯한 생산성 및 공동 작업 서비스를 제공합니다. 

365 Microsoft Office 2013 이상에만 적용됩니다. Office 365 정부 제공에 대한 자세한 내용은 [Government용 Office 365 발표: 미국 정부 커뮤니티 클라우드를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=325414) ITAR(International Traffic in Arms [Regulations)는 미국 USML(Munitions List)에서](https://go.microsoft.com/fwlink/p/?LinkId=325415)국방 관련 문서 및 서비스의 수출 및 가져오기 기능을 제어하는 미국 정부 규정 집합입니다. 

Microsoft Office 365 for Enterprise는 ITAR이 적용된 미국 연방 정보 보안 관리(FISMA) 인증 및 상업적 엔터티를 요구하는 미국 연방 기관에 대한 보안, 개인 정보 보호 및 규정 준수 요구 사항을 지원하는 Microsoft 생산성 솔루션에 대한 전용 호스팅 서비스를 제공합니다.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>IPv6 및 Office 365를 사용할 때 고려해야 할 것

IPv6을 사용하지 않도록 설정하지 않는 것이 좋습니다. 자세한 내용은 이 지침 문서를 [참조하세요.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) 네트워크에서 사용되는 IP 버전을 확인하기 위해 다음을 고려합니다.
  
- 명령 프롬프트에 **IPConfig** 명령이 표시될 때 "IPv6 주소" 또는 "임시 IPv6 주소"라는 행이 포함되어 있는 경우 환경에 IPv6이 있는 것입니다.

- 모든 IPv6 주소가 "fe80"으로 시작하고 "Link-Local IPv6 Address"라는 행에 해당하는 경우 환경에 IPv6이 없는 것입니다.

이러한 고려 사항이 네트워크에 적용될 수 있습니다.
  
- 공용 구독 서비스는 IPv6을 통해 신용 카드로 구매를 지원하지 않습니다. 이는 정부가 EA(정부 커뮤니티 클라우드) 라이선스를 기업계약 않습니다.

- IPv6에서는 일부 RMS(권한 관리 서비스) 시나리오를 지원하지 않습니다.

- BlackBerry는 IPv6을 지원하지 ® Enterprise Server(BES)를 지원하지 않습니다.

- Office 365에서 AD FS(Active Directory Federation Services)를 사용하는 경우 IPv6을 사용하여 AD FS 네트워크 끝점을 Office 365에 광고하는 것은 지원되지 않습니다. Exchange Online을 사용할 때 AD FS DNS 항목에 AAAA 레코드를 포함하면 안 됩니다. 

다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>참고 항목

[IPv6 학습 로드맵](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 사용 가이드](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
