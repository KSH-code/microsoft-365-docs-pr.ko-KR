---
title: Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비
description: 인증서/i a c/lan
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
ms.openlocfilehash: c7c57861986d275165484ae726140720a75da88e
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530034"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비  
 
인증서 기반 인증은 Microsoft Managed Desktop을 사용 하는 고객에 게 일반적인 요구 사항입니다. Wi-fi 또는 LAN에 액세스 하거나, VPN 솔루션에 연결 하거나, 조직의 내부 리소스에 액세스 하려면 인증서가 필요할 수 있습니다.   
 
Microsoft Managed Desktop 장치는 Azure Active Directory (Azure AD)에 연결 되 고 Microsoft Intune에서 관리 되므로 Intune과 통합 된 단순 인증서 등록 프로토콜 (SCEP) 또는 PKCS (공개 키 암호화 표준) 인증서 인프라를 사용 하 여 이러한 인증서를 배포 해야 합니다.    
 
## <a name="certificate-requirements"></a>인증서 요구 사항 
 
루트 인증서는 SCEP 또는 PKCS 인프라를 통해 인증서를 배포 하는 데 필요 합니다. 조직의 다른 응용 프로그램 및 서비스에 대 한 루트 인증서를 Microsoft Managed Desktop 장치에 배포 해야 할 수 있습니다.    
 
Microsoft Managed Desktop에 SCEP 또는 PKCS 인증서를 배포 하기 전에 조직에서 사용자 또는 장치 인증서가 필요한 각 서비스에 대 한 요구 사항을 수집 해야 합니다. 이 작업을 용이 하 게 하기 위해 다음 계획 템플릿 중 하나를 사용할 수 있습니다.  
 
