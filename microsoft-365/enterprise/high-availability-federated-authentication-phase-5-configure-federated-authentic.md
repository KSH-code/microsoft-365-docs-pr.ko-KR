---
title: 고가용성 페더타 인증 5단계 고가용성 인증에 대한 페더타 인증 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: '요약: 2016년 커넥트 대한 고가용성 페더전 인증에 대해 Azure AD Microsoft 365 구성하는 Microsoft Azure.'
ms.openlocfilehash: e5a11c1b94f9a0297ccfa0a18e1963fae9898f65
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152709"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a>고가용성 페더러타 인증 5단계: 페더러에 대한 페더 Microsoft 365

Azure 인프라 서비스에서 Microsoft 365 대한 고가용성 페더링 인증을 배포하는 이 최종 단계에서는 공용 인증 기관에서 발급한 인증서를 다운로드하여 설치하고 구성을 확인한 다음 디렉터리 동기화 서버에 Azure AD 커넥트 설치 및 실행합니다. Azure AD 커넥트 페더화 인증을 위해 Microsoft 365 및 AD FS(Active Directory Federation Services) 및 웹 응용 프로그램 프록시 서버를 구성합니다.
  
모든 [단계는 Azure에서](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) 고가용성 Microsoft 365 인증 배포를 참조하세요.
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a>공용 인증서를 다운로드하여 디렉터리 동기화 서버에 복사

다음 속성을 사용하여 공용 인증 기관에서 디지털 인증서를 얻습니다.
  
- SSL 연결을 만드는 데 적합한 X.509 인증서입니다.
    
- SAN(주체 대체 이름) 확장 속성은 페더임 서비스 FQDN(예: fs.contoso.com)으로 설정됩니다.
    
- 인증서에는 개인 키가 있어야하며 PFX 형식으로 저장해야 합니다.
    
또한 조직 컴퓨터와 장치는 디지털 인증서를 발급하는 공용 인증 기관을 신뢰해야 합니다. 이 트러스트는 컴퓨터 및 장치의 신뢰할 수 있는 루트 인증 기관 저장소에 공용 인증 기관의 루트 인증서를 설치하여 설정됩니다. Microsoft Windows 실행하는 컴퓨터에는 일반적으로 일반적으로 사용되는 인증 기관에서 설치되는 이러한 유형의 인증서 집합이 있습니다. 공용 인증 기관의 루트 인증서가 아직 설치되어 있지 않은 경우 이 인증서를 조직의 컴퓨터 및 장치에 배포해야 합니다.
  
페더라이트 인증의 인증서 요구 사항에 대한 자세한 내용은 페더전 설치 및 구성에 대한 사전 요구 [사항을 참조하세요.](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)
  
인증서를 받으면 디렉터리 동기화 서버의 C: 드라이브에 있는 폴더에 복사합니다. 예를 들어 파일 이름을 SSL.pfx로 지정하고 디렉터리 동기화 서버의 C: Certs 폴더에 \\ 저장합니다.
  
## <a name="verify-your-configuration"></a>구성 확인

이제 Azure AD 2013에 대해 Azure AD 커넥트 페더러시트 인증을 구성할 준비가 Microsoft 365. 확인을 위해 검사 목록은 다음과 같습니다.
  
- 조직의 공용 도메인이 조직 구독에 Microsoft 365 추가됩니다.
    
- 조직의 Microsoft 365 계정이 조직의 공용 도메인 이름으로 구성되어 성공적으로 로그인할 수 있습니다.
    
- 공용 도메인 이름을 기반으로 페더임 서비스 FQDN을 결정했습니다.
    
- 페더ation Service FQDN에 대한 공용 DNS A 레코드는 웹 응용 프로그램 프록시 서버에 대한 인터넷 연결 Azure 부하 균형 조정 서비스의 공용 IP 주소를 지점으로 합니다.
    
- 페더ation Service FQDN에 대한 개인 DNS A 레코드는 AD FS 서버에 대한 내부 Azure 부하 관리 서비스의 개인 IP 주소를 지점으로 합니다.
    
- 페더ation service FQDN으로 설정된 SAN과의 SSL 연결에 적합한 공용 인증 기관 발급 디지털 인증서는 디렉터리 동기화 서버에 저장된 PFX 파일입니다.
    
- 공용 인증 기관의 루트 인증서는 컴퓨터 및 장치의 신뢰할 수 있는 루트 인증 기관 저장소에 설치됩니다.
    
Contoso 조직의 예는 다음과 같습니다.
  
**Azure의 고가용성 페더타 인증 인프라에 대한 구성 예**

