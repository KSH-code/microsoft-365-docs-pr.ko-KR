---
title: Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비
description: certs/wifi/lan
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9f4490711c1ea051afe9d8efb081a2f7a141f8ba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909121"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비  
 
인증서 기반 인증은 Microsoft Managed Desktop을 사용하는 고객에게 일반적인 요구 사항입니다. 인증서를 사용하여 Wi-Fi 또는 LAN에 액세스하거나 VPN 솔루션에 연결하거나 조직의 내부 리소스에 액세스해야 할 수 있습니다.   
 
Microsoft Managed Desktop 장치는 Azure AD(Azure Active Directory)에 가입되고 Microsoft Intune에서 관리하기 때문에 Intune과 통합된 SCEP(Simple Certificate Enrollment Protocol) 또는 PKCS(공개 키 암호화 표준) 인증서 인프라를 사용하여 이러한 인증서를 배포해야 합니다.    
 
## <a name="certificate-requirements"></a>인증서 요구 사항 
 
SCEP 또는 PKCS 인프라를 통해 인증서를 배포하려면 루트 인증서가 필요합니다. 조직의 다른 응용 프로그램 및 서비스를 Microsoft Managed Desktop 장치에 배포하려면 루트 인증서가 필요할 수 있습니다.    
 
MICROSOFT Managed Desktop에 SCEP 또는 PKCS 인증서를 배포하기 전에 조직에 사용자 또는 장치 인증서가 필요한 각 서비스에 대한 요구 사항을 수집해야 합니다. 이 활동을 더 쉽게 만들기 위해 다음 계획 템플릿 중 하나를 사용할 수 있습니다.  
 
