---
title: 비즈니스용 Microsoft 365에서 도메인에 가입된 Windows 10 장치를 관리하도록 설정
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 몇 단계만 수행하면 Microsoft 365에서 로컬 Active-Directory 가입 Windows 10 장치를 보호하는 방법을 알아보십시오.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560846"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Microsoft 365 Business Premium에서 도메인에 가입된 Windows 10 장치를 관리하도록 설정

조직에서 Windows Server Active Directory를 사용하는 경우 Microsoft 365 Business Premium을 설정하여 Windows 10 디바이스를 보호하는 동시에 로컬 인증이 필요한 여전히 프레미스 리소스에 대한 액세스 권한을 유지할 수 있습니다.
이 보호를 설정하기 위해 하이브리드 Azure AD 가입 **장치를 구현할 수 있습니다.** 이러한 디바이스는 모두 On-premises Active Directory와 Azure Active Directory에 가입됩니다.

이 비디오에서는 가장 일반적인 시나리오에 대해 이 설정 방법을 설정하는 단계에 대해 설명합니다. 이 단계는 다음 단계에 자세히 설명되어 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>시작하기 전에 다음 단계를 완료해야 합니다.
- Azure AD Connect를 사용하여 사용자를 Azure AD에 동기화합니다.
- Azure AD Connect OU(조직 구성 단위) 동기화를 완료합니다.
- 동기화하는 모든 도메인 사용자에게 Microsoft 365 Business Premium에 대한 라이선스가 있는지 확인

단계는 [도메인 사용자를 Microsoft에 동기화하는](manage-domain-users.md) 단계를 참조하세요.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Intune에서 MDM 기관 확인

[끝점](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) 관리자로 이동한 후 Microsoft Intune 페이지에서 장치 등록을 선택한 다음 개요 페이지에서 **MDM** 기관이 **Intune에** 있는지 확인합니다.  

- **MDM** 기관이 **없음인** 경우 **MDM** 기관을 클릭하여 **Intune으로 설정합니다.**
- **MDM** 기관이 **Microsoft Office 365인** 경우 장치 등록 장치로 이동한 후 오른쪽의 MDM 기관 추가 대화 상자를 사용하여  >   **Intune MDM** 기관을  추가합니다(MDM 기관 추가 대화 상자는 **MDM** 기관이 Microsoft Office 365로 설정된 경우만 사용할 수  있습니다).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. 컴퓨터 가입에 대해 Azure AD가 사용하도록 설정되어 있는지 확인

- 관리 센터 목록에서 관리 센터로 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Azure Active Directory(Azure Active Directory가** 표시되지 않는 경우 모두 표시 선택)를 선택합니다.  
- Azure **Active Directory 관리 센터에서** Azure Active  **Directory로** 이동하여 디바이스를 선택한 다음 장치 설정을 **선택합니다.**
- 사용자가 **Azure AD에 장치를 가입할** 수 있는지 확인 
    1. 모든 사용자를 사용하도록 설정하려면 All로 **설정해야 합니다.**
    2. 특정 사용자를 사용하도록 설정하려면 특정 사용자 그룹을 사용하도록 **설정하려면 Selected로** 설정해야 합니다.
        - Azure AD에서 동기화된 원하는 도메인 사용자를 보안 그룹에 [추가합니다.](../admin/create-groups/create-groups.md)
        - 그룹 **선택을** 선택하여 해당 보안 그룹에 대해 MDM 사용자 범위를 사용하도록 설정할 수 있습니다.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. MDM에 대해 Azure AD가 사용하도록 설정되어 있는지 확인

- 관리 센터로 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Endpoint Managemen** t  **선택(Endpoint Manager가** 표시되지 않는 경우 모두 표시 선택)
- Microsoft **Endpoint Manager 관리 센터에서** Windows 등록 자동 등록 **장치로**  >    >    >  **이동하세요.**
- MDM 사용자 범위가 사용하도록 설정되어 있는지 확인합니다.

    1. 모든 컴퓨터를 등록하려면 사용자가 Windows에 작업 계정을 추가할 때 Azure AD에 가입된 모든 사용자 컴퓨터와 새 컴퓨터를 자동으로 등록하도록 **All로** 설정하세요.
    2. 특정 사용자 **그룹의** 컴퓨터를 등록하도록 일부로 설정
        -  Azure AD에서 동기화된 원하는 도메인 사용자를 보안 그룹에 [추가합니다.](../admin/create-groups/create-groups.md)
        -  그룹 **선택을** 선택하여 해당 보안 그룹에 대해 MDM 사용자 범위를 사용하도록 설정할 수 있습니다.

## <a name="4-create-the-required-resources"></a>4. 필요한 리소스 만들기 

[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 모듈에 있는 [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet을 사용하여 하이브리드 [Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) 조인을 구성하는 데 필요한 작업을 간소화했습니다. 이 cmdlet을 호출하면 필요한 서비스 연결 지점 및 그룹 정책이 만들어지며 구성됩니다.

PowerShell 인스턴스에서 다음을 호출하여 이 모듈을 설치할 수 있습니다.

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Azure AD Connect를 실행하는 Windows Server에 이 모듈을 설치하는 것이 좋습니다.

필요한 서비스 연결 지점 및 그룹 정책을 만들기 위해  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet을 호출합니다. 이 작업을 수행할 때 Microsoft 365 Business Premium 전역 관리자 자격 증명이 필요합니다. 리소스를 만들 준비가 되면 다음을 호출합니다.

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

첫 번째 명령은 Microsoft 클라우드와 연결을 설정하고 메시지가 표시될 때 Microsoft 365 Business Premium 전역 관리자 자격 증명을 지정합니다.

## <a name="5-link-the-group-policy"></a>5. 그룹 정책 연결

1. GPMC(그룹 정책 관리 콘솔)에서 정책을 연결하려는 위치를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 기존 *GPO 연결...을* 선택합니다.
2. 위의 단계에서 만든 정책을 선택하고 확인을 **클릭합니다.**

## <a name="get-the-latest-administrative-templates"></a>최신 관리 템플릿 다운로드

기본 Azure AD 자격 증명을 사용하여 자동 **MDM** 등록 사용 정책이 표시되지 않는 경우 Windows 10 버전 1803, 버전 1809 또는 버전 1903에 대한 ADMX가 설치되어 있지 않은 것일 수 있습니다. 이 문제를 해결하기 위해 다음 단계를 수행합니다(참고: 최신 MDM.admx는 역과 호환됨).

1.  다운로드: [Windows 10 2019년 5월 업데이트(1903)에 대한 관리 템플릿(.admx)입니다.](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)
2.  PDC(주 도메인 컨트롤러)에 패키지를 설치합니다.
3.  폴더 버전에 따라 **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 2019 May 2019 Update (1903) v3**.
4.  위의 경로에서 **PolicyDefinitions의** 정책 정의 폴더 이름을 **다시 지정합니다.**
5.  **PolicyDefinitions** 폴더를 **C:\Windows\SYSVOL\domain\Policies에 복사합니다.** 
    -   전체 도메인에 대해 중앙 정책 저장소를 사용하려면 PolicyDefinitions의 콘텐츠를 추가합니다.
6.  정책을 사용할 수 있도록 주 도메인 컨트롤러를 다시 시작합니다. 이 절차는 향후 버전에도 사용할 수 있습니다.

이제 사용 가능한 기본 Azure AD 자격 증명을 사용하여 **자동 MDM** 등록 사용 정책을 볼 수 있습니다.
