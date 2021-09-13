---
title: Microsoft 365 서비스의 IPv6 지원
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/28/2021
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
description: '요약: 정부 서비스 및 Microsoft 365 구성 요소의 IPv6 지원에 Microsoft 365 설명'
ms.openlocfilehash: be9ce7cc2eaaec74889e9d88ddfa9b781c6d308e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215965"
---
# <a name="ipv6-support-in-microsoft-365-services"></a>Microsoft 365 서비스의 IPv6 지원

Microsoft 365 IPv6 및 IPv4를 모두 지원하지 않습니다. 그러나 모든 Microsoft 365 IPv6에서 완전히 사용하도록 설정되지는 않습니다. 즉, IPv4와 IPv6을 모두 사용하여 IPv4에 연결해야 Microsoft 365. Microsoft 365 트래픽을 필터링하는 경우 Microsoft 365 지원되는 IPv6 주소의 전체 목록은 Microsoft 365 URL 및 IP 주소 범위 [문서에서](urls-and-ip-address-ranges.md)찾을 수 있습니다. 네트워크를 구성하고 적절한 IPv6 주소를 허용한 후 Microsoft 다운로드 센터에서 Microsoft 365 [IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) 테스트 계획을 다운로드할 수 있습니다.

> [!NOTE]
> 고객이 모든 위치에서 Microsoft 365 SaaS 서비스를 경험할 수 있도록 하는 것이 Microsoft의 우선 순위입니다. 여기에는 고객이 IPv6 사용 및 IPv6 전용 Microsoft 365 및 정보 시스템에서 연결하고 사용할 수 있도록 허용하는 것이 포함됩니다. 또한 정부 고객이 네트워크에서 IPv6 약정을 충족하는 동시에 중단 없이도 Microsoft 365 생산성 시나리오를 계속 사용할 수 있도록 지원합니다.  
> 이 문서에서는 현재 직접 IPv6 연결을 Microsoft 365 SaaS 서비스 목록을 제공합니다. 직접 IPv6 연결을 허용하는 서비스의 범위는 계속 확장될 것으로 예상됩니다. Microsoft 365 AAD(Azure Active Directory) 인증 서비스를 포함하기 위해 직접 IPv6 지원에 대해 명시적으로 언급되지 않은 Microsoft 365 서비스는 DNS64/NAT64가 IPv6 클라이언트 및 환경에서만 연결하도록 요구하는 것으로 생각해야 합니다.  이는 현재 기존 NIST USGv6 설명서에 설명된 의도와 일치합니다. [NIST Special Publication 500-267A Revision 1](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.500-267Ar1.pdf) NAT64/DNS64의 전환 메커니즘 기능 요구 사항은 사용 가능한 기술입니다.
> - 전환 메커니즘 NAT64 [RFC6146](https://datatracker.ietf.org/doc/html/rfc6146) Stateful NAT64: IPv6 클라이언트에서 IPv4 서버로의 네트워크 주소 및 프로토콜 변환에 대한 NAT64 지원
> - 전환 메커니즘 DNS64에 대한 DNS64 지원. [RFC6147](https://datatracker.ietf.org/doc/html/rfc6147) DNS64: IPv6 클라이언트에서 IPv4 서버로의 네트워크 주소 변환을 위한 DNS 확장

  
## <a name="ipv6-support-in-microsoft-365-subscription-service"></a>Microsoft 365 구독 서비스의 IPv6 지원

### <a name="exchange-online-and-ipv6"></a>Exchange Online 및 IPv6

연결에 사용하는 프로그램에서 IPv6을 Exchange Online 경우 유선 네트워크와 무선 네트워크 모두에서 기본적으로 IPv6을 사용합니다. 사용자와의 통신을 제어하려는 Exchange Online URL 및 IP 주소 Microsoft 365 IP 주소 범위를 [사용하세요.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint 온라인 및 IPv6

 **Microsoft 365 Government G1/G3/G4/K1** SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6을 사용하려고 합니다.
  
 **공용 다중 테넌트 클라우드** Microsoft는 요청 시 SharePoint 온라인 IPv6을 사용할 수 있도록 합니다. 조직의 DNS 인프라에 대해 CIDR에서 고지된 IP 주소를 제공해야 합니다. 테넌트에 대해 IPv6을 사용하도록 설정하기 위해 다른 조직에서는 이 DNS 인프라를 공유할 수 없습니다. IPv6을 사용하도록 설정한 후 SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6이 사용됩니다.
  
SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 유선 네트워크와 무선 네트워크 모두에서 기본적으로 IPv6을 사용합니다. SharePoint Online에 대한 통신을 제어하려는 경우 MICROSOFT 365 URL 및 IP 주소 범위의 IP 주소 범위를 [사용하세요.](urls-and-ip-address-ranges.md)
  
 
  
### <a name="skype-for-business-and-ipv6"></a>비즈니스용 Skype 및 IPv6

IPv6은 IPv6에서 지원되지 비즈니스용 Skype 더 이상 사용할 수 없습니다.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 및 IPV6

Microsoft Teams 직접 라우팅은 IPv4만 지원됩니다. 서비스 Microsoft Teams 클라이언트는 IPv4 및 IPv6을 모두 지원합니다. 사용자와의 통신을 제어하려는 Microsoft Teams URL 및 IP 주소 Microsoft 365 IP 주소 범위를 [사용하세요.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection 및 IPv6

Exchange Online Protection(EOP)는 전송 계층 보안 프로토콜을 통해 전송이 발생하는 경우 IPv6을 지원합니다. EOP 범위의 경우 URL Microsoft 365 IP 주소 범위 [를 사용하세요.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-microsoft-365-government-offerings"></a>정부 제품용 IPv6 Microsoft 365 지원

Microsoft 365 정부 제공에 대한 IPv6 지원은 행정부 및 기관의 최고 정보 책임자에 대한 OMB(관리 및 예산) Office 및 IPv6(Federal Government Adoption of Internet Protocol Version 6) memorandum을 준수합니다. [Microsoft Microsoft 365 정부용 Microsoft는](https://go.microsoft.com/fwlink/p/?LinkId=325414) 미국 정부 데이터를 분계된 커뮤니티 클라우드에 저장하는 다중 테넌트 서비스입니다. 다른 Microsoft 365 서비스와 마찬가지로 Exchange Online, 비즈니스용 Skype, SharePoint Online 및 엔터프라이즈용 Microsoft 365 앱. 

Microsoft Microsoft 365 정부 제품은 2013 이상에만 적용됩니다. 정부 제품 Microsoft 365 대한 자세한 내용은 Government용 Microsoft 365 [발표: 미국](https://go.microsoft.com/fwlink/p/?LinkId=325414)정부 커뮤니티 클라우드. ITAR(International Traffic in Arms [Regulations)는 미국 USML(Munitions List)에서](https://go.microsoft.com/fwlink/p/?LinkId=325415)국방 관련 문서 및 서비스의 수출 및 가져오기 기능을 제어하는 미국 정부 규정 집합입니다. 

Microsoft Microsoft 365 엔터프라이즈용 Microsoft는 ITAR이 적용된 FISMA(Federal Information Security Management) 인증 및 상업적 엔터티를 요구하는 미국 연방 기관에 대한 보안, 개인 정보 보호 및 규정 준수 요구 사항을 지원하는 Microsoft 생산성 솔루션에 대한 전용 호스팅 서비스를 제공합니다.
  
## <a name="things-to-consider-when-using-ipv6-and-microsoft-365"></a>IPv6 및 IPv6을 사용할 때 고려해야 할 Microsoft 365

IPv6을 사용하지 않도록 설정하지 않는 것이 좋습니다. 자세한 내용은 이 지침 문서를 [참조하세요.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) 네트워크에서 사용되는 IP 버전을 확인하기 위해 다음을 고려합니다.
  
- 명령 프롬프트에 **IPConfig** 명령이 표시될 때 "IPv6 주소" 또는 "임시 IPv6 주소"라는 행이 포함되어 있는 경우 환경에 IPv6이 있는 것입니다.

- 모든 IPv6 주소가 "fe80"으로 시작하고 "Link-Local IPv6 Address"라는 행에 해당하는 경우 환경에 IPv6이 없는 것입니다.

이러한 고려 사항이 네트워크에 적용될 수 있습니다.
  
- 공용 구독 서비스는 IPv6을 통해 신용 카드로 구매를 지원하지 않습니다. 이는 정부가 EA(정부 커뮤니티 클라우드)GCC(기업계약) 라이선스에 적용되지 않습니다.

- IPv6에서는 일부 RMS(권한 관리 서비스) 시나리오를 지원하지 않습니다.

- BlackBerry는 IPv6을 지원하지 ® Enterprise 서버(BES)를 지원하지 않습니다.

- AD FS(Active Directory Federation Services)를 Microsoft 365 AD FS 네트워크 끝점을 IPv6을 Microsoft 365 광고하는 것은 지원되지 않습니다. AD FS DNS 항목에 AAAA 레코드를 포함하면 안 Exchange Online. 

다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/o365ip6]()

## <a name="see-also"></a>참고 항목

[IPv6 Learning 로드맵](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 사용 가이드](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
