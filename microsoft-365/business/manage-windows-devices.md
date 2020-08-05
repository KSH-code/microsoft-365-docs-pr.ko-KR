---
title: 비즈니스를 위해 Microsoft 365에서 관리할 도메인에 가입 된 Windows 10 장치를 사용 하도록 설정
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
description: Microsoft 365에서 일부 단계만 수행 하 여 Active Directory에 가입 된 로컬 Windows 10 장치를 보호 하도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560846"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Microsoft 365 Business Premium에서 관리할 도메인에 가입 된 Windows 10 장치를 사용 하도록 설정

조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business Premium을 설정 하 여 Windows 10 장치를 보호 하 고 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다.
이 보호를 설정 하기 위해 **하이브리드 AZURE AD에 가입 된 장치**를 구현할 수 있습니다. 이러한 장치는 온-프레미스 Active Directory 및 Azure Active Directory에 모두 가입 되어 있습니다.

이 비디오에서는 다음 단계에서 자세히 설명 되는 가장 일반적인 시나리오에 대해이 설정을 구성 하는 단계를 보여 줍니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>시작 하기 전에 다음 단계를 완료 해야 합니다.
- Azure AD Connect를 사용 하 여 Azure AD에 사용자를 동기화 합니다.
- Azure AD Connect OU (조직 구성 단위) 동기화를 완료 합니다.
- 동기화 한 모든 도메인 사용자에 게 Microsoft 365 Business Premium에 대 한 라이선스가 있는지 확인 합니다.

단계를 보려면 [도메인 사용자를 Microsoft에 동기화를](manage-domain-users.md) 참조 하십시오.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Intune에서 MDM 기관 확인

[Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) 로 이동 하 여 Microsoft Intune 페이지에서 **장치 등록**을 선택한 다음 **개요** 페이지에서 **MDM 기관이** **Intune**인지 확인 합니다.

- **Mdm 기관이** **없는 경우** **Mdm 기관을** 클릭 하 여 **Intune**으로 설정 합니다.
- **MDM 기관이** **Microsoft office 365**인 경우 **장치**  >  **등록 장치** 를 열고 오른쪽에 있는 **mdm 인증** 추가 대화 상자를 사용 하 여 **Intune mdm** 기관을 추가 합니다 (mdm 기관이 Microsoft Office 365로 설정 된 경우 **MDM Authority** 에만 **mdm 기관 추가** 대화 상자를 사용할 수 있음).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Azure AD가 컴퓨터 가입에 사용 되도록 설정 되어 있는지 확인

- 관리 센터에서를 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 선택 하 고 **Azure active Directory** (azure active directory가 표시 되지 않는 경우에는 모든 경우를 선택 하세요.)를 **관리** 센터 목록에 표시 합니다. 
- **Azure Active directory 관리 센터**에서 **azure active directory** 로 이동 하 여 **장치** 를 선택한 다음 **장치 설정을**선택 합니다.
- **사용자가 AZURE AD에 장치를 연결할 수** 있는지 확인 설정 
    1. 모든 사용자를 설정 하려면 **모두**로 설정 합니다.
    2. 특정 사용자를 사용 하도록 설정 하려면 특정 사용자 그룹을 사용 하도록 **선택** 된로 설정을 지정 합니다.
        - Azure AD에서 동기화 되는 원하는 도메인 사용자를 [보안 그룹](../admin/create-groups/create-groups.md)에 추가 합니다.
        - **그룹 선택을** 선택 하 여 해당 보안 그룹에 대 한 MDM 사용자 범위를 사용 하도록 설정 합니다.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. MDM에 대해 Azure AD가 사용 되도록 설정 되었는지 확인

