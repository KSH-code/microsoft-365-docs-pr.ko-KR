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
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564952"
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

Portal.azure.com로 이동 하 여 Intune 페이지 검색을 시작 합니다.
Microsoft Intune 페이지에서 **장치 등록** 을 선택 하 고 **개요** 페이지에서 **MDM 기관이** **Intune**인지 확인 합니다.

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

## <a name="4-set-up-service-connection-point-scp"></a>4. SCP (서비스 연결 지점) 설정

이러한 단계는 [하이브리드 AZURE AD 조인 구성](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)에서 간소화 되었습니다. Azure AD Connect와 Microsoft 365 Business Premium 전역 관리자 및 Active Directory 관리자 암호를 사용 하는 데 필요한 단계를 완료 합니다.

1.  Azure AD Connect를 시작한 다음 **구성을**선택 합니다.
2.  **추가 작업** 페이지에서 **장치 옵션 구성을**선택 하 고 **다음**을 선택 합니다.
3.  **개요** 페이지에서 **다음**을 선택 합니다.
4.  **AZURE AD에 연결** 페이지에서 Microsoft 365 Business Premium에 대 한 전역 관리자의 자격 증명을 입력 합니다.
5.  **장치 옵션** 페이지에서 **하이브리드 Azure AD 조인 구성을**선택 하 고 **다음**을 선택 합니다.
6.  **Scp** 페이지에서 Azure AD CONNECT가 scp를 구성 하도록 하려는 각 포리스트에 대해 다음 단계를 완료 하 **고 다음을 선택 합니다**.
    - 포리스트 이름 옆의 확인란을 선택 합니다. 포리스트는 AD 도메인 이름 이어야 합니다.
    - **인증 서비스** 열에서 드롭다운을 열고 일치 하는 도메인 이름을 선택 합니다 (하나만 옵션 하나만 있어야 함).
    - **추가** 를 선택 하 여 도메인 관리자 자격 증명을 입력 합니다.  
7.  **장치 운영** 체제 페이지에서 Windows 10 이상 도메인 가입 장치만을 선택 합니다.
8.  **구성 준비 완료** 페이지에서 **구성을**선택 합니다.
9.  **구성 완료** 페이지에서 **끝내기**를 선택 합니다.


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a>5. Intune 등록을 위한 GPO 만들기 – ADMX 메서드

하십시오. ADMX 서식 파일

1.  AD server에 로그온 하 고 **서버 관리자**  >  **도구**  >  **그룹 정책 관리**를 검색 하 고 엽니다.
2.  **Domains** (도메인)에서 도메인 이름을 선택 하 고 **그룹 정책 개체** 를 마우스 오른쪽 단추로 클릭 하 여 **새로 만들기**를 선택 합니다.
3.  새 GPO 이름 (예: "*Cloud_Enrollment*")을 지정 하 고 **확인**을 선택 합니다.
4.  **그룹 정책 개체** 아래의 새 GPO를 마우스 오른쪽 단추로 클릭 하 고 **편집**을 선택 합니다.
5.  **그룹 정책 관리 편집기**에서 **컴퓨터 구성**  >  **정책**  >  **관리 템플릿**  >  **Windows 구성 요소**  >  **MDM**으로 이동 합니다.
6. **기본 Azure AD 자격 증명을 사용 하 여 자동 MDM 등록 사용** 을 마우스 오른쪽 단추로 클릭 한 다음 확인 **사용**을 선택  >  **OK**합니다. 편집기 창을 닫습니다.

> [!IMPORTANT]
> **기본 AZURE AD 자격 증명을 사용 하 여 자동 MDM 등록**정책이 표시 되지 않는 경우 [에는 최신 관리 템플릿 가져오기를](#get-the-latest-administrative-templates)참조 하세요.

## <a name="6-deploy-the-group-policy"></a>6. 그룹 정책 배포

1.  서버 관리자의 **도메인** > 그룹 정책 개체 아래에서 위의 3 단계에서 GPO를 선택 합니다 (예: "Cloud_Enrollment").
2.  GPO의 **범위** 탭을 선택 합니다.
3.  GPO의 범위 탭에서 **링크**아래의 도메인에 대 한 링크를 마우스 오른쪽 단추로 클릭 합니다.
4.  GPO를 배포 하려면 **적용** 을 선택 하 고 확인 화면에서 **확인** 을 클릭 합니다.

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