- [PKCS 인증서 템플릿](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 인증서 템플릿](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi 연결 요구 사항

엔터프라이즈 네트워크에 대한 필수 Wi-Fi 장치를 자동으로 제공하려면 Wi-Fi 구성 프로필이 필요할 수 있습니다. 이러한 프로필을 장치에 배포하도록 Microsoft Managed Desktop을 구성할 수 있습니다. 네트워크 보안에 장치가 로컬 도메인에 가입해야 하는 경우 Wi-Fi 네트워크 인프라를 평가하여 Microsoft Managed Desktop 장치와 호환되는지 확인해야 할 수도 있습니다(Microsoft Managed Desktop 장치는 Azure AD 가입 전용). 
 
Microsoft Managed Desktop Wi-Fi 구성을 배포하기 전에 각 관리되는 데스크톱 네트워크에 대한 조직의 요구 사항을 Wi-Fi 합니다. 이 활동을 더 쉽게 만들 수 있도록 이 WiFi 프로필 템플릿을 [사용할 수 있습니다.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>유선 연결 요구 사항 및 802.1x 인증 
 
802.1x 인증을 사용하여 장치에서 LAN(Local Area Network)으로의 액세스를 보호하는 경우 필요한 구성 세부 정보를 Microsoft Managed Desktop 장치에 푸시해야 합니다. Windows 10 버전 1809 이상을 실행하는 Microsoft Managed Desktop 장치는 WiredNetwork CSP(구성 서비스 공급자)를 통해 802.1x 구성 배포를 지원합니다. 자세한 내용은 [WiredNetwork CSP 설명서를 참조하십시오.](/windows/client-management/mdm/wirednetwork-csp) 
 
유선 네트워크 구성 프로필을 Microsoft Managed Desktop 장치에 배포하기 전에 유선 회사 네트워크에 대한 조직의 요구 사항을 수집합니다. 이렇게 하려면 다음 단계를 따릅니다. 
 
 
1. 기존 802.1x 프로필이 구성되어 있으며 LAN 네트워크에 연결된 장치에 로그인합니다.  
2. 관리 자격 증명을 사용하여 명령 프롬프트를 열 수 있습니다. 
3. netsh 인터페이스 표시 인터페이스를 실행하여 LAN **인터페이스 이름을 검색합니다.** 
4. **netsh lan export profile folder=를 실행하여 LAN 프로필 XML을 내보낼 수 있습니다.  Interface="interface_name"**. 
5. Microsoft Managed Desktop 장치에서 내보낼 프로필을 테스트해야 하는 경우 **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" 를** 실행합니다. 
 
 
## <a name="deploy-certificate-infrastructure"></a>인증서 인프라 배포  
 
Intune을 사용하는 기존 SCEP 또는 PKCS 인프라가 이미 있으며 이 방식이 요구 사항을 충족하는 경우 Microsoft Managed Desktop에도 사용할 수 있습니다. SCEP 또는 PKCS 인프라가 아직 없는 경우 준비해야 합니다.  
 
자세한 내용은 [Microsoft Intune에서 장치에](/intune/certificates-configure)대한 인증서 프로필 구성을 참조하세요. 
 
 
 
## <a name="deploy-a-lan-profile"></a>LAN 프로필 배포 
 
LAN 프로필을 내보낼 때 다음 단계를 수행하여 Microsoft Managed Desktop에 대한 정책을 준비할 수 있습니다.   
 
1. 다음 설정을 사용하여 LAN 프로필에 대한 사용자 지정 프로필을 Microsoft [Intune에서 만드시다(Intune에서 Windows 10 디바이스에 대한](/intune/custom-settings-windows-10)사용자 지정 설정 사용 참조). 사용자 **지정 OMA-URI 설정에서** **추가를** 선택하고 다음 값을 입력합니다. 
    - 이름: *최신 Workplace-Windows 10 LAN 프로필* 
    - 설명: 설정에 대한 개요와 기타 중요한 세부 정보를 제공하는 설명을 입력합니다. 
    - OMA-URI(대/중문자): *./Device/Vendor/MSFT/WiredNetwork/LanXML 입력*
    - 데이터 형식: **문자열(XML 파일)을 선택합니다.** 
    - 사용자 지정 XML: 내보낼 XML 파일을 업로드합니다.
2. Microsoft Managed Desktop Admin 포털을 사용하여 Microsoft Managed Desktop IT Operations에 지원 요청을 제출하여 구성 프로필을 검토하고 "최신 작업 공간 장치 - 테스트"에 배포합니다. Microsoft Managed Desktop IT Operations를 사용하면 관리 포털의 지원 요청을 통해 요청이 완료되는 경우를 알 수 있습니다.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>인증서 및 Wi-Fi/VPN 프로필 배포 
 
 
인증서 및 프로필을 배포하려면 다음 단계를 수행합니다.

1. 각 루트 및 중간 인증서에 대한 프로필을 만들 수 있습니다(신뢰할 수 있는 인증서 프로필 [만들기 참조).](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles) 이러한 각 프로필에는 만료 날짜가 DD/MM/YYYY 형식으로 포함된 설명이 있어야 합니다. **만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**
2. 각 SCEP 또는 PKCS 인증서에 대한 프로필 [만들기(SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 인증서 프로필 만들기 또는 [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)인증서 프로필 만들기 참조) 이러한 각 프로필에는 만료 날짜가 DD/MM/YYYY 형식으로 포함된 설명이 있어야 합니다. **만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**
3. 각 회사 WiFi 네트워크에 대한 프로필을 [생성합니다(Windows 10](/intune/wi-fi-settings-windows)이상 장치에 대한 Wi-Fi 설정 참조).
4. 각 회사 VPN에 대한 프로필을 생성합니다(Intune을 사용하여 VPN 연결을 추가하려면 [Windows 10 및 Windows Holographic](/intune/vpn-settings-windows-10)장치 설정을 참조).
5. Microsoft Managed Desktop Admin 포털을 사용하여 "인증서 배포" 또는 "Wi-Fi 프로필 배포"라는 지원 요청을 Microsoft Managed Desktop IT Operations에 제출하여 구성 프로필을 검토하고 "최신 작업 공간 장치 - 테스트"에 배포합니다. Microsoft Managed Desktop IT Operations를 사용하면 관리 포털의 지원 요청을 통해 요청이 완료된 경우를 알 수 있습니다. 
 