- [PKCS 인증서 템플릿](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 인증서 템플릿](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>현재 EAP 유형을 사용 하는 경우에는 Microsoft Managed Desktop에 대 한 Wi-fi 프로필 배포에 대해서만 SCEP 인증서 프로필을 사용할 수 있습니다. PKCS 인증서 프로필은 지원 되지 않습니다. 참조에 대해서는 [Intune에서 Windows 10 장치에 대 한 wi-fi 설정 추가를](https://docs.microsoft.com/intune/wi-fi-settings-windows) 참조 하세요.

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-fi 연결 요구 사항

엔터프라이즈 네트워크에 필요한 Wi-fi 구성을 사용 하 여 장치를 자동으로 제공 하려면 Wi-fi 구성 프로필이 필요할 수 있습니다. Microsoft Managed Desktop을 구성 하 여 장치에 이러한 프로필을 배포할 수 있습니다. 네트워크 보안이 로컬 도메인에 포함 되어야 하는 경우에는 Wi-fi 네트워크 인프라를 평가 하 여 Microsoft 관리 되는 데스크톱 장치와 호환 되도록 해야 할 수도 있습니다 (Microsoft Managed Desktop devices = Azure AD에만 가입 됨). 
 
Microsoft Managed Desktop 장치에 Wi-fi 구성을 배포 하기 전에 각 Wi-fi 네트워크에 대 한 조직의 요구 사항을 수집 해야 합니다. 이를 보다 쉽게 수행 하려면이 [WiFi 프로필 템플릿을](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)사용 하면 됩니다.
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>유선 연결 요구 사항 및 802.1 x 인증 
 
802.1 x 인증을 사용 하 여 장치에서 LAN (local area network)으로의 액세스를 보호 하는 경우 필요한 구성 정보를 Microsoft Managed Desktop devices로 푸시 해야 합니다. Windows 10을 실행 하는 Microsoft Managed Desktop devices, 버전 1809 이상에서는 CSP (구성 서비스 공급자)를 통한 802.1 x 구성 배포를 지원 합니다. 자세한 내용은 [WIREDNETWORK CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) 설명서를 참조 하십시오. 
 
유선 네트워크 구성 프로필을 Microsoft Managed Desktop 장치에 배포 하기 전에 유선 회사 네트워크에 대 한 조직의 요구 사항을 수집 해야 합니다. 이렇게 하려면 다음 단계를 따릅니다. 
 
 
1. 기존 802.1 x 프로필이 구성 되어 있고 LAN 네트워크에 연결 되어 있는 장치에 로그온 합니다.  
2. 관리 자격 증명을 사용 하 여 명령 프롬프트를 엽니다. 
3. **Netsh interface show interface**를 실행 하 여 LAN 인터페이스 이름을 찾습니다. 
4. **Netsh lan export profile folder =를 실행 하 여 LAN 프로필 XML을 내보냅니다.  Interface = "interface_name"** 
5. 내보낸 프로필을 Microsoft Managed Desktop 장치에서 테스트 해야 하는 경우에는 **netsh lan add profile filename = "PATH_AND_FILENAME.xml" interface = "INTERFACE_NAME"** 를 실행 합니다. 
 
 
## <a name="deploy-certificate-infrastructure"></a>인증서 인프라 배포  
 
Intune을 사용 하는 기존 SCEP 또는 PKCS 인프라가 있고,이로 인 한 요구 사항을 충족 하는 경우에는 Microsoft Managed Desktop에도이 인프라를 사용할 수 있습니다. SCEP 또는 PKCS 인프라가 이미 없는 경우에는 하나를 준비 해야 합니다.  
 
자세한 내용은 [Microsoft Intune에서 장치에 대 한 인증서 프로필 구성을](https://docs.microsoft.com/intune/certificates-configure)참조 하세요. 
 
 
 
## <a name="deploy-a-lan-profile"></a>LAN 프로필 배포 
 
LAN 프로필을 내보낸 후에는 다음 단계를 수행 하 여 Microsoft Managed Desktop에 대 한 정책을 준비할 수 있습니다.   
 
1. 다음 설정을 사용 하 여 Microsoft Intune for LAN 프로필에 사용자 지정 프로필을 만듭니다 ( [Intune에서 Windows 10 장치에 대 한 사용자 지정 설정 사용](https://docs.microsoft.com/intune/custom-settings-windows-10)참조). **사용자 지정 OMA-URI 설정**에서 **추가**를 선택 하 고 다음 값을 입력 합니다. 
    - 이름: *현대 직장-Windows 10 LAN 프로필* 
    - 설명: 설정에 대 한 개요 및 기타 중요 한 세부 정보를 제공 하는 설명을 입력 합니다. 
    - OMA-URI (대/소문자 구분):/Device/Vendor/MSFT/WiredNetwork/LanXML를 입력 *합니다.*
    - 데이터 형식: **문자열 (XML 파일)** 을 선택 합니다. 
    - 사용자 지정 XML: 내보낸 XML 파일을 업로드 합니다.
2. Microsoft managed desktop Administration portal을 사용 하 여 Microsoft Managed Desktop IT 작업에 대 한 지원 요청을 제출 하 여 구성 프로필을 검토 하 고 "현대적인 작업 공간 장치-테스트"로 배포 합니다. Microsoft Managed Desktop IT 작업을 통해 요청이 관리자 포털의 지원 요청을 통해 완료 되는 시기를 알 수 있습니다.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>인증서 및 Wi-fi/VPN 프로필 배포 
 
 
인증서 및 프로필을 배포 하려면 다음 단계를 수행 합니다.

1. 각 루트 및 중간 인증서에 대 한 프로필을 만듭니다 ( [신뢰할 수 있는 인증서 프로필 만들기](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)참조). 이러한 각 프로필에는 DD/MM/YYYY 형식의 만료 날짜가 포함 된 설명이 있어야 합니다. **만료 날짜가 없는 인증서 프로필은 배포 되지 않습니다.**
2. 각 SCEP 또는 PKCS 인증서에 대 한 프로필 만들기 ( [scep 인증서 프로필](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 만들기 또는 [Pkcs 인증서 프로필 만들기](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)참조) 각 프로필에는 만료 날짜를 DD/MM/YYYY 형식으로 포함 하는 설명이 있어야 합니다. **만료 날짜가 없는 인증서 프로필은 배포 되지 않습니다.**
3. 각 회사 WiFi 네트워크에 대 한 프로필을 만듭니다 ( [Windows 10 이상 장치에 대 한 wi-fi 설정](https://docs.microsoft.com/intune/wi-fi-settings-windows)참조).
4. 각 회사 VPN에 대 한 프로필을 만듭니다 ( [Intune을 사용 하 여 VPN 연결을 추가 하려면 windows 10 및 Windows Holographic 장치 설정](https://docs.microsoft.com/intune/vpn-settings-windows-10)참조).
5. Microsoft Managed Desktop Administration portal을 사용 하 여 Microsoft Managed Desktop IT 작업에 "인증서 배포" 또는 "Wi-fi 프로필 배포" 라는 지원 요청을 제출 하 여 구성 프로필을 검토 하 고 "최신 직장 회사 장치-테스트"로 배포 합니다. Microsoft Managed Desktop IT 작업을 통해 관리자 포털의 지원 요청을 통해 요청이 완료 된 시기를 알 수 있습니다. 
 
 