- 관리 센터로 이동한 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 후 **끝점 Managemen**t 선택 ( **endpoint Manager** 가 표시 되지 않는 경우 **모두 표시** 선택)을 선택 합니다.
- **Microsoft Endpoint Manager 관리 센터**에서 **장치**  >  **windows**  >  **windows 등록**  >  **자동 등록**으로 이동 합니다.
- MDM 사용자 범위가 사용 하도록 설정 되어 있는지 확인 합니다.

    1. 모든 컴퓨터를 등록 하려면 사용자가 Windows에 작업 계정을 추가할 때 Azure AD 및 새 컴퓨터에 연결 된 모든 사용자 컴퓨터를 자동으로 등록 하도록 **all** 로 설정 합니다.
    2. 특정 사용자 그룹의 컴퓨터를 등록 하려면 **Some** 로 설정 합니다.
        -  Azure AD에서 동기화 되는 원하는 도메인 사용자를 [보안 그룹](../admin/create-groups/create-groups.md)에 추가 합니다.
        -  **그룹 선택을** 선택 하 여 해당 보안 그룹에 대 한 MDM 사용자 범위를 사용 하도록 설정 합니다.

## <a name="4-create-the-required-resources"></a>4. 필요한 리소스 만들기 

[Secmgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 모듈에 있는 [SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet을 사용 하 여 [하이브리드 Azure AD join을 구성](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) 하기 위해 필요한 작업을 수행 하는 과정을 간소화 했습니다. 이 cmdlet을 호출 하면 필요한 서비스 연결 지점 및 그룹 정책이 생성 되 고 구성 됩니다.

PowerShell 인스턴스에서 다음을 호출 하 여이 모듈을 설치할 수 있습니다.

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Azure AD Connect를 실행 하는 Windows 서버에이 모듈을 설치 하는 것이 좋습니다.

필요한 서비스 연결 지점 및 그룹 정책을 만들려면 [SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet을 호출 합니다. 이 작업을 수행 하는 경우 Microsoft 365 Business Premium global 관리자 자격 증명이 필요 합니다. 리소스를 만들 준비가 되 면 다음을 호출 합니다.

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

첫 번째 명령은 Microsoft 클라우드와의 연결을 설정 하 고 메시지가 표시 되 면 Microsoft 365 Business Premium 전역 관리자 자격 증명을 지정 합니다.

## <a name="5-link-the-group-policy"></a>5. 그룹 정책 연결

1. GPMC (그룹 정책 관리 콘솔)에서 정책을 연결할 위치를 마우스 오른쪽 단추로 클릭 하 고 상황에 맞는 메뉴에서 *기존 GPO 연결* ...을 선택 합니다.
2. 위의 단계에서 만든 정책을 선택 하 고 **확인**을 클릭 합니다.

## <a name="get-the-latest-administrative-templates"></a>최신 관리 템플릿 가져오기

**기본 AZURE AD 자격 증명을 사용 하 여 자동 MDM 등록**정책이 사용 되지 않는 경우에는 Windows 10, 버전 1803, 버전 1809 또는 버전 1903에 대해 ADMX가 설치 되어 있지 않을 수 있습니다. 이 문제를 해결 하려면 다음 단계를 수행 합니다 (참고: 최신 MDM-admx가 이전 버전과 호환 됨).

1.  다운로드: [Windows 10 용 관리 템플릿 (admx)이 업데이트 (1903)를 2019 수 있습니다](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  주 도메인 컨트롤러 (PDC)에 패키지를 설치 합니다.
3.  폴더에 대 한 버전에 따라 탐색: **C:\Program files (x86) \Microsoft Group Policy\Windows 10 5 월 2019 업데이트 (1903) v3이 될 수 있습니다**.
4.  위의 경로에서 **정책 정의** 폴더의 이름을 **policydefinitions**로 바꿉니다.
5.  **Policydefinitions** 폴더를 **C:\Windows\SYSVOL\domain\Policies**에 복사 합니다. 
    -   전체 도메인에 대해 중앙 정책 저장소를 사용 하려는 경우에는 여기에 PolicyDefinitions의 내용을 추가 합니다.
6.  정책을 사용 하려면 주 도메인 컨트롤러를 다시 시작 합니다. 이 절차는 이후 버전 에서도 작동 합니다.

이제 사용 가능한 **기본 AZURE AD 자격 증명을 사용 하 여 자동 MDM 등록** 정책을 볼 수 있어야 합니다.