![Azure의 페더 Microsoft 365 인프라에 대한 고가용성 구성의 예입니다.](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a>Azure AD 커넥트 실행하여 페더타 인증 구성

Azure AD 커넥트 도구는 다음 단계를 사용하여 AD FS 서버, 웹 응용 프로그램 프록시 서버 및 Microsoft 365 인증을 구성합니다.
  
1. 로컬 관리자 권한이 있는 도메인 계정을 사용하여 디렉터리 동기화 서버에 대한 원격 데스크톱 연결을 만들 수 있습니다.
    
2. 디렉터리 동기화 서버의 바탕 화면에서 를 열고 Internet Explorer 로 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 이동하십시오.
    
3. Microsoft Azure Active Directory 커넥트 **페이지에서** **다운로드를** 클릭한 다음 실행을 **클릭합니다.**
    
4. Azure AD 커넥트 페이지에서 **동의를** **클릭하고** 계속을 **클릭합니다.**
    
5. **기본 설정** 페이지에서 **사용자 지정** 을 클릭합니다.
    
6. **필수 구성 요소 설치** 페이지에서 **설치** 를 클릭합니다.
    
7. **사용자 로그인** 페이지에서 **AD FS로 페더레이션** 을 클릭하고 **다음** 을 클릭합니다.
    
8. Azure **AD 커넥트** 페이지의 **Azure AD DC** 관리자 또는 Microsoft 365 전역 관리자  계정의 이름과 암호를 입력하고 다음 을 **클릭합니다.**
    
9. 디렉터리  커넥트 페이지에서 포리스트에서 AD DS(Active Directory 도메인 서비스) 포리스트가 선택되어 있는지 **확인한** 다음 도메인 관리자 계정의 이름과 암호를 입력하고 디렉터리 추가를 클릭한 후 다음 을 **클릭합니다.**
    
10. Azure **AD 로그인 구성 페이지에서** 다음 을 **클릭합니다.**
    
11. 도메인 **및 OU 필터링 페이지에서** 다음 을 **클릭합니다.**
    
12. 고유하게 사용자 **식별 페이지에서** 다음 을 **클릭합니다.**
    
13. 사용자 **및 장치 필터링 페이지에서** 다음 을 **클릭합니다.**
    
14. 선택적 **기능 페이지에서** 다음 을 **클릭합니다.**
    
15. AD **FS 팜** 페이지에서 새 **AD FS 팜 구성을 클릭합니다.**
    
16. **찾아보기를** 클릭하고 공용 인증 기관에서 SSL 인증서의 위치와 이름을 지정합니다.
    
17. 메시지가 표시될 때 인증서 암호를 입력한 다음 확인 을 **클릭합니다.**
    
18. 주체  이름 및 페더ation **서비스** 이름이 페더임 서비스 FQDN으로 설정되어 있는지 확인하고 다음 을 **클릭합니다.**
    
19. AD **FS 서버** 페이지에서 첫 번째 AD FS 서버 이름(테이블 M - 항목 4 - 가상 컴퓨터 이름 열)을 입력한 다음 추가를 **클릭합니다.**
    
20. 두 번째 AD FS 서버 이름(테이블 M - 항목 5 - 가상 컴퓨터 이름 열)을 입력하고 **추가를** 클릭한 후 다음을 **클릭합니다.**
    
21. 웹 **응용 프로그램 프록시** 서버 페이지에서 첫 번째 웹 응용 프로그램 프록시 서버의 이름(테이블 M - 항목 6 - 가상 컴퓨터 이름 열)을 입력한 다음 추가를 **클릭합니다.**
    
22. 두 번째 웹 응용 프로그램 프록시 서버의 이름(테이블 M - 항목 7 - 가상 컴퓨터 이름 열)을 입력하고 **추가를** 클릭한 후 다음을 **클릭합니다.**
    
23. 도메인 **관리자 자격 증명 페이지에서** 도메인 관리자 계정의 사용자 이름과 암호를 입력하고 다음 을 **클릭합니다.**
    
24. AD **FS 서비스 계정** 페이지에서 엔터프라이즈 관리자 계정의 사용자 이름과 암호를 입력하고 다음 을 **클릭합니다.**
    
25. Azure **AD 도메인 페이지의** **도메인에서** 조직의 DNS 도메인 이름을 선택하고 다음 을 **클릭합니다.**
    
26. **구성 준비 완료** 페이지에서 **설치** 를 클릭합니다.
    
27. **설치 완료** 페이지에서 **확인** 을 클릭합니다. 인트라넷 및 인터넷 구성이 모두 성공적으로 확인되었음을 나타내는 메시지가 두 개 표시됩니다.
    
  - 인트라넷 메시지에는 AD FS 서버에 대한 Azure 내부 부하 균형 조정의 개인 IP 주소가 나열됩니다.
    
  - 인터넷 메시지에는 웹 응용 프로그램 프록시 서버에 대한 Azure 인터넷 연결 부하 균형 조정 프로그램의 공용 IP 주소가 나열됩니다.
    
28. **설치 완료** 페이지에서 **끝내기** 를 클릭합니다.
    
다음은 서버의 자리 holder 이름을 사용 하는 최종 구성입니다.
  
**5단계: Azure의 고가용성 페더전 인증 인프라의 최종 구성**

![Azure의 페더 Microsoft 365 인프라에 대한 고가용성의 최종 구성입니다.](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Azure에서 사용할 수 있는 고가용성 페더 Microsoft 365 인프라가 완료되었습니다.
  
## <a name="see-also"></a>참고 항목

[Azure에서 Microsoft 365용 고가용성 페더레이션 인증 배포](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Microsoft 365/테스트 환경에 대한 페더티드 ID](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 솔루션 및 아키텍처 센터](../solutions/index.yml)

[Microsoft 365](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)
