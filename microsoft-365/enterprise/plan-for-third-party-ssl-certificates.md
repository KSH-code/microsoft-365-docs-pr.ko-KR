---
title: Microsoft 365용 타사 SSL 인증서 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: '요약: AD FS를 사용하는 Exchange 하이브리드, AD FS를 사용하는 SSO, Exchange Online 서비스 및 Exchange SSL 인증서에 대해 설명합니다.'
ms.openlocfilehash: f2ad14bd35d68067cdc462706bed763e894455f8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187907"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Microsoft 365용 타사 SSL 인증서 계획

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

클라이언트와 서버 환경 간의 통신을 암호화하려면 Microsoft 365 서버에 타사 SSL(Secure Socket Layer) 인증서를 설치해야 합니다.

이 문서는 에 대한 네트워크 계획 및 성능 [조정의 Microsoft 365.](./network-planning-and-performance.md)
   
인증서는 다음 구성 요소에 Microsoft 365 필요합니다.
  
- Exchange 프레미스
    
- SSO(Single Sign-On)(AD FS(Active Directory Federation Services) 페더ation 서버 및 AD FS 페더ation 서버 디렉터리 모두에 대해)
    
- Exchange Online, Outlook, 웹 서비스 등의 Exchange 서비스
    
- Exchange 하이브리드 서버
    
## <a name="certificates-for-exchange-on-premises"></a>Exchange 대한 인증서

디지털 인증서를 사용하여 조직과 보안 유지를 위한 Exchange 통신하는 방법에 대한 개요는 TechNet 문서 Exchange Online 인증서 요구 사항 [이해를 참조하세요.](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141))
  
## <a name="certificates-for-single-sign-on"></a>Single Sign-On용 인증서

사용자에게 강력한 보안이 포함된 간소화된 Single Sign-On 환경을 제공하려면 다음 표에 나와 있는 인증서가 페더러ation 서버 또는 페더러ation 서버 proxies에 필요합니다. 아래 표에서는 AD FS(Active Directory Federation Services)에 대해 중점적으로 설명하고, 타사 ID 공급자 사용에 대한 자세한 [정보도 제공합니다.](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)
  
| 인증서 유형 | 설명 | 배포하기 전에 알아야 할 것 |
|:-----|:-----|:-----|
|**SSL 인증서(서버 인증 인증서라고도 불리며)** <br/> |이 인증서는 페더미스 서버, 클라이언트 및 페더전 서버 프록시 컴퓨터 간의 통신을 안전하게 하는 데 사용되는 표준 SSL 인증서입니다.  <br/> |AD FS에는 SSL 인증서가 필요합니다. 기본적으로 AD FS는 IIS(2013)의 기본 웹 사이트에 대해 구성된 SSL 인터넷 정보 서비스 사용됩니다.  <br/> 이 SSL 인증서의 주체 이름은 배포하는 각 AD FS 인스턴스에 대한 FS(페더전 서비스) 이름을 확인하는 데 사용됩니다. 새 CA(인증 기관)에서 발급한 인증서의 주체 이름을 선택할 수 있습니다. 이 인증서는 새 CA(인증 기관)에서 발급할 회사 또는 조직의 이름을 가장 잘 나타내는 Microsoft 365. 이 이름은 인터넷 라우팅이 가능해야 합니다.  <br/>**주의:** AD FS를 사용하려면 이 SSL 인증서에 점 없는(짧은 이름) 주체 이름이 필요합니다.          <br/> **권장 사항:** 이 인증서는 AD FS 클라이언트에서 신뢰해야 하기 때문에 공용(타사) CA 또는 공개적으로 신뢰할 수 있는 루트에 하위인 CA에서 발급한 SSL 인증서를 사용하는 것이 좋습니다. 예를 들어 VeriSign 또는 Thawte와 같습니다.  <br/> |
|**토큰 서명 인증서** <br/> |이 인증서는 페더링 서버에서 발급하는 모든 토큰에 안전하게 서명하는 데 사용하며, 이 인증서는 Microsoft 365 수락하고 유효성을 검사합니다.  <br/> |토큰 서명 인증서에는 FS의 신뢰할 수 있는 루트에 연결하는 개인 키가 포함되어야 합니다. 기본적으로 AD FS는 자체 서명된 인증서를 만듭니다. 그러나 조직의 요구에 따라 AD FS 관리 스냅인을 사용하여 이 인증서를 CA 발급 인증서로 변경할 수 있습니다.  <br/>**주의:** 토큰 서명 인증서는 FS의 안정성에 중요합니다. 인증서가 변경된 경우 Microsoft 365 알림을 해야 합니다. 알림이 제공되지 않은 경우 사용자는 자신의 Microsoft 365 서비스에 로그인할 수 없습니다.<br/>**권장 사항:** AD FS에서 생성된 자체 서명된 토큰 서명 인증서를 사용하는 것이 좋습니다. 이렇게 하면 기본적으로 이 인증서가 관리됩니다. 예를 들어 이 인증서가 만료될 때 AD FS는 새 자체 서명된 인증서를 생성합니다.  <br/> |
   
페더ation 서버 proxies를 사용하려면 다음 표에 설명된 인증서가 필요합니다.
  
| 인증서 유형 | 설명 | 배포하기 전에 알아야 할 것 |
|:-----|:-----|:-----|
|SSL 인증서  <br/> |이 인증서는 페더링 서버, 페더링 서버 프록시 및 인터넷 클라이언트 컴퓨터 간의 통신을 보안하는 데 사용되는 표준 SSL 인증서입니다.  <br/> |AD FS 페더ation 서버 프록시 구성 마법사를 실행하려면 이 SSL 인증서를 IIS의 기본 웹 사이트에 바인딩해야 합니다.  <br/> 이 인증서는 회사 네트워크의 페더전 서버에 구성된 SSL 인증서와 주체 이름이 같아야 합니다.  <br/> **권장 사항:** 이 페더ation 서버 프록시가 연결되는 페더러ation 서버에 구성된 서버 인증 인증서와 동일한 서버 인증 인증서를 사용하는 것이 좋습니다.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>자동 검색, 모든 Outlook 및 Active Directory 동기화를 위한 인증서

외부 연결 Exchange 2013, Exchange 2010, Exchange 2007 및 Exchange 2003 CAS(클라이언트 액세스 서버)에는 자동 검색, 외부에서 사용Outlook Active Directory 동기화 서비스에 대한 보안 연결을 위한 타사 SSL 인증서가 필요합니다. 이 인증서를 이미 사내 환경에 설치한 것일 수 있습니다.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>하이브리드 서버의 Exchange 인증서

외부 연결 Exchange 하이브리드 서버 또는 서버에는 Exchange Online 서비스에 대한 보안 연결을 위해 타사 SSL 인증서가 필요합니다. 타사 SSL 공급자로부터 이 인증서를 제공해야 합니다.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365 인증서 체인

이 문서에서는 인프라에 설치해야 할 수 있는 인증서에 대해 설명합니다. Microsoft 365 서버에 설치된 인증서에 대한 자세한 내용은 Microsoft 365 [인증서 체인을 참조하세요.](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)
  
## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)